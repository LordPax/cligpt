# CliGPT

## Description

A bash script that use openai api to generate text, image and speech.

## Required Dependencies

**general dependencies**

* `jq`
* `bat`
* `curl`
* `base64`

**speech dependencies**

* `pacat`

## Installation

1. Clone the repository:

```bash
git clone https://github.com/LordPax/cligpt.git
cd cligpt
```

2. Execute the script to generate config file in `.config/cligpt`

```bash
./cligpt
```

3. Add your API key to `~/.config/cligpt/config`:

**Example**

```bash
API_KEY=your-api-key
API_ROUTE=https://api.openai.com/v1
TEXT_MODEL=gpt-4
TEXT_TEMP=0.7
IMAGE_MODEL=dall-e-3
IMAGE_NB=1
IMAGE_SIZE=1024x1024
SPEECH_MODEL=whisper-1
SPEECH_LANG=fr
```

## Usage

* main help

```
Usage : cligpt [option] [command]

Option :
-h or --help ........................... Show help
-v or --version ........................ Show version
-l or --list ........................... List all available model
-i or --inerte ......................... Do nothing except saving prompt in history

Command :
text ................................... Generate text
image .................................. Generate image
speech ................................. Generate text from speech
```

* text help

```
Usage : cligpt [generalOption] text [option] [prompt]

Option :
-h or --help ........................... Show help text command
-m or --model <model> .................. Select model (default : gpt-4)
-t or --temp <temperature> ............. Set temperature (default : 0.7)
-s or --system [text] .................. Instruction with role system (use "-" for stdin)
-c or --clear .......................... Clear history
-l or --list-history ................... List history

Example :
cligpt text # Interactive mode
cligpt text "some prompt with role user"
cat somefile.txt | cligpt text -s - # Instruction mode
cat somefile.txt | cligpt text -s - "some prompt with role user"
cligpt text -s "some prompt with role system" "some prompt with role user"
```

* image help

```
Usage : cligpt [generalOption] image [option] <prompt>

Option :
-h or --help ........................... Show help image command
-m or --model <model> .................. Select model (default : dall-e-3)
-n or --nb <number> .................... Number of image to generate (default : 1)
-s or --size <size> .................... Size of image (default : 1024x1024)
-o or --output <name> .................. Get image in file

Size :
- 256x256
- 512x512
- 1024x1024
- 1024x1792
- 1792x1024

Example :
cligpt image "some prompt with role user"
cligpt image -o image.png "some prompt with role user"
```

* speech help

```
Usage : cligpt [generalOption] speech [option] [file]

Option :
-h or --help ........................... Show help speech command
-m or --model <model> .................. Select model (default : whisper-1)
-l or --lang <language> ................ Select language (default : fr)

Example :
cligpt speech # record audio and generate text
cligpt speech somefile.mp3
```

## Integration with tmux

```
bind H new-window "cligpt text" \; rename-window "cligpt"
```

## Vim plugin

```vim
Plug 'LordPax/vim-cligpt'
```

## FAQ

### How do I get my OpenAI API key?

To get an OpenAI API key, you need to sign up on the OpenAI website and follow the instructions to create an account and obtain an API key.

## Example

[![asciicast](https://asciinema.org/a/568168.svg)](https://asciinema.org/a/568168)
