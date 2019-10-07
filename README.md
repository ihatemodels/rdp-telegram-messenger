# rdp-telegram-messenger

**The script is used to send a telegram message when a new rdp connection is established to host/server**

> **Аfter 1 hour of headache and trying different methods, I decided to create the repo**

## Credits: 
**:point_down:**
**[StackOverFlow](https://stackoverflow.com/questions/32423837/telegram-bot-how-to-get-a-group-chat-id)**

## Set-Up 

### Create a telegram account

> **Send "/start" to the @BotFather**
> **Click on /newbot**
> **Set a bot-name**
> **Send "/token" to the @BotFather**
> **Copy your bot token**

### Create a new telegram group
- **@my_bot refers to your bot name**
> **Add the newly created bot to the group**
> **Send "/my_id @my_bot" to the newly created bot**
> **Send "/my_id @my_bot" to the newly created group**
> **visit https://api.telegram.org/botPASTER-YOUR-BOT-TOKEN-HERE/getUpdates**
> **Look for "chat":{"id":-zzzzzzzzzz**
    *-zzzzzzzzzz is your chat id (with the negative sign).*

### Clone the repo move the script in C:\Where-You-Want

```git
git clone https://github.com/ihatemodels/rdp-telegram-messenger
```
```powershell
Set-Location -Path .\rdp-telegram-messenger\
```
**Open your favourite text editor**
**--> Edit line 10 and 11 with your "chatId" and botId**

```powershell
Move-Item rdp-telegram.ps1 C:\Where-You-Want
```

### Establish an RDP connection to the machine 
### Open Event Viewer
> GOTO: -> Applications and Services Logs -> Microsoft -> Windows -> TerminalServices-RemoteConnectionManager -> Admin
> The last event with a **ID=20521** is the rdp connection
> Right-Click on the event - **Select attach task to this event**

### Set-Up The Task
- **In Create a Basic Task:** 
        Name: Set your task name
- **In Action**
        Program/Script: **powershell**
        Add arguments(optional): **The path to rdp-telegram-messenger** "C:\rdp-telegram-messenger.ps1"
- **Save tthe task**

### Happy Messegaes
