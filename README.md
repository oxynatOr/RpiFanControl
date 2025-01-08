# RpiFanControl
This package adds additional FanControl over HW-PWM (sysFS) for Venus OS running on Raspberry PI platforms. 
It is not suitable for other GX devices such as CCGX or Cerbo GX.

The stock RPI Venus distribution there are no Kernel driven PWM

This script adds:
    pwmchip0 to sysfs

Installation:

RpiFanControl requires that SetupHelper is installed first.

The easiest way to install RpiGpioSetup is to do a "blind install" of SetupHelper
	and then add the RpiFanControl package via the PackageManager menus.

Refer to the SetupHelper ReadMe for instructions and for other install options:
	https://github.com/kwindrem/SetupHelper
