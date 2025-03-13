* Install Ansible 
```
sudo apt install ansible -y
```

- If you facing this issue .
`ansible --version `
`ERROR: Ansible requires the locale encoding to be UTF-8; Detected ISO8859-1.`
1. Check Current Locale Settings.
```
locale
```
2. Generate the UTF-8 Locale.
```
sudo locale-gen en_US.UTF-8
```
3.  Set the Locale.
```
export LC_ALL=en_IN.UTF-8
```
Add this line to your `~/.bashrc` or `~/.zshrc` file to make it permanent:
```
echo 'export LC_ALL=en_IN.UTF-8' >> ~/.bashrc
```
```
source ~/.bashrc
```
```
ansible --version
```
- check ansible man page[doc]
```
ansible-doc -l 
```
- check specific module commands.
```
ansible-doc -l | grep docker
```
