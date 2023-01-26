VCVRack V2
===

The upgrade was quite painless after **2.0.6** was installed. A simple `plugin.json` change and some checking to see if no API deprecation was needed. Nope, so build and **2.25.25** was issued, and **2.25.26** was started so I could add anything extra from the new API, like labels for ports.

It's going well on the conversion to API 2. The most confusing issue is perhaps handling RGB lights. It would seem that having 3 tool tips registered would be a bit excessive. Lucky for me I have buttons in the LED bezels, and so the button has a label option `default = ""` as the second parameter to `configButton`.

I've submitted **2.25.26** for publication in the library. Not all machines have been API 2 converted, but quite a few have. To prevent documentation suffering from boiler plate documentation boredom this was necessary. The rest are easy to convert, as there is perhaps just one snap knob to handle.

## 2.25.27
Full API 2 edits to label all ports and lights. Up on test before commit to distribution. I seem to be going along at about 100 downloads a day on **2.25.25** and I hope this continues or get better. This build has no new instruments, but has moved all modules to API 2.

Now to think up some new modules. Maybe just a few ...

## 2.26.28
Fixed a few things when upgrading to `Rack-lin-arm64-2.2.3` and submitted. The `Z` module is just some GUI elements at present.

[Moonshine Elliptical](https://github.com/jackokring/KRTPluginA/blob/master/Z%20Moonshine%20Elliptical.pdf) is mildly interesting just from a mathematical point of view. [BSD conjecture](https://en.wikipedia.org/wiki/Birch_and_Swinnerton-Dyer_conjecture) might be related and is the sense that five groups in combination seem to have some generative power of description. But thinking exactly how this can be used for audio is quite challenging.

I started building on `lin-amd64` available [Linux ARM](https://drive.google.com/drive/folders/11k81iJwAW_xP3fNGO9ZmNh-XwS2DexbF) Chromebook Tested. I just have to get back in the post COVID swing. I might develop some comercial modules after `Z`. 

## 2.28.29
TBC