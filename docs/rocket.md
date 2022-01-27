VCVRack V2
===

The upgrade was quite painless after **2.0.6** was installed. A simple `plugin.json` change and some checking to see if no API deprecation was needed. Nope, so build and **2.25.25** was issued, and **2.25.26** was started so I could add anything extra from the new API, like labels for ports.

It's going well on the conversion to API 2. The most confusing issue is perhaps handling RGB lights. It would seem that having 3 tool tips registered would be a bit excessive. Lucky for me I have buttons in the LED bezels, and so the button has a label option `default = ""` as the second parameter to `configButton`.

I've submitted **2.25.26** for publication in the library. Not all machines have been API 2 converted, but quite a few have. To prevent documentation suffering from boiler plate documentation boredom this was necessary. The rest are easy to convert, as there is perhaps just one snap knob to handle.

## 2.25.27
Full API 2 edits to label all ports and lights. Up on test before commit to distribution.
