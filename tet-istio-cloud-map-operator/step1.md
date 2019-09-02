## First, install Envoy

Update apt index
`sudo apt-get update`{{execute}}

Install packages required for apt to communicate via HTTPS
`sudo apt-get install -y \
apt-transport-https \
ca-certificates \
curl \
gnupg-agent \
software-properties-common`{{execute}}

Add the Tetrate GPG key
`curl -sL 'https://getenvoy.io/gpg' | sudo apt-key add -`{{execute}}

Verify the key has the fingerprint 5270 CEAC 57F6 3EBD 9EA9 005D 0253 D0B2 6FF9 74DB.
`apt-key fingerprint 6FF974DB`{{execute}}

Add the stable repository
`sudo add-apt-repository \
"deb [arch=amd64] https://dl.bintray.com/tetrate/getenvoy-deb \
$(lsb_release -cs) \
stable"`{{execute}}

Install Envoy binary
`sudo apt-get update && sudo apt-get install -y getenvoy-envoy`{{execute}}

Great! Verify Envoy has been installed:

`envoy --version`{{execute}}

Congratulations! Next: getting Envoy set up as a basic front proxy for Google and Bing.  
