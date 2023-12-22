# Instagram Automation with Node.js

## Overview

This Node.js script provides automation for interacting with Instagram using the [Instagram Private API](https://github.com/dilame/instagram-private-api). It covers login, profile information retrieval, and fetching user feed data.

## Features

1. **Login to Instagram**: With this script, you can automate the login process to Instagram by providing your credentials. The script utilizes the Instagram Private API to handle the authentication and login procedures programmatically.
2. **Profile Information**: The script allows you to retrieve comprehensive profile information for a specified Instagram user. This includes details such as the user's bio, profile picture, follower count, following count, and other relevant information.
3. **User Feed Data**: You can fetch and analyze the latest posts and activity from a targeted Instagram user's feed. This includes posts, captions, timestamps, and other relevant data to keep you updated on a user's recent Instagram activity.

## Prerequisites

- Node.js installed on your machine
- Instagram account credentials (username and password)
- [Instagram Private API](https://github.com/dilame/instagram-private-api) library

## Setup

1. Clone this repository to your local machine.

    ```bash
    git clone https://github.com/your-username/instagram-automation.git
    ```

2. Install dependencies.

    ```bash
    cd instagram-automation
    npm install
    ```

3. Update the script with your Instagram credentials and other relevant information.

4. Run the script.

    ```bash
    node index.js
    ```

## Usage

Customize the script according to your needs and execute it to automate various Instagram interactions.

```javascript
(async () => {
  // Set Instagram credentials
  var username = 'your-username';
  var password = 'your-password';

  // Set proxy options if needed
  const proxyOptions = {
    host: 'proxy-hostname',
    port: 80,
    username: 'proxy-username',
    password: 'proxy-password'
  };

  // Initialize InstagramLogin
  const instagramLogin = new InstagramLogin(null, username, password);
  const loginData = await instagramLogin.login();
  console.log(loginData);

  // Fetch and display profile information
  const webProfileInfo = new WebProfileInfo(loginData, null, "target-username");
  const profileData = await webProfileInfo.getProfileData();
  console.log(profileData);

  // Fetch and display user feed data
  const userFeed = new UserFeed(loginData, null, "target-username");
  const userFeedData = await userFeed.getUserFeedData();
  console.log(userFeedData);
})();