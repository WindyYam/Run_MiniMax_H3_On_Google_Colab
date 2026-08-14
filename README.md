# Run MiniMax H3 on Google Colab

Run MiniMax H3 on a Google Colab A100 runtime.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/WindyYam/Run_MiniMax_H3_On_Google_Colab/blob/main/MiniMax_H3_Final.ipynb)

[Open the notebook in Google Colab](https://colab.research.google.com/github/WindyYam/Run_MiniMax_H3_On_Google_Colab/blob/main/MiniMax_H3_Final.ipynb)

## Setup

1. **Strongly recommended:** Select the **A100 high-RAM** runtime variant in Colab. The notebook has very high memory requirements; an A100 with 80 GB VRAM and at least 60 GB of system RAM provides the most reliable experience.
2. Create a Hugging Face access token at [Hugging Face Settings > Access Tokens](https://huggingface.co/settings/tokens). Sign in, select **Create new token**, choose the **Read** permission, and copy the token. In Colab, open the **Secrets** tab, add a secret named `HF_TOKEN`, paste the token as its value, and enable **Notebook access**. Never commit or share the token.
3. Run the code cells in order:
	- The first cell mounts Google Drive and caches the SageAttention wheel at `/content/drive/MyDrive/wheels/sageattention`.
	- In the next cell, set `USE_DRIVE = True` if model files should persist in `DRIVE_CACHE`.
	- Run the restart cell containing `os._exit(00)`. The runtime disconnect or apparent crash is expected. Wait for Colab to reconnect, then run the model-loading cell and generation GUI cell.
4. The model-loading cell checks VRAM and system RAM automatically. If needed, it switches to slower CPU-RAM group offloading. Disk offload is disabled because TorchAO quantized tensors cannot use Diffusers disk offload. Google Drive is used only for persistence. Set `FORCE_LOW_MEMORY_MODE` in that cell to override automatic selection.

The model download is large. Use Google Drive storage to avoid downloading it again in a new runtime.
