# Layer rotation: a surprisingly powerful indicator of generalization in deep networks?
This repository contains the code used to create all the figures of our paper "Layer rotation: a surprisingly powerful indicator of generalization in deep networks?", by Simon Carbonnelle and Christophe De Vleeschouwer, available [on arXiv](https://arxiv.org/abs/1806.01603v2) and presented during the ICML 2019 workshop "Identifying and Understanding Deep Learning Phenomena".

### Code structure
Code structure tries to follow the structure of the paper. I.e.:
- 'A systematic study of layer rotation configurations with Layca' = Section 4
- 'A study of layer rotation in standard training settings' = Section 5
- 'MNIST - 1st layer feature visualization' = Section 6


import_task.py and models.py are used to load the data and the untrained models corresponding to the 5 tasks used in the experiments.

rotation_rate_utils.py contains the code for recording and visualizing layer rotation curves

layca_optimizers.py contains the code to apply Layca on SGD, Adam, RMSprop or Adagrad, and to use layer-wise learning rate multipliers when using SGD.

get_training_utils.py contains utilities to get (optimal) training parameters such as learning rate schedules, learning rate multipliers, stopping criteria and optimizers for training of the five tasks

experiment_utils.py contains utilities such as training curves visualization, one-hot encoding, ...

### Libraries configuration
Code was run with tensorflow-gpu 1.4.0 and keras 2.1.2

### Steps
1. Download the latest Miniconda installer (Linux 64-bit)
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

2. Run the installer
bash Miniconda3-latest-Linux-x86_64.sh
At the end, it will ask:

Do you wish the installer to initialize Miniconda3?

Type yes.

3. Refresh the shell to activate conda
source ~/.bashrc

Create a new environment (use Python version you need)
conda create --name myenv python=3.6

Activate it
conda activate myenv

pip install -r requirements.txt

git clone repo_link

cd LayerRotation

cd 'A study of layer rotation in standard training settings'

python train.py


Install tmux if it's not already installed:

sudo apt update && sudo apt install tmux


Then:

tmux


Start your training:

python train.py


Then detach from the session with:

Ctrl + B, then press D


This keeps your session alive even if you close the browser.

To reconnect later:

tmux attach





To download the trained model with all other files:
Install gcloud SDK from:
https://cloud.google.com/sdk/docs/install

Then configure the setup.

gcloud auth login
gcloud config set project your-project-id


Finally use it:
gloud compute scp --recurse username@vm-name:/path/to/model /local/path --xone=zone-name

gcloud compute scp --recurse s225207935@layer-rotation-modeling:/home/s225207935/LayerRotation "C:\Users\rjtdu\Downloads" --zone=us-central1-f
