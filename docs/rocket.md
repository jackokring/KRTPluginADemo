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

## 2.26.28 Published 2023-01-30
Yes, it's uploaded. `C` is fixed so a nice triple channel mix, invert and filter with link chaining. Now to focus on `Z` (the GUI style preview is only partially done with no processing of sound). `E` has been de-glitched too.

This leaves me now to work on the `Z` module GUI, which has changed a little. I've got to decide on the VCO kind and location, as it might just be a simple sine wave or some kind of spectral additive. It is destined to got through a wave-shaper of sorts given the nature of the module. It also will have phased outputs, so it likely will need two ratio tuning knobs.

I'm tunning the include and excludes to ignore the many `~/Rack/plugins/**` source files to speed scanning my own source. `"../**": true` in `settings.json` perhaps (I mean I don't want it to exclude the directory `~/Rack/plugins/KRTPluginA` and apparently it doesn't). I've also added the markdown for this blog into the project. This makes it easier to edit in the one place now that VSCode is much, much faster due to also having all the unused extensions switched off.

I'm cleaning up the archives of older versions as they aren't much use to me or even to others as the `2.2.3` version of Rack is quite nice and stable. And apparently I have to exclude the same header search from this repo and "this markdown like C" needs the extensions for C too, as it's part of the workspace now with its own `settings.json`.

# Latest

## General Coding
So I deleted `nautilus` and installed `thunar` instead to increase efficiency. That background `tracker-miner-fs` task is a bit of a hog at inconvenient moments (glitch). I also added in some more recent versions of some plugins.

I've also been building `OpenRA` (Red Alert - the game) and `J` (from jsoftware - the language) to get more things running on this Chromebook. `J` especially was a big task (SSD wise) as `jqt` needed quite a lot of `Qt5` dependancies installed. I seem to have `QtCreator` installed now "for free". I might have to pack down some of the build code, of some projects, to free up some space.

For python I have made some `.bashrc` entries:
```
# pip utilities
alias pipfix="(pip check | awk '{print $1}' | xargs pip install --upgrade) && pip check"

# pip upgrade all
alias pipnew="(pip list -o | cut -f1 -d' ' | tr ' ' '\n' | awk '{if(NR>=3)print}' | cut -d' ' -f1 | xargs -n1 pip install -U) && pip check"
``` 
To allow upgrading packages, and reducing the number of version conflicts after. I managed to get my current `pip check` down to just `ossfs` needing an older version of `fsspec` for some AWS thing built into something, which I'm not using.

The build of `J` is interesting, as I'm making an new branch to investigate if a `KRTPluginJ` might be possible. Basically (kind of inspirational pun intended) the `J` library in its own thread with IO module extenders to operate on data streams represented as `J` global variables with all the code in `A` to `Z` globals set in `profile.ijs`. Some limits on the `mac-arm64` version as they don't directly `make` such a `libj.so` equivelent.

With a bit of planning this might be a nice module. I'm imagining something like time, polyphony and some other control CV for indexing the `J` arrays returned. Of course it will be a bit inefficient as parsing and stringifying floats might be quite division intensive. But, the goal is to make the change over between arrays synchronous in some fashion.

## So `KRTPluginJ` Then

The starting repository is here. Not much done yet apart from [planning](https://github.com/jackokring/jqt-chromebook-arm/blob/libj-wrapper/VCVRack.md) how it will work, and what front panelage might be needed. It has to be external to the `KRTPluginA` which has a MIT licence as `J` is all GPL3. Also it might only be self build DIY and not in the library.

## 2.26.29
TBC
