# install-scripts
Installation on Ubuntu for a GPU-based deep learning development environment

This installation uses Ansible, which requires adding a PPA for the more recent versions:

```bash
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible git
```

There are different install scripts; it is recommended to start with `base.yaml` and add the others as needed:
+ `base.yaml`: basic system and python packages
+ `gpu.yaml`: CUDA, CUDNN on an NVIDIA system with deep learning packages for python
+ `extra.yaml`: extra utilities like editors and more

The scripts can either be pulled using `ansible-pull`:

```bash
sudo ansible-pull -U https://github.com/sureli/install-scripts.git <<filename>>
```

or can be downloaded and run locally using `ansible-playbook`:

```bash
git clone https://github.com/sureli/install-scripts.git
cd install-scripts
sudo ansible-playbook <<filename>>
```
