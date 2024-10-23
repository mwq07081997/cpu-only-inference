# CPU-only Inference using Intel CPU

## Problem Statement
Many companies that deal with sensitive data are concerned about using third-party services that offer large-language model (LLM) for enterprise use. Hence, the direct alternative is to build their own on-prem systems that host and run these LLM. Unfortunately, on-prem solutions have their own limitations, which include: 
- limited to open-source LLM, which often only perform at an extremely high number of parameter (>70B parameters)
- require costly GPU clusters to host the very large LLM

## Objective
To develop a system that can run locally on a CPU-only device because most companies have thousands of existing devices with Intel CPU without a dedicated GPU.

## Solution
Build a locally-installed application that only require the use of Intel's CPU to perform inference. A smaller LLM will be quantized and finetuned to perform a specific use case, instead of a larger model due to the resource constraints in a CPU-only solution.

Sample Screeshot of Inference in Command Prompt run locally: 
<img width="571" alt="image" src="https://github.com/user-attachments/assets/412e4b65-5ff5-43db-9a05-31263f4452aa">

Screenshot of the CPU usage when inference is performed: 
<img width="476" alt="image" src="https://github.com/user-attachments/assets/9c133311-7aa1-4876-8643-ea61e3525719">


## Hardware and Software Used
Since the goal is for this local application to work in a typical corporate device. I use a standard Dell Latitude laptop that has an i7 Intel CPU and 16GB RAM. Note that this system will not utilize GPU, which means we have to optimize the system to perform inference inside a CPU, which has limited resources.

## Updates
### Update as of 23/10/2024 
- The latest solution uses an open-source model from Meta, called the Llama 3.2 3B model. The model is quantized to fit into a CPU-only hardware during inference.
- Inference is performed using standard OpenAI's and HuggingFace SDK that can be done **offline**.
- Each query takes approximately **180 seconds** to generate (speed of 5 tokens per second)
