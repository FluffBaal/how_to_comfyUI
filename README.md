## ComfyUI starter  

The information provided here includes things I found helpful for getting started.
This guide is intended as a supplement to the existing ComfyUI README.md, which you can find here: [ComfyUI GitHub](https://github.com/comfyanonymous/ComfyUI)
It assumes that you have already successfully installed ComfyUI. 

### Key Terms

- **Checkpoint (Base Model)**: The main AI model containing learned weights (like SD1.5). Start your workflow here.
- **LoRA (Low-Rank Adaptation)**: Small files adjusting the style or subject of your base model. Requires a checkpoint.
- **VAE (Variational Autoencoder)**: Handles image encoding/decoding; affects image quality and colors.
- **Workflow**: A visual graph of nodes that instruct ComfyUI on generating images.

### Setting Up Models

- **Checkpoints**: Place `.safetensors` or `.ckpt` files in `ComfyUI/models/checkpoints`.
- **LoRA**: Place LoRA files (`.safetensors`) in `ComfyUI/models/loras`.
- **VAE**: Optional. Place VAE files (`.safetensors`) in `ComfyUI/models/vae`.

### Using ComfyUI Manager

ComfyUI Manager simplifies managing extensions and nodes.
- To install manually:
  ```bash
  git clone https://github.com/ltdrdata/ComfyUI-Manager custom_nodes/comfyui-manager
  ```
- Restart ComfyUI, and use the built-in Manager interface to browse and install nodes.

### Building a Workflow

Basic text-to-image workflow:
1. **Load Checkpoint Node** → select your base model.
2. **CLIP Text Encode Node** → input your prompt.
3. **KSampler Node** → generates the latent image.
4. **VAE Decode Node** → converts latents into visible images.
5. **Save Image Node** → saves the generated images.

**Using LoRAs:**
- Add a **Load LoRA Node** after your checkpoint.
- Set LoRA strength to control its influence.

### Finding & Using Workflows

- Workflows can be saved/loaded as `.json` files or embedded in image metadata.
- Drag workflow images into ComfyUI to instantly load setups.
- Official workflows and examples: [ComfyUI GitHub](https://github.com/comfyanonymous/ComfyUI)

### Desktop Version

- Easy setup with built-in dependencies, automatic updates, and a new intuitive UI.
- Includes ComfyUI Manager by default.
- Ideal for beginners: [Download here](https://www.comfy.org/download)

happy generating!

