# Prerequisites

- `python3`
- `ninja`
- `dfu-util`

# Build

## Installing dependencies

```sh
python -m venv .venv
source .venv/bin/activate
pip install west
west sdk install
west zephyr-export
west update && west packages pip --install
```

## Building an example app

```sh
west build -b stm32f401_mini zephyr/samples/basic/blinky`
```

# Flashing

Connect the board via USB to your PC.
Hold down the BOOT0 button and press NRST to bring device into DFU Boot mode.
Then run the following command:

```sh
west flash
```

In case of errors like `LIBUSB_ERROR_ACCESS` it might have to
be ran with sudo.