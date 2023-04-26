You can install terraform by simply downloading the binary and moving it to /usr/local/bin directory

```bash
wget https://releases.hashicorp.com/terraform/1.4.5/terraform_1.4.5_linux_386.zip
unzip terraform_1.4.5_linux_386.zip
mv terraform /usr/local/bin
terraform version

```

 You can also use a package manager

## Ubuntu
```bash
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```