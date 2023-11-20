# User Manual

Team : Théo Pirouelle

<a href="https://www.python.org/">
  <img src="https://img.shields.io/badge/language-python-blue?style=flat-square" alt="laguage-python" />
</a>

---

## Preamble

To use the script, you'll need an [OpenAI API key](https://platform.openai.com/account/api-keys) for Whisper and GPT-4.
You will therefore need to modify the `openai.api_key` variable for the script to work properly.

The script on the repository is configured in French; it's easy to modify the script to adapt it to another language (just translate the few instructions given to GPT).

> [!WARNING]
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

## Usage

```bash
python3 main.py file_name.mp3
```

> [!WARNING]
> The file must be a `.mp3`.

When you run the script, it will ask you whether you want to run the complete script or just the transcript.
The complete script includes transcript, summary, key points and action points.

You can change the model used in the code by modifying the `model_gpt` variable. You can find a list of the different GPT models supported on the [OpenAI site](https://platform.openai.com/docs/guides/function-calling), along with the methods of use for API calls.


If you get the error that the `mp3` file is too heavy, feel free to cut it to make it lighter with the following commands:

```bash
# Tool installation
sudo apt install ffmpeg

# Using ffmpeg
ffmpeg -i test.mp3 -ss 00:00:30 -to 00:10:00 -c copy output.mp3  # Here from 30 seconds to 10 minutes
```

## Performance

Here are the performances I've seen in use:

| Model | Recording time | Treatment duration | Cost |
| --- | --- | --- | --- |
| gpt-4 | 1min | 40sec |  |
| gpt-4 | 3min | 2min | 0.07$ |
| gpt-4 | 10min | 3min30 | 0.11$ |
| gpt-4-1106-preview | 10min | 1min20 | 0.17$ |
| gpt-4 | 15min |  | 0.49$ |
| gpt-4-1106-preview | 16min37 | 3min20 | 0.27$ |
| gpt-4-1106-preview | 17min32 | 2min13 | 0.26$ |
| gpt-4-1106-preview | 18min35 | 3min28 |  |
| gpt-4 | 27min17 | 4min15 | 0.79$ |

You can find costs for the various models (including Whisper and GPT-4) on the [OpenAI website](https://openai.com/pricing).

You can also find all your consumption for the current month, as well as your payment history, on the [Usage page](https://platform.openai.com/usage).
