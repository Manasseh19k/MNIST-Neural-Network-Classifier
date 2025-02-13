# MNIST Neural Network Classifier

This is a Python implementation of a simple feedforward neural network to recognize handwritten digits from the [MNIST dataset](http://yann.lecun.com/exdb/mnist/). It trains on the provided MNIST training set and evaluates its performance on the test set. It can also make predictions on user-provided images formatted as 28×28 PNG files.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Dependencies](#dependencies)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Additional Notes](#additional-notes)
- [License](#license)
- [Contact](#contact)

---

## Overview

This script:

1. Defines a `neuralNetwork` class that:
   - Initializes network parameters (input, hidden, output nodes).
   - Implements training via backpropagation.
   - Implements querying (forward propagation) for inference.
2. Trains the neural network on the MNIST training data (`mnist_train.csv`) over a specified number of epochs.
3. Evaluates network performance against the MNIST test data (`mnist_test.csv`) by measuring the fraction of correct predictions.
4. Demonstrates how to load and query the network with custom images (28×28 PNG files).

---

## Features

- **Neural Network Architecture**: Single hidden layer (configurable number of nodes).
- **Sigmoid Activation**: Uses `scipy.special.expit` as the activation function.
- **Weight Initialization**: Random normal distribution scaled by the inverse square root of node count.
- **Backpropagation**: Gradient-based weight updates.
- **Performance Metric**: Prints out the classification accuracy on the test set.
- **Custom Image Inference**: Reads and preprocesses user-generated 28×28 PNGs to classify digits.

---

## Dependencies

Make sure you have the following Python libraries installed:

- [NumPy](https://numpy.org/)
- [SciPy](https://www.scipy.org/)
- [Matplotlib](https://matplotlib.org/)
- [imageio](https://pypi.org/project/imageio/)

You will also need:

- A **Python 3** environment (3.6+ recommended).
- The [MNIST dataset](http://yann.lecun.com/exdb/mnist/) in CSV format:
  - `mnist_train.csv`
  - `mnist_test.csv`
- Custom PNG images (optional). Must be 28×28 pixels and grayscale.

---

## Installation

1. **Clone or download** the repository containing this script.

   ```bash
   git clone https://github.com/YourUsername/YourRepository.git
   ```

2. **Navigate** to the project directory:

   ```bash
   cd YourRepository
   ```

3. **(Optional) Create and activate a virtual environment**:

   ```bash
   # For Windows:
   python -m venv venv
   venv\Scripts\activate

   # For macOS / Linux:
   python3 -m venv venv
   source venv/bin/activate
   ```

4. **Install dependencies**:

   ```bash
   pip install numpy scipy matplotlib imageio
   ```

   *(If you have a `requirements.txt`, you can run `pip install -r requirements.txt` instead.)*

5. **Download the MNIST dataset** in CSV format. Place the files in the paths expected by the script, for example:
   - `C:/Users/fajos/Desktop/Neural Network/mnist_train.csv`
   - `C:/Users/fajos/Desktop/Neural Network/mnist_test.csv`

---

## Usage

1. **Edit file paths (if needed)**:  
   - Inside the script, locate the lines where `mnist_train.csv`, `mnist_test.csv`, and the custom images folder paths are defined. Update them to your local paths if they differ.

2. **Run the script**:

   ```bash
   python main.py
   ```
   - The script will:
     1. Initialize the neural network with specified input, hidden, and output nodes.
     2. Load and preprocess the MNIST training data.
     3. Train over the defined number of epochs.
     4. Load and evaluate on the MNIST test data, printing out the overall performance.
     5. (Optionally) Load custom 28×28 PNG images from the specified folder to run inference.

3. **Inspect Results**:
   - You’ll see a final accuracy (Performance) printed in the console for the test data.
   - The script also displays predictions for custom images and indicates whether they matched the true label.

---

## Project Structure

A typical layout might be:

```
YourRepository/
│
├── MNIST-Neural-Network-Classifier.ipynb # The script shown in the conversation
├── requirements.txt          # Optional: lists the required Python libraries
├──datasets
  ├── mnist_train.csv           # Place your MNIST training data here
  ├── mnist_test.csv            # Place your MNIST test data here
└── my_own_images/
    ├── 2828_my_own_0.png     # Example custom image
    ├── 2828_my_own_1.png
    └── ... etc.
```

*(Adjust filenames and directories as you see fit.)*

---

## Additional Notes

- **Image Preprocessing**: 
  - The script expects custom images to be 28×28 pixels, grayscale.  
  - Inverts pixel values (255.0 - pixel) to match the MNIST style.  
  - Scales them to a [0.01, 1.0] range.
- **Hyperparameters**:
  - `hidden_nodes = 200`, `learning_rate = 0.1`, `epochs = 5`.  
  - Adjust these values based on experimentation.
- **Performance**:
  - Final accuracy on the MNIST test set can vary, typically in the range of 94% to 97+% for this kind of network.
- **GPU / Speed**:
  - Since this is a simple network in Python (without libraries like TensorFlow/PyTorch), training speed is CPU-bound. For faster training, consider using optimized libraries or smaller datasets.

---

## License

If you plan to share or open-source this code, add the relevant license text here. For example:

```
This project is licensed under the MIT License - see the LICENSE file for details.
```

---

## Contact

- **Author**: [Frank Kendemah](https://github.com/YourGitHubProfile)  
- **Email**: [joseph74790@gmail.com](mailto:joseph74790@gmail.com)

If you have any questions, suggestions, or feedback, feel free to reach out!

---

*Happy coding and enjoy exploring neural networks with MNIST!*
