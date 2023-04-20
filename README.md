# Hello Pico Ravenscar

### How to build:

```
$ alr build --release
```

### How this crate was first constructed:

Followed process here: https://pico-doc.synack.me/#the_ravenscar_profile

```
$ alr init --bin hello_pico_ravenscar
$ cd hello_pico_ravenscar
$ alr with ravenscar_full_rp2040 --use=https://github.com/JeremyGrosser/ravenscar_full_rp2040
$ alr with pico_bsp
```

Then configure rp2040_hal by adding the following to the bottom of the alire.toml:

```
[configuration.values]
rp2040_hal.Use_Startup = false
```

Make sure the project GPR file has no references to rp2040_hal's linker switches.

Finally, build using the instructions above.

Since, I have started using my own versions of ravenscar_full_rp2040 and pico_bsp which fix some issues with the demo.
