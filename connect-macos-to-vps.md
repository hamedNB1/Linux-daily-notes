```bash
# Connect macOS Terminal to Ubuntu VPS

# This guide explains how to connect your macOS Terminal to an Ubuntu VPS using SSH.
# It also includes optional SSH key setup, changing your VPS password, and troubleshooting tips.

# --------------------------------------------------------------------------
# Prerequisites
# - VPS IP address
# - SSH username (usually `root` or a custom user)
# - Password or SSH key
# - macOS Terminal
# --------------------------------------------------------------------------

# Step 1: Open Terminal
# Press Command + Space, type Terminal, and press Enter.

# --------------------------------------------------------------------------
# Step 2: Connect via SSH
ssh username@server_ip

# Example:
ssh root@123.456.78.90

# On first connection, you may see:
# The authenticity of host '123.456.78.90 (123.456.78.90)' can't be established.
# ECDSA key fingerprint is SHA256:...
# Are you sure you want to continue connecting (yes/no)?
# Type yes and press Enter to continue.

# --------------------------------------------------------------------------
# Step 3: Enter Password
# After running the SSH command, you will be prompted for your VPS password:
# username@server_ip's password:
# Type your password (characters will not show for security) and press Enter.
# Once entered correctly, you will be logged into your VPS.

# --------------------------------------------------------------------------
# Step 4: Optional - SSH Key Setup (Password-less Login)

# 1. Generate a key pair (if you don’t have one already):
ssh-keygen -t rsa -b 4096

# 2. Copy your public key to the VPS:
ssh-copy-id username@server_ip

# 3. Connect without a password:
ssh username@server_ip

# --------------------------------------------------------------------------
# Step 5: Change VPS Password
passwd

# You will be prompted to enter the current password.
# Then enter your new password and confirm it.
# Password must meet VPS security requirements (usually at least 8 characters).

# Example:
# Current password:
# New password:
# Retype new password:
# passwd: password updated successfully

# --------------------------------------------------------------------------
# Tips & Best Practices
# - Use SSH keys for secure, password-less login.
# - Keep your private key safe (~/.ssh/id_rsa).
# - Avoid using root for regular tasks; create a sudo user.
# - Consider changing the default SSH port for better security.
# - Always use strong, unique passwords.

# --------------------------------------------------------------------------
# Troubleshooting
# - Connection timed out → Check VPS firewall and ensure port 22 is open.
# - Permission denied → Verify username, password, or SSH key.
# - SSH key issues → Check permissions of private key: chmod 600 ~/.ssh/id_rsa
# - Host key changed warning → If connecting to a new server or reinstalled VPS, remove old key from ~/.ssh/known_hosts.
# - Cannot change password → Make sure you are typing the current password correctly and the new password meets security requirements.
