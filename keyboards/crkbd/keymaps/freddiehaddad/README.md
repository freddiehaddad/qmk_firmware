# Quantum Mechanical Keyboard Firmware

[docs](https://docs.qmk.fm)
[repo](https://github.com/qmk/qmk_firmware)
[tool](https://config.qmk.fm/#/crkbd/rev1/LAYOUT_split_3x6_3)

## Layout

Custom Overrides

```text
key     | shift + key
--------+-------------
KC_PIPE | KC_QUES
KC_BKSP | KC_DEL
```

Layer 0

![scrn-2023-11-03-13-20-16](https://github.com/freddiehaddad/qmk_firmware/assets/6127369/b8fea392-e3f1-4b0b-a891-05e30cc3cb9c)

Layer 1

![scrn-2023-11-03-13-20-41](https://github.com/freddiehaddad/qmk_firmware/assets/6127369/95a1a65b-11fd-422b-9f36-7b6d0b2fdf0c)

Layer 2

![scrn-2023-11-03-13-21-02](https://github.com/freddiehaddad/qmk_firmware/assets/6127369/2f8a2ecd-26ce-4a9a-ada2-998235103209)

Layer 3

![scrn-2023-11-03-13-21-21](https://github.com/freddiehaddad/qmk_firmware/assets/6127369/40276f5b-29e9-4f00-8940-e4b9f4ca83b7)

## Installation

```text
echo "PATH=$PATH:$HOME/.local/bin" >> $HOME/.zshrc
python3 -m pip install --user qmk
```

## Configuration

```text
qmk setup -H $HOME/projects/git/qmk_firmware freddiehaddad/qmk_firmware
qmk new-keymap --keyboard crkbd --keymap freddiehaddad
qmk config user.keyboard=crkbd
qmk config user.keymap=freddiehaddad
```

## Flashing

```text
qmk compile --clean
qmk flash --bootloader dfu
```

## Miscellaneous

### Initial Flash

See: [Github Issue](https://github.com/qmk/qmk_firmware/issues/22050#issuecomment-1722308968)

```text
 dfu-programmer atmega32u4 erase --force
```

### Generate keymap.json

```text
qmk c2json --keyboard crkbd --keymap freddiehaddad --output keymap.json keymap.c
```

