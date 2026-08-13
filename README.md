# Fundamentals-of-Machine-Learning
Fundamentals of Machine Learning, by Packt Publishing

This repository will include all of the labs I completed for the Fundamentals of Machine Learning course. I made updates to the files where I deemed appropriate. For example, when I got to ex2 - logistic regression, I decided to reconfigure my setup to use WSL2. I started putting my isntructions in a markdown cell in ex2 - logistic regression.ipynb, but now I'm moving the setup instructions here:
## For Windows users
Before you begin, if you are running this on Windows, you'll want to use Windows Subsystem for Linux (WSL2). I'll go through the steps to get set up with this.
1. **Install WSL2:** Open PowerShell as Administrator and type wsl --install. Restart your computer when prompted.
    - you'll need to set up a password
2. **Install NVIDIA Drivers:** Ensure you have the latest game-ready or studio drivers installed on your host Windows system.
    - sudo apt install nvidia-utils-595
3. **Run this in your terminal (Ubuntu):**
    - sudo add-apt-repository ppa:deadsnakes/ppa
    - sudo apt update
    - sudo apt install python3.12 python3.12-venv python3.12-dev
    - sudo snap install code --classic

4. **Create a new virtual environment and activate it**
    - python3.12 -m venv .venv
    - source .venv/bin/activate

5. **Install tensorflow with within your Linux environment**
    - https://www.tensorflow.org/install/pip
    - python3 -m pip install tensorflow[and-cuda]
    - python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
    - Note: I ran into an error with not enough space so I created a custom temp directory with the code below
        - mkdir -p ~/temp_pip
        - TMPDIR=~/temp_pip pip install --cache-dir ~/temp_pip tensorflow[and-cuda]

6. **Install graphiz**
    - sudo apt update
    - sudo apt install graphviz
    - verify the installation: dot -V

7. **Install other dependencies**
    - pip install ipykernel pydot pydotplus graphviz
    - pip install -q seaborn


*Final note:*  In the end, I still don't see this running on GPU, but it doesn't error out.


