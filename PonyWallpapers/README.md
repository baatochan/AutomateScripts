# Pony Wallpapers
All the scripts connected with sending MLP wallpapers to telegram.

## Some background
I'm running [Muzei](https://github.com/romannurik/muzei) app as a wallpaper with [Muzei Ponies](https://github.com/berwyn/muzei-ponies) as a source. It's set to download a new image from [Derpibooru](https://derpibooru.org/) every hour. Some of those images are pretty neat and it would be nice to have a simple way to share them to telegram where I chat with all my friends.

BTW the images are searched on Derpibooru with this query:
```
safe, score.gte:200, -transparent background, -monochrome,  -comic, -twitter, -oc:anon, -vulgar, -artist:badumsquish, -impossibly wide hips, -them's fightin' herds, -obese, -morbidly obese, -impossibly large belly, aspect_ratio:0.5625~0.3
```

The idea was started by [@Macter4][GitHub Macter4] who set up script for sharing every single wallpaper. At the beginning I've just wanted to use exact copy of [@Macter4's][GitHub Macter4] script, but his script needs premium version of [Automate](https://llamalab.com/automate/) which I don't have yet. So I thought that it should be possible to make it shorter as it's enough for me to share only those I like via pressing a button (manually running a script). And it turns out it IS possible.

## Why two scripts?
There are two version of the script:
* The simple one `sendID.flo` which sends `>>ImageID` message to my personal chat with my bot and then that message can be forwarded to [BonBot](https://t.me/bonbot) which will download the image (or forwarded to the group with BonBot).
* The second one `sendWallpaper.flo` which sends the picture message via a tg bot. Can send messages to private chats with bot, channels or groups.

Both of them works perfectly fine on free version of Automate.

## How does it work?
Both of the scripts need to get the derpibooru image ID from Muzei somehow. While Muzei doesn't provide any way to get it I had to unlock showing notifications and get the ID from the notif. After that the notif gets dismissed as I really hate to have cluttered notifications on Android.

When the script have the ID the next step depends on the script version.

The simple one takes this ID, removes the following `#` sign with `>>` and sends it as a message to my private chat with the bot.

The more advanced one takes this ID, sends request to the Derpibooru API, extracts the image URL from the response and sends a picture to the specified chat with URL to the derpibooru post (different than the image URL) as a caption.

## How to set it up?
* Install [Muzei](https://github.com/romannurik/muzei).
* Install [Muzei Ponies](https://github.com/berwyn/muzei-ponies).
* Set up Muzei Ponies as a source for Muzei, set searched query to the desired one and set Muzei as a live wallpaper.
* Install [Automate](https://llamalab.com/automate/).
* Get your telegram bot:
	* Go to the [BotFather](https://t.me/BotFather).
	* Create a new bot.
	* Save your bot token.
* Get the ID of your private chat with the bot (if you want to send the wallpapers to different chat just Google how to get the chatID):
	* Open the private chat.
	* After starting the bot send any message (really it can be anything eg. `/my_id`).
	* Run getStatus command via your browser (some basic queries are in [tg-bot-commands.md](tg-bot-commands.md)).
	* Save the chat ID from the response.
* Download the script (flow) file and open it in Automate.
* Edit the script and put correct `botToken` and `chatID`.
* Run the script manually (make sure you have the notification from Muzei in the notification list, if not, ask Muzei for new wallpaper).
* Confirm that you understand the risk of using scripts from not trusted sources.
* You should get message from your bot.
* Add the widget with shortcut to running this script to your home screen (Widgets -> Automate -> Flow beginnings)

Now you can customize the script as you wish. For debugging purposes the `Log` block is very useful.

[GitHub Macter4]: https://github.com/Macter4
