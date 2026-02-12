# Switching Ubuntu from GUI to CLI (Terminal-Only Mode)
## Convert Ubuntu Desktop into a terminal-only system by disabling the graphical interface using systemd targets.
### Step 1: Check Current Default Target
```bash
systemctl get-default
```
excepted output 
  graphical.target
  
### Step 2: Change Default Target to CLI Mode
```bash
sudo systemctl set-default multi-user.target
  ```
This switches the system to boot into terminal mode.

### Step 3: Disable GNOME Display Manager (gdm)
```bash
sudo systemctl disable gdm
```
This prevents the GUI from starting automatically at boot.

### Step 4: Reboot the System
```bash
sudo reboot
```
After reboot, the system boots into:

tty1
login:namexx
password:admin@123
Terminal-only environment activated.

### Step 5: Verify Current Mode
```bash
systemctl get-default
```
Expected output:
multi-user.target
System successfully running in CLI mode.


### Switching Back to GUI Mode
```bash
sudo systemctl set-default graphical.target
```
```bash
sudo systemctl enable gdm
```
```bash
sudo reboot
```


graphical.target → GUI mode

multi-user.target → CLI mode

