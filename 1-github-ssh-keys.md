I generate SSH keys for Github a lot. Here’s how to make them and add them to your Github account as fast as humanly possible.

* Open <https://github.com/settings/ssh/new> in a new tab
* `ssh-keygen -t rsa -b 4096` in your terminal. Make a passphrase. Save the key in the default location.
* `eval "$(ssh-agent -s)"; ssh-add ~/.ssh/id_rsa; cat ~/.ssh/id_rsa.pub` in your terminal.
* Copy and paste the terminal output into the Github page you opened before.
