# n8n with tailscale

Runs n8n in a machine in the tailscale-provided domain

1. Set up tailscale
    ```
    sudo systemctl enable --now tailscaled
    sudo tailscale up
    ```

2. Use the .env.example file to create a .env file

3. Start docker compose
    ```
    docker compose up -d
    ```

4. Make sure tailscale is up in your machine, and access the server using the url
    OR alternatively, you could:
5. Funnel n8n's port, which enables access for everybody on the internet
    ```
    sudo tailscale funnel 5678
    ```

For more info, read the official docs of n8n (docker compose):
https://docs.n8n.io/hosting/installation/server-setups/docker-compose/#7-start-docker-compose
