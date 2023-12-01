# PowerFit installation guide

PowerFit is a powerful automatic model-map fitting tool designed by the Bonvin lab: https://www.bonvinlab.org/. It is used in Slice'N'Dice EM as  tool that leverages the GPU for accelerated searches.

This guide will walk you through the process of installing PowerFit on your local machine.

Please check out the orginal PowerFit repository for more information:
https://github.com/haddocking/powerfit

PowerFit38 is a fork of the original PowerFit repository that has been modified to work with Python 3.8. This is required for Slice'N'Dice EM to work with PowerFit. Please check out the PowerFit38 repository for more information:
https://github.com/hllelli2/powerfit38

## Table of Contents
- [PowerFit installation guide](#powerfit-installation-guide)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
  - [Usage](#usage)
    - [Notes](#notes)

## Getting Started

These instructions will help you get a copy of the project up and running on your local machine.

### Prerequisites

Before you begin, make sure you have the following installed on your machine:

- Conda  (https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html)  
or
- Miniconda (https://docs.conda.io/en/latest/miniconda.html)  

- Git (https://git-scm.com/downloads)


### Installation

1. Download the enviroment file from https://github.com/hllelli2/powerfit-installation-guide/ 

    ```bash
    wget "https://github.com/hllelli2/powerfit-installation-guide/blob/master/powerfit_env.yml"
    # or with curl
    curl -LO "https://github.com/hllelli2/powerfit-installation-guide/blob/master/powerfit_env.yml"
    ```

2. Create an enviroment with the following command:

    ```
    conda env create -f powerfit_env.yml --name PfGPU_1912935144935
    ```

3. Activate the enviroment with the following command:

    ```
    conda activate PfGPU_1912935144935
    ```

4. Clone the repository of gpyfft and install it 
    ```bash
    git clone https://github.com/hllelli2/gpyfft.git
    cd gpyfft
    pip install .
    cd ..
    ```

5. Clone the repository of PowerFit and install it 
    ```bash
    git clone https://github.com/hllelli2/powerfit38.git
    cd powerfit38
    pip install .
    cd ..
    ```


## Usage

Once installed, Slice'N'Dice EM now should be able to detect PowerFit and run it within the Slice'N'Dice EM pipeline.

Or, you can run PowerFit directly from the command line with the following command:

```
powerfit <mapin> <resolution> <pdbin>
```


### Notes

- Currently only tested on Linux.
- GPU verision only tested on NVIDIA GPUs, as CUDA is not required it shouldn't be a problem to run on AMD GPUs.
- If you have any issues, please contact me at: hllelli2@liverpool.ac.uk


