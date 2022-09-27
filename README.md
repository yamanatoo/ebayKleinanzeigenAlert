# ebayKleinanzeigenAlert - (ebAlert)
Small CLI program that will send you a Telegram message for every new posts on the specific links of the Ebay Kleinanzeigen website. 

No API required - Only URL of the query.

## Install

1. Clone this repository
   ```sh
   git clone https://github.com/vinc3PO/ebayKleinanzeigenAlert
   ```
2. Navigate to the cloned repository
   ```sh
   cd ebayKleinanzeigenAlert
   ```
3. Create a Telegram Bot
   1. Open the chat with [@BotFather](https://t.me/BotFather)
   2. Enter `/newbot`
   3. Enter the name of your Bot (e.g. eBay Kleinanzeigen Bot)
   4. Enter a unique username for your bot (e.g. my_ebay_kleinanzeigen_bot)
   5. Copy the token
4. Get you Telegram Message ID
   1. Open the chat with [@RawDataBot](https://t.me/RawDataBot)
   2. Copy the message ID. Either from `message/from/id` or `message/chat/id`. The message ID looks like `417417807`.
5. Edit `ebAlert/core/config.py` and insert your token & message ID.
6. Install dependencies
   ```sh
   pip install .
   ```
7. Run the `ebAlert` CLI
   ```sh
   python -m ebAlert
   ```

You can also watch [this](https://www.youtube.com/watch?v=lAqDkUdGKy0) YouTube tutorial (in German) on how to setup this CLI and configure it with `crontab`.

## Usage & Example
* ```ebAlert links [opts] ``` to show, add, remove links
* ```ebAlert links --help ``` to get list of options for the links
  
* ```ebAlert start``` to start receiving notification


* ```ebAlert links -a "https://www.ebay...k0l9354r20"```  This assumes that you just had a look through the web page already, so no notification will be send. 
* Typically, this would be run as a cron job on an hourly basis.

## Requirements
* A telegram bot API token and your personal conversation id
* Python 3
* click, requests, bs4 and sqlalchemy (arguably sqlalchemy is a little overkill for that purpose)

## ChangeLog
 1.0 -> 1.1
* Refactoring
* Removing most of the data added to database as it was not used
* Move to SQLalchemy 1.4
* Adding testing suite
* Better handling of special characters that messed up the telegram message
* Preparing for multiple chat id

 0.6 -> 1.0
* Refactoring.
* Add TOKEN and CHAT_ID taken from environment variable. 
* Fix title and city and distance if so.
* Update telegram message.  

## Future Plans

* add functionality to add links directly via telegram.

## Development Branch

** dev_telegram **
* Bot data stored in the database
* Multibot allowed
* Possibility to choose towards which bot goes which notification
* Docker

## Featured German Tutorial
From dandud100

https://youtu.be/lAqDkUdGKy0