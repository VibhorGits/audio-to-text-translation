
# Audio to Text Translation Pipeline

The pipeline accepts an audio recording from the user along with a specified translation language, then displays the transcribed text from the audio.  
This pipeline uses Open AI's Text and Speech Recognition components to handle audio file( mp3,mp4,wav format etc).  
Pipeline Link: https://instill.tech/vibhor/pipelines/audio-to-text/editor



## Demonstration

![Description of GIF](https://s1.gifyu.com/images/SyKc5.gif)



## Pipeline Overview

### Components

#### 1.audio-extract (OpenAI Component)

- Analyzes the uploaded audio recording to provide a summarized output.
- **Model**: whisper-1
- **Steps**:
  - Summarizes the audio content.
  - Extracts a title.
  - Lists key insights.
  - Identifies relevant keywords or tags.
  - Suggests any relevant locations if applicable.

#### 2.audio-translate (OpenAI Component)

- Translates the extracted text summary from the audio into the specified language.
- **Model**: gpt-4o-mini
- **Steps**:
  - Receives the summarized text from `audio-extract`.
  - Translates it into the user-specified language. 

### Variables

| Parameter       | Type     | Description                                       |
| :-------------- | :------- | :------------------------------------------------ |
| `audio`         | `audio`  | **Required**. The audio recording to be analyzed. |
| `language`      | `string` | **Required**. The desired language for translation. |

### Output

| Parameter      | Type     | Description                                               |
| :------------- | :------- | :-------------------------------------------------------- |
| `content`      | `text`   | The summarized text output from the `audio-extract` step. |
| `translate`    | `text`   | The translated text output in the specified language.     |




## Example Usage

###  To use the audio processing and translation pipeline, follow these steps:  

#### 1. Prepare Your Audio Recording: Ensure your audio recording is in a supported format (e.g., MP3, WAV).

#### 2. Select the Desired Language: Choose the language you want the audio summarized and translated into (e.g., Spanish, French).

#### 3. Input Variables: Use the following structure to input your variables:

   ```json
   {
     "audio": "path/to/your/audiofile.mp3",
     "language": "Spanish"
   }

