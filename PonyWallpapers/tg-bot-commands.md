# Simple commands for Telegram bot

_`###BOTTOKEN###` and `###CHATID###` are variables witch have to be changed before running_

* `https://api.telegram.org/bot###BOTTOKEN###/`  
	You put commands after `/`.

* `https://api.telegram.org/bot###BOTTOKEN###/getUpdates`  
	See recent messages sent to your bot by tg users.

* `https://api.telegram.org/bot###BOTTOKEN###/sendMessage?chat_id=###CHATID###&text="Hello%20World!"`  
	Send `"Hello World!"` message to specified chat.

* `https://api.telegram.org/bot###BOTTOKEN###/sendMessage?chat_id=201942014&text=>>1`  
	Send `>>1` message to specified chat.

* `https://api.telegram.org/bot###BOTTOKEN###/sendPhoto?chat_id=###CHATID###&photo=https://derpicdn.net/img/2015/12/10/1040710/tall.png&caption=https://derpibooru.org/1040710`  
	Sends image that is under https://derpicdn.net/img/2015/12/10/1040710/tall.png with caption "https://derpibooru.org/1040710" to specified chat.
