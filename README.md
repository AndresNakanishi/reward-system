<!-- For later
implement badges
 -->

# Reward System

<!-- <img width="1758" alt="turbo2" src="https://user-images.githubusercontent.com/51714798/213819392-33e50db9-3e38-4c51-9a22-03abe5e48f3d.png">
 -->

Introducing the perfect companion for your Discord community! 💻🚀 This reward calculation bot is the ultimate tool for those seeking recognition for their contributions. From small code tweaks to large collaborative projects, this bot is equipped to calculate and display the rewards deserved for each contribution. ⚙️💰 With its precision and speed, this bot will make your creators feel valued and motivated to keep working in the community. Don't wait any longer to add it to your Discord server and give your members the gratification they deserve! 💯💪

<!-- Add an image here if you have one that showcases the bot in action -->

## Table of Contents

- [Prerequisites](#prerequisites)
- [Project File Tree](#project-file-tree)
- [Installation](#installation)

  - [Run the Main Project](#run-the-main-project)
  - [Run the Bot](#run-the-bot)

- [Quick Start](#quick-start)
  - [Setup .ENV](#setup-env)
  - [Configure DB (SUPABASE)](#configure-db-supabase)
  - [Configure DISCORD BOT](#configure-discord-bot)
  - [Configure DISCORD KEYS](#configure-discord-keys)
  - [Configure Discord WEBHOOKS](#configure-discord-webhooks)
- [How can I contribute?](#how-can-i-contribute)
  - [Join Our Community](#join-our-community)
  - [Read the Contribution Guidelines](#read-the-contribution-guidelines)
- [License](#license)

# Getting Started

## Pre-requisites

Before you start, make sure you have the following:

- [Node.js version 16 or higher](https://nodejs.org/en)
- [pnpm package manager](https://pnpm.io/)
- [Discord account for bot development and testing](https://discord.com/)

## Project File Tree

```
.github
  └─ workflows
        └─ CI with pnpm cache setup
.vscode
  └─ Recommended extensions and settings for VSCode users
apps
  ├─ bot
  |   ├─ Node
  |   ├─ Discord JS
  |   ├─ tRPC Client
  |   └─ TypeScript
  └─ next.js
      ├─ Next.js 13
      ├─ React 18
      ├─ Tailwind CSS
      └─ E2E Typesafe API Server & Client
packages
 ├─ api
 |   └─ tRPC v10 router definition
 ├─ auth
     └─ authentication using next-auth. NOTE: Only with Discord
 └─ db
     └─ typesafe db-calls using Prisma
```

<div align="right">

[ [ ↑ to top ↑ ] ](#reward-system)

</div>

# Installation

As the project uses Turborepo, you could run the following commands on the root, and it will run every inner same command.

## Run the Main Project

1. Install the project dependencies by running `pnpm install`.
2. Build the project by running `pnpm build`.
3. Start the project by running `pnpm dev`.

> **Note** `pnpm dev` will run discord and nextjs project

<div align="right">

[ [ ↑ to top ↑ ] ](#reward-system)

</div>

## Usage

To get it running, follow the steps below:

### Setup .ENV

```
DATABASE_URL="your_database_url"

NEXTAUTH_SECRET="your_nextauth_secret"
NEXTAUTH_URL="your_localhost."

DISCORD_CLIENT_ID="your_client_id_here"
DISCORD_CLIENT_SECRET="your_client_secret_here"
DISCORD_BOT_TOKEN="your_bot_token_here"
DISCORD_WEBHOOK_URL="your_discord_server_webhook_url"

```

<details>
<summary>Explanation of Required Environment Variables for Discord OAuth2 and Bot Authentication</summary>
<br/>

These are environment variables that you need to set in order to use Discord's OAuth2 API and to authenticate your bot with Discord.

- `DATABASE_URL:` This is the URL for your database. You need to replace it with the actual URL for your database.

- `NEXTAUTH_SECRET:` This is a secret key used by NextAuth.js for secure session cookies and CSRF protection. You should generate a new secret key and replace it with the placeholder.

- `NEXTAUTH_URL:` This is the URL for your application. Replace it with the actual URL where your application will be hosted.
- DISCORD_CLIENT_ID: This is the client ID of your Discord application. You can get it from the Discord Developer Portal.

- `DISCORD_CLIENT_SECRET:` This is the client secret of your Discord application. You can get it from the Discord Developer Portal.

- `DISCORD_BOT_TOKEN:` This is the bot token for your Discord bot. You need to create a bot in the Discord Developer Portal and get the token from there.

- `DISCORD_WEBHOOK_URL`: This is the webhook URL for your Discord server. You can create a webhook in your server settings and get the URL from there.

</details>

### Configure DB (SUPABASE)

To use Supabase as your database provider, you'll need to create a new project in Supabase and obtain your connection string URI. Here's how:

1. Create a new project in Supabase.
2. In your project, go to Settings -> Database.
3. Under the "Connection" tab, copy the Connection string (URI).
4. In your project, create a .env.local file at the root of the project folder.
5. In the .env.local file, set the DATABASE_URL variable to your Supabase connection string URI.

For more details on setting up your Supabase database, check out the Supabase
[documentation.](https://supabase.com/docs/guides/database/overview)

### Configure DISCORD BOT

1. [Go to the Discord Developer Portal](https://discordapp.com/developers/applications/).

<details>
<summary>
2. Create a New Application.
</summary>

![Application](https://res.cloudinary.com/dwtba7bmh/image/upload/v1678755937/o1vaqzbm7f6tozark9yo.png 'Application')

</details>

<details>
<summary>
3. Your next step is to go over the menu on the left side of the screen and click “Bot”.
</summary>

![Bot](https://res.cloudinary.com/dwtba7bmh/image/upload/v1678756136/pwgtlao3pd9evqedtnxm.png 'Bot')

</details>

<details>
<summary>
4. Now you want to click the blue “Add Bot” button.
</summary>

![Add Bot](https://res.cloudinary.com/dwtba7bmh/image/upload/v1678756280/wcr0nny5wdcd8fovf768.png 'AddBot')

</details>

5. Click the “Yes, do it!” button…

<details>
<summary>
6. You’ll also see a “Token” and a blue link you can click called “Copy”.
</summary>

![Token](https://res.cloudinary.com/dwtba7bmh/image/upload/v1678756280/x3f9nk65tq5szib6jb22.png 'Token')

</details>

`DISCORD_BOT_TOKEN="YOUR_TOKEN"`

7. Add Your Bot to a Discord Server

<details>
<summary>
8. In order to add your bot to your Discord Server, you’ll need to navigate back to the “OAuth2” "URL GENERATOR" tab.
</summary>

![Token](https://res.cloudinary.com/dwtba7bmh/image/upload/v1678759651/pw1svnypnnbvbt0ceczt.png 'Token')

</details>

<details>
<summary>
9. In the “Scopes” section, you’ll want to select the “bot” checkbox.
</summary>

![Token](https://res.cloudinary.com/dwtba7bmh/image/upload/v1678759632/ntra1xoyhye5r3tixy9c.png 'Token')

</details>

10. “Bot Permissions” section. This is where you choose what permissions to give your bot, and what it can and can’t do.

11. After you’ve selected your permissions, scroll up a little bit and look at the URL that was generated.

12. Click the blue “Copy” button on the right side. This is the URL you’ll navigate to in order to add your bot to a server.

### Configure DISCORD KEYS

1. Navigate to the "OAuth2" section in the Discord Developer Portal and select the "GENERAL" tab.

<details>
<summary>
2. Under the "CLIENT ID" section, copy the client ID.
</summary>

![Token](https://res.cloudinary.com/dwtba7bmh/image/upload/v1678759900/qxbzfxoseuesr8eza5ic.png 'Token')

</details>

`DISCORD_CLIENT_ID="1xxxxxxxxx"`

3. Click the blue “Reset Secret” button.

4. Click “YES” button.

5. You’ll also see a “Token” and a blue link you can click called “Copy”.

`DISCORD_CLIENT_SECRET="SECRET_TOKEN"`

These steps will configure your Discord keys and enable your application to access the Discord API. If you need additional help, consult the Discord Developer Documentation or contact Discord support.

### Configure Discord WEBHOOKS

1. Go to your Discord server where you want to add the webhook.

<details>
<summary>
2. Click on the channel where you want to send the webhook messages.
</summary>

![channel-webhook](https://user-images.githubusercontent.com/14036522/229307261-8dee4db1-37b1-49ce-a450-645e1bd25a6f.gif)

</details>

<details>
<summary>
3. Click on the settings icon and select "Integrations".
</summary>

![Discord_MkqQdiBzb7](https://user-images.githubusercontent.com/14036522/229307265-81d6071c-9bb1-4d15-a3d4-b048ed5ecf2d.gif)

</details>

<details>
<summary>
4. Click the "Create Webhook" button and enter the webhook name and select the channel you want to send messages to.
</summary>

![webook](https://user-images.githubusercontent.com/14036522/229307263-3347e9f8-9ec6-4e7d-9d90-1b271cdc0341.gif)

</details>

5. Copy the webhook URL and set it as an environment variable in your project:

6. DISCORD_WEBHOOK_URL="https://discord.com/api/webhooks/your_webhook_id/your_webhook_token"

7. Save the changes and restart your server to make the changes take effect.

<div align="right">

[ [ ↑ to top ↑ ] ](#reward-system)

</div>

# How can I contribute?

We welcome contributions from anyone who would like to help improve our project. Whether you're an experienced developer or just starting out, there are plenty of ways to get involved.

## Support

If you need help using our project, please visit our [SUPPORT.md](./docs/SUPPORT.md) file. This document provides information on how to get help from the community, how to report issues, and where to find additional resources.

## Join Our Community

Join our [Discord](https://.discord.gg/77guznJ8mZ) community to connect with other contributors and get help from the maintainers. This is a great place to ask questions, get feedback on your ideas, and collaborate with others on the project.

## Read the Contribution Guidelines

Before you start contributing, please read our [CONTRIBUTING.md](./docs/CONTRIBUTING.md) file. This outlines the contribution guidelines and provides instructions for setting up your development environment, submitting pull requests, and more.

We appreciate all contributions, big and small. Thank you for helping to make our project better!

## Security

We take the security of our project seriously. If you discover a security vulnerability, please let us know right away. We will investigate all legitimate reports and do our best to quickly address any issues.

To learn more about our security practices, please read our [SECURITY.md](./docs/SECURITY.md) file.

## License

[MIT License](./LICENSE)

## References

The stack originates from [create-t3-app](https://github.com/t3-oss/create-t3-app).

A [blog post](https://jumr.dev/blog/t3-turbo) where I wrote how to migrate a T3 app into this.

Test the Github GraphQL schema [**here**](https://studio.apollographql.com/public/github/explorer?variant=current)

---

<h2 id="contributors">Contributors</h2>

<a href="https://github.com/serudda/reward-system/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=serudda/reward-system" />
</a>

Made with [contrib.rocks](https://contrib.rocks).

<div align="right">

[ [ ↑ to top ↑ ] ](#reward-system)

</div>

---

**Folow us at**

<a href="https://github.com/Indie-Creator-Community">
<img src="https://img.shields.io/badge/IndieCreatorsHQ-FAFF00?style=for-the-badge&logo=github&logoColor=black">
</a>
<a href="https://.discord.gg/77guznJ8mZ">
<img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white">
</a>
<a href="https://twitter.com/IndieCreatorsHQ">
<img src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white">
</a>

---
