# Landmark Detection & Robot Tracking (SLAM)

## Project Overview

In this project, we will implement SLAM (Simultaneous Localization and Mapping) for a 2 dimensional world. We will combine robot sensor measurements and movement to create a map of an environment from only sensor and motion data gathered by a robot, over time. SLAM gives a way to track the location of a robot in the world in real-time and identify the locations of landmarks such as buildings, trees, rocks, and other world features. This is an active area of research in the fields of robotics and autonomous systems. 

*Below is an example of a 2D robot world with landmarks (purple x's) and the robot (a red 'o') located and found using *only* sensor and motion data collected by that robot. This is just one example for a 50x50 grid world; in your work you will likely generate a variety of these maps.*

<p align="center">
  <img src="./images/robot_world.png" width=50% height=50% />
</p>

The project will be broken up into three Python notebooks; the first two are for exploration of provided code, and a review of SLAM architectures, so **only Notebook 3 and the `robot_class.py` file will need to be completed**:

__Notebook 1__ : Robot Moving and Sensing

__Notebook 2__ : Omega and Xi, Constraints 

__Notebook 3__ : Landmark Detection and Tracking 


## Project Instructions

Instructions for creation and activation of Python virtual environment are given below.

### Local Environment Instructions

1. Clone the repository, and navigate to the downloaded folder.
```
git clone https://github.com/udacity/P3_Implement_SLAM.git
cd P3_Implement_SLAM
```

2. Create (and activate) a new environment, named `cv-nd` with Python 3.6. If prompted to proceed with the install `(Proceed [y]/n)` type y.

	- __Linux__ or __Mac__: 
	```
	conda create -n cv-slam python=3.6
	source activate cv-slam
	```
	- __Windows__: 
	```
	conda create --name cv-slam python=3.6
	activate cv-slam
	```
	
	At this point, the command line should look something like: `(cv-slam) <User>:Implement_SLAM <user>$`. The `(cv-slam)` indicates that your environment has been activated, and we can proceed with further package installations.

6. Install a few required pip packages, which are specified in the requirements text file (including OpenCV).
```
pip install -r requirements.txt
```

## Notebooks

1. Navigate back to the repo. (The source environment should still be activated at this point.)
```shell
cd
cd Implement_SLAM
```

2. Open the directory of notebooks, using the below command. We will see all of the project files appear in your local environment; open the first notebook and follow the instructions.
```shell
jupyter notebook
```

3. Once any of the project notebooks are open, make sure you are in the correct `cv-slam` environment by clicking `Kernel > Change Kernel > cv-slam`.

__NOTE:__ While some code has already been implemented as started code, we will need to implement additional functionality as described below.

### `robot_class.py`: Implementation of `sense`

#### Implement the `sense` function
|  Implement the `sense` function for the robot class. |  Implement the `sense` function to complete the robot class found in the `robot_class.py` file. This implementation should account for a given amount of `measurement_noise` and the `measurement_range` of the robot. This function should return a list of values that reflect the measured distance (dx, dy) between the robot's position and any landmarks it sees. One item in the list has the format: `[landmark_index, dx, dy]`. |

### Notebook 3: Implementation of `initialize_constraints`

#### Initialize omega and xi matrices 
|  Initialize constraint matrices. |  Initialize the array `omega` and vector `xi` such that any unknown values are `0` the size of these should vary with the given `world_size`, `num_landmarks`, and time step, `N`, parameters. |


### Notebook 3: Implementation of `slam`

#### Update the constraint matrices as you read sensor measurements 
|  Iterate through the generated `data` and update the constraints. |  The values in the constraint matrices should be affected by sensor measurements *and* these updates should account for uncertainty in sensing. |

#### Update the constraint matrices as you read robot motion data 
|  Iterate through the generated `data` and update the constraints. |  The values in the constraint matrices should be affected by motion `(dx, dy)` *and* these updates should account for uncertainty in motion. |

#### `slam` returns a list of robot and landmark positions, `mu`
|  The result of slam should be a list of robot and landmark positions, `mu`. |  The values in `mu` will be the x, y positions of the robot over time and the estimated locations of landmarks in the world. `mu` is calculated with the constraint matrices `omega^(-1)*xi`. |


#### Analyze the final pose
|  Compare the `slam`-estimated and *true* final pose of the robot; analyze why these values might be different. |

#### `slam` passes all tests
| Test the implementation of `slam`.  |  There are two provided test_data cases, test the implementation of slam on them and see if the result matches.|

IDEA: This project is a part of the Udacity Computer Vision nanodegree curriculum.

LICENSE: This project is licensed under the terms of the MIT license.
