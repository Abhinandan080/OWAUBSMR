let reading = 0
//* JavaScript
radio.setTransmitSerialNumber(true)
radio.setGroup(4)
led.setBrightness(64)
basic.forever(function () {
    reading = pins.analogReadPin(AnalogPin.P0)
    if (reading < 500) {
        pins.servoWritePin(AnalogPin.P2, 0)
        basic.pause(3000)
        pins.servoWritePin(AnalogPin.P2, 80)
        basic.pause(3000)
        pins.analogWritePin(AnalogPin.P2, 0)
        basic.pause(5000)
    } else {
        pins.servoWritePin(AnalogPin.P2, 80)
    }
    basic.pause(5000)
    pins.servoWritePin(AnalogPin.P2, 0)
    basic.pause(3000)
    pins.servoWritePin(AnalogPin.P2, 80)
    basic.pause(5000)
})
