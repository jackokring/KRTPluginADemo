Welcome to the [KRTPluginA](https://library.vcvrack.com/KRTPluginA) Blog Site
===

Built with the most excellent GitHub pages facility. **Under Construction: Always But Slowly**. Recommended.

More info on [the process](process.md) such as using `master` and not a branch for easy tests by others but confusion on the command line compile.

And it came to pass that VCV Rack didn't need a full build, which didn't work for me, and now I can make some modules. This plugin brings together some ideas I've had for a while into functioning modules. The public release is [here](https://library.vcvrack.com/KRTPluginA), and as compiling a later test release can be complicated you may have to wait sometimes for the new features.

Enter the Rasin' Detre (**RD**) for the modules. This might explain a rationale for purpose.

An alphabetic list [of modules](alphabet.md) so that I don't reuse letra-labels.

The First 26 HP **v1.6.9**
---

### A
is a filter, as I've had the DSP code together for a while. It didn't go VST or even Android app. What's special? 18 dB (3 pole), with the fourth pole set to match the first but of opposing pass. The 45 degree phase shifts make for a nice ring modulation multiply for some extra tonal brightness you may or may not like depending on the patch.

Try [DA](https://github.com/jackokring/KRTPluginADemo/blob/master/DA.vcv) for an exaple patch. Or just download this [archive](https://github.com/jackokring/KRTPluginADemo/archive/refs/heads/master.zip) if all the copy and file extension change business seems more than a strain than a few megabytes of download excess.

**RD** I half made a synth in [SynthEdit](http://www.synthedit.com/) `JK77` which had almost this 18dB filter. It was different enough.

### μ
started out as some idea about using calculus to make an interesting module. I pulled forth some interesting FIR filter coefficient lists, added some advanced integration by parts (it's a thing to make the sums maybe possible) and added in some of my own findings around the independence of f(x) when observed in a way such that x doesn't have to be known. In fact depending on how sigularities (think black holes and errors in general relativity) are placed in the unknown relative coordinates can lead to different results.

I then went and ruined it by truncating (precise bit crush is a good analogue) the calculations and then even harmonically cube rooted the extreams of the signal, bringing up the compression as it were for sonic utility. Perhaps an ego module, but it is the gold one.

Demo [crisp](https://github.com/jackokring/KRTPluginADemo/blob/master/crisp.vcv).

**RD** integral calculus near a singularity (or not) has multiple approximations (equals number out look good). Does it sound good? At low precission of series is it a bitcrush?

### T
was a perfection of an idea about slowing down the sound and then speeding it up (like a chorus) but in time to a trigger sync/gate. The switching point decided by possible maths given an octave ratio. Twist for tuning, and add in the origional sound source for some arp chordy goodness. I like it. If you have no trigger it appears like a pass through, so yes it does need a trigger to be useful. For extra utility it does provide a computed output trigger when it goes from low to high pitch. You can't go high first as you can't playback samples faster than you store them.

A demo of possibly simple but demonstrative purposes is [I shat the she riff](https://github.com/jackokring/KRTPluginADemo/blob/master/I%20shat%20the%20she%20riff..vcv), and it was a good name.

**RD** has a nice symetric consumption to it, and can be good?

### L
was an idea about audio inputs and latency. If you are delayed a bar, then the future match timing requires slightly less than a bar to be on time. A [boring](https://github.com/jackokring/KRTPluginADemo/blob/master/boring.vcv) patch just tests the delay, but usage is so latent specific I'll leave use upto you.

**RD** latency coverup?

### ;D
got jokingly assigned a letter by TL;DR, but it is an exponetial VCA. It also features all pass future prediction technology. A bit of a joke, but the phase could be considered to be phase lead by lagging the right amount given the lead and sampling rate. It might need post filtering due to differential crackle. Good at tracking aliasing. Demo [DA](https://github.com/jackokring/KRTPluginADemo/blob/master/DA.vcv).

### R
such a simple module. take any cable and split it to the input and the output goes to where the cable ended. Precise CV conservation pass through. Then you can gain another signal on, and take that sum which is the output with the other signal on, and take it as another gain controlled CV to somewhere else. A generic mixer/splitter and no demo is needed.

**RD** a prepositional 3HP to factor out so many **unused** always input gains. 

Installment of the Next 18 HP Allocation **v1.8.13**
---

### Ω
for a randomization of a clock signal to many gateable modules for some chaotic looping. Internally a mathematics thing again with a `BIRD` knob for some patterns from modal logic. It has a reset input to repeat the same sequence and so can work as an automatic pattern sequencer similar to a Euclidian step sequencer.

The most interesting design decision is about the nature of polyphonic in the context of a clock distributor. With a polyphonic clock the outputs latch earlier versions of the first channel into later channels.

**RD** I needed to find out how to use custom displays (for self happiness). Added in a computational machine as well as randomness. It added some audio to "solve" ping story of the man throwing "machined" at the wall and being fired as the manager never understood the ear and the nature of good and bad pings.

### V
helps with all the clocking combining to trigger envelopes and the CV of oscillators. It is really good to be able to trigger an envelope VCA and just wire it into oscillators. So a three envelopes in one was designed, and having trigger combining for CV modulation to decide a note seemed cool too.

Try [Omicron](https://github.com/jackokring/KRTPluginADemo/blob/master/Omicron.vcv) for both these last two modules.

**RD** an envelope and maybe `T0` should be there. But it was nice to do and had some multiple combination charm.

From Beyond **v1.9.15**
---

So with eight modules completed [plugin issues](https://github.com/jackokring/KRTPluginA/issues) can be filed for feature requests. Any interesting demos can be [filed with a link](https://github.com/jackokring/KRTPluginADemo/issues) to extend the demos available.

I'm currently putting together ideas for more modules. The built in selection is quite good and I've got to check out more of the library.

### F
an interesting F/Q extension to a three parameter F/S/S. Control of the default filter (some standard patterns), brings the filter into a 3D morphological extension of a standard quad of default beautifuls. Bessel, Botterworth, Linkwitz-Riley and Legendre.

I think a 1V by 1V square on `SPD` and `SKW` should do it. Try [morph](https://github.com/jackokring/KRTPluginADemo/blob/master/morph.vcv) for this module.

A 5V by 5V modulation square with +6dB ins (20V) gives quite a range. The filter is now fixed, and the wise will notice the higher damped filter pole pair ordering comes second in the series, so that the hard clamping smooths a little `DRV` on high Q in the first pole pair. Origionally this was just basic noise control principals, but is better.

**RD** no sh*t this thing can be nice. I prefere it to `A`. It has some purity of access to unmodulated wants, while showing what can be done without excursion resonance.

Utility **v1.11.16**
---

### W
a simple module to add or subtract standard 10V gate signals into a chromatic sum. Can turn a drum sequencer into an arpegiator.

**RD** arps a sequencer to free the imperfect knobing of a scale with nicer settings like Q and well you get the wires a free didn't you?

Try [W](https://github.com/jackokring/KRTPluginADemo/blob/master/W.vcv) for this module.

Sequencing **v1.11.16**
---

### Y
a complex module for gate patterns. I've always wondered why drum machines don't even have the extra 12 buttons for triples. Sounds like it would add less than an extra 50 currency units and not too much complexity to the software given **shuffles** div three flexibles.

Yep, not transfering patterns globally could be a big thing, but also lack of pattern space too for playing the old stuff, along with the new. Seems Rack has a module preset save in the latest version though. Nice, so just saving the current pattern via a right click preset is good.

Also an experiment into controlling the module using `CV/Gate` on the keyboard for easy playing without using the mouse. The plan being to make a useful design with an easy to remember keyboard mapping.

**RD** never had a good party without a rythum. Maybe a nice chill out, but I haven't made a PicoDrum emulator and I won't.

Try [Y](https://github.com/jackokring/KRTPluginADemo/blob/master/Y.vcv) to get your sequence on.

Oscillator **v1.12.18**
---

### O
a triple feedback oscillator of the skew parabolic saw wave variety. The algorithm is quite simple. Inspired by the **Everyday Electronics** weird sound effects generator from somewhere around the 70s. The whole integrated into **Wireless World** with an **ETI** page or two as the offshored consumer detatchment of `circuit` from the people became a marketing control own goal, as they would see it later, as the physics brought upon the exponential of climate. Top Everest or even a K too. To Giro ah-man. Hull and Rug-A? Hence a Labowski.

**RD** a good oscillator is always a good oscillator.

Try [parabolic](https://github.com/jackokring/KRTPluginADemo/blob/master/parabolic.vcv).

Spice for Time **v1.15.19**
---

### S
some kind of MIDI-CV to 10V divided by 64 sychronization scratch thing. Added a slight update `JAZZ` input to `Y` to accept it [Jazz Standard](jazz.md). Make sure `Y` is `RST` to sync.

**RD** external sync and some accident of availability allows for a beat stutter replacement of an unknown bpm on the initial and so why not all beats?

### E
a simple envelope AR. Percusive and with its own modulation control for those filter cut-offs.

**RD** eliminates space of a VCA and an envelope generator often.

Try [SE](https://github.com/jackokring/KRTPluginADemo/blob/master/SE.vcv), it's quite detuned but ...

### Various optimizations
so why not? Sounds good with no noticable audio artifacting.

### X
an oversampled wave floder with a few additional controls.

**RD** an oversampled design just has to be done.

Thinking of a Number **v1.18.20**
---

### M
the first rule of modulation in the land of `Fourier-Nyquist Non-linear Club (FNNC)` is pre-emphisis, and de-emphisis noramalization. A normal default to RIAA sounds occasionally useful on not buttering the diamond with vinyl.

**RD** hot audio-logical zones and the gradient deviation rate is controlled. This reduces higher harmonics. The post amplification may reamplify the fundementals, but the harmonic production of higher frequencies is less.

### Something Esoteric or a Little Strange
I'm in the thought zone. I wonder what might come up. For module 17 something a little weird would be nice. Not too weird, and I'm not sure if it would be control or sound as the focus.

### Q
a little physical modelling effect.

**RD** why not?

### C
a three channel attenuverter (with gain) and each having a simple low-pass pole. A sum output is also available for mixer use. A chain input is also provided for bigger mix channel combinations.

**RD** a mixer sixer was just an obvious use of such a module as the 18th.

Pitching a Perfect **v1.20.21**
---

### U
a qunatizer sample and hold. Combining the function of a quantizer and sample and hold for CV pattern generation.

**RD** seems sample and hold could do with some quantization.

### B
a cross bar router with functions on the grid. Seems changing some of the patch is good for progressive music.

**RD** performance and to not include something other than addition as the cross function seems a bit of a waste.

Something for the Weekend **v1.22.22**
---

### J
an all-pass filter. For some phaser classic sounds.

**RD** should be fun.

### K
oooh, what to do on the catch-22? I'll go black almost on the panel. A phase modulation VCO. Some simple controls and a simple algorithm.

**RD** to make some nice spectral timbres.

Seeing the Light **v1.23.22**
---

### H
an organ with some extra sounds? Standard Hammond stops with CVs and a little bit of phase modulation CV goodness.

**RD** as a classic organ set of harmonics mixed with some base weighted phase modulation, why not?

Extras **vTBC (NFA - No Fixed Arrival)**
---

### P
a spice flange malange. A delay with some all-pass feedback chorus style modulation?