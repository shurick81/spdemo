# Project for no brain SP 2019 sandbox installation

Tested on Windows but you can use it across any platform that is supported by Vagrant.

## Prerequisites

First of all, you will need git and Vagrant installed. If you miss any of these components, you can use the following Windows PowerShell snippet to fill the gap:

```PowerShell
Set-ExecutionPolicy Bypass -Force;
iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
choco install -y git
choco install -y vagrant
```

If one of installed components was Vagrant, you now need to reboot your machine.

Beside these two main components, you also want to install 
Vagrant Reload Provisioner plugin. Run following command to do that: `vagrant plugin install vagrant-reload`.

### Azure prerequisites

The only virtualization provider currenlty supported by this project is Azure, so before using this tool, please install necessary components and set variables.

#### Vagrant Azure Provider

In order to install this plugin, run `vagrant plugin install vagrant-azure`

#### Environmental variables

1. Create application and assign proper roles for managing Azure resources
2. Set values for following environment variables:
* ARM_CLIENT_ID
* ARM_CLIENT_SECRET
* ARM_SUBSCRIPTION_ID
* ARM_TENANT_ID

Use this instruction as a baseline: https://www.packer.io/docs/builders/azure-setup.html

## Usage

1. Clone the project to local directory via running following command:

`git clone https://github.com/shurick81/spdemo c:\projects\spdemo`

2. Open `spdemo` directory in command line
3. Run `vagrant up`
4. Connect to sp2019demo machine via following credential:

| User name | Password |
| --------- | ---------- |
| vagrant | Fractalsol365 |