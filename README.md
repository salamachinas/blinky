# blinky

## installing tinygo on mac

install tinygo using brew

```sh
brew tap tinygo-org/tools
arch -arm64 brew install tinygo
```

add arduino dependencies

```sh
arch -arm64 brew install avrdude
```

## vscode config

Getting GOROOT and build tags by controller

```sh
tinygo info arduino
```

Vscode settings.json example for arduino controller

```sh
{
  "go.toolsEnvVars": {
    "GOROOT": "~/Library/Caches/tinygo/goroot-fec2d8579c293d2bd4e0e76a523c22d1acfbd2d095f15ac22320ece59243a0fb",
    "GOFLAGS": "-tags=avr baremetal linux arm atmega328p atmega avr5 arduino tinygo math_big_pure_go gc.conservative scheduler.none serial.uart"
  }
}
```

## flashing

Flashing blinky to arduino-mega2560 controller

```sh
tinygo flash -target=arduino-mega2560 main.go
```
