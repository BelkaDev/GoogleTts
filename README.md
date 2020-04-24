## GoogleTts

Google Text-to-speech and translation tools from the comfort of your command line.
Wow very cool! </br>
![doge](https://github.com/BelkaDev/GoogleTts/blob/master/src/wow.jpg)</br>

### Requirements

[`jq` ](https://github.com/stedolan/jq) </br>
[`xclip` ](https://github.com/astrand/xclip) (optional)

### How to install?
```
git clone https://github.com/BelkaDev/GoogleTts.git ~/Tts && cd ~/Tts
chmod +x *
copy both scripts to your $PATH directory
```
### Features 
* Cli text to speech or textual translations
* Language selection and automatic detection
* Real-time translation and cross-language speech 
* Word filtering and pattern changes
* Read highlighted text

### How to use?
**Text-to-speech**
* `-a, --auto` for auto-detection mode. </br>
	* `-a "こにちわ"` will read in Japanese</br>
	* `-a "hola"` will read in Spanish
* `-t, --translate <lang>` to translate and read </br>
	* `-t "こにちわ"` will translate to default language and read.
	* `-t de "こにちわ"` will translate to German and read.
* `-l, --language <lang>` to change the language </br>
	* ` -l es "hi" ` reads input in Spanish voice
</br>
<u><i>Notes</i></u></br>
 All options can be specified on runtime or set up </br>
by default in the settings, accepted values 
are `true` , `false` </br> for boolean attributes, for language codes </br>use one of valid language tags supported by Google.</br>

[The complete list can be found here](https://sites.google.com/site/opti365/translate_codes)</br></br>
Stack order follows this order: language>auto>translate</br>
Meaning the highest will always dismiss the others.</br>
`-l en -t こにちわ` will not perform translation.</br>
</br>
If no text input is given, current selection (highlighted text),</br>
is processed, this requires an X environement. </br>
When run on terminal, double quotes must wrap the input.</br></br>

**Translation**</br>
*the translation script can be used independently, but not the other way around*</br>*most broad syntax is as follows:* </br>
`translate [from <source> to <target> <text>]` </br>
Each parameter can be ommited, in that case automatic values are considered.</br> examples:</br>
`translate to ko "hello"`: detects language and translates to Korean</br>
`translate from fr "bonjour"`: translates from French to default language</br>
`translate`: translate selection from detected language to default language

Output format contains synonyms and examples and is made easy to parse using pipes. </br> </br>
![output](https://github.com/BelkaDev/GoogleTts/blob/master/src/output.jpg)

* parse translation:` | grep -w "translation" | cut -f2 -d ":"`
* parse source language:` | grep -w "source_lang" | cut -f2 -d ":"`
</br>


### Extra

* A set of patterns can be configured to ignore undesirable/irrelevant words or replace specific sequences. As all options it can be changed at the top of the file, it follows this structure </br>
`{ "sequence" ; "alternative", ...}`</br></br>
Setting up an empty string will ignore the corresponding sequence. (option is disabled by default.) 

* Audio files can be stored in the directory of your choice.

### To do:
Todo: feed files or web urls to the script

### Known issues
All parameters should be interchangeable, but this can lead to unexpected results if they get mixed up.</br>
Encoding erros: some characters may cause the script to fail.

