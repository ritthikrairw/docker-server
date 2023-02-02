
# How to Generate SSL Key


## For Windows system (Local Development)

Run this command for install choco

```bash
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

Run this command for install mkcert

```bash
choco install mkcert
```

Run this command for install mkcert CA ROOT

```bash
mkcert -install
```

Run this command for generate cert and key

```bash
mkcert -key-file private.pem -cert-file certificate.pem "docker.localhost" "*.docker.localhost" "domain.local" "*.domain.local"
```

Generate dhparam.pem

```bash
apk add openssl # incase no openssl
openssl dhparam -out dhparam.pem 2048
```