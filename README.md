# Cylus
######Library for RaspberryPi GPIO - [Documentation](http://stackin.money/doc/cylus/index.html)

To cross-compile on RaspberryPi, follow these instructions: https://github.com/Ogeon/rust-on-raspberry-pi

#Example

```rust
#![allow(deprecated)]
extern crate cylus;

use cylus::Cylus;

fn main() {
    let gpio = Cylus::new(24);  // BCM Pin 24 aka GPIO5
    unsafe {
        for _ in 1..10 {
          println!("{}", gpio.read());
          gpio.high();
          std::thread::sleep_ms(1000);
          println!("{}", gpio.read());
          gpio.low();
          std::thread::sleep_ms(1000);
        }
    }
}
```

#TODO
- [x] get Rust working on raspberrypi
- [x] Read BCM2835 ARM Peripherals manual
- [x] make it work

#Converting into a library

- [x] simple digital GPIO input/output
- [ ] add Pwm functionality
- [ ] publish to crates.io
