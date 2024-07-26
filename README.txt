# BOB = Current user to clone
# PETE = New user - create it BEFORE proceeding
# Create also a new temporary user, log out from existing session, log in with the temporary user

sudo bash
cd /home/bob
tar --exclude='./Documents' --exclude='./Downloads' cf - . | (cd ../pete; tar xf -)
chown -R pete:pete /home/pete
exit
