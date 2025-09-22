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
```bash
cd ~/project
rm -rf build cmake-build-* CMakeFiles CMakeCache.txt
cmake -S . -B build
cmake --build build
```

**Submission script**

Create `submit.sh`:
```bash
vim submit.sh
```

Enter or Paste:
```bash
#!/usr/bin/env bash
SUBMIT=~gopal-assignments/csci6410-fall25/bin/submit

FILES=$(find . -type f \( -name "*.c" -o -name "*.h" -o -name "CMakeLists.txt" -o -name "Makefile" -o -iname "readme*" \) -not -path "./build/*" -not -path "./cmake-build-*/*")

${SUBMIT} 1 ${FILES}
```

Make `submit.sh` executable and run:
```bash
chmod +x submit.sh
./submit.sh
```
⤷ `+x` adds the execute permission for all users to the existing permissions
