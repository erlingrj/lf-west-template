# Lingua Franca West Template
For complete docs see [here](https://www.lf-lang.org/docs/handbook/zephyr?target=c) 

## Requirements
- Linux system (or WSL). Should be fine on MacOS also, but not tested yet.
- lfc v0.4 or greater 
- west
- Zephyr SDK and toolchain  

## Getting started
1. Pull down the Zephyr RTOS sources

```
west update
```

2. Build QEMU emulation
```
cd application
west lf-build src/HelloWorld.lf -w "-t run"
```

3. Build NRF52 Blinky
This requires that the `nrfjprog` utility is installed. See installation guide [here](https://www.nordicsemi.com/Products/Development-tools/nrf-command-line-tools/download)

```
cd application
west lf-build src/NrfBlinky.lf -w "-b nrf52dk_nrf52832 -p always"
west flash
```