
# Dria Node Setup Script

This script automates the installation of **Dria**, **Ollama**, and required dependencies, then launches the Dria compute node in a persistent `screen` session.

---

### What It Does

- Updates & upgrades your system packages
- Installs essential tools: `sudo`, `curl`, `screen`
- Installs [Ollama](https://ollama.com) (local LLM runtime)
- Installs [Dria](https://dria.co) compute node
- Adds Dria binaries to your `PATH`
- Starts the Dria node inside a `screen` session (`screen -r dria`)

---

### Requirements

- Ubuntu 20.04 or newer (Debian-based)
- User with `sudo` privileges
- Internet access

---

### How to Use
1. **Install Dependencies**:
   if sudo command not found:
    ```bash
    apt install sudo
    ```
    else
   ```bash
    sudo apt-get update && sudo apt-get upgrade -y
    sudo apt install git -y
    ```
   
3. **Download the script**:
    ```bash
    git clone https://github.com/CodeDialect/Dria
    cd Dria
    chmod +x setup_dria.sh
    ```

4. **Run it**:
    ```bash
    ./setup_dria.sh
    ```

5. **Attach to the Dria screen session**:
    ```bash
    screen -r dria
    ```
To minimize the screen press ctrl + a + d
If the screen is detached or you're re-attaching later, use `screen -ls` to see running sessions.

---

### Notes

- Dria installs to: `~/.dria/bin`
- The script adds it to your `~/.bashrc` for future terminal sessions.
- If Dria installation appears incomplete, check the screen logs or re-run:
    ```bash
    dkn-compute-launcher start
    ```

---


### Troubleshooting

- **`dkn-compute-launcher: command not found`**  
  Make sure `~/.dria/bin` is in your `PATH`, or restart your terminal.

- **Dria screen not running?**  
  Run manually:  
  ```bash
  screen -S dria
  dkn-compute-launcher start
  ```

---

### License

This script is provided as-is for personal or development use. 
