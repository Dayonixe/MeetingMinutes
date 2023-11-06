# User Manual

Team : Théo Pirouelle

<a href="https://www.python.org/">
  <img src="https://img.shields.io/badge/language-python-blue?style=flat-square" alt="laguage-python" />
</a>

---

## Préambule

To use the script, you'll need an [OpenAI API key](https://platform.openai.com/account/api-keys) for Whisper and GPT-4.
You will therefore need to modify the `openai.api_key` variable for the script to work properly.

The script on the repository is configured in French; it's easy to modify the script to adapt it to another language (just translate the few instructions given to GPT).

> **Warning**<br>
> To use the script, you need to be connected to the Internet so that it can call the OpenAI API.

You will also need to install the necessary :
```bash
sudo apt-get update

sudo apt install python3
sudo apt install python3-pip

pip3 install openai
pip3 install python-docx
pip3 install pydub
```

## Utilisation

```bash
python3 main.py file_name.mp3
```

> **Warning**<br>
> The file must be a `.mp3`.

When you run the script, it will ask you whether you want to run the complete script or just the transcript.

The complete script includes transcript, summary, key points and action points.


If you get the error that the `mp3` file is too heavy, feel free to cut it to make it lighter with the following commands:

```bash
# Installation de l'outil
sudo apt install ffmpeg

# Utilisation de ffmpeg
ffmpeg -i test.mp3 -ss 00:00:30 -to 00:10:00 -c copy output.mp3  # Ici de 30 secondes à 10 minutes
```

## Performance

Here are the performances I've seen in use:

| Recording time | Treatment duration | Cost |
| --- | --- | --- |
| 1min | 40sec |  |
| 3min | 2min |  |
| 10min | 3min30 | 0.11$ |
| 15min |  | 0.49$ |
| 27min17 | 4min15 | 0.79$ |
