# Hi ... The Process

So building a master (although tags help) does leave it open for `git clone <repo>` not used tags before. VCV central do provide a cross-platform compile (Win/Lin/Mac) on a commit SHA so that's good.

I'd go fortnightly on the "CI build of plugin" (the library site one) thread as the person likely has many "stability and as described" issues. Automation of a code "throw" to many potential "executors" without some forethought isn't a good idea.

Keep **ALL** non instrument code such as example patches and large build for mates binaries **OFF** the main plugin repository.

You maybe code blind to how you see your module, but yes, I've miss-labelled IO before.

Try not to push code on an empty stomach. At least wait while you're saited before a "dial commit" to "downstream", and yes there should be an unlocking locking mechanism and a "side fart" on the discussion mailer, but this is not of Git today, so ...

# How I do a Module **Rack v1** (better than 0.x)
## Some details may be humourous
* Find module of similar HP, LANES and RUNGS. `Save As ...` the graphics. Add a `components` layer. do `5.08 * HP` and set dimensions in `sudo apt got inkscape`.
* run the `../../yes <X>` script that does not exist but `createmodule` might.
* Copy the macros:
```
//geometry edit
#define HP 5
#define LANES 2
#define RUNGS 7

//ok
#define HP_UNIT 5.08
#define WIDTH (HP*HP_UNIT)
#define X_SPLIT (WIDTH / 2.f / LANES)

#define HEIGHT 128.5
#define Y_MARGIN 0.05f
#define R_HEIGHT (HEIGHT*(1-2*Y_MARGIN))
#define Y_SPLIT (R_HEIGHT / 2.f / RUNGS)

//placement macro
#define loc(x,y) mm2px(Vec(X_SPLIT*(1+2*(x-1)), (HEIGHT*Y_MARGIN)+Y_SPLIT*(1+2*(y-1))))
```

* Fill in IO and parameter names.
* Add controls.
* Test compile.
* Move about the labels, delete (essential?) "contols" `components` layer.
* Copy:
```
	int maxPoly() {
		int poly = 1;
		for(int i = 0; i < NUM_INPUTS; i++) {
			int chan = inputs[i].getChannels();
			if(chan > poly) poly = chan;
		}
		for(int o = 0; o < NUM_OUTPUTS; o++) {
			outputs[o].setChannels(poly);
		}
		return poly;
	}
```
* Copy:
```
		float fs = args.sampleRate;
		int maxPort = maxPoly();

		float spd = params[SPD].getValue();

		// PARAMETERS (AND IMPLICIT INS)
#pragma GCC ivdep
		for(int p = 0; p < maxPort; p++) {
			float ispd = inputs[ISPD].getPolyVoltage(p) * 0.1f + spd;
 
			// OUT
			outputs[OUT].setVoltage(ispd, p);
		}
```
* Compile again to have the right names for everything so far.
* Switch between coding and indirect XML graphics **.svg** until satisfied.
* Let your professionalism override your enthusiasm.
* Repeat ...

## And
* You might need some of the:
```
        configParam(LAM, -36.f, 0.f, 36.f, "Halflife", " dBs");
```
* And some:
```
		addInput(createInputCentered<PJ301MPort>(loc(2, 6), module, W::I11));

		addOutput(createOutputCentered<PJ301MPort>(loc(1, 7), module, W::PLUS));
```
* With some slug change on the `<x>::<control>`.
* Then it's all [DSP](https://en.wikipedia.org/wiki/Digital_signal_processing).

## Useful (Within scope?)
```
dsp::SchmittTrigger sRst;
bool trigRst = sRst.process(rescale(rst, 0.1f, 2.f, 0.f, 1.f));
//more ...

```

## Hello
* [C++ reference](https://en.cppreference.com/w/) - it's a bit over-coercive on the no `&` pointer (for handles, with that C nakedness Java doesn't have). New `ISO` way as it states. I think it's a C++/Python convergence conspiracy. The SDK does make it a bit like sophisticated Arduino.