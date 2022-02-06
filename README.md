# Pterodactyl-ansible-manager

- You need to prepare Ansible control machine environment.
- Make sure you already add the target host's SSH public key to the control machine. Also, you need to setup `./inventories/host.yml` properly.

## Playbooks

- Playbooks are under `./playbooks` directory

### health\_check.yml

- Add pterodactyl container UUIDs you want to monitor in `./containers/container.yml`.
- You can find the UUID in the Pterodactyl panel -> Click a server -> Settings -> Debug Information -> Server ID.
