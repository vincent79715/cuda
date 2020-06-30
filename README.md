sudo apt-get purge nvidia*
sudo add-apt-repository -y ppa:graphics-drivers/ppa 
sudo apt-get update
sudo apt-get install nvidia-driver-440

reboot

nvidia-smi

sudo dpkg -i cuda-repo-ubuntu1804-10-0-local-10.0.130-410.48_1.0-1_amd64.deb
sudo apt-key add /var/cuda-repo-10-0-local-10.0.130-410.48/7fa2af80.pub
sudo apt-get update
sudo apt-get install cuda-toolkit-10-0

echo 'export PATH=/usr/local/cuda-10.0/bin${PATH:+:$PATH}' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/usr/local/cuda-10.0/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc
sudo ldconfig
nvcc -V

sudo dpkg -i libcudnn7_7.6.5.32-1+cuda10.0_amd64.deb
