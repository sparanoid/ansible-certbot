# sparanoid.certbot

Ansible role for python2-certbot

## Supported Plugins

- python2-certbot-dns-cloudflare
- python2-certbot-dns-route53
- python2-certbot-nginx

## Available Tags

- `certbot`
- `certbot_setup`
- `certbot_setup_plugin`
- `certbot_setup_plugin_credentials`
- `certbot_setup_cron`
- `certbot_generate`

## Site Configurations

```yaml
certbot_email: email@domain.tld
certbot_sites:
  server_hostname:
    - { domain: "*.domain.tld,domain.tld", plugin: "dns-cloudflare", args: "--dns-cloudflare-credentials ~/.secrets/certbot/cloudflare.ini" }
    - { domain: "*.domain2.tld,domain2.tld", plugin: "dns-route53" }
    - { domain: "domain3.tld,www.domain3.tld", plugin: "nginx" }
    # default to `nginx` if `plugin` is not defined
    - { domain: "domain4.tld,www.domain4.tld" }
```

## License

MIT
