# nginx-mod-backup
Encountered a configuration error with Nginx recently? Say no more. Introducing nginx-mod-restore, your solution to swiftly tackle missing module mishaps and restore seamless operation.

## The Error Encounter:
Ever stumbled upon a confounding Nginx configuration error like this?

```bash
[emerg] 64631#64631: open() "/etc/nginx/modules-enabled/50-mod-ssl-ct.conf" failed (2: No such file or directory) in /etc/nginx/nginx.conf:5
nginx: configuration file /etc/nginx/nginx.conf test failed
```

Surprising, isn't it? Especially when everything seemed shipshape just a while ago on the same version, nginx/1.24.0.

## The Culprit:
A quick peek under the hood using ls -la /etc/nginx/modules-enabled/ reveals a broken symbolic link pointing to 50-mod-ssl-ct.conf -> /usr/share/nginx/modules-available/mod-ssl-ct.conf. Ah, the missing puzzle piece: the Nginx module mod-ssl-ct.conf nowhere to be found.

## The Solution:
But fret not! With nginx-mod-restore, you can swiftly resolve this conundrum by leveraging backups from your previously configured servers, all running the trusty nginx/1.24.0.

### Usage:
```bash
nginx-mod-restore [options]
```

Empower your Nginx experience with nginx-mod-restore. Don't let configuration errors turn your website off. Stay resilient, stay smooth-sailing with nginx-mod-restore.