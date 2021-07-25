# Antenna-Amplifiers
A choice of simple antenna amplifier circuits for use with Henner Zeller's "txtempus" DCF77, WWVB, JJY and MSF clock LF-band signal transmitter.

Henner Zeller's tool to set radio controlled timepieces using NTP and a Raspberry Pi can be found here:
https://github.com/hzeller/txtempus

The amplifier circuit itself is from the work of Andreas Spiess, in particular his YouTube video here:
https://youtu.be/6SHGAEhnsYk

All circuits include a way of selecting the VCC to the amplifier (3.3v / 5v), however please be sure to watch the video first as increasing the voltage to the amplifier can cause interference to other nearby receivers. With the exception of the "ultra compact" surface mount board each amplifier also includes an optional shutdown button to safely power down the Pi.

# FAQ
So what are these for ?

These are simple circuits to boost the output of the transmitter part of Henner Zeller's solution to radio controlled timepieces not recieving their time signal. Txtempus gets the time from NTP and using a Raspberry Pi modulates that in a format that your radio controlled watch / clock can use to set itself accurately. The range of the original circuit described by Henner has a range of approx a few centimetres. Adding an amplifier circuit extends the range a little. For example, this could be the difference between being able to set a watch a couple of inches away from the Pi and setting a wall clock a couple of feet away. The circuit was designed by Andreas Spiess.

Great, so why not just hard-wire it to 5v (or more) ?

Because it is easy to overload the gain control on a receiver so you may find that using these circuits actually make the performance of nearby timepieces worse. For example, I can set a problematic wall clock from 3ft using this and a ferrite for an antenna, but a radio controlled desk clock 6ft away cannot sync when this is running. Oh yes, blasting out RF is probably illegal so just set it to the 3.3v drive level and forget I mentioned the 5v option. Seriously, you do it at your own risk. Plus if you follow my example you will quickly discover that ferrites make awful transmitting antennas as they saturate at low levels and become ineffective very quickly.

So how can I get these boards ? Do you sell them ?

I have included Fritzing source files and Gerbers so you should be able to get these boards made locally. I have used OSH Park (United States) and Aisler (Germany) before with great success at a good price if you're not in a rush. Both of those companies ship internationally. I don't sell the boards (either bare or assembled) but if you email me I might have a spare looking for a home. If you live in the UK and ask me for a board I will ask you to consider making a small donation to MIND or MacMillan Cancer Care. I can probably send a couple of boards to the EU without breaking the bank. Let me know what your prefered board type is and an alternative or two and I'll see what I can do.

What parts do I need ? Where can I get them ?

I will generate a parts list shortly, but for now I have put the component values on the PCB instead of component numbers so it should not be difficult to work out. Please bear with me - I hate half complete descriptions of how to do things on Github and I am guilty of it here. But I absoloutely will do a parts list as soon as I have the time. Small quantities of all of the parts I have used here are easily available from electrical suppliers or even ebay.

Why use Fritzing ? Your PCB sucks !

I haven't done any circuit designs in about 40 years prior to this, in fact the last board I made was drawn out with a marker pen, etched in acid, and hand drilled as part of a school project. My designs are available for free and are worth every penny. They will probably improve in time. Or they may not.

