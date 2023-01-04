# youtube-targeted-downloader
Download (archive) youtube content with specifications.

## Motivation 
Youtube content has become important to people. You can download videos which are important to you or of which you want to do further research on from your hard disk. Moreover, anytime channels can get closed and the videos won't be available online any longer. Due to that, you can archive videos on your own computer. 

## Usage
You can specify channels or playlists or singular videos.

You set which channel etc. you target in the file `yt-dlp-channels-audio.txt` or `yt-dlp-channels-video.txt` respectively. You can list as much targests as you want here, each in a new line.
1. Go to the channel's videos section for example
2. Copy the address shown in the address bar
3. Paste this address into the channels file.

The program then reads the content from the channels file and downloads all the content according to the specifications set in the configuration file which is explained below.

After downloading each youtube content,the unique ID of that one is then saved under the archive files `yt-dlp-archive-video.txt` or `yt-dlp-archive-audio.txt` respectively.  

## Get started

1. Install yt-dlp (see below)
2. Insert the youtube content URLs you are targeting into the channels file.
3. Open the configuration file and set in line 4 the path for where you keep your channels and archive file. After, set the download path in line 6 where you want your downloads to be saved. 

You run it via `yt-dlp --config-clocation "c:\path\to\the\configfile`

## Download pattern and filter setup
### Videos
- Quality settings are set for getting the best videos but with a highest resolution of 800p (to save disk space).
- free formats are preferred.
- Title names which match a certain pattern are downloaded only
Here, the title must include two keywords in order to be triggered for downloading: _sleep_ and _meditation_. 
This is useful to execute a targeted filter towards the title name. In a channel about spirituality for example, you get only content which is about a possible interaction of sleep and meditation.
- Output file names are set to be congruent to windows file name prerequisites.
- Output file naming pattern is here: title - license-comments-likes-views

__Example output__:
`Why Do We Fall Asleep in Meditation - Questions and Answers with Shunyamurti - NA-51comments-422likes-8408views.webm`

- Metadata and thumbnail picture are saved.
- The video's description text is being saved to a file with extension `.description`.
- A JSON file is being saved with details of the downloaded content which is suitable for post-processing in your online application.
- The comments will be saved inside the json file too
- Subtitle file is being downloaded too, if available

### Audio extractions
The options of the video context is equal; though video format settings are replaced with audio settings: 
- An order of file formats are set: `opus` format is preferred over `mp3` is preferred over `aac` is preferred over `m4a`
- The audio quality is set as 5 of 10, while __0__ is best and __10__ is worst quality. This provides decent quality but not extreme (which can be adequate for vocal content such as a podcast or an audio book. Set this value lower in case you require high quality for audiophile music or activate the line below in the configuration file which yields for the high resolution FLAC file format. When choosing quality, think about that higher quality demands also more disk space.

## Development setup

The environment used is
- yt-dlp: https://github.com/yt-dlp/yt-dlp

Thank you to its developers.

Download the latest [release](https://github.com/yt-dlp/yt-dlp/releases/) and copy the extracted file it into the folder of your development setup, i.e. `c:\users\username\Anaconda3\` if you have installed the Anaconda package. This folder should be set as an environment variable.

## Meta

Author: Jonas Dossmann

Distributed under the UNLICENSE license.

[https://github.com/dossma/](https://github.com/dossma/)
