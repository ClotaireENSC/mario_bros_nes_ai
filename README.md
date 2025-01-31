## Prerequisites

Before installing the project, make sure you have the following installed on your machine:

- **Python 3.12** (or a compatible version)
- **Poetry** (for Python dependency management)
- **Required dependencies**: `bison`, `flex`, `boost`, `cmake`, `SDL2`, `xdotool`

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
sudo apt update && sudo apt install -y bison flex libboost-all-dev cmake libsdl2-dev xdotool
```

## Installation

1. **Clone the repository**
   ```sh
   git clone https://github.com/ClotaireENSC/mario_bros_nes_ai
   cd mario_bros_nes_ai
   ```

2. **Install Python dependencies**
   ```sh
   poetry install
   ```

3. **Compile the C++ project**
   ```sh
   cd src/SPMBros
   . buildproject.sh rebuild
   ```

## Execution

You can start an AI training session with:
```sh
cd src/mario_ai
poetry run python3 main.py
```

## Show best mario

Once you've trained your model, copy the neural network json you want into ```/mario_ai/saves``` as ```nn.json```.

Edit ```/mario_ai/main.py``` to execute ```simulation.load_best_simulation()```

Your best mario will play with 
```
poetry run python3 main.py
```

## Project Structure

- `SPMBros/` : Game engine source code
- `src/mario_ai/` : AI code
- `src/game_manager/` : Management of Super Mario Bros NES game window
- `src/network/` : Server and data parser
- `src/maps/` : JSON of all world maps (Only Map 1-1 was used, others may be incorrect)
- `src/saves/` : Saved game data
- `src/utils/` : Logger and JSON saver
