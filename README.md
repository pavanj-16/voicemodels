# Voice-to-LLM Models

This repository contains a Jupyter Notebook for Google Colab that demonstrates a complete **Speech-to-Text (STT) to Large Language Model (LLM)** pipeline. It allows you to record your voice directly in the browser, transcribe it using state-of-the-art models (including Indian languages), and get a response from a powerful LLM.

## 🚀 Features

- **Direct Browser Audio Recording**: Uses a custom JavaScript component to record audio directly from your microphone within Google Colab.
- **Configurable Speech-to-Text**: Support for various Whisper models, including:
    - OpenAI Whisper (Base, Small, Large)
    - **ARTPARK-IISc Vaani Models**: Specialized models for Indian languages like **Kannada** (`whisper-small-vaani-kannada`) and **Hindi** (`whisper-large-v3-vaani-hindi`).
- **Configurable LLM**: flexible integration with different LLMs using 4-bit quantization for efficiency on Colab T4 GPUs:
    - **Qwen2.5** (1.5B and 3B Instruct versions)
    - **Llama 3.2** (1B Instruct)

## 📋 usage

1.  **Open in Google Colab**: Upload the `speech_to_text_llm.ipynb` file to Google Colab.
2.  **Runtime Setup**: Ensure you are using a GPU Runtime (`Runtime` > `Change runtime type` > `T4 GPU`).
3.  **Install Dependencies**: Run the first cell to install `transformers`, `accelerate`, `bitsandbytes`, and `ffmpeg`.
4.  **Select Models**: In the **Configuration** cell, use the dropdown menus to select your desired:
    - `stt_model_name`: Choose between OpenAI or ARTPARK-IISc models.
    - `language`: Set the language for transcription (e.g., 'kannada', 'hindi', 'english').
    - `llm_model_id`: Choose the reasoning model.
5.  **Run the Pipeline**: Execute the cells. When the recording cell runs, click the **"Press to Start Recording"** button, speak your query, and click again to stop. The system will transcribe your speech and generate a response.

## 🎤 Audio Recording Component

The notebook uses a custom `IPython.display.Javascript` snippet to bridge the gap between the Python backend and the browser's Media API. This allows:
- **In-browser recording**: No need to upload pre-recorded files.
- **Immediate processing**: Audio is saved as a WAV file on the Colab instance and immediately processed by the pipeline.

## 🛠️ Models Used

-   **Whisper**: General-purpose speech recognition.
-   **Vaani (ARTPARK-IISc)**: specialized speech recognition for Indian languages.
-   **Qwen2.5 / Llama 3.2**: Efficient instruction-tuned LLMs for generating intelligent responses.
