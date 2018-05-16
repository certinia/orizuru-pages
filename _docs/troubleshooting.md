---
---

# Installation

## NPM global installs fail with Error: EACCESS: permission denied
#### When:
I ran `npm install <any-package> --global` and the command failed.
#### What happens:
The command line logs out something like:
> npm ERR! code EACCES<br>
> npm ERR! errno -13<br>
> npm ERR! syscall access<br>
> npm ERR! Error: EACCES: permission denied, access '/usr/local/lib/node_modules/@financialforcedev/orizuru-tools/node_modules/color-convert'<br>
> npm ERR!  { Error: EACCES: permission denied, access '/usr/local/lib/node_modules/@financialforcedev/orizuru-tools/node_modules/color-convert'<br>
> npm ERR!   stack: 'Error: EACCES: permission denied, access \'/usr/local/lib/node_modules/@financialforcedev/orizuru-tools/node_modules/color-convert\'',<br>
> npm ERR!   errno: -13,<br>
> npm ERR!   code: 'EACCES',<br>
> npm ERR!   syscall: 'access',<br>
> npm ERR!   path: '/usr/local/lib/node_modules/@financialforcedev/orizuru-tools/node_modules/color-convert' }<br>
> npm ERR!<br>
> npm ERR! Please try running this command again as root/Administrator.<br>

#### How to fix it:
By default on MacOS and Linux, you will not have permission to write to the directories that npm uses to store global packages and commands. Refer to the [npm docs for fixing permissions](https://docs.npmjs.com/getting-started/fixing-npm-permissions) to resolve this.

# orizuru deploy

## orizuru deploy failed and asked me to verify my account
#### When:
I ran orizuru deploy and the command failed while adding add-ons to my application.
#### What happens:
The command line logs out something like:
> Command failed: heroku addons:create cloudamqp:lemur -a morning-waters-96022<br>
> Creating cloudamqp:lemur on morning-waters-96022... !<br>
> ▸    Please verify your account to install this add-on plan (please enter a<br>
> ▸    credit card) For more information, see<br>
> ▸    https://devcenter.heroku.com/categories/billing Verify now at<br>
> ▸    https://heroku.com/verify

#### How to fix it:
Make sure you have supplied your billing details in your Heroku account.
The Orizuru template apps use Heroku Add-ons - Heroku only allows add-ons to be added programmatically to Heroku apps in verified accounts, i.e. those that have completed their billing details.

This is the case *even when installing add-ons under a free plan.*
