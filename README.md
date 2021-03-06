# Autosub-dual

## [Modification method](https://boblee.cn/2019/03/12/autogenerating-dual-subtitles-for-video-shi-pin-z/)
  
## Install && Replace original script
```bash
# macOS
brew install ffmpeg
pip install autosub

mv /usr/local/bin/autosub /usr/local/bin/autosub.bak

curl https://raw.githubusercontent.com/bobleer/autosub-dual/master/autosub/modified.py -o /usr/local/bin/autosub && chmod +x /usr/local/bin/autosub
```

## Usage
```bash
# need Google Translate API key
autosub -D zh-CN -K [APIKEY] [VIDEOPATH]
```

![](https://github.com/bobleer/autosub-dual/raw/master/Theresa%20May%20warns%20MPs%20-%20'We%20may%20never%20leave%20the%20EU%20at%20all'-R8HWmT1r99Q-0001.jpg)


## Original autosub README

### Auto-generated subtitles for any video

Autosub is a utility for automatic speech recognition and subtitle generation. It takes a video or an audio file as input, performs voice activity detection to find speech regions, makes parallel requests to Google Web Speech API to generate transcriptions for those regions, (optionally) translates them to a different language, and finally saves the resulting subtitles to disk. It supports a variety of input and output languages (to see which, run the utility with the argument `--list-languages`) and can currently produce subtitles in either the [SRT format](https://en.wikipedia.org/wiki/SubRip) or simple [JSON](https://en.wikipedia.org/wiki/JSON).

### Installation

1. Install [ffmpeg](https://www.ffmpeg.org/).
2. Run `pip install autosub`.

### Usage

```
$ autosub -h
usage: autosub [-h] [-C CONCURRENCY] [-o OUTPUT] [-F FORMAT] [-S SRC_LANGUAGE]
               [-D DST_LANGUAGE] [-K API_KEY] [--list-formats]
               [--list-languages]
               [source_path]

positional arguments:
  source_path           Path to the video or audio file to subtitle

optional arguments:
  -h, --help            show this help message and exit
  -C CONCURRENCY, --concurrency CONCURRENCY
                        Number of concurrent API requests to make
  -o OUTPUT, --output OUTPUT
                        Output path for subtitles (by default, subtitles are
                        saved in the same directory and name as the source
                        path)
  -F FORMAT, --format FORMAT
                        Destination subtitle format
  -S SRC_LANGUAGE, --src-language SRC_LANGUAGE
                        Language spoken in source file
  -D DST_LANGUAGE, --dst-language DST_LANGUAGE
                        Desired language for the subtitles
  -K API_KEY, --api-key API_KEY
                        The Google Translate API key to be used. (Required for
                        subtitle translation)
  --list-formats        List all available subtitle formats
  --list-languages      List all available source/destination languages
```

### License

MIT
