# HARDWARE

## INTEL AND AWS

Intel is a multinational corporation and is one of the world largest semiconductor chip manufacturers. Intel is the inventor of the x86 instruction.

There is another popular instruction set called ARN which uses fewer instruction and usually results better power efficiency which results in lower costs.

Every time you lauch an instance you have to choose between x86 or ARN.

### Intel Xenon Scalable and Intel Gaudi

Intel Xenon Scalable Processor is a high-performance CPU designed for enterprise and server applications, commonly used in AWS instances.

Intel Habana Gaudi is a AI training processor developed by Habana Labs, a company acquired by Intel. Gaudi is tailored for deep learning models. Gaudi is often viewed as a competitor to NVIDIA's GPUs. While NVIDIA GPUs are higly versatile and widely adopted, Guadi offer a specialized alternative that's optimized specifically for AI training.

## GPU

A General Processing Unit (GPU) is a processor that is specialized to quickly render high-resolution images and video concurrently.

GPUs can perform parallel operations on multiple sets of data, and so they are commonly used for non-graphical tasks such as machine learning and scientific computation.

CPU can have average 4 to 16 processors cores. While GPU can have thousands of processor cores. 4 to 8 GPUs can provide as many as 40000 cores.

GPUs are best suited for repetitive and highly parallel computing tasks:
 - Rendering graphics
 - Cryptocurrency mining
 - Deep learning and ML

## Cuda

NVIDIA is a company that manufactures graphical processing units (GPUs) for gaming and professional markets.

Compute Unified Device Architecture (CUDA) is a parallel computing platform and framework by NVIDIA that allows developers to use CUDA-enabled GPUs for general purpose computing of GPUs.

In AWS the have:
 - EC2 P3 Instances have up to 8 NVIDIA Tesla V100 GPUs
 - EC2 G3 Instances have up to 4 NVIDIA Tesla M60 GPUs
 - EC2 G4 Instances have up to 4 NVIDIA T4 GPUs
 - EC2 P4 Instances have up to 8 NVIDIA Tesla A100 GPUs

All major deep learning frameworks are integrated with NVIDIA Deep Learning SDK

The NVIDIA Deep Learning SDK is a collection of NVIDIA libraries for deep learning. One of those libraries is the CUDA Deep Neural Network library (cuDNN). cuDNN provides highly tuned implementations for standard routines such as:
 - Forward and backward convolution
 - Pooling
 - Normalization
 - Activation layers