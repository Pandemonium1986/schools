# Ansible Lab 2021

You will discover Ansible through several exercises using the knowledge you have acquired during the training.

The aim is to provide you with a solid foundation in the use of Ansible.

-   Installing Ansible.
-   Managing an inventory.
-   Using ad-hoc commands.
-   Create playbooks.
-   Create and install reusable roles.

Some general remarks for the lab execution:

-   A good knowledge of basic linux controls is mandatory.
-   A good knowledge of ssh and the associated key management is mandatory.
-   You will need to use an ssh client of your choice ([putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), [kitty](http://www.9bis.net/kitty/#!index.md), [msys2](https://www.msys2.org/), [wsl2](https://docs.microsoft.com/en-us/windows/wsl/install-win10)) or a native ssh client for linux or mac.
-   L’ensemble de l’examen doit se faire sur la machine <span style="color:orange">docker</span>. La machine <span style="color:red">operator</span> n’est là que pour faire rebond.
-   The labs are executed from the <span style="color:red">operator</span> machine which is mutualized.
-   You all have your own personal  <span style="color:orange">docker</span> machine.

Good luck

## Verification of pre-requisites

1.  Login to the <span style="color:red">operator</span> machine.

```sh
ssh YOUR_PERSONAL_LOGIN@85.158.XX.XX
```

2.  From the <span style="color:red">operator</span> machine make sure that your <span style="color:orange">docker</span> machine is accessible.

```sh
ping -c 3 YOUR_PERSONAL_LOGIN-docker-vm
```

3.  Create a folder `ansible-lab` which contains a file named `init.txt` in which you write today's date and your first name.

```sh
mkdir -p ~/ansible-lab && touch ~/ansible-lab/init.txt && echo "2021-XX-XX YOUR_NAME Your_first_name" > ~/ansible-lab/init.txt
```

## Ansible

1.  Create a "myansible" virtualenv on the ansible machine at the root of your home directory.

```sh
python3 -m venv ~/myansible
```

2.  Activate the virtualenv.

```sh
cd ~ && source myansible/bin/activate
```

3.  Update "pip" from venv.

```sh
pip install --upgrade pip
```

4.  Install the latest version of ansible.

```sh
pip install ansible
```

5.  Check the installation by displaying the ansible version.

```sh
ansible --version
```

## Ssh

1.  Create an ssh key for the user YOUR_PERSONAL_LOGIN on the machine <span style="color:red">operator</span>.

```sh
ssh-keygen -q -b 4096 -t rsa -C ansible-lab -N "" -f ~/.ssh/id_rsa
```

2.  Copy the public key of the YOUR_PERSONAL_LOGIN user to the <span style="color:orange">docker</span> machine from the <span style="color:red">operator</span> machine.

```sh
ssh-copy-id docker@YOUR_PERSONAL_LOGIN-docker-vm
```

3.  Check the correct stripping of the keys by connecting to the haproxy blue green machines from the haproxy machine.

```sh
ssh docker@YOUR_PERSONAL_LOGIN-docker-vm hostname
```

## Ad-Hoc

## Playbook

## Roles
