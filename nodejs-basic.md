You can use brew install node@4, brew install node@6, or brew install node@8 command to install LTS version of Node via Homebrew.

If another version of Node is already installed, you should uninstall it first to avoid conflicts.

Also note that LTS versions of node (e.g. node@10) are keg-only and must either be linked with --force (brew link --force node@12) or you need to add the binary to your path by running:
``` bash
echo 'export PATH="/usr/local/opt/node@12/bin:$PATH"' >> ~/.bashrc
```
