For School Final Project
from:https://github.com/GoGoDuck912/Self-Correction-Human-Parsing?tab=readme-ov-file
Here is a professional, high-quality **English version** of the `README.md` for your GitHub repository. I have structured it to follow industry standards for Deep Learning projects.

---

 🚀 Advanced Human Parsing (SCHP-based)

This project provides a robust and easy-to-use solution for **Human Parsing**, the task of segmenting a human image into fine-grained semantic parts (e.g., hat, hair, upper clothes, left arm, right leg, etc.).

It is based on the **Self-Correction Human Parsing (SCHP)** framework, which achieved state-of-the-art results in the LIP (Look Into Person) challenge.

🌟 Key Features

Multi-class Segmentation: Supports 20 semantic categories based on the LIP dataset.
Pre-trained Weights: Optimized for high-performance inference using ResNet-101.
Modern Environment Support: Fixed compatibility issues between InPlace-ABN and PyTorch 2.x / Python 3.12.
Batch Processing: Easily extract parsing results from entire folders with a single command.

📸 Demo Results

Input Image,Parsing Result (Color Map)
![messageImage_1765885237362_0](https://github.com/user-attachments/assets/9de3775f-e176-48f9-9b88-ce0140707bf8)
![messageImage_1765885232731_0](https://github.com/user-attachments/assets/1718ebf2-d01d-4428-ae85-f6af9101b775)


 🛠️ Installatio

1. **Clone the Repository**

git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME




2. **Setup Environment**
It is recommended to use Python 3.9 or higher. Install the dependencies via pip:

pip install -r requirements.txt




3. **Hotfix for InPlace-ABN (Important)**
If you are running in a modern environment (Python 3.12+), run the following commands to patch the C++/CUDA extension before running the extractor:

sed -i 's/z.type()/z.scalar_type()/g' modules/src/inplace_abn_cpu.cpp
sed -i 's/the_type/the_type.scalar_type()/g' modules/src/inplace_abn_cuda.cu





🚀 Usage

 1. Download Pre-trained Models

Download the pre-trained weights (e.g., `final.pth`) and place them in the `checkpoints/` directory.

2. Run Simple Extractor

Place your input images in the `inputs/` folder and execute the script:

```bash
python3 simple_extractor.py \
    --dataset 'lip' \
    --model-restore 'checkpoints/final.pth' \
    --input-dir 'inputs' \
    --output-dir 'outputs'

```

📊 Label Definitions (LIP Dataset)

The model segments the human body into the following 20 classes:

* `0`: Background | `1`: Hat | `2`: Hair | `3`: Glove | `4`: Sunglasses
* `5`: Upper-clothes | `6`: Dress | `7`: Coat | `8`: Socks | `9`: Pants
* `10`: Jumpsuits | `11`: Scarf | `12`: Skirt | `13`: Face | `14`: Left-arm
* `15`: Right-arm | `16`: Left-leg | `17`: Right-leg | `18`: Left-shoe | `19`: Right-shoe

🔗 Acknowledgements

Special thanks to the authors of the following projects:

* [GoGoDuck912/Self-Correction-Human-Parsing](https://github.com/GoGoDuck912/Self-Correction-Human-Parsing)
* [LIP Dataset Team](https://www.google.com/search?q=http://sysu-hcp.net/lip/)

