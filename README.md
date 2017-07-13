# Configure system-wide outgoing HTTP/HTTPS proxy
This Ansible role configures an outgoing HTTP/HTTPS proxy through system-wide environment variables.

## Requirements

RHEL or CentOS versions 6 or 7

## Role Variables

| Name        | Default value | Description                                                                 |
|-------------|---------------|-----------------------------------------------------------------------------|
| state       | present       | If `absent` delete the proxy configuration file (`/etc/profile.d/proxy.sh`) |
| http_proxy  | ""            | Proxy URL for HTTP requests                                                 |
| https_proxy | ""            | Proxy URL for HTTPS requests                                                |
| no_proxy    | []            | List of IPs, hosts and domains to access without proxy                      |

## Example Usage

`playbook.yml`:

```yaml
roles:
- role: ansible-role-system-proxy
  http_proxy: http://proxy.example.org:3128/
  https_proxy: http://proxy.example.org:3128/
  no_proxy:
  - 127.0.0.1
  - localhost
  - .example.org
```
