# clone-user-ubuntu

# BOB = Current user to clone
# PETE = New user - create it BEFORE proceeding
# Create also a new temporary user, log out from existing session, log in with the temporary user



# Ensure BOB is logged out before proceeding
# Create PETE user before running this script

# Switch to root privileges for the following commands
sudo tar cf - -C /home/bob . | sudo tar xf - -C /home/pete
sudo chown -R pete:pete /home/pete
exit


## TO EXCLUDE SOME FOLDERS:
# sudo tar cf - --exclude=/home/bob/Documents --exclude=/home/bob/Downloads -C /home/bob . | sudo tar xf - -C /home/pete

sudo tar cf - \
  --exclude=/home/bob/Music \
  --exclude=/home/bob/Documents \
  --exclude=/home/bob/Pictures \
  --exclude=/home/bob/Dropbox \
  --exclude=/home/bob/VirtualBox\ VMs \
  --exclude=/home/bob/Downloads \
  -C /home/bob . | sudo tar xf - -C /home/pete
sudo chown -R pete:pete /home/pete
