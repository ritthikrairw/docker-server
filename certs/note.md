## How to Generate SSL Key

---

### For Windows system (Local Development)

---

Run this command for install choco

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

Run this command for install mkcert

`choco install mkcert`

Run this command for install mkcert CA ROOT

`mkcert -install`

Run this command for generate cert and key

`mkcert -key-file mkcert-ssl.key -cert-file mkcert-ssl.crt example.local *.example.local`

Install openssl

`apk add openssl`

Generte dhparam.pem

`openssl dhparam -out dhparam.pem 2048`

---


If it's the firt install of mkcert, run

`mkcert -install`

Generate certificate for domain "docker.localhost", "domain.local" and their sub-domains

`mkcert -cert-file local-cert.pem -key-file local-key.pem "docker.localhost" "*.docker.localhost" "domain.local" "*.domain.local"`