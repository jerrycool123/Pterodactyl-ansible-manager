# Pterodactyl-ansible-manager

- You need to prepare Ansible control machine environment.
- Make sure you already add the target host's SSH public key to the control machine. Also, you need to setup `./inventories/host.yml` properly.

## Playbooks

- Playbooks are under `./playbooks` directory.

### fetch\_servers.yml

- You need to provide 2 environment variables:
  - `PANEL_URL`: Your Pterodactyl panel URL.
  - `APPLICATION_API_KEY`: Your Pterodactyl application api key. You can create one by navigating to the admin panel -> Application API -> Create New.
- Run `ansible-playbook -i ./inventories/host.yml ./playbooks/fetch_servers.yml`.
- You are suggested to run this first to create the proper mapping of container UUIDs and names.

### health\_check.yml

- Add pterodactyl container UUID-name mappings you want to monitor in `./containers/container.yml`.
- You can find the UUID in the Pterodactyl panel -> Click a server -> Settings -> Debug Information -> Server ID. But if you have run `fetch_servers.yml`, every UUID-name mappings should have already been generated automatically. Then, you can filter them on demand.
- Run `ansible-playbook -i ./inventories/host.yml ./playbooks/health_check.yml`.
