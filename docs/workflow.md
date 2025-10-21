**Copy your project to the server using `scp` (Secure Copy Protocol):**
```bash
project="/path/to/project"

scp -r "${project}" username@csstu.intra.ecu.edu:~
```
⤷ `-r` initiates recursive secure copy (necessary for directories)
> **Note:** Replace `username` with your PirateID. 

After setting up `Host ecu` alias in `~/.ssh/config`:
```bash
scp -r "${project}" ecu:~
```

**Rebuild on the server:**
```bash
cd "${project}"
cmake -S . -B build --fresh
cmake --build build
```
**Bundle as binary archive for submission:**
```bash
cd ..
find "${project}" -type -f | cpio -o > "${project}.cpio"
```