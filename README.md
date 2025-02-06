# Super Mario Bros AI

This project is an AI-powered Super Mario Bros NES emulator using machine learning techniques.

## Prerequisites

Before installing the project, make sure you have the following installed on your machine:

- **Python 3.12** (or a compatible version)
- **Poetry** (for Python dependency management)
- **Required dependencies**: `bison`, `flex`, `boost`, `cmake`, `SDL2`, `xdotool` and `g++`

### Install Poetry

If you don’t have Poetry installed, you can install it using the following command:

```sh
curl -sSL https://install.python-poetry.org | python3 -
```

Then, add Poetry to your system PATH (if it’s not already available):

```sh
export PATH="$HOME/.local/bin:$PATH"
```

To verify the installation, run:

```sh
poetry --version
```

### Install Required Dependencies

On **Ubuntu/Debian**, run:

```sh
sudo apt update && sudo apt install -y bison flex libboost-all-dev cmake libsdl2-dev xdotool g++
```

## Installation

Follow these steps to set up the project on your local machine.

1. **Clone the repository**:
   ```sh
   git clone https://github.com/ClotaireENSC/mario_bros_nes_ai
   cd mario_bros_nes_ai
   ```

2. **Install Python dependencies**:

   Recommended : Disable Keyring
   ```sh
   poetry config keyring.enabled false 
   ```

   Install:
   ```sh
   poetry install
   ```

3. **Compile the C++ project**:
   ```sh
   cd src/SPMBros
   . buildproject.sh rebuild
   ```

## Execution

You can start an AI training session with:

Go to mario_ai folder:
```sh
cd ../mario_ai
```

Launch training:
```sh
poetry run python3 main.py
```

## Show Best Mario

Once you've trained your model, copy the neural network JSON file you want to use into `src/mario_ai/saves` as `nn.json`.

Then, edit `src/mario_ai/main.py` to execute `simulation.load_best_simulation()`.

Your best Mario will play with:

```sh
poetry run python3 main.py
```

(A nn.json file is already available in the project)

## Project Structure

- `SPMBros/`: Game engine source code
- `src/mario_ai/`: AI code
- `src/game_manager/`: Management of Super Mario Bros NES game window
- `src/network/`: Server and data parser
- `src/maps/`: JSON of all world maps (Only Map 1-1 was used, others may be incorrect)
- `src/saves/`: Saved game data
- `src/utils/`: Logger and JSON saver

