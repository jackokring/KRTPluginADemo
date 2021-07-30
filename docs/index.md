Welcome to [KRTPluginA](https://library.vcvrack.com/KRTPluginA)
===

Built with the most excellent GitHub pages facility. **Under Construction: Always But Slowly**. Recommended.

And it came to pass that VCV Rack didn't need a full build, which didn't work for me, and now I can make some modules. This plugin brings together some ideas I've had for a while into functioning modules.

The First 26 HP **v1.6.9**
---

### A
is a filter, as I've had the DSP code together for a while. It didn't go VST or even Android app. What's special? 18 dB (3 pole), with the fourth pole set to match the first but of opposing pass. The 45 degree phase shifts make for a nice ring modulation multiply for some extra tonal brightness you may or may not like depending on the patch.

Try [DA](https://github.com/jackokring/KRTPluginADemo/blob/master/DA.vcv) for an exaple patch. Or just download this [archive](https://github.com/jackokring/KRTPluginADemo/archive/refs/heads/master.zip) if all the copy and file extension change business seems more than a strain than a few megabytes of download excess.

### μ
started out as some idea about using calculus to make an interesting module. I pulled forth some interesting FIR filter coefficient lists, added some advanced integration by parts (it's a thing to make the sums maybe possible) and added in some of my own findings around the independence of f(x) when observed in a way such that x doesn't have to be known. In fact depending on how sigularities (think black holes and errors in general relativity) are placed in the unknown relative coordinates can lead to different results.

I then went and ruined it by truncating (precise bit crush is a good analogue) the calculations and then even harmonically cube rooted the extreams of the signal, bringing up the compression as it were for sonic utility. Perhaps an ego module, but it is the gold one.

Demo [crisp](https://github.com/jackokring/KRTPluginADemo/blob/master/crisp.vcv).

### T
was a perfection of an idea about slowing down the sound and then speeding it up (like a chorus) but in time to a trigger sync/gate. The switching point decided by possible maths given an octave ratio. Twist for tuning, and add in the origional sound source for some arp chordy goodness. I like it. If you have no trigger it appears like a pass through, so yes it does need a trigger to be useful. For extra utility it does provide a computed output trigger when it goes from low to high pitch. You can't go high first as you can't playback samples faster than you store them.

A demo of possibly simple but demonstrative purposes is [I shat the she riff](https://github.com/jackokring/KRTPluginADemo/blob/master/I%20shat%20the%20she%20riff..vcv), and it was a good name.

### L
was an idea about audio inputs and latency. If you are delayed a bar, then the future match timing requires slightly less than a bar to be on time. A [boring](https://github.com/jackokring/KRTPluginADemo/blob/master/boring.vcv) patch just tests the delay, but usage is so latent specific I'll leave use upto you.

### ;D
got jokingly assigned a letter by TL;DR, but it is an exponetial VCA. It also features all pass future prediction technology. A bit of a joke, but the phase could be considered to be phase lead by lagging the right amount given the lead and sampling rate. It might need post filtering due to differential crackle, but it does also have an error output based on the unexpectedness of the input and hence is good for tracing potential sources of alias distrotion. Demo [DA](https://github.com/jackokring/KRTPluginADemo/blob/master/DA.vcv).

### R
such a simple module. take any cable and split it to the input and the output goes to where the cable ended. Precise CV conservation pass through. Then you can gain another signal on, and take that sum which is the output with the other signal on, and take it as another gain controlled CV to somewhere else. A generic mixer/splitter and no demo is needed.

Installment of the Next 18 HP Allocation **vTBC**
---

### Ω
for a randomization of a clock signal to many gateable modules for some chaotic looping. Internally a mathematics thing again with a `BIRD` knob for some patterns from modal logic. It has a reset input to repeat the same sequence and so can work as an automatic pattern sequencer similar to a Euclidian step sequencer.

There is a great book on modal logic called [To Mock a Mocking Bird](https://en.wikipedia.org/wiki/To_Mock_a_Mockingbird), itself a follow up to [Forever Undecided(https://en.wikipedia.org/wiki/Raymond_Smullyan). A lay person introduction to the subject.

### V
helps with all the clocking combining to trigger envelopes and the CV of oscillators. It is really good to be able to trigger an envelope VCA and just wire it into oscillators.

From Beyond **vTBC**
---

