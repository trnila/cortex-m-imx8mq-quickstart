# `cortex-m-imx8mq-quickstart`

1. install thumbv7em-none-eabihf

``` console
$ rustup target add thumbv7em-none-eabihf
```

2. Clone this repository or use the generator:

``` console
$ cargo generate --git https://github.com/trnila/cortex-m-imx8mq-quickstart.git
 Project Name: app
 Creating project called `app`...
 Done! New project created app
$ cd app
```

3. Enable JTAG access to AHB by disabling sleep in Linux

    * append `cpuidle.off=1` to cmdline
    * or `for i in /sys/devices/system/cpu/cpu*/cpuidle/state*/disable; do echo 1 > $i; done`

4. Run the OpenOCD server

``` console
$ openocd -f ./openocd.cfg
```

5. Run and build

``` console
$ cargo run
```

# ARM Semihosting

``` console
(gdb) monitor imx8mq.m4 arm semihosting enable
```

# VS Code

This template includes launch configurations for debugging CortexM programs with Visual Studio Code located in the `.vscode/` directory.  
See [.vscode/README.md](./.vscode/README.md) for more information.  
If you're not using VS Code, you can safely delete the directory from the generated project.

# License

This template is licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or
  http://www.apache.org/licenses/LICENSE-2.0)

- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.
