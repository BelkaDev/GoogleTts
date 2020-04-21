# GoogleTts

Google Text-to-speech from the comfort of your command line.
Wow very cool!
![doge](https://raw.githubusercontent.com/BelkaDev/GoogleTts/master/doge.png)
### How to install?
```
git clone https://github.com/BelkaDev/GoogleTts.git ~/Tts && cd ~/Tts
chmod +x tts
copy the script to your $PATH directory
```
### How to use ?
` tts [ --lang|-l <language> ] <text> `
Should be given one of the valid language codes supported by Google Translate.
[The complete list can be found here:](https://sites.google.com/site/opti365/translate_codes)

### Extra
To hear the current selection:
`tts "$(echo -n $(xclip -o))"`
Bind this command and you have a systemwide text to speech, enjoy