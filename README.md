# CliGPT

## Description

A bash script that use chatGPT api

[![asciicast](https://asciinema.org/a/567606.svg)](https://asciinema.org/a/567606)

## Dotenv

Create a .env file using .env.example

```
API_KEY=your api key
```

## Usage

```
Usage : cligpt [option] [text]

Option :
-h or --help ........................... Show help
-v or --version ........................ Show version
-l or --list ........................... List all available model
-m or --model <model> .................. Select model (default : gpt-3.5-turbo)
-t or --temp <temperature> ............. Set temperature (default : 0.7))

Example :
cligpt # Interactive mode with a chat history
cligpt "Hello, how are you ?"
echo Hello, how are you ? | cligpt -
cligpt -l
```

## Integration with tmux
```
bind H new-window "cligpt" \; rename-window "cligpt"
```
