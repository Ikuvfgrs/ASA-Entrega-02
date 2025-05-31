# ASA-Entrega-02

## Objetivo

Este projeto tem como objetivo montar uma infraestrutura usando Docker Compose contendo:

- Um servidor DNS com uma zona primária
- Um servidor proxy reverso HTTP (nginx)
- Dois servidores web com páginas personalizadas

## Estrutura do projeto

- `dns/` - Configurações e arquivos do servidor DNS (bind9)
- `proxy/` - Configuração do proxy reverso nginx
- `web1/` - Primeiro servidor web
- `web2/` - Segundo servidor web
- `docker-compose.yml` - Orquestração dos containers

## Como usar

1. Clone o repositório:

   ```bash
   git clone git@github.com:Ikuvfgrs/ASA-Entrega-02.git
   cd ASA-Entrega-02
   ```

2. Build e subir containers:

   ```bash
   docker compose up --build -d
   ```

3. Testar servidores web:

   - Web 1: http://localhost:8081
   - Web 2: http://localhost:8082
   - Proxy (acesso aos dois via proxy): http://localhost/web1/ e http://localhost/web2/

4. Testar DNS:

   Use o comando `dig` para testar a resolução da zona primária.

---

## Observações

- O servidor DNS está configurado para a zona `example.com` com IPs fictícios.
- O proxy nginx faz o redirecionamento baseado em path `/web1/` e `/web2/`.
- Os dois servidores web servem páginas HTML simples para identificação.
