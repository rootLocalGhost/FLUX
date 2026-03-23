# 🌟 FLUX.2 Klein - Intel XPU Edition! 🚀

Run the blazing-fast **FLUX.2 [klein]** model natively on your Intel Arc GPU (like the A770) without your computer crying about VRAM? You are in the exact right place! 🧠✨

## 🤹‍♂️ The Magic Trick (How it fits in 16GB)



This massive model usually eats VRAM for breakfast. 🥞 To keep it under a strict 16GB diet, these scripts do a carefully choreographed dance:

1. Load Text Encoder ➡️ Encode Prompt ➡️ **NUKE VRAM!** 💥
2. Load Transformer ➡️ Denoise Image ➡️ **NUKE VRAM!** 💥
3. Load Autoencoder ➡️ Decode to Pixels ➡️ **DONE!** 🎉

No IPEX headaches. Just pure, native PyTorch XPU goodness. 💙 *(Plus, the scripts will automatically download the weights from `rootlocalghost/FLUX.2-klein-4B` on your first run! ☁️)*

## 🛠️ Installation

Just grab the native PyTorch XPU wheels and some Hugging Face goodies:

```bash
# 1. Install PyTorch with native Intel XPU support ⚡
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/xpu

# 2. Install the rest of the gang 📦
pip install transformers accelerate einops safetensors pillow huggingface_hub
```

## 📂 Where things go

Make sure your folders look exactly like this so the scripts know where to find the brains! 🧠

```text
└── Klein/
    ├── flux2/                       # ⚙️ The core engines
    ├── model/                       # 🤖 Your heavy models
    ├── klein_4b_gen_xpu.py          # 🎨 Script 1
    ├── klein_4b_edit_xpu.py         # ✂️ Script 2
    ├── klein_4b_refgen_xpu.py       # 🔄 Script 3
    └── klein_4b_multi_refgen_xpu.py # 👯‍♂️ Script 4
```

## 🎮 How to Play

### 1. Create out of thin air! (Generation) 🪄
Generates a brand new image from scratch using just your text prompt.
```bash
python klein_4b_gen_xpu.py
```

### 2. Edit an existing image! (Editing) ✂️
Takes your image and directly modifies it based on a new prompt (like changing a blue crystal to red).
```bash
python klein_4b_edit_xpu.py
```

### 3. Evolve a single image! (Ref-Gen) 🔄
Uses your input image as a stylistic and structural reference to generate a completely fresh, related image from a new noise canvas.
```bash
python klein_4b_refgen_xpu.py
```

### 4. Mash things together! (Multi-Ref) 👯‍♂️
Feeds *multiple* images into the model at once to guide a totally new generation. Perfect for fusing concepts! 🧬
```bash
python klein_4b_multi_refgen_xpu.py
```

---
**Happy Generating!** 🎨✨ Let those Intel Xe cores cook! 🔥