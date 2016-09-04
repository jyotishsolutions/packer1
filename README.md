# Packer

What Is Packer?

Packer is an open source tool for creating identical machine images for multiple platforms from a single source configuration. Packer is lightweight, runs on every major operating system, and is highly performant, creating machine images for multiple platforms in parallel. Packer does not replace configuration management like Chef or Puppet. In fact, when building images, Packer is able to use tools like Chef or Puppet to install software onto the image.

A machine image is a single static unit that contains a pre-configured operating system and installed software which is used to quickly create new running machines. Machine image formats change for each platform. Some examples include AMIs for EC2, VMDK/VMX files for VMware, OVF exports for VirtualBox, etc.

https://www.packer.io/intro/

packer 1
# installation
```
$mkdir packer
$cd packer
$ wet https://releases.hashicorp.com/packer/0.9.0/packer_0.9.0_linux_386.zip
$unzip packer_0.9.0_linux_386.zip
$mv packer /usr/bin
$ packer --version
0.9.0
```

# example1.json
```
In this example we are just create a aws AMI [ cloning a existing ] aws ubuntu t2.micro ami

Command to execute the example1.json  [ replace aws access key and secret key with your account details ]

$ packer validate example2.json 
Template validated successfully.

$ packer build \
    -var 'aws_access_key=xxxx' \
    -var 'aws_secret_key=Ytrtretret4654654654654regrgtretret' \
    example.json
```
# aws_ami_provisioning 
```
The aws_ami_provisioning folder Simple and small process provision a AWS AMI with apache and customer index.html file.
we are using following softwares - packer ansible and aws account.
To execute it..  [ replace aws access key and secret key with your account details ]

$cd aws_ami_provisioning
$sudo packer build \
    -var 'aws_access_key=xxxxx' \
	-var 'aws_secret_key=xxxx' 
	\   example2.json
```

```
## packer 1 Usage
Include the `cloudwatchlogs` role in your playbook yml like this:

    - role: cloudwatchlogs
      logs:
        - file: /var/log/syslog
          format: "%b %d %H:%M:%S"
          group_name: syslog
        - file: /var/log/my_app_log
          format: "%b %d %H:%M:%S"
          group_name: my-app-log
```

