# Antenna-Amplifiers
A choice of simple antenna amplifier circuits for use with Henner Zeller's "txtempus" DCF77, WWVB, JJY and MSF clock LF-band signal transmitter.

Henner Zeller's tool to set radio controlled timepieces using NTP and a Raspberry Pi can be found here:
https://github.com/hzeller/txtempus

The amplifier circuit itself is from the work of Andreas Spiess, in particular his YouTube video here:
https://youtu.be/6SHGAEhnsYk

All boards include a way of selecting the VCC to the amplifier (3.3v / 5v), however please be sure to watch the video first as increasing the voltage to the amplifier can cause interference to other nearby receivers. With the exception of the "sub compact" surface mount board each amplifier also includes an optional shutdown button to safely power down the Pi.

**Example PCBs:**

![PCB examples](https://github.com/GOTO-GOSUB/Antenna-Amplifiers/blob/a565473eafd16990c48fda6feb0ad8221f1f548c/Amplifier%20Images/Amplifier%20and%20Compact.jpg)

![PCB examples](https://github.com/GOTO-GOSUB/Antenna-Amplifiers/blob/bc6ef2cd6c2dc795e1626ea5f89cc4b4c28771ef/Amplifier%20Images/Pi%20Zero%20HAT,%20compact,%20sub%20compact%20SMT.jpg)

**The "Compact" version directly mounted to a Pi Zero (with added headers) with a tuned 60Khz ferrite**

![Compact amplifier PCB in use](https://github.com/GOTO-GOSUB/Antenna-Amplifiers/blob/2c20f4bca110fa08fe32f662a68d8b8b71eef103/Amplifier%20Images/Compact%20Amplifier%20Direct%20Pi%20Mount.jpg)

# FAQ
**So what are these for ?**

These are simple circuits to boost the output of the transmitter part of Henner Zeller's solution to radio controlled timepieces not receiving their time signal. Txtempus gets the time from NTP and using a Raspberry Pi modulates that in a format that your radio controlled watch / clock can use to set itself accurately. The range of the original circuit described by Henner has a range of approx a few centimetres. Adding a tuned ferrite and / or an amplifier circuit extends the range. For example, this could be the difference between being able to set a watch a couple of inches away from the Pi and setting a wall clock a couple of feet away. The circuit was designed by Andreas Spiess.

![Setting a watch](https://github.com/GOTO-GOSUB/Antenna-Amplifiers/blob/a877eaa5c8f308b4535af3daff0da98b6ea18988/Amplifier%20Images/Setting%20a%20watch%20at%20close%20proximity.jpg)

**Great, but what's with the voltage selector ? Why not just hard-wire it to 5v (or more) ?**

Because it is easy to overload the gain control on a receiver so you may find that using these circuits actually make the performance of nearby timepieces worse. For example, I can set a problematic wall clock from 3ft using this and a ferrite for an antenna but my radio controlled desk clock 6ft away cannot sync when this is running. Oh yes, there is also the possibility that blasting out RF might be illegal in some parts of the world so make sure you know what you are doing. But let's be honest here - the signal is still very weak, even with the amplifier. Plus if you go bonkers with the gain you will quickly discover that ferrites make awful transmitting antennas as they saturate at low levels and become ineffective very quickly.

Just 7 turns of 22AWG tinned copper wire works wonders:

![Setting a watch with 7 turns of 22AWG TCW for a simple antenna](https://github.com/GOTO-GOSUB/Antenna-Amplifiers/blob/f041ddb4def2a57d2a17181c06081b72f2764d4b/Amplifier%20Images/Setting%20watch%20with%207%20turns%20of%2022AWG%20TCW.jpg)

**So how can I get these boards ? Do you sell them ?**

I have included Fritzing source files and Gerbers so you should be able to get these boards made locally. I am in the UK and have used OSH Park (United States) and Aisler (Germany) before with great success at a good price if you're not in a rush. Both of those companies ship internationally. I don't sell the boards (either bare or assembled) but if you email me I might have a spare that you can have. I can probably send a couple of boards to the EU without breaking the bank. Please be sure to let me know what your prefered board type is and an alternative in case your first choice is not available and I'll see what I can do. If I send you a board please consider making a donation to MIND or Macmillan Cancer Care (see below) in lieu of any payment.

**What parts do I need ? Where can I get them ?**

Please see the parts list attached for your choice of board. I have included links to suppliers of suitable parts so you can either buy them from there or confirm the specification if you would rather buy elsewhere. Please note that some parts are optional such as the shutdown button and you may wish to use wire links instead of switches to keep the overall height down if putting it into a case. If you are considering buying a pre-made tuned ferrite, please be sure to buy one that is correct for your region and to replace the capacitor with a wire link instead as this is not required. The capacitor is also not required (replace it with a wire link) if you are just going to use a coil of wire for your antenna. This is all in the parts lists, so don't worry.

**What is the watch shown in the photographs ?**

That is a Casio MTG-9000U G-Shock Solar Waveceptor. I bought it new what must be close to 20 years ago now and it's still going strong, although the rechargeable battery was showing signs of wear about a decade ago so I replaced that. Casio still make radio controlled watches that start at approx £35 for the WV-58U-1AVES.

**Why use Fritzing ? Your PCB sucks !**

I haven't done any circuit designs in about 40 years prior to this. In fact the last board I made was drawn out with a marker pen, exposed to UV then etched in acid and hand drilled as part of a school project. I found Fritzing easy to get in to and it's free. My designs are also available for free and are worth every penny. They will probably improve in time. Or they may not. Where-ever possible I like to use off the shelf parts and when I use surface mount components I don't use the ridiculously small ones because I can't see them without magnification any more, I am that old. I also assume that most people who look at my work here are going to be hobbyists and don't have access to professional equipment. It is my intention that these designs "just work" and do not exclude anyone from having a go.

**How do I use the shutdown button ?**

Just add the line

> dtoverlay=gpio-shutdown

to 

> /boot/config.txt

Then when you press the button the Pi will perform a safe shutdown then sleep. You can press the button again to restart the Pi or safely remove the power.

**This has been really helpful ! Please take my money !**

That is very kind of you, but please pay it forward. If anything here has made your day a little bit better please consider making a small donation to MIND or Macmillan Cancer Support.

https://www.mind.org.uk/donate/

https://www.macmillan.org.uk/donate

