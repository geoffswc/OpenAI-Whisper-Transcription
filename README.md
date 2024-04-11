# OpenAI-Whisper-Transcription
Using Whisper to Generate Transcriptions from Industry Documents Videos

### Overview

This repository contains examples for using the whisper module from OpenAI locally to generate transcriptions for mp4 video files. Although whisper does have an API that may be preferable from a performance perspective, there may be some advantages to using whisper locally on your laptop or workstatopn (for example, you may prefer to bypass the need for an account and an API key, the need for a network connection, and so forth). This repository contains examples for using whisper locally only (no use of the API).  

Although whisper is highly configurable, the idea here is to provide very simple examples along with some installation help to get started. The examples here also focus on a common use case at the UCSF library, which is to derive a transcript from a video hosted on a public URI. 

### Sample Video Files

#### tobacco_wbr62a00.mp4

Note - at 26.5mb, the sample video file is slightly too large to be stored on github. You can download this video at:
https://archive.org/download/tobacco_wbr62a00/tobacco_wbr62a00.mp4

You can also download this file by running the workbook: Whisper-On-Video-Remote-URI.ipynb

The sample video file, tobacco_wbr62a00.mp4, is a youth anti-smoking produced by Philip Morris in 2000. It is hosted on the Internet Archives and is part of the Industry Documents Library, a large collection of files from industries that have affected public health.  The file is about four minutes long and contains logos, embedded text, gestures, and speech. This repository will only consider the speech-to-text extraction. 

For more information on this specific file, please see the Tobbaco Archives page at: 
https://archive.org/details/tobacco_wbr62a00

Note: If you're interested in embedded text, logos, and other visual information in addition to speech-to-text, you may be interested in Google VideoIntelligence API. For more information, see:

https://github.com/geoffswc/IDLPublicDatasets/blob/main/Parse-VideoIntelligence-JSON-Demo.ipynb

### Sample Workbooks

#### Whisper-On-Video-Local-File.ipynb

This workbook provides a short, simple example of how to extract a transcript from a local video file (tobacco_wbr62a00.mp4)

#### Whisper-On-Video-Remote-URI.ipynb

This workbook provides a short, simple example for downloading an mp4 file from a public URI and extracting the transcript. 

### Installation issues:

#### Install ffmpeg

One really nice thing about whisper is that it doesn't require you to extract an audio file (such as a .flac file) from the video prior to transcribing it. You can transcribe an mp4 file directlym and whisper will manage the audio extraction for you. This does mean that whisper has a dependency on ffmeg, so you'll need to install that prior to using the transcribe() method

#### Install whisper

To install whisper, follow the instructions at https://github.com/openai/whisper
Note: whisper does have a number of dependencies. I found it easiest to install directly from the repo:

pip install git+https://github.com/openai/whisper.git 

#### Troubleshooting ffmpeg

I ran into an additional install issue with dependencies when using whisper with my locally installed ffmpeg. The solution described in this github issue report worked for me:

https://github.com/Homebrew/homebrew-core/issues/153177
