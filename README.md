# CliGPT

## Description

A bash script that use chatGPT api

## Required Dependencies

-   `jq`
-   `bat`

Make sure these dependencies are installed before using CliGPT.

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

3. Add your API key to `~/.config/cligpt/.env`:

```bash
API_KEY=your-api-key
```

## Usage

```
Usage : cligpt [option] [text]

Option :
-h or --help ........................... Show help
-v or --version ........................ Show version
-l or --list ........................... List all available model
-m or --model <model> .................. Select model (default : gpt-3.5-turbo)
-t or --temp <temperature> ............. Set temperature (default : 0.7)
-s or --system [text] .................. Instruction with role system (use "-" for stdin)
-c or --clear .......................... Clear history
-L or --list-history ................... List history
-i or --inerte ......................... Do nothing except saving prompt in history

Example :
cligpt # Interactive mode
cligpt "some prompt with role user"
cat somefile.txt | cligpt -s - # Instruction mode
cat somefile.txt | cligpt -s - "some prompt with role user"
cligpt -s "some prompt with role system" "some prompt with role user"
```

## Integration with tmux

```
bind H new-window "cligpt" \; rename-window "cligpt"
```

## FAQ

### How do I get my ChatGPT API key?

To get a ChatGPT API key, you need to sign up on the OpenAI website and follow the instructions to create an account and obtain an API key.

## Example

[![asciicast](https://asciinema.org/a/568168.svg)](https://asciinema.org/a/568168)
[![asciicast](https://asciinema.org/a/568170.svg)](https://asciinema.org/a/568170)
