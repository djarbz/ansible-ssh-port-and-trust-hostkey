## Ansible-SSH-Port-and-Trust-Hostkey

This role will detect the ssh port the host is listening on, default(22). Then it will add the host to your trusted hostkeys default(~/.ssh/known_hosts)
You should not gather facts before this role is ran.

The tasks to detect the ssh port in detect_port.yaml is based on work by David Moreau Simard <dms@redhat.com>

### Vars
| Variable | Default | Description|
|-----------|----------|----------|
| skip_facts | false | By default, we will gather facts after we discover the correct SSH port. |
| known_hosts | ~/.ssh/known_hosts | Path the the known hosts to store the host keys in. |
| ansible_port | | Port in inventory that Ansible thinks it should connect on. |

### Todo
Check if hostkey has already been added and fail if different. Allow override to update hostkey.

Update SSH service to listen on custom port.