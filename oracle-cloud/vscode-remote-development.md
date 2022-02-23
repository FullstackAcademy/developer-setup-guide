## Setting up Visual Studio Code Remote Development

Using a remote computer in the cloud completely through the command line is possible
but would definitely be challenging. However, Microsoft has a very clever solution
to developing code using a remote server.

First, you will need to install [Visual Studio Code] for your computer if you
don't already have it.

Then head to the extensions tab of VSCode and search for Remote Development.

![VSCode Remote Extensions]

You'll want to install both of these extensions.

Once you have them installed (you may need to restart VSCode after installation), 
Check out the new icon that has appeared in your VSCode icon bar

![Remote Icon]

Click that and in the side panel verify that it says "SSH Targets" in the drop
down at the top. (If not, then select it from the list)

![SSH Targets Dropdown]

Then click the `+` button below that to add a new SSH host.

![SSH connection command]

In this box you'll type the same ssh command you used to connect from the terminal, making sure
to use the public IP address.

```shell
ssh ubuntu@publicipaddress
```

VSCode will then ask you which SSH config file you want to update, choose the first one from the list.

The IP address of your machine should now appear in the Remote Explorer sidebar.

Hover your mouse over the IP, and this icon will appear:

![Open remote icon]

When you click this, VSCode will attempt to connect to your remote machine.

After a few moments of initial setup, you should see a button in the bottom lower left of the
VSCode Window that says this:

```text
>< SSH: your public IP
```

You are now connected! You can open the Integrated Terminal in VSCode from the Terminal menu
and you should see the prompt from your remote computer.

To open a folder on the remote computer click the "Open Folder" button and then use the dropdown menu to navigate 
to the folder you want to open.

Typically you'll want to create a new folder for a single project or clone a new github repository from the command line and then use the *open folder* button to open that folder in VSCode to begin work.

You can also type `code .` inside a folder at the command line and it will open a brand new VSCode window for that folder just like you would normally do if you were working locally.

The biggest difference between working this way and working on your local computer is that you will need to manage your files from the command line with commands like `mkdir`,`cd`,`ls`,`cp`,`rm` and `mv`.  If you want more info, see the [Shell Basics] part of this guide, but come back here to finish the setup of your computer.

Now that we have an Ubuntu server, we can follow the regular Ubuntu setup instructions starting with [Installing Ansible]

[Installing Ansible]:ansible-setup.md
[Shell Basics]:../common/shell-basics.md
[Open remote icon]:images/open-remote-folder-icon.png
[SSH connection command]:images/ssh-connection-command.png
[SSH Targets Dropdown]:images/ssh-targets-dropdown.png
[Remote Icon]:images/remote-icon.png
[VSCode Remote Extensions]:images/vscode-remote-extensions.png
[Visual Studio Code]:https://code.visualstudio.com/
