# [Ansible] installation

This guide uses [Ansible](https://ansible.com) to automate installation of the
development tools you'll need.

[Ansible] is an IT Automation tool usually used for Linux servers. We don't need to know how ansible works, you'l just
install Ansible and run an ansible playbook to install the rest of the development tools we need.

The ansible playbook we've created installs the following tools:

At the command line:

- [zsh] - If you didn't already have it, your default shell will now be zsh.
- [nvm] - The node version manager, a program to help you manage different node
versions
- [Node.JS] - A JavaScript code runner, we'll be using this to run our JavaScript
- [zip and unzip] - Command line utilities to compress and uncompress zip files.
- [htop] - A nice way to view all the programs running on your computer from the terminal
- [pgcli] - A fancy postgres command line interface
- [starship] - A fancy replacment shell prompt which shows you lots of interesting information about your node version and information about your git repos.

And running as a background program:

- [PostgreSQL] - A database server we'll use to store data for our applications

## Running the Ansible Install and Playbook

This guide uses an automatic shell script to install ansible and run the playbook.

To get started open a terminal connected via SSH to your Oracle Cloud virtual computer and run
the following command:

```shell
curl https://raw.githubusercontent.com/FullstackAcademy/developer-playbook/main/oracle-cloud.sh | sh
```

Sit back and relax, this could take a while.

After this finishes, you should see a message saying the the setup is complete and
it is rebooting the server. This will disconnect you from the cloud machine.

Give it 5 or so minutes and try using SSH to log back in to your cloud machine.

Once you've logged back in, you should notice your prompt looks different. This is the [starship] prompt `>`,
and it can show you more information than just the folder you are in. (things like the node version of your project and information about your git branch.. Just trust us, this will be useful later.)

## Congratulations

You've now got all the software installed you need to be a real web developer!

Once you've got this completed you can move on an read about [extra resources]

[extra resources]:../common/extra-resources.md
[Ansible]:https://ansible.com
[Running the Ansible Playbook]:../common/ansible-playbook-setup.md
[zsh]:https://www.zsh.org/
[nvm]:https://github.com/nvm-sh/nvm
[Node.JS]:https://nodejs.org/en/
[htop]:https://htop.dev/
[pgcli]:https://www.pgcli.com/
[starship]:https://starship.rs
[PostgreSQL]:https://www.postgresql.org/
[zip and unzip]:http://infozip.sourceforge.net/
