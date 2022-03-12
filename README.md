<div id="top"></div>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <h3 align="center">VECA</h3>
</div>


[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) 



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#citation">Citation</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

![veca_overview](./docs/veca.png)

VECA is currently preparing for the public release of Bayley-4 cognitive tasks, Unity packages, and additional system optimizations. Sorry for the delay.
<p align="right">(<a href="#top">back to top</a>)</p>



### Built With

This section should list any major frameworks/libraries used to bootstrap your project. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.

* [Unity3D](https://unity.com/)
* [python](https://www.python.org/)
* [numpy](https://numpy.org/)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

### Prerequisites
VECA environment requires two separate terminal sessions to properly execute it. One is to execute `Unity3D-based Environment` (*Environment* from now on), and the other is to execute the `agent algorithm` (*Algorithm* from now on). A session executing the environment should be executed on `Windows OS`. 

Two sessions need not be on the same machine, since the communication between the environment and algorithm is socket-based. So the environment can run on Windows desktop, and the agent algorithm can run on linux cluster server. To sum up, the OS requirement is as follows:

* Environment session: Windows OS 

* Algorithm session: Any OS supporting python3 

You need python3 and ffmpeg to execute scripts. In Ubuntu, you can install them with following command.
```
sudo apt install python3 ffmpeg
```

You also need 3 python packages numpy, moviepy, and pillow. You can install them with following command.
```
pip install numpy moviepy pillow
```
or use `requirements.txt` file to install as follows:
```
pip install -r requirements.txt
```


<p align="right">(<a href="#top">back to top</a>)</p>

### Installation

1. Clone this veca repository. Both the *environment* and *algorithm* session should clone it.
```
git clone https://github.com/GGOSinon/VECA.git
```

2. (Only for the *environment* session) Create `bin` directory inside the repository, 
```
mkdir bin && cd bin
```
and download the zip file `disktower.zip` containing a unity application executable. 

* click [google drive link](https://drive.google.com/file/d/1mQEpN0wqztujGxtyYxARv_c_fxCAmIey/view?usp=sharing) to download, 
* OR use [gdown](https://github.com/wkentaro/gdown) program to download from the commandline.

```
gdown https://drive.google.com/uc?id=1mQEpN0wqztujGxtyYxARv_c_fxCAmIey

```


3. (Only for the *environment* session) unzip the downloaded zip file, and go back to root directory of the repo.

```
unzip disktower.zip
cd ../
```

#### Other tasks 
Unity application executables for tasks besides DiskTower are available in the following google drive links. Download and unzip it on a different directory. Modify an unity executable path in the `env_manager.py` script to use it.

* KickTheBall task: [google drive link](https://drive.google.com/file/d/1jIxQyA2rS54-XH_AQxfWXRJqcYepMZ_T/view?usp=sharing)
* MazeNav task: [google drive link](https://drive.google.com/file/d/1SSsQIklTFChWRvR14aRB9lTzMgMdPorv/view?usp=sharing)
* BabyRun task: [google drive link](https://drive.google.com/file/d/1LZYNrQ8JUQEgT-rx_pTs_clwzeOHXqlI/view?usp=sharing)
 

<p align="right">(<a href="#top">back to top</a>)</p>

#### How to Run

The configuration of each script can be altered in two ways: modify a default config inside the script; or specify the optional argument on execution.

NOTE:
* env_manager.py should be executed **before** the algorithm.py
* IP and ALGO_PORT of algorithm.py should match the ip and port of env_manager.py script's machine IP and ALGO_PORT.

The environment manager can be executing using this command.
```
python env_manager.py
```
Configuration of environment e.g., number of parallel environments, ip and port of algorithm server, can be altered.
```
usage: env_manager.py [-h] [--executable EXECUTABLE] [--port PORT]

VECA Environment Manager

optional arguments:
  -h, --help            show this help message and exit
  --executable EXECUTABLE
                        Unity Executable Path
  --port PORT           Port exposed for algorithm
```

The agent algorithm can be executed using this command.

```
python algorithm.py
```

Configuration of algorithm e.g., number of parallel environments, port of algorithm server, can be altered.
```
usage: algorithm.py [-h] [--ip IP] [--port ENV_PORT] [--num_envs NUM_ENVS]

VECA Algorithm Server

optional arguments:
  -h, --help           show this help message and exit
  --ip IP              Envionment Manager machine's ip
  --port ENV_PORT      Environment Manager's port
  --num_envs NUM_ENVS  Number of parallel environments to execute
```

<p align="right">(<a href="#top">back to top</a>)</p>


<!-- CONTACT -->
## Contact

Kwanyoung Park - [@Github](https://github.com/GGOSinon) - william202@snu.ac.kr
Hyunseok Oh - [@Github](https://github.com/ohsai) - ohsai@snu.ac.kr

<!-- Project Link: [https://github.com/your_username/repo_name](https://github.com/your_username/repo_name) -->

<p align="right">(<a href="#top">back to top</a>)</p>


## Citation

<!-- ADD your bibtex -->
 If you find this work useful in your research, please cite
```
 @article{park2021veca,
  title={VECA: A Toolkit for Building Virtual Environments to Train and Test Human-like Agents},
  author={Park, Kwanyoung and Oh, Hyunseok and Lee, Youngki},
  journal={arXiv preprint arXiv:2105.00762},
  year={2021}
}
```
<p align="right">(<a href="#top">back to top</a>)</p>

<!-- ACKNOWLEDGMENTS -->
## Acknowledgments


This work was supported by Institute for Information & communications Technology Promotion(IITP) grant funded by the Korea government(MSIT) (No.2019-0-01371, Development of brain-inspired AI with human-like intelligence

<p align="right">(<a href="#top">back to top</a>)</p>
