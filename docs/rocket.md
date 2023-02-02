# VCVRack V2

![Donate](PaypalDonate.png)

[Donate](https://www.paypal.com/donate/?hosted_button_id=Y94P8UE7PYCJY)

* [Old Stuff](index.md)
* [New Stuff](#latest)
* [Linux ARM Builds](https://drive.google.com/drive/folders/11k81iJwAW_xP3fNGO9ZmNh-XwS2DexbF)

The upgrade was quite painless after **2.0.6** was installed. A simple `plugin.json` change and some checking to see if no API deprecation was needed. Nope, so build and **2.25.25** was issued, and **2.25.26** was started so I could add anything extra from the new API, like labels for ports.

It's going well on the conversion to API 2. The most confusing issue is perhaps handling RGB lights. It would seem that having 3 tool tips registered would be a bit excessive. Lucky for me I have buttons in the LED bezels, and so the button has a label option `default = ""` as the second parameter to `configButton`.

I've submitted **2.25.26** for publication in the library. Not all machines have been API 2 converted, but quite a few have. To prevent documentation suffering from boiler plate documentation boredom this was necessary. The rest are easy to convert, as there is perhaps just one snap knob to handle.

## 2.25.27
Full API 2 edits to label all ports and lights. Up on test before commit to distribution. I seem to be going along at about 100 downloads a day on **2.25.25** and I hope this continues or get better. This build has no new instruments, but has moved all modules to API 2.

Now to think up some new modules. Maybe just a few ...

## 2.26.28
Fixed a few things when upgrading to `Rack-lin-arm64-2.2.3` and submitted to the build pipeline. The `Z` module is just some GUI elements at present.

[Moonshine Elliptical](https://github.com/jackokring/KRTPluginA/blob/master/Z%20Moonshine%20Elliptical.pdf) is mildly interesting just from a mathematical point of view. [BSD conjecture](https://en.wikipedia.org/wiki/Birch_and_Swinnerton-Dyer_conjecture) might be related and is the sense that five groups in combination seem to have some generative power of description. But thinking exactly how this can be used for audio is quite challenging.

I started building on `lin-amd64` available [here](https://drive.google.com/drive/folders/11k81iJwAW_xP3fNGO9ZmNh-XwS2DexbF) Chromebook Tested and read the **README**. I just have to get back in the post COVID swing. I might develop some commercial modules after `Z`.

It's been fun getting this Chromebook to run Rack. There is no library support for `lin-arm64` so I built about **1067** modules. Missed out on some good `x86` only ones. I have only recently added a spell checker for my markdown in this latest Chromebook venture. Whey hey, I'm a pro!

## Brown Out, Brown Noise
Well, still waiting for the library update, and the Rack community forum site appears offline (Error 504 followed by waiting for the server loading circles). Maybe it's some hacky from the fabulous people of the non-musical suck the profit instead foundation. You'll never hear about them on television. If you have a television they'll whip you for not sucking the profit.

Maybe next week then the new bug found and fixed in `C` won't crash when loaded.

# Latest

## 2.26.28 Published 2023-01-30
Yes, it's uploaded. `C` is fixed so a nice triple channel mix, invert and filter with link chaining. Now to focus on `Z` (the GUI style preview is only partially done with no processing of sound). `E` has been de-glitched too.

This leaves me now to work on the `Z` module GUI, which has changed a little. I've got to decide on the VCO kind and location, as it might just be a simple sine wave or some kind of spectral additive. It is destined to got through a wave-shaper of sorts given the nature of the module. It also will have phased outputs, so it likely will need two ratio tuning knobs.

I'm tunning the include and excludes to ignore the many `~/Rack/plugins/**` source files to speed scanning my own source. `"../**": true` in `settings.json` perhaps (I mean I don't want it to exclude the directory `~/Rack/plugins/KRTPluginA` and apparently it doesn't). I've also added the markdown for this blog into the project. This makes it easier to edit in the one place now that VSCode is much, much faster due to also having all the unused extensions switched off.

I'm cleaning up the archives of older versions as they aren't much use to me or even to others as the `2.2.3` version of Rack is quite nice and stable.

## 2.26.29
TBC