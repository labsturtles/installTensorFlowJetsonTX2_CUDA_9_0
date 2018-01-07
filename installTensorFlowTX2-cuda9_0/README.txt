Install TensorFlow v1.4.1 on NVIDIA Jetson TX2 Development Kit

Jetson TX2 is flashed with JetPack 3.2 which installs:

    L4T 28.1 an Ubuntu 16.04 64-bit variant (aarch64)
    CUDA 9.0
    cuDNN 7.0.5


//-----------------------------------------------------------------//

#Preparation
sudo nvpmodel -m 2
./createSwapfile.sh -d ~/ -s 8


#For Python 2.7
./installPrerequisites.sh
./cloneTensorFlow.sh
./setTensorFlowEV.sh


#For Python 3.5
./installPrerequisitesPy3.sh
./cloneTensorFlow.sh
./setTensorFlowEVPy3.sh


#Build TensorFlow
./buildTensorFlow.sh
./packageTensorFlow.sh


#Install wheel file for Python 2.X
pip install tensorflow-1.4.1-cp27-cp27mu-linux_aarch64.whl


#Install wheel file for Python 3.X
pip3 install tensorflow-1.4.1-cp35-cp35mu-linux_aarch64.whl
