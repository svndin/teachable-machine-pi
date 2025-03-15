# teachable-machine-pi
Implementation of Google Coral's Teachable Machine for Raspberry Pi Zero 2 W with Coral USB Accelerator.


![teachable](https://github.com/svndin/teachable-machine-pi/blob/main/coral-pi-img.jpg)


This project is an implementation of the [Teachable Machine](https://github.com/google-coral/project-teachable) example by Google Coral on a Raspberry Pi Zero 2 W with the Coral USB Accelerator.

## Requirements

- **Hardware**:
  - Raspberry Pi Zero 2 W
  - Coral USB Accelerator

- **Software**:
  - Operating System: Raspbian GNU/Linux 10 (buster)
  - Python Version: 3.7 (default in Raspbian Buster)

## Installation

1. **Update the system**:

    ```bash
    sudo apt-get update
    sudo apt-get upgrade
    ```

2. **Install Edge TPU runtime**:

    Add the Coral package repository and install the Edge TPU runtime:

    ```bash
    echo "deb https://packages.cloud.google.com/apt coral-edgetpu-stable main" | sudo tee /etc/apt/sources.list.d/coral-edgetpu.list
    curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
    sudo apt-get update
    sudo apt-get install libedgetpu1-std
    ```

3. **Install PyCoral library**:

    Install the PyCoral library, which is required for communication with the Coral USB Accelerator:

    ```bash
    sudo apt-get install python3-pycoral
    ```

4. **Clone the project repository**:

    Clone the original Teachable Machine repository from Google Coral:

    ```bash
    git clone https://github.com/google-coral/project-teachable.git
    cd project-teachable
    ```

5. **Install dependencies**:

    Install the required Python dependencies:

    ```bash
    bash install_requirements.sh
    ```

## Usage

1. **Connect the Coral USB Accelerator**:

    Plug the Coral USB Accelerator into the Raspberry Pi Zero 2 W.

2. **Start Teachable Machine**:

    Run the following script to start the Teachable Machine:

    ```bash
    bash run.sh
    ```

3. **Train classes**:

    - **Key 1**: Trains Class 1 with the current camera image.
    - **Key 2**: Trains Class 2 with the current camera image.
    - **Key 3**: Trains Class 3 with the current camera image.
    - **Key 4**: Trains Class 4 with the current camera image.
    - **Key Q**: Exits the program.

    Point the camera at an object and press the corresponding key to assign it to a class. Repeat this process for different objects and classes. Once trained, the system will classify detected objects in real-time.

## Notes

- **Python Version**: Ensure you are using Python 3.7, as newer versions may not be compatible.
- **Operating System**: This project has been tested on Raspbian Buster. Other versions or distributions may cause compatibility issues.
- **Performance**: The Raspberry Pi Zero 2 W has limited resources. For better performance, a more powerful Raspberry Pi is recommended.

## References

- Original Project: [https://github.com/google-coral/project-teachable](https://github.com/google-coral/project-teachable)
- Coral Documentation: [https://coral.ai/docs/accelerator/get-started/](https://coral.ai/docs/accelerator/get-started/)
