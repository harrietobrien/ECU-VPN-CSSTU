**Copy your project to the server using `scp` (Secure Copy Protocol):**
```bash
scp -r ~/project username@csstu.intra.ecu.edu:~
```
⤷ `-r` initiates recursive secure copy (necessary for directories)
> **Note:** Replace `username` with your PirateID. 

After setting up `Host ecu` alias in `~/.ssh/config`:
```bash
scp -r ~/project ecu:~
```

**Rebuild on the server:**

Run cmake with path to root directory (`.`) and path to build directory (`build`)
```bash
cd ~/project
cmake -S . -B build --fresh
cmake --build build
```
⤷ `--fresh` performs a fresh configuration of the build tree, removing any existing `CMakeCache.txt` file and associated `CMakeFiles/` directory, and recreates them from scratch.
