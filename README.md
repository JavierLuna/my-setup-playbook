# My setup playbook

A playbook to configure my setup in my different workstations.

It is fully idempotent, meaning it'll work on both a fresh and already configured workstation.

## Requirements

- You have `ansible` installed.
- You have `brew` installed. (I'll add support to install it via this playbook eventually, sorry)
- If you use a SSH `dotfiles_remote` (see config.yml), you need to have the SSH keys configured yourself.
- Only Macs supported (M1 included). I only work with Macs nowadays so I don't have the need to support more platforms, sorry.

## Run the playbook

```
# First, install the requirements
ansible-galaxy install -r requirements.yml

# Run it!
ansible-playbook main.yml
```

I believe you are now either 1) enlightened by my playbook's experience or 2) angry as you found something did not work as you expected.

So I'm either 1) happy that you liked it! or 2) Sorry that you encountered problems. Either way, cut me a Github issue :)

## Tweak it

The playbook is configured for my use case in mind.
Please change values in `config.yml` to your liking.

### About the dotfiles repo

I have a [dotfiles repo](https://github.com/JavierLuna/dots) with config files for my tools.

By default, the playbook will clone my dotfiles and configure them, although you can change it to your liking (again, `config.yml`).

The playbook will check if your repo contains a `tasks` folder, will assume that those are ansible tasks, and include them.

You can use that to configure your repository as you like. Check out [how I do it](https://github.com/JavierLuna/dots/tree/main/tasks).
