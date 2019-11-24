Deep Cyber tinkering environment for pixelflut stuff.

# Getting started
Build your virtual environment, enter it, and install requirements

    virtualenv -ppython3 venv
    . venv/bin/activate
    pip install -r requirements.txt

To re-use the env later, enter it by just

    . venv/bin/activate

# Running the led-tetris-wall emulator
Inside your virtual env, call:

    ./led-tetris

# Running reels (or games)
Start the `led-tetris` as stated above. In a second terminal, enter your virtual env and enter `reels`.
There you can just run the reels:

    . venv/bin/activate
    cd reels
    python <reelname.py>

# Writing reels (or games)
You can just use fluter. It accepts PIL images or numpy arrays to set the complete wall in one command.
Take a look at `randimg.py` for the simplest example of sending PIL images. See `rauschen.py` for a simple 
numpy based example. Fluter is documented, see `fluter/__init__.py`.

# Running your reels on the real thing
Fluter connects to the pixelflut server set in the environment variable `PIXELFLUT_HOST` (format: `<host>:<port`). 
So if you are in the same network as the wall and it has the IP-address `192.168.33.44`, you can output to it 
running:

    `PIXELFLUT_HOST="192.168.33.44:1234" python <reel.py>
