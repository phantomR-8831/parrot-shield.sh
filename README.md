# phantomR-8831 Laboratory 🧪

Welcome to the sandbox. This repository holds my custom-baked automation tools, system resilience modules, and experimental calculators. Built for tech geeks who care about uptime and hate system crashes.

---

## Core Modules Architecture

### 1. Parrot OS Docker Shield (`parrot-shield.sh`)
* **The Mess:** You deploy a shady Docker container or spin up an aggressive node. It spawns hidden layers, floods the logs, starves your disk space, and *boom* — your pentest distro panics and freezes.
* **The Fix:** A bulletproof bash automation tool. It forces a system state snapshot via `Timeshift` before you do anything stupid, and introduces a one-click purge to wipe out Docker junk.

### 2. Resilience Model (`resilience_model.py`)
Python core engine built to simulate system stress and model high-availability uptimes under heavy workloads.

### 3. Building Calculator (`building_calc.py`)
Custom mathematical module for algorithmic infrastructure estimations.

---

## Parrot OS Docker Shield Source Code

Let's look under the hood. Here is the fully commented source code of the shield script. Check out how the logic flows:

```bash
#!/bin/bash

# =====================================================================
#  PARROT OS SHIELD & RESTORE SCRIPT (2026 Edition)
#  Maintainer: phantomR-8831
#  Note: Run this with sudo privileges or the system will reject us!
# =====================================================================

while true; do
    clear
    echo "================================================="
    echo "   PARROT OS SHIELD & RESTORE SCRIPT (2026)      "
    echo "================================================="
    echo "1. Create System Snapshot (Before running Docker)"
    echo "2. Full System Restore from the last snapshot"
    echo "3. Purge Docker Garbage (Prevent disk exhaustion)"
    echo "4. Exit"
    echo "================================================="
    read -p "Select action [1-4]: " choice

    case $choice in
        1)
            # Okay, look here: first, we initialize the backup routine.
            # We are calling Timeshift to capture the current stable state of the OS
            # before any untrusted container messes up our environment.
            echo "[+] Initializing system snapshot routine..."
            timeshift --create --comments "Pre-Docker Sandbox State" --tags D
            
            # Boom! State saved. Now we can safely proceed with experiments.
            echo "[+] Snapshot successfully deployed!"
            echo ""
            read -p "Press [Enter] to jump back to main menu..." temp
            ;;
        2)
            # Watch out! Here comes the panic button.
            # If a container broke the dependencies or corrupted the system,
            # we roll back time to our last known good configuration.
            echo "[!] WARNING! System rollback sequence is initiating."
            echo ""
            read -p "Are you absolutely sure about this? (y/n): " confirm
            if [ "$confirm" = "y" ]; then
                # Pulling the trigger. Timeshift takes over the bootloader here.
                timeshift --restore
            else
                # Safe escape route if you misclicked.
                echo "Rollback aborted. No changes made."
                read -p "Press [Enter] to jump back to main menu..." temp
            fi
            ;;
        3)
            # Alright, now look at this cleanup cycle.
            # Docker layers can hoard gigabytes of cached junk silently.
            # We run an aggressive prune sequence to force-evict all unused volumes and containers.
            echo "[+] Initiating deep Docker purge sequence..."
            docker system prune -a --volumes -f
            
            # Disk space reclaimed. The host system can breathe again.
            echo "[+] Storage sanitized successfully!"
            echo ""
            read -p "Press [Enter] to jump back to main menu..." temp
            ;;
        4)
            # Graceful shutdown of the script environment.
            echo "Exiting script environment. Stay safe out there."
            exit 0
            ;;
        *)
            # Standard exception handling for fat fingers.
            echo "Invalid selection token. Let's try that again..."
            sleep 2
            ;;
    esac
done

Compilation & Execution Guide
Grant execution permissions to the script:

Bash
   chmod +x parrot-shield.sh
Execute with superuser privileges to let Timeshift do its magic:

Bash
   sudo ./parrot-shield.sh
Support the Laboratory ☕
If this tool saved your Linux environment from a total meltdown, prevented a kernel panic, or saved your NVMe drive from getting choked by Docker logs, consider backing the project. Fuel the compiler!

Ethereum / EVM Mainnet: 0x43da3f65EE51dC498F5AD8065f8FdC39397B205e

Polygon (Low gas fee option): 0x43da3f65EE51dC498F5AD8065f8FdC39397B205e

Bitcoin (BTC): bc1q0www72wea09ayksc9ll05n795vdm5ghnujryvr
