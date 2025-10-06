
# How to Check, Open, and Close Programs on Linux 
A quick guide to managing open applications using the command line on  Linux.

# 1. Check Which Programs Are Running

```
ps -e
```
or
```
ps aux
```
<img width="658" height="111" alt="Screenshot 2025-10-06 at 17 30 24" src="https://github.com/user-attachments/assets/7212a73a-532e-45d7-b766-6be4b5129623" />

Shows all running processes, including background services.
For a live interactive view:
```
top
```
or, if you prefer a friendlier interface:
```
htop
```
Install htop
```
sudo dnf install htop -y
```
![htop](https://github.com/user-attachments/assets/f62afa96-c45e-4220-a0cc-e08c91bf9c5a)

# 2. List Only Open (Visible) Applications
```
wmctrl -l
```
If you don’t have wmctrl:
```
sudo dnf install wmctrl -y
```
Shows all currently open windows.
# 3. Open an Application
```
firefox &
gnome-terminal &
nautilus &
```
The "&" lets the app run in the background so the terminal stays usable.
# 4. Close (Quit) an Application
Find the process and kill it:
```
ps aux | grep firefox
kill <PID>
```
or more simply:
```
pkill firefox
```
