<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a id="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![project_license][license-shield]][license-url]
<br />
<h1 align="center">RpiFanControl <sup>WIP</sup></h1>

 

<!-- ABOUT THE PROJECT -->
This package adds additional FanControl for Venus OS running on Raspberry PI platforms. 
It is not suitable for other GX devices such as CCGX or Cerbo GX.

The stock RPI Venus distribution there are no Kernel driven PWM

This script adds:
    ```pwmchip0``` to sysfs

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### GPIO Pinout

##### Warning! The Pi has 3.3V GPIO, so your pull-up resistor must be connect to 3.3V ONLY! You will fry your Pi if Vcc is connected to 5V.

The pull-up resistor that I use is 1kΩ 1/4W. The white paper says the maximum current is 5mA. According to Ohm’s Law: ```R=3.3/0.005``` <br>
the resistor should be 660Ω or larger to protect your fan.

| Rpi | Fan | Fan Colour | Note |
| --- | --- | --- | --- |
| GPIO 18 | PWM Signal | ***Blue*** |  |
| GPIO 17 | Tacho | ***Green*** | Connect to GPIO and 3v3 woth a Pull-Up-Resistor! |
| GND | GND | ***Black*** |  |
| 5v  | VCC | ***Yellow*** |  |
| 3v3 | Tacho | ***Green*** | You need at least 660Ohm resistor. |

The Fan-Connector is calld: ```KF2510``` 

### Installation

RpiFanControl requires that SetupHelper is installed first.

The easiest way to install RpiGpioSetup is to do a "blind install" of SetupHelper
	and then add the RpiFanControl package via the PackageManager menus.

Refer to the SetupHelper ReadMe for instructions and for other install options:
	https://github.com/kwindrem/SetupHelper

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Manual Installation


#### Overlay Instructions

Put it in /u-boot/overlays:<br>
```sudo cp FileSets/VersionIndependent/pwm.dtbo /u-boot/overlays/pwm.dtbo```

Add a line to /u-boot/config.txt:<br>
```dtoverlay=pwm,pin=18,func=2```
<br>
Note /u-boot typically appears as /boot when the SD card is mounted on a computer

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ROADMAP -->

### Fan Modes ###

##### Curve #####



$\mathrm{PWM} = PWM_{min} + (PWM_{max} - PWM_{min}) * ( 1-e^{-k *(temperature−temp_min)}) $

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Roadmap

- [ ] Curve Mode
- [ ] UserMode
- [ ] PID Controller (Proportional-Integral-Derivative)

See the [open issues](https://github.com/oxynatOr/RpiFanControl/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>


### Top contributors:

<a href="https://github.com/oxynatOr/RpiFanControl/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=oxynatOr/RpiFanControl" alt="contrib.rocks image" />
</a>

<!-- LICENSE -->
## License

Distributed under the MIT. See `LICENSE` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[wip-shield]: https://img.shields.io/github/contributors/oxynatOr/RpiFanControl.svg?style=for-the-badge
[contributors-shield]: https://img.shields.io/github/contributors/oxynatOr/RpiFanControl.svg?style=for-the-badge
[contributors-url]: https://github.com/oxynatOr/RpiFanControl/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/oxynatOr/RpiFanControl.svg?style=for-the-badge
[forks-url]: https://github.com/oxynatOr/RpiFanControl/network/members
[stars-shield]: https://img.shields.io/github/stars/oxynatOr/RpiFanControl.svg?style=for-the-badge
[stars-url]: https://github.com/oxynatOr/RpiFanControl/stargazers
[issues-shield]: https://img.shields.io/github/issues/oxynatOr/RpiFanControl.svg?style=for-the-badge
[issues-url]: https://github.com/oxynatOr/RpiFanControl/issues
[license-shield]: https://img.shields.io/github/license/oxynatOr/RpiFanControl.svg?style=for-the-badge
[license-url]: https://github.com/oxynatOr/RpiFanControl/blob/main/LICENSE
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
