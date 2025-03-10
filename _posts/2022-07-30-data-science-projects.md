---
date: 2023-08-30 08:57:37
layout: post
title: "Multilingual Speech Transcription & Translation"
subtitle: Brief overview of a personal project of mine
description: 
image: /assets/img/openai-whisper.jpg
optimized_image: /assets/img/openai-whisper.jpg
category: datascience
tags:
author:
paginate: 
---


> ##### Introduction

Born a Chinese Malaysian, I moved to the United States for high school and college. Over time, I've become less exposed to Malay, the national language of Malaysia, and have begun to forget it. Despite this, my interest in Malaysian politics has grown as I remain deeply connected to my home country. However, all government meetings and debates are conducted in Malay, which I no longer fully understand. To bridge this gap, this project utilized Whisper AI's model to translate Malay into English. 



> ##### Background of Whisper AI model

This project utilizes the Whisper model from Open AI, which is an automatic speech recognition (ASR) system trained on 680,000 hours of multilingual and multitask supervised data collected from the web. The Whisper architecture is a simple end-to-end approach, implemented as an encoder-decoder Transformer. Input audio is split into 30-second chunks, converted into a log-Mel spectrogram, and then passed into an encoder. A decoder is trained to predict the corresponding text caption, intermixed with special tokens that direct the single model to perform tasks such as language identification, multilingual speech transcription, and to-English speech translation. 

![Whisper](/assets/img/whisper.jpg "Whisper")


> ##### Detailed Breakdown of the Audio Transcription Process

The application initiates by downloading audio from a specified YouTube URL, and saving it in MP3 format. This is followed by a conversion process where the downloaded MP3 file is transformed into WAV format, utilizing ffmpeg. This step is necessary as WAV files are uncompressed, meaning they contain raw audio data without any loss of quality. MP3 files, on the other hand, are compressed. The lossy nature of MP3 can lead to a reduction in the clarity and detail of the sound, which can affect the accuracy of speech recognition systems. Next, an essential step of resampling is incorporated. This step adjusts the sample rate of the audio data and interpolates it to align with the new sample rate, a crucial step to ensure compatibility with the Whisper AI model.

Finally, the transcribe audio function is activated. In this phase, the application loads the 'medium' model of Whisper AI and proceeds with the transcription of the audio into English. The outcome of this process is the return of the transcribed text. The entire workflow is seamlessly integrated and built using Streamlit. 

![gif](/assets/img/ips-82DEA1B7-D4EF-4E37-8B7E-C5CBF00A56B7.gif "gif")
 

> ##### Model Performance Comparison in Whisper AI

In my project, I compared Whisper AI's small, medium, and large models for audio transcription and translation on a 2-minute file. The small model, while it ran the fastest, performed badly in accuracy. Conversely, the large model excelled in accuracy with a near-perfect translation but it took about 4 minutes to run, which is double the audio's duration. I opted for the medium model, which provided a good balance of speed and accuracy, completing the task in about 20 seconds. Although its accuracy is slightly inferior to the large model, it still delivers a sufficiently accurate translation. 


> ##### Project Enhancements and Future Prospects

Given that the project currently operates on a CPU, a 2-minute duration was an ideal amount of time to test the performance. However, using a GPU could notably improve performance, especially by enabling the large Whisper AI model to process longer audio with greater transcription and translation accuracy. 


> ##### Future Development: Live Audio Translation Application

Moving forward with this project, I aim to develop a live audio translation application whereby real-time translation can be done as a video is playing on any platform. This application would be particularly useful for translating less commonly spoken languages and unique dialects that are only spoken within small communities. 





