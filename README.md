
<p align="center">
  <img src="https://github.com/ejgarcian/videosubs/blob/main/visagiaheader.jpeg">
</p>

# Video Subs Automatic Generator IA (VSAGIA) Jupyter Notebook
This is a python script to create subs close caption file .str video from a video file .mp4 as a source automatically. This script use NVIDIA/CUDA GPU to generate the subs. It’s powered through Whisper a powerful and robust speech recognition model that can transcribe audio in multiple languages and translate it to English. It is based on a Transformer encoder-decoder architecture and trained on a large and diverse dataset of audio.

The performance of this work was made in a RTX3060, was 4.30 minutes to process a mp4 video file with size of 1.81GB and 1:38 hours of duration. The test of a CPU capable is no recommended because is too slow the processing. In some circumstances the IA model can add some unexpected or illusion hearing in the silent space, more of them when the duration is large, but maybe can be improve increasing the parameter settings like model size, to set the model size:
```
model = whisper.load_model("base",device="cuda:0") # Change this to your desired model values "tiny, base, small, medium or large"
```

To set the working folder set the variable line at:
```
file = "YOUR--VIDEO--FILE.mp4"
```

But for the results obtained was very well in performance and precision of the close caption and time frames position. Another strange situation is the model capture al sounds as sounds and other languages speakers, but it was very interesting experience.

Other parameters in the example provided script is the use of the translation mode, I use the translation of a English Video to a Spanish Closed Caption, and it was very well, to handle the translation mode:
```
#use to translate directly to English
#transcribe = model.transcribe(path + audio, task="translate") 
#use to translate english to spanish 
transcribe = model.transcribe(path + audio, task="translate", language="es")
```

At the end the .srt file, it is a text file that contains subtitles for a video. It has a simple format: each line has a number, a time range, and the subtitle text. For example:
```
1
00:00:01,000 --> 00:00:03,000
Hello world.

2
00:00:03,500 --> 00:00:05,500
I'm here to explain srt files.

4
00:00:08,500 --> 00:00:10,500
You can just watch the video and listen.

5
00:00:28,500 --> 00:00:30,500
Thank you for your attention.
```
You can use Jupiter to run the notebook in this repository https://github.com/ejgarcian/videosubs/blob/main/vsagia.ipynb and enjoy.

Thank you for watching this code! I hope you enjoyed it and learned something new. If you want to create your own subtitles for your videos, you can use the Video Subs Automatic Generator IA (VSAGIA). It's a powerful tool that can generate subtitles in different languages and formats powered whit. You can try it for free and see how it works. I would love to hear your feedback and suggestions on how to improve it. Please leave a comment below or contact me through my social media. Have a great day!

NOTE: Remember preparing the environment with the all CUDA and Python packages requirements to execute GPU programs in the computer, for more information refer to: https://developer.nvidia.com/rdp/cudnn-download and https://github.com/openai/whisper, others technical requirements will be specific of your video card and https://pypi.org/project/ffmpeg/

