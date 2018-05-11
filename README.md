# pmm
Tools/scripts to release mails quarantined by MIMEsweeper's Personal Message Manager
used by ASTRON.

## Note
This software is in alpha-stage. It has only been tested on Linux Mint 18.3, a derivative of
Ubuntu 16.04 LTS.

## Requirements
In order to use this software, you need to have the following packages installed on your machine.

* Selenium for Python (version 3.x). The version in the software repository (2.48) is too old.
Install the latest version using `pip`:
  ```
  pip install selenium
  ```

* Chromium Chromedriver (version 2.35 or later):
  ```
  sudo apt install chromium-chromedriver
  ```

## Usage
The script `pmm_release_mail` currently uses hard-coded URLs and user credentials. The URL to
Personal Message Manager is valid for ASTRON. The only two lines that need to be modified are
those that define `USERNAME` and `PASSWORD`. Note that `USERNAME` should contain your 
*email address*. 

You can simply run `pmm_release_mail` from the command-line, but you benefit
most of it when you create a `cron` job that will run the script at regular intervals.

## How it works
The script uses Selenium, which automates web browsers, and Chromedriver which provides a 
head-less Chromium browser. The names of the fields to be filled in and the buttons to be
pushed were retrieved by using the my browser's *Developer Tools*.

## Known bugs
* The current version of the script does not handle multiple pages of messages. So if you have
  a lot of quarantined messages, then only the messages on the first page will be released.

## TODO
* Provide a command-line interface to specify username, password, and possibly the URL to PMM.
