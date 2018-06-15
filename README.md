### Salvator: The Saviour, When You Forget Birthdays

## What is Salvator?
Salvator is a bot which uses puppeteer to scrape the list of birthdays from facebook and sends them a personal
message.

It also sends the user an email notification with the list of birthdays and their profile link.

## How does it work?
Puppeteer uses a headless browser to navigate to `facebook.com/login` and using the credentials from the `.env` file,
logs in. There after it navigates to the birthday events page, scrapes the profile links for birthday people, forms
the messenger link using it and sends them a personalised message.<br/>
E.g `Hey thealphadollar! Happy Birthday :D`, if user's first name is "thealphadollar".

## Install
Salvator can be installed using npm or source.

### Install using npm
1. [Install npm](https://www.npmjs.com/get-npm)
2. `npm install -g puppeteer-salvator`

### Build using source (RECOMMENDED)
1. `git clone https://www.github.com/thealphadollar/salvator`
2. `cd salvator`
3. [Install npm](https://www.npmjs.com/get-npm)
4. `npm install` (this step installs all the dependencies)

## Using Salvator
The following environment variables must be set to avail full functionality of the client:
```$xslt
FB_ID=<your login email/phone for facebook>
FB_PASS=<your login password for facebook>
EMAIL=<notification will be sent from this address>
EMAIL_PASS=<password for the email>
MAILTO=<notification will be sent to this address>
```

You can also create a `.env` file in the `salvator` folder with the above mentioned environment variables.

Salvator can be launched manually using the commands,
- `puppeteer-salvator`, if installed from npm
- `node.js index.js`, from source directory

However, it is recommended to [add a cronjob](https://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/) to automatically launch the client at the desired time, 
favorable 00:05 hours. By this time facebook updates the list of birthdays and hence you could be among the first to
 wish.
 
## Contributing
Contributions are welcome, please look [here](www.github.com/thealphadollar/salvator/issues) for issues to work on.