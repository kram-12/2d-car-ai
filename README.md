<h1 align="center">2D Self-Driving Car Simulation</h1>

This project is a 2D self-driving car simulation developed in Python using Pygame. It features a Q-learning agent that learns to navigate a circuit by interacting with its environment and optimizing its actions through a reward system.  

## Features
- **Reinforcement Learning**: Implements Q-learning to train an AI agent to navigate a circuit.
- **Sensor System**: The vehicle is equipped with sensors that provide information about its surroundings, allowing for informed decision-making.
- **Visual Feedback**: Real-time visualization of the vehicle's performance, including speed, scores, and sensor values.
- **Logging**: Tracks the performance of the agent across episodes and stores it for further analysis.
- **Dual Mode Operation**: Supports both training and simulation modes through the `TRAINING_MODE` configuration.

## Setup Instructions

### Prerequisites
To run this project, you'll need Python 3.x along with the Pygame library. You can install the required libraries using pip:
```bash
pip install pygame
````

### Installation

1. Clone the repository:

```bash
git clone https://github.com/matiascarabella/self-driving-ai.git
cd self-driving-ai
```

## Usage

1. Run the simulation:

```bash
python3 main.py
```

2. Let the AI agent learn through Q-learning <sup>Or control the vehicle yourself by setting `MANUAL_CONTROL = True` in the `config.py` file</sup>

## Configuration

The project includes a `config.py` file where you can adjust various parameters:

### Session Configuration

```python
SESSION_CONFIG = {
    "TRAINING_MODE": True,    # Toggle between training and evaluation modes
    "NUM_EPISODES": 50,       # Number of episodes to run
    "EPISODE_DURATION": 20,   # Duration of each episode in seconds
    "MANUAL_CONTROL": False   # Enable manual control with arrow keys
}
```

### Agent Modes

* **Training Mode** (`TRAINING_MODE = True`):

  * Used for training the agent
  * Agent explores new actions using epsilon-greedy strategy
  * Updates Q-table based on experiences
  * Behavior varies between runs due to exploration

* **Evaluation Mode** (`TRAINING_MODE = False`):

  * Used for testing or demonstrating learned behavior
  * Agent uses learned knowledge deterministically
  * No Q-table updates or exploration
  * Consistent behavior between runs

### Other Configuration Options

* Vehicle settings (dimensions, speed, acceleration)
* Q-learning parameters (learning rate, discount factor, exploration rate)
* Window and display settings

## Log Files

The training results are logged within the `logs` folder in a file named `v1.txt`, which records the episode number and the final score. This log can be used for performance analysis and progress visualization.

## Visualizing Progress

To visualize the agent's progress, use the `visualization/plot_progress.py` script:

```bash
python3 visualization/plot_progress.py
```

This will generate a graph of scores across episodes, highlighting the 100-episode moving average to illustrate the agent's improvement over time.
