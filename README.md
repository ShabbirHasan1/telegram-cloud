# Telegram-cloud (A.K.A tgcloud)
[![Telegram-cloud](https://github.com/iw4p/telegram-cloud/raw/master/images/Group.png
)](https://pypi.org/project/telegram-cloud/)


## telegram-cloud
### Searching in groups, private channel and chats, Download and upload files via telegram and Using your telegram account as free cloud storage.

[![PyPI version](https://img.shields.io/pypi/v/telegram-cloud.svg)](https://pypi.org/project/telegram-cloud)
[![Supported Python versions](https://img.shields.io/pypi/pyversions/telegram-cloud.svg)](#Installation)
[![Downloads](https://pepy.tech/badge/telegram-cloud)](https://pepy.tech/project/telegram-cloud)
[![StackOverflow](https://img.shields.io/static/v1?label=stackoverflow%20tag&logo=stackoverflow&logoColor=fe7a16&color=brightgreen&message=telegram-cloud)](https://stackoverflow.com/tags/telegram-cloud)
 [![Build demos workflow](https://github.com/iw4p/telegram-cloud/workflows/Upload%20Python%20Package/badge.svg?branch=master)](https://github.com/iw4p/telegram-cloud/actions?query=workflow%3A"Build+demos") 
[![Documentation Status](https://readthedocs.org/projects/telegram-cloud/badge/?version=latest)](https://telegram-cloud.readthedocs.io/en/latest/?badge=latest)

Uploader, Downloader, Crawler, Bot 50MB limitation bypasser. (Maybe can wash the dishes someday)

  - Upload file upto 2 GB
  - Download file from every conversation, group, channel, ...
  - Crawling! search by name or caption for a specific file to download it

You can also:
  - Use it for multiple accounts, download from one Telegram account and upload that on another account, there is no difficulty 
  - download files with file_id
  - Send regular and silent messages to any user, channel or chat

### Hmm what is this?

It's a python package for [Telegram messenger](https://telegram.org/), which can give you an ability to download, upload, and more options to do with your Telegram account on CLI.

### Installation

telegram-cloud requires [Python3](https://www.python.org/psf-landing/) and [Telethon](https://github.com/LonamiWebs/Telethon) as requirment.

```sh
$ pip3 install telegram-cloud
```
Also can be found on [pypi](https://pypi.org/project/telegram-cloud/)
### How can I use it?
  - install the package by pip package manager.
  - after installing, type `tglogin` on your terminal
  - Now you need to get api_id and api_hash from here [Telegram](https://my.telegram.org/)
  from [Telethon document](https://docs.telethon.dev/en/latest/basic/signing-in.html):
    >Before working with Telegram’s API, you need to get your own API ID and hash:
    [Login to your Telegram](https://docs.telethon.dev/en/latest/basic/signing-in.html) account with the phone number of the developer account to use.
    Click under API Development tools.
    A Create new application window will appear. Fill in your application details. There is no need to enter any URL, and only the first two fields (App title and Short name) can currently be changed later.
    Click on Create application at the end. Remember that your API hash is secret and Telegram won’t let you revoke it. Don’t post it anywhere!
  - After that you able to call `tgcloud` on your terminal.
  
### Commands

telegram-cloud is currently working with the following commands. 

| args | help |
| ------ | ------ |
| --mode / -m | Two modes for specify what you want, Available modes: download - upload |
| --name / -n | A Name you choose while tglogin-ing and use for specify the current user you work on it |
| --username / -u | Target username that you want to send file, type `me` if you want to get it on your `saved messages` |
| --path / -p | For download mode: pass simple directory path like "/Users/nima/Desktop/Iwanttoescapefrom/"|
| --path / -p | For upload mode: pass file path like "/Users/nima/Desktop/Iwanttoescapefrom/Iran.zip"|
| --caption / -c | For download mode: pass the name of file or caption to crawl and download|
| --caption / -c | For upload mode: write the caption to see it under your file |

tgutil accepts these arguments:

| args | help |
| ------ | ------ |
| --name / -n | A Name you choose while tglogin-ing and use for specify the current user you work on it |
| --username / -u | Target username's chat that you want to edit/delete message on it, type `me` if you want to get it on your `saved messages` |
| --mode { edit, editall, delete, deleteall }| Choose what you need to do, delete/edit last message or deleteall/editall|
| --text | the text that you are looking for to do operation on it |
| --newtext | the new text that you want to be replaced with current text, can be used for `edit` and `editall` |

tgsend accepts these arguments:

| args | help |
| ------ | ------ |
| --name / -n | A Name you choose while tglogin-ing and use for specify the current user you work on it |
| --username / -u | Target username that you want to send file, type `me` if you want to get it on your `saved messages` |
| --format { text, markdown, html }| How to parse message body. Default is `text`|
| --no-link-preview | Disable web link preview card for this message |
| --silent | Disable audible notification |
| --stdin | Read message text from stdin |

tginfo accepts these arguments:

| args | help |
| ------ | ------ |
| --name / -n | A Name you choose while tglogin-ing and use for specify the current user you work on it |
| --username / -u | Target username that you want to fetch info, type `me` if you want to get it on your `saved messages` |
| --search / -s | search specific extension or text |

### Need more examples?
Are you done with `tglogin`? so come with me.

## Unix based operating systems
`Download` a music from my `saved messages` and save it on `/Users/nima/Desktop/`:
```sh
$ tgcloud -m download -n nima -u me -p "/Users/nima/Desktop/" -c "sad but true"
```
```sh
$ tgcloud --mode download --name nima --username me --path "/Users/nima/Desktop/" --caption "sad but true"
```

`Upload` a banner with caption to my `saved messages`:
```sh
$ tgcloud -m upload -n nima -u me -p "/Users/nima/Desktop/banner.png" -c "Help me"
```
```sh
$ tgcloud --mode upload --name nima --username me --path "/Users/nima/Desktop/banner.png" --caption "Help me"
```

`Upload` a pdf to an `telegram ID`:
```sh
$ tgcloud -m upload -n nima -u @autisticbruh -p "/Users/nima/Desktop/file.pdf" -c "Help me"
```
`Search` and `download` a zip from telegram `chat_id group`:
```sh
$ tgcloud -m download -n nima -u -1001240213443 -p "/Users/nima/Desktop/" -c "best memes"
```

Send a `silent` text message to a `chat group`:
```sh
$ tgsend -n anightshade -u -1001240213443 --silent "Panda eats shoots and leaves"
```
Send a fortune cookie to yourself via `stdin`:
```sh
$ tgsend -n anightshade -u me --stdin
```
`Search` all PDFs inside a telegram conversation:
```sh
$ tginfo -n testSession -u me -s ".pdf
```

`Edit` the last `hello` text message on your `saved message` to `bye`:
```sh
$ tgutil -n nimnim -u me --mode edit --text "hello" --newtext "bye"
```
`Edit` all `hello` text messages on your `saved message` to `bye`:
```sh
$ tgutil -n nimnim -u me --mode editall --text "hello" --newtext "bye"
```
`Delete` the last `hello` text message on your `saved message`:
```sh
$ tgutil -n nimnim -u me --mode delete --text "hello"
```
`Delete` all `hello` text messages on your `saved message`:
```sh
$ tgutil -n nimnim -u me --mode deleteall --text "hello"
```

`Get info` for all Media inside a telegram conversation:
```sh
$ tginfo -n testSession -u me
```
## not Unix (Lol I mean windows)
Just like unix but **CAREFUL** about paths, your path must not end with `\` !!
`Download` all PDFs from your `saved messages` and save it on `C:\Users\Nima\Desktop`:
```sh
$ tgcloud -m download -n nima -u me -p "C:\Users\Nima\Desktop" -c ".pdf"
```
### What is file_id?
from [Telegram Doc](https://core.telegram.org/api/files):
>When working with the API, it is sometimes necessary to send a relatively large file to the server. For example, when sending a message with a photo/video attachment or when setting the current user’s profile picture.

You can upload a file to Telegram once, and send it again to others or do things with file_id.
So when you upload a file, you can see the file_id.
So now what? If you have a Telegram bot and you have 50MB limitation for uploading and send to users, you can bypass this limitation by this trick and upload files upto 2 GB and pass it by file_id or message_id or...

### Good to know
The config file can be found on `~/.telegram-cloud/` (Also `~\.telegram-cloud\` in windows)
Each login make *.session file which is located there and it cause script for logged-in user works globally.
Inside `telegram-cloud-config.ini`, you can find api_hash and api_id and name you've entered by `tglogin` 

### To do

- [x] Send a message via cli (`tgsend`)
- [x] Delete a message via cli (`tgutil`)
- [x] Edit a message via cli (`tgutil`)
- [ ] Increasing the speed of Download and Upload
- [ ] Clean and compelete document (please help, please)
- [ ] Code is super dirty, need to be cleaned and have a good structure
- [ ] Upload and download multiple files
- [ ] Upload and download a directory
- [x] Add progress bar while downloading/uploading 
- [x] Add progress bar while downloading/uploading 

### Issues
Feel free to submit issues and enhancement requests.

### Contributing
Please refer to each project's style and contribution guidelines for submitting patches and additions. In general, we follow the "fork-and-pull" Git workflow.

 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Update the Version** in [Setup.py](https://github.com/iw4p/telegram-cloud/blob/master/setup.py)
 4. **Commit** changes to your own branch
 5. **Push** your work back up to your fork
 6. Submit a **Pull request** so that we can review your changes

NOTE: Be sure to merge the latest from "upstream" before making a pull request!

#### Python + Telethon 
 - [![Python](https://www.python.org/static/community_logos/python-powered-w-200x80.png)](https://www.python.org/psf-landing/)

 - See [Telethon](https://github.com/LonamiWebs/Telethon)

# Contributors 🤝

Special thanks to Contributors

[@anightshade](https://github.com/anightshade): For adding `tgsend` and fixing bugs!
[@anightshade](https://github.com/anightshade): For adding Command line option to select format for the file caption.
[@rany2](https://github.com/rany2): For fixing uploading path and files
[@anightshade](https://github.com/anightshade): For adding option to disable weblink preview in message 


### LICENSE
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

