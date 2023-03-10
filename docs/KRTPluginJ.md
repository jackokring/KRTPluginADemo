# Captain's Log `KRTPluginJ`

[Latest](#latest) Auto jump to where the "edit limit" is plus addition forward ... Auto insert on save?

So the `make` works, but te modules are nowhere near ready. I'm making the "standard" `plugin.cpp`/`plugin.hpp` for all my future plugins. A generic project starter. I've abstracted the edits when making modules to be in `modules.hpp` (for the list of module sources) and `menus.txt` (for the context menus and threaded signalling).

Sayc, sarc .ASM a bound?

I've added `make macjig` to force `menus.txt` change recompilation. A stop gap as `.hpp` er, should standardly work, 'cos like that's how `.cpp` lines of `#include` go like man. Owe quey, reda di Manuelle Jaw de sure like man?

Next!

I vont to vrock'it into spass. Like a moo-sycle style like so man, hey dudumdida, ho, yes, or "well it's like the loader is like flawed, but excellent, but needs a stop 'till end then go, as an easy man." 2023-03-02 yes either same TB-303*2.

Yes, the build system should now be better. It follows a few botches and generic code hacks. So now I'm thinking about maybe other languages to add. I though LOGO for fun, but `TO NAME :VAR` is all wrong. It should've been `TO "NAME "VAR` for evaluation consistency. As an adult it makes lisp `macro` look useful but primarily avoided to remove one letter and add much in the source code. Implicit `"` is kind of cool in `setq`, but suffers from inconsitency, and as a learner lingo distracted by pizza turtles and living in the sewer, erm, is it really the daddy or the diddy, butt wee wont go win to dat?

Hi ho. Next up (no `postscipt` although cool, has much to  blit and little to command line decompose).  ~~I~~ So `netpbm` is graphically cool in a textual number data format. I wonder about that fractal algorithm, as it reminds me of the `.fif` file extension from the really early '90s. I managed to recompress the uncompressed residual in a loop at 50% quality and after 3 iterations it was better than 100%b in less time, even though an archive `.zip` of the multiple outputs was required.

~~COBOL, ASM (machine specific), PL/1, FORTRAN (good supercomputer heritage though)~~, spreadsheet outputs (LibreOffice), CSV, ...

So I've classed the menus as `OnMenu` so multiple instances can occur. That was realatively easy, but involved a bit of forwarding of classes to callback actions. So it now is complete enough. Next is hot keys. I've got to read up on the docs.

`error: assignment to 'int (*)(const __mpq_struct *, const __mpq_struct *)' from incompatible pointer type 'FARPROC' {aka 'long long int (*)()'} [-Werror=incompatible-pointer-types]` is the latest, perhaps a cast? So ...

So `mac` builds, `lin` complained at `sudo` so removed for assumed root, and `win` seemed to fail on the `j` link, perhaps an unneeded resource file from MS. I'll set it to one more wizz tonight and fingers crossed only `win` will be left to fix in the morning. :D

So I might have solved the `mingw` resource compiler issue, but the shared `linux` container baulks about not finding the include for `-luuid` in `premake5` building, while both the `macos` version fail on `*** "invalid configuration release".` when building `efsw` with the built `premake5`, so perhaps that's a default config issue ...

But yes closer than yesterday.

```
cd efsw/make/macosx && make config=release
Makefile:42: *** "invalid configuration release".  Stop.
make: *** [libefsw.a] Error 2
Error: Process completed with exit code 2.
```

And

```
x86_64-ubuntu16.04-linux-gnu-gcc -o build/bootstrap/premake_bootstrap -DPREMAKE_NO_BUILTIN_SCRIPTS -DLUA_USE_POSIX -DLUA_USE_DLOPEN -I"contrib/lua/src" -I"contrib/luashim" src/host/*.c contrib/lua/src/lapi.c contrib/lua/src/lbaselib.c contrib/lua/src/lbitlib.c contrib/lua/src/lcode.c contrib/lua/src/lcorolib.c contrib/lua/src/lctype.c contrib/lua/src/ldblib.c contrib/lua/src/ldebug.c contrib/lua/src/ldo.c contrib/lua/src/ldump.c contrib/lua/src/lfunc.c contrib/lua/src/lgc.c contrib/lua/src/linit.c contrib/lua/src/liolib.c contrib/lua/src/llex.c contrib/lua/src/lmathlib.c contrib/lua/src/lmem.c contrib/lua/src/loadlib.c contrib/lua/src/lobject.c contrib/lua/src/lopcodes.c contrib/lua/src/loslib.c contrib/lua/src/lparser.c contrib/lua/src/lstate.c contrib/lua/src/lstring.c contrib/lua/src/lstrlib.c contrib/lua/src/ltable.c contrib/lua/src/ltablib.c contrib/lua/src/ltm.c contrib/lua/src/lundump.c contrib/lua/src/lutf8lib.c contrib/lua/src/lvm.c contrib/lua/src/lzio.c  -lm -ldl -lrt -luuid
src/host/os_uuid.c:12:10: fatal error: uuid/uuid.h: No such file or directory
   12 | #include <uuid/uuid.h>
      |          ^~~~~~~~~~~~~
compilation terminated.
make[2]: *** [Bootstrap.mak:110: linux] Error 1
make[2]: Leaving directory '/__w/jqt-chromebook-arm/jqt-chromebook-arm/premake-core'
make[1]: *** [Makefile:141: premake-core/bin/release/premake5] Error 2
make[1]: Leaving directory '/__w/jqt-chromebook-arm/jqt-chromebook-arm'
make: *** [Makefile:186: plugin-build-linux-x64] Error 2
Error: Process completed with exit code 2.
```

But still some way to go. I won't know if the `windows` build has similar `premake5` issues until it passes the `j` build point, which is not helped by the combined container process kill. So options are install uuid but given the container complained when trying to install `premake4` which is a linux package from `bionic` Ubuntu onwards, but `uuid-dev` might work where `premake4` didn't.

[WinRes MinGW](https://blog.didierstevens.com/2018/09/17/quickpost-compiling-exes-and-resources-with-mingw-on-kali/) might work though to compile resources.

Some nice macro expansions to make the names and variables for a module from just a `#define NAME Blank` at the top. Makes for an easy generic copy of the Blank template to add new modules. [Nice Macros](https://www.iar.com/knowledge/learn/programming/advanced-preprocessor-tips-and-tricks/).

Ok, so UUID and `uuid-dev` package. I'm not sure even this will completely fix the `premake5` dependancy chain, as that is just the bootstrap `premake5` before the actual build full which includes all sorts of SSL and `curl` stuff, which isn't needed for many things. I'm on Debian Bullseye, and I've installed many `*-dev` packages doing things.

# Latest

OK :D (Nice Rust ID on the SIM repo ... robot giggle)

`>`

`Friday 2023-03-10 16:00:43 [dev-bot] #47` compiles all, but the `win` has no `j`, no `efsw` callback working and no forking due to `posix` pipe support and `fork` not being available. There's a nice `isWindows()` function though for further development, and a `fileExeTension()` for when the base name doesn't work. I kept it generic justb in case I make windows `fork` work. So a weird hack of `premake4` (`lin` by the repo makefiles predone, `mac` by a botch `brew` and `win` by ignoring such notifications of change). It's kind of impossible without a set of makefiles for `win`. Any offers?
