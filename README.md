# Federated-Learning-Project
Federated Learning with Flower using CIFAR-10/100
This project implements Federated Learning using the Flower (FLWR) framework.
We evaluate training performance under:
- CIFAR-10 vs CIFAR-100 datasets
- IID (balanced) vs Non-IID (imbalanced) data distributions
- Different aggregation strategies such as FedAvg and FedProx
Each simulated client trains locally and only shares model weights with the server, preserving privacy and r
This README will be updated as the project progresses.
Currently includes: project introduction, setup instructions, and run commands.
----------------------------------------
Technologies Used
Category | Technology
---------|------------
Federated Learning | Flower (FLWR)
Deep Learning Framework | PyTorch
Datasets | CIFAR-10 & CIFAR-100
Language | Python 3.x
Environment | venv Virtual Environment
Logging | CSV
----------------------------------------
Setup Instructions

1️⃣ Create & Activate Virtual Environment

python3 -m venv venv

MacOS: source venv/bin/activate 

Windows: venv\Scripts\activate

----------------------------

2️⃣ Install Base Dependencies

pip install -r requirements.txt

⚠️ PyTorch is NOT included inside requirements.txt because each teammate may have different hardware (GPU / MPS / CPU)

----------------------------

Install PyTorch Based on Your Hardware
(Choose ONE option below ✅)

A) Windows / Linux with NVIDIA GPU (CUDA)

Check version: https://pytorch.org/get-started/locally/
Example for CUDA 12.1:

pip install torch torchvision --index-url https://download.pytorch.org/whl/cu121

B) macOS Apple Silicon (M1/M2/M3 – MPS Support)

pip install torch torchvision torchaudio

C) CPU-only Installation

pip install torch torchvision

----------------------------

Verify PyTorch Backend

python - <<EOF

import torch

print("CUDA:", torch.cuda.is_available())

print("MPS:", torch.backends.mps.is_available())

EOF

→ If any returns True, GPU acceleration is active ✅

----------------------------

Running the Project

Terminal 1 — Start FL Server:
python server.py

Terminal 2 — Start Client 0:
python client.py --client-id 0

Terminal 3 — Start Client 1:
python client.py --client-id 1

(Repeat for each additional client: 0,1,2,...)

→ Each client automatically receives its own dataset partition.

----------------------------

Project Structure (To be added later)

----------------------------------------
Results (To be added later)
- Accuracy vs Rounds
- Training Time vs Hardware Type (CPU/GPU/MPS)
- Comparison between dataset difficulty
- IID vs Non-IID performance differences
----------------------------------------
Analysis & Discussion (To be added later)
- Client drift on Non-IID data
- Convergence gap between FedAvg & FedProx
- Real federated edge scenario reflection
- Impact of heterogeneous compute resources
----------------------------------------
References (To be added later)
- Flower Documentation – https://flower.ai
- PyTorch Documentation – https://pytorch.org/
----------------------------------------
Contributors

(Ozgur Yilmaz) – CIFAR-10 IID + FedAvg

(Silan Ceylan) – CIFAR-10 Non-IID + FedAvg

(Mustafa Dogan Ozgun) – CIFAR-100 IID + FedProx

(Alperen Ozturk) – CIFAR-100 Non-IID + FedProx

----------------------------------------
README will be updated as project continues.
