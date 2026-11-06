# tailscale

Tailscale as a Docker Compose stack: the host joins the tailnet (host network, kernel mode). Server-specific names live in `.env`, not in the repo.

## Install

    git clone https://github.com/feruzabad/tailscale.git ~/tailscale
    cd ~/tailscale
    cp env.example .env && chmod 600 .env && $EDITOR .env
    sudo docker compose up -d

`TS_AUTHKEY` is only needed the first time. Once the state volume holds the node's identity, it can stay empty. Use a reusable, non-ephemeral key.

## Update

    cd ~/tailscale && git pull && sudo docker compose up -d

Renovate bumps the image tag (and digest) in `compose.yaml`.
