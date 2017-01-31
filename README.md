<a href="http://www.ffuenf.de" title="ffuenf - code • design • e-commerce"><img src="https://github.com/ffuenf/Ffuenf_Common/blob/master/skin/adminhtml/default/default/ffuenf/ffuenf.png" alt="ffuenf - code • design • e-commerce" /></a>

vagrant-shopware
================
[![GitHub tag](https://img.shields.io/github/tag/ffuenf/vagrant-shopware.svg)][tag]
[![PayPal Donate](https://img.shields.io/badge/paypal-donate-blue.svg)][paypal_donate]
[tag]: https://github.com/ffuenf/vagrant-shopware
[paypal_donate]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=J2PQS2WLT2Y8W&item_name=Shopware%3a%20vagrant-shopware&item_number=vagrant-shopware&currency_code=EUR

This is an opinionated fork of [Vagrant Shopware Box](https://github.com/shopwareLabs/shopware-vagrant) to match our own project structure.
Additional features include:

* directory structure to allow remote deployment via [Laravel Envoyer](https://envoyer.io/)
* usage of our baseboxes from [vagrant-boxes](https://github.com/ffuenf/vagrant-boxes) / currently based on Ubuntu Xenial Xerus 16.04.1 Server x86_64
* installation of Java8 through ansible
* removal of different php versions / currently on PHP 7.0
* removal of adminer / we use an SSH-Tunnel with [Sequel Pro](https://www.sequelpro.com/) to access the database directly
* removal of phpinfo
* integration of [vlucas/phpdotenv](https://github.com/vlucas/phpdotenv) to allow configuration through environment variables needed for later deployment with [Laravel Envoyer](https://envoyer.io/)
* integration of [b3nl/sw-migrations](https://packagist.org/packages/b3nl/sw-migrations) to allow custom database migrations

Usage
-----

Adjust the settings in `tools/vagrant/Vagrantfile` to match your project.
Starting with a fresh repository and `'provision' => true` in your Vagrantfile will install a fresh copy of the latest shopware version from github (including test_images).
Be aware about the linked out folders `../../public/` and `../../shared/`. This way you will be working on the source files directly on your host - they are not part of your vagrant vm!

Attention!
Do not use for production usage - this is only meant to be for local shopware development.
We recommend to use a deployment workflow (git, envoyer, whatever suits you) to bring your project save to production.

Development
-----------
1. Fork the repository from GitHub.
2. Clone your fork to your local machine:

        $ git clone https://github.com/USER/vagrant-shopware

3. Create a git branch

        $ git checkout -b my_bug_fix

4. Make your changes/patches/fixes, committing appropriately
5. Push your changes to GitHub
6. Open a Pull Request

License and Author
------------------

- Author:: Achim Rosenhagen (<a.rosenhagen@ffuenf.de>)
- Copyright:: 2017, ffuenf

The MIT License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
