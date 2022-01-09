# Trumpet

This is a Discord Bot. The bot's sole purpose is to announce arrivals and departures in voice chat via TTS. This is [a fork of a lightweight Discord music bot](https://github.com/xypwn/go-musicbot) written in go with minimal dependencies.

## Building from source

- Make sure to have [Go (Golang)](https://golang.org) installed.

- Let Go install all library dependencies: `go mod tidy`.

- Build the program: `go build .`.

## Prerequisites

- Make sure to have [ffmpeg](https://ffmpeg.org/) installed (basically every Linux/BSD distro should have a package for it).

- Make sure to have a **RECENT** version of [youtube-dl](https://yt-dl.org/). If your distro doesn't package a recent version, see the section titled "Obtaining a recent youtube-dl binary".

## Running the binary

Example configuration:

```json
{
	"ffmpeg_path": "ffmpeg",
	"google_service_account_credentials": "google-translate-api-credentials.json",
	"ignore_list": [],
	"prefix": "!",
	"token": "insert your discord bot token here",
	"user_audio_path": "audio/",
	"youtube-dl_path": "youtube-dl"
}
```

- Copy `config.json.example config.json` or run the binary once to generate `config.json`: `./trumpet`.



- In `config.json`, find the line that says `"token"`. In that line, change the text that says `"insert your discord bot token here"` to whatever your bot token is (just look it up if you don't know how to get one). Remember to keep the `""` surrounding the token.

- Run the program: `./trumpet`.

## Notes

- youtube-dl might cause some problems with certain Unicode characters if the locale isn't configured correctly (messages like "Adding 0 tracks to queue." may arise). Quick fix: `sudo sh -c "echo 'LC_ALL=\"en_US.UTF-8\"' >> /etc/environment"`.
