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

4. Add your API key to `~/.config/cligpt/.env`:

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

Example :
cligpt # Interactive mode with a chat history
cligpt "Hello, how are you ?"
cligpt -l
```

## Integration with tmux

```
bind H new-window "cligpt" \; rename-window "cligpt"
```

## FAQ

### How do I get my ChatGPT API key?

To get a ChatGPT API key, you need to sign up on the OpenAI website and follow the instructions to create an account and obtain an API key.

### The script is not working, what should I do?

Make sure you have correctly installed all dependencies. If the problem persists, check that you are using the latest version of the script and report the issue on the project's GitHub page.

## Exemple

[![asciicast](https://asciinema.org/a/568168.svg)](https://asciinema.org/a/568168)
[![asciicast](https://asciinema.org/a/568170.svg)](https://asciinema.org/a/568170)
