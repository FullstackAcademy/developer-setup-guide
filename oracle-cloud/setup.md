# Oracle Cloud with Ubuntu Linux Setup Guide (BETA)

*This feature is a **BETA** currently and may change*

Oracle Cloud is a service by Oracle, Inc. which allows you to allocate a virtual
computer in the cloud.  On their Always-Free tier, you can allocate two x86 based
Virtual computers with 1GB of RAM and a single CPU, plus as many ARM based virtual machines
as you would like as long as the total of those machines doesn't exceed 24GB of RAM
and 4 CPUs.  

In this guide be using a single ARM based cloud machine with 24GB of ram, 4 CPUs and
50 GB of disk space (although you can allocate up to 200GB total for your machines
on the free plan)

We will also be installing Ubuntu Linux on this computer, and we'll be using it remotely
from our computer via SSH, and via Visual Studio Code's Remote Development Extension.

## Registering for Oracle Cloud

Start by visiting the [Oracle Cloud website], and signing up for a new account.

![Oracle Cloud Registration]


You will need to enter a credit card to sign up, but as long as you only allocate
the virtual machines we recommend in this guide you won't be charged for anything.

## Allocating a machine

Once you finish registering, you should visit the [Oracle Cloud website] again and login.

You should see a screen like this:

![Oracle Cloud Landing Page]

Head to the hamburger menu in the top left corner, and open it up, the navigate to the Compute Link, then click on Instances.

![Oracle Cloud Menu]

Look on this screen for the blue "Create instance" button and press it.

![Create Instance Button]

On the next screen, enter a name for your compute instance, you can make this whatever you
would like as long as you remember it.

Skip the Placement section, and instead click Edit on the Image and Shape section

![Image and Shape]

Click Change Image, as we do not want to use Oracle Linux, we'll be using Ubuntu.

Wait for the list to load and select the Canonical Ubuntu Linux version (20.04 as of the writing of this guide)

![Ubuntu Linux]

Click *Select Image*.

Now click the *Change Shape* button.

We want to choose Virtual Machine, and Ampere for the Shape series.

![Select Shape]

Then scroll down and click the checkbox next to `VM.Standard.A1.Flex`

Drag the sliders to select 4 OCPUs and 24GB of RAM.

![Select CPU and Memory]

Finally click *Select Shape* which returns you to the Create Compute instance screen

Skip the Networking section, and move to the *Add SSH keys* section

If you already have an SSH key generated on your computer that you use for Github, you can select *Paste public keys* and paste your *public* key, just like you do on Github. If you have not yet done this, go back and follow [Github's guide to generating an SSH Key].

![Add SSH Key]

We can leave the Boot Volumes section alone. However, if you would like to increase your machine's disk space to more than 50GB you can check *Specify a custom boot volume size* and specify a value in Gigabytes, but do not exceed 200GB as that is all the free plan allows.

Once you have done all of this, click the blue *Create* button at the bottom and it should take you back to the 
instances screen, where you should see your instance in the process of starting up.

Wait for the state of your machine to be *Running* and then you are ready to ssh into it and try connecting for the first time!

We will need the Public IP from the table on the instances page. You will need to remember this IP from now on, so 
make a note of it somewhere.

Open a terminal (Powershell on Windows, Terminal on macOS)
and type the following, replacing "yourpublicIP" with the IP from the table.

```shell
ssh ubuntu@yourpublicIP
```

You should see a message containing text like this:

```text
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.11.0-1028-oracle aarch64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
```

You should see a prompt such as this with `yourmachinesname` replaced with whatever you named it.

```text
ubuntu@yourmachinesname:~$
```

**Congratulations!** You now have your very own computer in the cloud.  When you want to logout of the computer you can type `exit` or `logout` at the prompt or use `Control-D`.

Next move on to [Setting up VSCode Remote Development]

[Setting up VSCode Remote Development]:vscode-remote-development.md
[Add SSH Key]:images/ssh-keys.png
[Github's guide to generating an SSH Key]:https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
[Select CPU and Memory]:images/select-cpu-and-memory.png
[Select Shape]:images/select-shape.png
[Ubuntu Linux]:images/ubuntu-linux.png
[Image and Shape]:images/image-and-shape.png
[Create Instance Button]:images/create-instance-button.png
[Oracle Cloud Menu]:images/oracle-cloud-menu.png
[Oracle Cloud Landing Page]:images/oracle-cloud-landing-page.png
[Oracle Cloud website]:https://cloud.oracle.com
[Oracle Cloud Registration]:images/oracle-cloud-registration.png
