# Stable Diffusion Setup Complete

## Installation Summary

Your Stable Diffusion project has been successfully set up on macOS with Apple Silicon support.

### Environment Details
- **Python Version**: 3.14.0
- **PyTorch Version**: 2.9.1
- **Virtual Environment**: `/Users/puneet/Programming/AI/stablediffusion/venv`

### Key Features Installed
- ✅ PyTorch 2.9.1 with Metal Performance Shaders (MPS) enabled
- ✅ Core dependencies: diffusers, transformers, kornia, einops
- ✅ UI frameworks: Gradio & Streamlit
- ✅ Project installed in editable mode

### GPU Acceleration
- **Metal Performance Shaders (MPS)**: ✅ Available
  - Provides GPU acceleration on Apple Silicon Macs
  - Automatically used for tensor operations on supported hardware
- **CUDA**: Not available (expected for macOS)

### How to Activate the Environment

To use the setup in future sessions:
```bash
source /Users/puneet/Programming/AI/stablediffusion/venv/bin/activate
```

Or add this alias to your shell profile (~/.zshrc or ~/.bash_profile):
```bash
alias stablediff='source /Users/puneet/Programming/AI/stablediffusion/venv/bin/activate'
```

### Available Scripts

After activating the environment, you can run:
```bash
# Text to Image
python scripts/txt2img.py --help

# Image to Image
python scripts/img2img.py --help

# Gradio UI
python scripts/gradio/txt2img.py
python scripts/gradio/img2img.py
python scripts/gradio/inpainting.py

# Streamlit UI
streamlit run scripts/streamlit/txt2img.py
```

### Next Steps

1. **Download Model Checkpoints**: Models must be placed in the `checkpoints/` directory
   - Models are available on [Hugging Face](https://huggingface.co/StabilityAI)
   - Popular: `sd-v1-4.ckpt`, `sd-v2-1-base.safetensors`

2. **Configure Model Paths**: Edit scripts to specify checkpoint locations

3. **Test Installation**:
   ```bash
   python scripts/txt2img.py --help
   ```

### Performance Tips for macOS

1. **Use MPS for acceleration** (automatically enabled):
   - Provides ~2-3x speedup on Apple Silicon
   - No additional configuration needed

2. **Memory Management**:
   - Monitor memory with `top` command
   - Reduce batch size if out of memory
   - Use `--enable-attention-slicing` for lower VRAM usage

3. **Model Precision**:
   - Default: float32 (accurate but slower)
   - Use `--precision autocast` for faster inference

### Troubleshooting

If you encounter issues:

1. **Verify Installation**:
   ```bash
   python -c "import torch; print(torch.backends.mps.is_available())"
   ```

2. **Update Pip**:
   ```bash
   pip install --upgrade pip setuptools wheel
   ```

3. **Reinstall Dependencies**:
   ```bash
   pip install --upgrade -r requirements.txt
   ```

### System Requirements
- macOS 12.3 or later (for MPS support)
- Apple Silicon Mac (M1/M2/M3 or later)
- 16GB+ RAM recommended
- Sufficient disk space for models (~4GB per model)

---
Setup Date: November 28, 2025
