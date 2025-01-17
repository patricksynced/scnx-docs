---
sidebar_position: 1
---

# Bots on SCNX

This documents contains guides applicable for both the [Custom Bot](../../custom-bot/intro) and
the [Modmail Bot](../../modmail/intro) - if you want to set up these bots, follow
the [Get started with Custom Bot](../../custom-bot) or the [Get started with Modmail-Bot](../../modmail) guides.

## Troubleshooting {#troubleshooting}

The steps to troubleshoot are different between the two bots. Please continue in the two different troubleshooting
guides:

* [Custom Bot](./../../custom-bot/troubleshooting)
* Modmail-Bot

## The Basics {#basics}

Each bot on SCNX is its own process running on a real, physical server. You can manage the process in your
Bot-Status-Panel of your [Modmail-](https://scnx.app/glink?page=modmail/manage)
or [CustomBot-](https://scnx.app/glink?page=bot/manage) Dashboard.

Here's an example of a Custom-Bot-Status-Panel:

![](@site/docs/assets/scnx/guilds/bots/bot-status-example.png)

As you can see, there are quite a few things you can do here. Here are the main ones you are going to need to know
about:

* "Reload configuration": When you reload your configuration, your bot will automatically apply all changes you have
  made to your configuration files (including Module-Changes) without any downtime. Generally speaking, you should use
  this rather than restarting your bot.
* "Restart bot": This restarts the process of your bot. This might take multiple minutes and involve a high downtime, in
  which your bot is unreachable. You should only restart your bot if you get asked to do this, are experiencing weird
  issues or want to [apply an update](#bot-updates).
* "Stop bot": This shuts down the process of your bot. It won't be reachable on Discord. It might take up to five
  minutes for your bot to be displayed as offline in Discord.
* "Log" / "Error log": In these Logs-Files your bot
  documents what it's doing and writes down the reason for failures or issues. Our staff (and technical experts) need
  these logs to diagnose
  problems and offer your solutions - or if they are bugs in the bot themselves - to fix them. You might get asked
  to [share them](#sharing-logs).
* Language: This is the (human) language your bot will use for any default-configuration-values and messages that can't
  be configured. Modmail might, in some cases, use the language of the user that is executing a command instead of this
  value. You can always [change the language](#bot-language) of your bot.
* Server: This is the physical server - also called Bot-Host - your bot is being hosted on. You
  can [change the Bot-Host](#bot-host) if you want.
* Branch (only available for Custom-Bots): The branch is a completely different code base for your bot. You should leave
  this on "v3" (Stable version), but can change it to the "beta"-Branch (Public beta; might be unstable).
* Version (only visible for Custom-Bots): This is a unique number identifying a published code-version. Depending on
  your version, your bot might not be able to use certain new features or take advanced of newly published releases. If
  your version is not up-to-date, you'll find a warning indicating this. Your Modmail is always up-to-date. Learn more
  about [Updates & Versions](#bot-updates).
* RAM / CPU Values: These are right below the "Online"-Status. You can safely ignore them, they are only there as a
  gimmick and show the RAM / CPU Usage of your Bot. These are irrelevant as SCNX is automatically optimizing your bot if
  it is eatin[g](https://www.linuxatemyram.com/) more RAM than it should.

### Bot-Updates {#bot-updates}

<Tabs groupId="scnx-bot-type-k">
    <TabItem value="customBot" label="Custom Bot">
        <ul>
            <li>We publish regular updates for Custom-Bots - we usually bundle a bunch of features into one release for the public version. For the <a href="#beta">beta version</a>, there are a bunch of releases, sometimes even multiple ones a day.</li>
            <li>Your Bot will send a message in your Bot-Log-Channel (if configured) when a new update is available.</li>
            <li>We'll announce every update on our <a href="https://scootk.it/dc">Discord-Server</a> and post a link to the changelog there.</li>
            <li>You can find all changelogs in your <a href="https://scnx.app/glink?page=bot/manage">Bot-Dashboard</a> and on our <a href="https://scnx.app/changelogs?branch=v3&type=CUSTOM_BOT">Changelog-Page</a>.</li>
            <li>To apply the newest version of the Custom-Bot ("upgrade"), simply restart the Bot in your <a href="https://scnx.app/glink?page=bot/manage">Bot-Dashboard</a> (updates will only apply when there's an update notice visible). Updates are always free of charge.</li>
            <li>You won't be able to use certain features if your bot is not on the latest version until you upgrade to a newer version.</li>
        </ul>
    </TabItem>
    <TabItem value="modmailBot" label="Modmail-Bot">
        <ul>
          <li>We publish regular updates for Modmail, sometimes even multiple versions a day. All updates are free of charge.</li>
          <li>Your Modmail is always running the newest version available for it.</li>
          <li>When there's a new version available, your Modmail will automatically restart to apply it.</li>
          <li>We'll announce big updates on our <a href="https://scootk.it/dc">Discord-Server</a> and post a link to the changelog there.</li>
          <li>Some small updates and bug-fixes won't be announced - your Modmail simply applies them without any commotion.</li>
          <li>You can find all changelogs in your <a href="https://scnx.app/glink?page=modmail/manage">Bot-Dashboard</a> and on our <a href="https://scnx.app/changelogs?type=MODMAIL">Changelog-Page</a>.</li>
          <li>When updating, your Modmail might be offline for a short period of time while applying database changes. This takes less than a minute and startup will continue as usual afterward.</li>
        </ul>    
    </TabItem>
</Tabs>

### Participate in Public Beta {#beta}

<Tabs groupId="scnx-bot-type-k">
    <TabItem value="customBot" label="Custom Bot">
        Before joining the public beta please keep in mind:
        <ul>
          <li>Public Beta Releases might be unstable. This means that your bot might crash or certain features might stop working without any reason.</li>
          <li>New features in Public Beta Releases might be untranslated. This means that your bot might speak English instead of a configured language in new features.</li>
          <li>While you can leave the Public Beta anytime, it might break your bot when the Beta-Version is on a higher release number than the older version. Additionally, configuration files might be corrupted after a switch-back and need to be reset, leading to data-loss.</li>
        </ul>
        Here are the steps to join the Custom-Bot-Beta:
        <ol>
          <li>Open the <a href="https://scnx.app/glink?page=bot/manage">Bot-Dashboard</a>.</li>
          <li>In the Status-Panel, click on "Change" next to the "Branch"-Setting.</li>
          <li>Select "Public Beta (might be unstable)".</li>
          <li>Confirm your change by clicking "Confirm".</li>
          <li>To receive update-notifications about Beta-Releases on our <a href="https://scootk.it/dc">Discord</a>, opt-in to the Beta-Channels in #beta.</li>
        </ol>
        Here are te steps to leave the Custom-Bot-Beta:
        <ol>
          <li>Open the <a href="https://scnx.app/glink?page=bot/manage">Bot-Dashboard</a>.</li>
          <li>In the Status-Panel, click on "Change" next to the "Branch"-Setting.</li>
          <li>Select "Stable Version (recommended)".</li>
          <li>Confirm your change by clicking "Confirm".</li>
        </ol>
    </TabItem>
    <TabItem value="modmailBot" label="Modmail-Bot">There's no public Beta-Version available for Modmail at this time. Selected users might receive access to a private beta, but generally speaking, all new features all available for everyone. Compared to Custom-Bot, we do a way more detailed Testing-Series and ensure that each release is fully stable when releasing to Modmail.</TabItem>
</Tabs>

### Change Bot-Host {#bot-host}

The Bot-Host is the physical server your bot is running on. We offer several Bot-Hosts running in different regions of
the world. Here's how to switch a Bot-Host:

1. Open the [Modmail-](https://scnx.app/glink?page=modmail/manage)
   or [CustomBot-](https://scnx.app/glink?page=bot/manage) Dashboard.
2. Next, click "Change" next to "Server" in the "Status"-Section.
3. Select the Bot-Host you want to switch to.
4. Save the changes.

<details>
  <summary>What is the difference between a Bot-Host labeled "Premium" and other Bot-Hosts?</summary>
  <ul>
    <li>Most of these Bot-Hosts are located in North America and have a faster connection to Discord's infrastructure.</li>
    <li>Premium Hosting infrastructure (higher reliability, higher bandwidth, …).</li>
    <li>Each Bot is allocated more resources.</li>
    <li>Premium Bot-Hosts are configured to take twice as many backups and store them offsite than other Bot-Hosts.</li>
  </ul>
</details>

<details>
  <summary>Which Bot-Host is the best? / Which Bot-Host should I choose?</summary>
  Ultimately, it doesn't matter (except for the Premium-Servers). Each Bot-Host is designed to host bots, just like yours. We have high-quality standards for each of the hosts and can guarantee the same experience on each of them. We might even move your bots around if you do not have a paid plan to distribute resources.
</details>

<details>
    <summary>I was asked to give up certain European Data Protection Rights when moving my bot outside the EU</summary>
    When you move your bot's data outside the European Union, the General Data Protection Regulation won't apply to your data anymore. This is only affecting your bot's data, like Leveling-Stats, configuration and the actual hosting of the bot. Please also keep in mind that Discord themselves
    are also storing most of their data outside the EU, and we only work with trusted hosting providers with high-security & privacy standards; the data protection laws of the country will apply. This sometimes means that we are unable to protect your data from being used / inspected by state agencies. 
    As is legal requirement (at least for our EU customers ♥), you have to agree to such data transfer. You can always switch back the hosting location of your bot to Bot-Host inside the EU:
</details>

### Change Bot-Language {#bot-language}

The (human) language your bot will be used for any default-configuration-values and messages that can't
be configured. Modmail might, in some cases, use the language of the user that is executing a command instead of this
value.

:::info
Changing your Bot-Language will not re-generate already generated or configured configuration files - you'll need to
either reset these files or translate fields yourself.
:::

To change the language of your bot, please

1. Open the [Modmail-](https://scnx.app/glink?page=modmail/manage)
   or [CustomBot-](https://scnx.app/glink?page=bot/manage) Dashboard.
2. Next, click "Change" next to "Server" in the "Status"-Section.
3. Select the new language you want to switch to.
4. Save the changes. Your bot will automatically restart to apply the changes.

![](@site/docs/assets/scnx/guilds/bots/change-language.png)

<details>
    <summary>The language of my server is not supported</summary>
    We're sorry to hear that your langauge is not supported by SCNX. However, we are quite a small team here at ScootKit with <i>very</i> limited resources and can currently not afford to add support for other languages except German and English.
    Feel free to reach out <a href="https://scnx.app/help">to our team</a> if you want to help translate, but please understand that we might not be able to accept your request. We'd definitely love to support every language of the world, but first we need to
    focus on our current Target-Groups.
</details>

## Remove mentions of SCNX {#offbrand}

<IncludedInPlan data={{PRO: true, ACTIVE_GUILD: false, STARTER: false}} />

You can always edit the footer of every editable message on SCNX, but you can also overwrite the default value used by
every message that is missing a configuration field or where you did not set a different footer manually.

To remove the "Powered by scnx.xyz ⚡" from *every* embed of your bot, please follow these instructions:

<Tabs groupId="scnx-bot-type-k">
    <TabItem value="customBot" label="Custom Bot">
        <ol>
            <li>Open the <a href="https://scnx.app/glink?page=bot/configuration?file=bot%7Cstrings">Messages & Appearance</a> configuration file of your bot's built in configuration.</li>
            <li>Change the "Embed-Footer" and "Embed-Footer-Image-URL" value to your liking. You can obtain an image URL in your <a href="https://scnx.app/user/files">files panel</a> - simply upload a file and click on "Copy public URL".</li>
            <li>Save the changes & restart your bot to apply these changes.</li>
        </ol>
    </TabItem> 
     <TabItem value="modmailBot" label="Modmail-Bot">
        <ol>
            <li>Open the <a href="https://scnx.app/glink?page=modmail/configuration?show=branding">Bot Branding</a> section of your Modmail's configuration.</li>
            <li>Change the "Default Embed-Footer" and "Default Embed-Footer-Image" value to your liking. You can simply upload an image if you like or remove it if not needed.</li>
            <li>Save the changes & reload the configuration your bot to apply these changes.</li>
        </ol>
    </TabItem>
</Tabs>

## Change username or Profile-Picture of my bot {#change-profile}

:::info Before you continue

* For this to work, your bot needs to be online on SCNX. If your bot is not online in SCNX, please visit
  the [troubleshooting guide](#troubleshooting).
* If you are not the owner of the server, you'll need "Manage
  Bot" [Trusted-Admin permissions](./trusted-admins#permissions) on the product you want to edit.

:::

You can change the Profile-Picture and username of your bot without ever leaving SCNX:

1. Open the [Modmail-](https://scnx.app/glink?page=modmail/manage)
   or [CustomBot-](https://scnx.app/glink?page=bot/manage) Dashboard.
2. Next, click on the username of your bot in the Bot-Status-Panel.
3. Enter the details you want to change and upload a new Profile-Picture.
4. Save the changes.

![](@site/docs/assets/scnx/guilds/bots/edit-profile.png)

<details>
    <summary>An issue occurred when I tried changing my bot's username</summary>
    <ul>
        <li>Please make sure your bot is online and running without issues. Refer to the <a href="#throubleshooting">troubleshooting guides</a> if this is not the case.</li>
        <li>Some usernames are reserved or over-used and can not be used for your bot. Try another, less common username.</li>
        <li>Uploading your image to SCNX uses your account's storage spaces. Please open your <a href="https://scnx.app/user/files">Files-Dashboard</a> and check if there's enough space left for the new Profile-Picture.</li>
        <li>You (or your bot) might be rate-limited. Please try again in 1-4 hours.</li>
        <li>You'll find the exact reason for this issue in your Bot's log. Please <a href="#sharing-logs">share your logs</a> and try finding the issue in them. If you are unsuccessful, please <a href="https://scnx.app/help">contact our staff</a>.</li>
    </ul>
</details>

## Change Bot's About me {#bot-about-me}

You can easily change the about me of your bot in the Discord Developer Portal. You can not do this on SCNX due to
technical limitations on the side of Discord.

1. Visit the [Discord Developer Portal](https://discord.com/developers/applications).
2. Select the Application of your bot. Please note that the name and picture of the application might not be the same as
   the username / profile-picture of your bot.
3. Locate the "Description" field in the "General Information"-Tab of your application.
4. Enter the About me you want to be displayed in Discord.
5. Click on "Save Changes" to apply the changes to your bot.
6. The About me will be updated in the next few hours on Discord 🎉

![](@site/docs/assets/scnx/guilds/bots/change-about-me.png)

## Invite my Bot {#invite-bot}

:::info Before you continue

* For this to work, your bot needs to be online on SCNX. If your bot is not online in SCNX, please open the "The Bot is
  not on my sever" section in the right [troubleshooting guide](#troubleshooting).

:::

:::caution
Your bot **will not work on other servers** then the server it was created for. If you want to switch to another
server, please follow the [transfer SCNX data guide](./faq#transfer) in our FAQ. If you want a bot for another
server, please first [add your server to SCNX](./../../setup) and then [set up the Custom-Bot](./../../custom-bot).
:::

1. Open the [Modmail-](https://scnx.app/glink?page=modmail/manage)
   or [CustomBot-](https://scnx.app/glink?page=bot/manage) Dashboard.
2. Next, click on the username of your bot in the Bot-Status-Panel.
3. Click on "View Invite-URL" and click on "Copy Invite-URL to clipboard".
4. Click on "Cancel".

## Sharing Logs {#sharing-logs}

Before we start, a quick explanation about Logs and why you might get asked to share them. Each bot is its own process
on SCNX, hosted on a real, physical server. As such process, it generates Log-Files. In these Logs-Files your bot
documents what it's doing and writes down the reason for failures or issues. Our staff needs these logs to diagnose
problems and offer your solutions - or if they are bugs in the bot themselves - to fix them.

:::info
Sharing your logs is a "one-time-capture" of them - they won't get updated as your bot writes new lines. Shared logs
expire 7 days after sharing. Logs don't usually contain any sensitive information, but please check them before
publishing logs publicly.
:::

:::caution
Please don't waste the time of our staff if you find something in your log. It's normal that your bot sometimes logs
issue, and we get these reported automatically. Only share them if you are experiencing an actual issue using your bot.
:::

Here's how you can share the logs of your bot:

1. Open the [Modmail-](https://scnx.app/glink?page=modmail/manage)
   or [CustomBot-](https://scnx.app/glink?page=bot/manage) Dashboard.
2. Next, click on "More options" in the Bot-Status-Panel.
3. Click on "Share your bot's logs" and then press the button "Share logs". Your Bot-Host will now upload the logs of
   your bot to [paste.scootkit.net](https://paste.scootkit.net). This might take a few seconds.
4. Copy **both** the Log-URL and Error-Log and send them **both** to our staff to investigate. If you have technical
   experience, you might also be able to use the logs to diagnose the issue yourself.

![](@site/docs/assets/scnx/guilds/bots/share-logs.png)

## Change Bot-Token {#change-token}

:::danger
You can **only** change your token in the Dashboard. **Never** send a token to another user, trusted-admins or a member
of our staff. Treat tokens like a password - users with access to your token are able to use your bot to perform
harmful actions.
:::

:::caution

* You need to be the owner of the server to change the Bot-Token.
* Changing your bot's token will **not solve any issues** you are experiencing. Please use
  the [troubleshooting guide](#troubleshooting) to diagnose and fix them like the Pro you are :wink:
* If you want to change the username or profile picture of your bot, follow [this guide](#change-profile).
* Changing your Bot's token might create new issues or complications. Please avoid changing your token if possible.

:::

You can change the token of your Bot easily without needing to delete your Bot from SCNX. Please follow these steps:

1. Open the [Discord Developer Panel](https://discord.com/developers/applications) and obtain a new token: First select
   your application, go to
   the "Bot"-Site and then click on "Regenerate token", and copy the result.
2. Open the [Modmail-](https://scnx.app/glink?page=modmail/manage)
   or [CustomBot-](https://scnx.app/glink?page=bot/manage) Dashboard.
3. Click on "More options" in the "Status"-Panel of your bot.
4. Click on "Change Bot-Token".
5. Enter your new Bot-Token and confirm it by pressing "Change token".
6. Your token will be saved and your bot will restart to apply the changes.

![](@site/docs/assets/scnx/guilds/bots/change-token.png)

If your bot is not working afterward, please follow the [troubleshooting guide](#troubleshooting).

## Delete Bot {#delete-bot}

:::danger

Deleting your Bot is irreversible and does not only delete your configuration, it also removes data (like
Leveling-Stats, or Ticket-Data).

:::

:::caution

* You need to be the owner of the server to delete a bot.
* Deleting your bot will, most likely, **not solve any issues** you are experiencing. Please use
  the [troubleshooting guide](#troubleshooting) to diagnose and fix them like the Pro you are :wink:
* If you want to change the username or profile picture of your bot, follow [this guide](#change-profile).

:::

We're sorry that you want to leave SCNX - if you are only experiencing an issue with SCNX, we
are [happy to help](https://scnx.app/help) on our [Discord](https://sc-net.work/dc).

To permanently delete your bot, please follow these instructions:

1. Open the [Modmail-](https://scnx.app/glink?page=modmail/manage)
   or [CustomBot-](https://scnx.app/glink?page=bot/manage) Dashboard.
2. Next, click on "More options" in the Bot-Status-Panel.
3. Select "Delete a bot".
4. You'll be asked to select a reason (you won't need to elaborate) for deletion. Next, start your request using the "
   Initiate Bot-Deletion request"-Button.
5. You'll receive a DM to confirm your deletion request. Use the button below the message to execute the data deletion.
6. After confirming, our system will delete your bot from SCNX. This might take 1-5 minutes.
7. You'll receive confirmation once we've deleted your bot from SCNX.