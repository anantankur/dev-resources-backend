# Rusty's Resources - Backend
The aim of this project is to create a web app that will display all of the student submitted resources, from the #dev-resources channel and potentially other channels on the ZTM Discord server. A Discord bot will be responsible for automatically adding new resources to a database, with the possibility of manually triggering the addition of new resources from other channels.

- [Front-End Repo](https://github.com/zeroDevs/dev-resources-frontend)
- [Front-End URL](https://zerodevs.github.io/dev-resources-frontend/)
- [Back-End Repo (Discord Bot)](https://github.com/zeroDevs/dev-resources-backend)
- [Back-End API URL](https://dev-resources.herokuapp.com/)

## About The Discord Bot

![](https://img.shields.io/badge/Language-Javascript-yellow.svg?style=for-the-badge&logo=javascript)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![](https://img.shields.io/badge/module-discord.js-orange.svg?style=for-the-badge&logo=discord)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![](https://img.shields.io/badge/module-discord--passport-red.svg?style=for-the-badge&logo=npm)

An independent bot that alongside the functionality of detecting and submitting resources to the database, will provide the backend and API for the frontend to produce a feature rich resource sharing platform for the Zero To Mastery community.

### **The resources bot will be responsible for:**

#### 🔗 Automatic Link Submission 🔗
Upon automatically detecting and validating a link only in the #dev-resources channel on Discord, the bot should:

- Collect data for the link such as: Title, Description, Thumbnail and any other relevant information from the links meta data. [See this npm package](https://www.npmjs.com/package/url-metadata)
- Collect the submitters details, such as: Discord username, avatar, etc.
- Save all the data to the database
- If successfully saved, return an embed, containing the information collected. This will serve as confirmation the data was saved, and a aesthetically pleasing, unified format for sharing the resource with others. The embed should also contain a link to view it on the front-end web app. 
- If successfully saved, the users original message should be deleted. If saving failed, it should be kept and perhaps a error should be raised so it can be looked into/fixed.

---

#### ☑️ :link: Manual Link Submission ☑️
Fantastic resources are often posted in various channels around the Discord server, as the bot is only pro-actively looking to add links in the #Dev-Resources, theses resources will soon be lost. 
Therefore the bot should have a command that will do the following, when a specified emoji, is used on a message containing a link:

- Collect the links meta data (As above)
- Collect the submitters details
- Save all data to the database
- If successful, return the embed to the resources channel
- Leave the original message in tact.

---

#### ♻️ Remove Posts Without Links ♻️
Any post in the channel that does not contain a valid link, should be instantly removed from the channel and inform the user why this occurred via DM. 

---

#### 📋 API and Request Handling 📋
The bot should provide an API along with brief documentation for the front end to interact with. 
Some example Endpoint are:
- View all resources
- View selected resources
- View resources in/with category/tag
- Edit resource
- Delete resource
- Bookmark resource
- Un-Bookmark resource
- View most Bookmarked
- View Andrei's Bookmarked/Favourites
- Upvote Resource
- Downvote Resource
- View all resources sorted by upvote total

## Installation Guide
A quick start guide to installing the bot for testing on your local machine

#### Requirements
- A Discord Bot Token
- A Mongo DB

#### Getting the files
- Fork this repo
- Clone your fork to your local machine
- CD into the bots root directory
- Run `npm install`
- Copy the `/envs/.env.example` and rename it to `.env`. So you have `/envs/.env
- Open up the `./env` file and add your token (see below), your mongodb url and set a prefix.
- Run `npm start`

#### Getting a Discord Bot Token
- Head on over to https://discordapp.com/developers/applications/
- Sign in with your Discord account, if you are not already signed in
- Click the "Create an Application" card
- On the "General Information" Tab, give your bot a name and an avatar image
- Click the bot tab on the left hand side menu
- Then click "Add Bot" & confirm by clicking "Yes, Do it"

![Install Image](https://github.com/zeroDevs/RustyBot/raw/master/install.png)