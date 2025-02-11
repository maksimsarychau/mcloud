Zebrunner MCloud
==================

Zebrunner MCloud is a Device Farm for automated test execution (Appium) and remote web access by humans to physical devices (Android and iOS) including phones, tablets, and TVs. It is fully integrated into the [Zebrunner (Community Edition)](https://zebrunner.github.io/community-edition) ecosystem and can be used both for manual and automated testing.

* It is built on top of [OpenSTF](https://github.com/openstf) and supports iOS devices remote control.

Feel free to support the development with a [**donation**](https://www.paypal.com/donate?hosted_button_id=JLQ4U468TWQPS) for the next improvements.

<p align="center">
  <a href="https://zebrunner.com/"><img alt="Zebrunner" src="https://github.com/zebrunner/zebrunner/raw/master/docs/img/zebrunner_intro.png"></a>
</p>

## System requirements 

### Hardware requirements

|                         	| Requirements                                                     	|
|:-----------------------:	|------------------------------------------------------------------	|
| <b>Operating System</b> 	| Ubuntu 16.04 - 21.10<br>Linux CentOS 7+<br>Amazon Linux 2 	      |
| <b>       CPU      </b> 	| 4+ Cores                                                         	|
| <b>      Memory    </b> 	| 16 Gb RAM                                                        	|
| <b>    Free space  </b> 	| SSD 32Gb+ of free space                                         	|

### Software requirements

* Install docker ([Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04), [Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04), [Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04), [Amazon Linux 2](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html), [Redhat/Cent OS](https://www.cyberciti.biz/faq/install-use-setup-docker-on-rhel7-centos7-linux/))
  
* Install [docker-composer](https://docs.docker.com/compose/install/#install-compose) 1.25.5+

* Install git 2.20.0+

## Usage
1. Clone [mcloud](https://github.com/zebrunner/mcloud) and set up:
   ```
   git clone https://github.com/zebrunner/mcloud.git && cd mcloud && ./zebrunner.sh setup
   ```
   > Provide valid protocol, hostname, and port
2. Start services `./zebrunner.sh start`
3. Open `http://hostname:80/stf`
4. Log in using any name/email values as auth-mock is configured by default
5. Goto Settings->Keys and generate new Access Token
6. Paste generated token into the variables.env for `STF_TOKEN` var
7. Restart services using `./zebrunner.sh restart`
8. Set up the servers with Android and iOS devices according to [mcloud-agent](https://github.com/zebrunner/mcloud-agent)
   > [mcloud-ios](https://github.com/zebrunner/mcloud-ios) can be used to connect iOS devices via MacOS
9. Use `http://hostname:80/mcloud/grid/console` to see connected devices and `http://hostname:80/mcloud/wd/hub` as Selenium/Appium hub url for test automation.

> Follow the installation and configuration guide in [Zebrunner CE](https://zebrunner.github.io/community-edition) to reuse MCloud components effectively for Test Automation.

## Components
* [mcloud-agent](https://github.com/zebrunner/mcloud-agent) - Device Farm agent for connecting physical Android and iOS devices including phones, tablets, and TVs via Linux.
* [mcloud-ios](https://github.com/zebrunner/mcloud-ios) - Device Farm agent for connecting physical iOS devices including phones, tablets, and TVs via Mac.
  > Support of simulators [coming soon](https://github.com/zebrunner/mcloud-ios/issues/87)
* [mcloud-device](https://github.com/zebrunner/mcloud-device) - Dockerized STF provider image for Android and iOS devices.
* [mcloud-grid](https://github.com/zebrunner/mcloud-grid) - Enhanced Selenium Grid for automating physical devices and emulators/simulators via Appium.
* [appium](https://github.com/zebrunner/appium) - Enhanced Appium image with low-level video recording and local storage for ipa/apk artifacts.

## Documentation and free support
* [Zebrunner PRO](https://zebrunner.com)
* [Zebrunner CE](https://zebrunner.github.io/community-edition)
* [Zebrunner Reporting](https://zebrunner.com/documentation)
* [Carina Guide](http://zebrunner.github.io/carina)
* [Demo Project](https://github.com/zebrunner/carina-demo)
* [Telegram Channel](https://t.me/zebrunner)
 
## License
Code - [Apache Software License v2.0](http://www.apache.org/licenses/LICENSE-2.0)

Documentation and Site - [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/deed.en_US)
