# Audio-to-Voice-Dataset

This repository contains a Python script that processes an input WAV audio file by using OpenAI's Whisper model to transcribe the speech into text, splits the audio into individual sentences based on silent breaks, and creates a dataset in the LJ Speech format. **All processing is done locally without sending your audio data to the cloud!** This LJ Speech based voice dataset can be used to create a voice clone using tools like Piper or Coqui TTS.

## Features

- Transcribes speech to text using OpenAI's Whisper model.
- Splits audio into sentences based on longer silent breaks.
- Saves each sentence as a separate WAV file.
- Generates a metadata CSV file mapping each sentence to its corresponding audio file.

## Prerequisites

Ensure you have Python installed. You will need to install the following Python libraries:

- `openai-whisper`
- `pydub`
- `pandas`

You can install these dependencies using `pip`:

```bash
pip install openai-whisper pydub pandas
```

## Usage
* Prepare your audio file: Place your input WAV file in a directory and note its path.
* Update the script: Modify the audio_path variable in the script to point to your input WAV file.
* Run the script: Execute the script. It will process the audio file, split it into sentences, and save each sentence as a separate WAV file in the audio directory within the output directory. It will also create a metadata.csv file in the output directory containing the sentences and corresponding audio file IDs.

## Output
Audio files: The script will create individual WAV files for each sentence in the audio directory within the output directory.
CSV file: The script will generate a metadata.csv file in the output directory, containing the transcribed sentences and IDs of the corresponding audio files.

## Example
After running the script, the output directory might look like this:

```
output/
├── audio/
│   ├── LJ0001.wav
│   ├── LJ0002.wav
│   ├── LJ0003.wav
│   └── ...
└── metadata.csv
```

The metadata.csv file will contain:
```
LJ0001|Hello, world.
LJ0002|This is a test.
LJ0003|How are you?
```

## Notes
* The Whisper model transcription process may take some time, especially for longer audio files.
* For best results, ensure the input audio file has clear speech with minimal background noise.

## What's next?
Use this voice dataset to create a human like sounding voice clone **locally** using tools like Piper or Coqui TTS. Please check my step by step tutorial videos on my "Thorsten-Voice" youtube channel and subscribe if you like open source voice technology - Thank you :).

* [Tutorial for local voice cloning with Piper TTS](https://youtu.be/b_we_jma220?si=uxgUgyI9y6kEuCfh)
* [Tutorial for local voice cloning with Coqui TTS](https://youtu.be/bJjzSo_fOS8?si=6yqSKhvPVBuT3gGz)
