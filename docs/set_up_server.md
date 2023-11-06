# Setting up a server

Using OVH Ubuntu VPS.

1. Ssh to the server

## Security/Firewall

1. Ensure that ufw is installed
2. Run:
  1. sudo ufw allow ssh
  2. sudo ufw allow http
  3. sudo ufw allow https
  4. sudo ufw enable

[More on security](https://www.pcmatic.com/blog/how-to-secure-your-linux-server/)
