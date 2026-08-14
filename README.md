# Run MiniMax H3 on Google Colab

Run MiniMax H3 on a Google Colab A100 runtime.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/WindyYam/Run_MiniMax_H3_On_Google_Colab/blob/main/MiniMax_H3_Final.ipynb)

[Open the notebook in Google Colab](https://colab.research.google.com/github/WindyYam/Run_MiniMax_H3_On_Google_Colab/blob/main/MiniMax_H3_Final.ipynb)

## Setup

1. Select an **A100** runtime in Colab. At least 60 GB of system RAM is recommended.
2. Add a Hugging Face secret named `HF_TOKEN` in Colab's **Secrets** tab and enable **Notebook access**.
3. Run the code cells in order:
	- The first cell mounts Google Drive and caches the SageAttention wheel at `/content/drive/MyDrive/wheels/sageattention`.
	- In the next cell, set `USE_DRIVE = True` if model files should persist in `DRIVE_CACHE`.
	- Run the restart cell containing `os._exit(00)`. The runtime disconnect or apparent crash is expected. Wait for Colab to reconnect, then run the model-loading cell and generation GUI cell.

The model download is large. Use Google Drive storage to avoid downloading it again in a new runtime.
