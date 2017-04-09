# Valet Aliases
Aliases for Laravel Valet `vup` and `vdown`

```bash
# Valet Up
vup() {
    # Start Valet
    valet start
    # Start MySql
    brew services start mysql
    # If a valet Dockerfile is present, run as daemon
    if [ -f docker-compose-valet.yml ]; then
        echo "👍    \e[4m\e[42m\e[30mValet Dockerfile found, running as daemon...\e[0m"
        docker-compose --file docker-compose-valet.yml up -d
    fi
}

# Valet Down
vdown() {
    # Stop Valet
    valet stop
    # Stop MySql
    brew services stop mysql
    # If a valet dockerfile exists then stop it
    if [ -f docker-compose-valet.yml ]; then
        echo "👍    \e[4m\e[42m\e[30mValet Dockerfile found, stopping...\e[0m"
        docker-compose --file docker-compose-valet.yml stop
    fi
}
```
