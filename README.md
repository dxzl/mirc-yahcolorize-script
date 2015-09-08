# mirc-yahcolorize-script
mIRC IRC chat-client script that allows mIRC to communicate with YahCoLoRiZe

You can remotely control YahCoLoRiZe by adding some Aliases to mIRC. In mIRC, click Tools->Scripts Editor and click the Aliases tab. Copy/paste the following text to the end and click OK: 

```
rem ***************************
rem NOTE: For some old versions of mIRC, replace $1- with *1 and replace
rem $left($lower($active),6) with $left(6,$lower($active)) - Cheers!
rem ***************************
rem Usage: /CPLAY <stop|start|pause|resume|filepath>
/cplay /dde colorize command ddeplay $1-
rem Usage: /CCHAN <New Channel To Set In YahCoLoRiZe>
/cchan /dde colorize command ddechan $1-
rem Usage: /CX <My Text To Process In YahCoLoRiZe>
cx {
if ($left($lower($active),6) == status) dde colorize command ddechan status
else dde colorize command ddechan $active
dde colorize command ddetext $1-
}
```

Now you can change the chat-room with /CCHAN #new-room and send color-text with /CX my-line of chat text. You can also now use /CPLAY start|stop|pause|resume and /CPLAY <path of a text file> 

Note1: For old mIRC versions (mIRC 4.7 era), replace $1- with *1 and also replace $left($lower($active),6) with $left(6,$lower($active)) in the above script!

For additional info: http://www.yahcolorize.com/#mIRC
