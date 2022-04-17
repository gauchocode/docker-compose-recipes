# Docker Compose Recipes
Similar idea https://github.com/docker/awesome-compose

## :gear: Installation
Install docker and docker-compose and clone repo:

```
sudo apt install docker.io docker-compose
git clone https://gitlab.com/broobe/docker-compose-samples.git
```
## :triangular_flag_on_post: First steps

```
# Go to the tool we want to install. Example:
cd docker-compose-samples/vaultwarden

# Edit .env
vim .env

# Download images
docker-compose pull

# Start containers
docker-compose up -d
```

## :compass: TODO List
* Better documentation.
* More docker compose-recipes.
* More installation variants from the existing recipes.

## :wave: Contributing

Considerations:

* Do not place passwords or sensitive data on docker-compose.yml. 
* Use .env files for make more customizable the installation.
* Each recipe should contain their own readme.md.
* Avoid using configurations with non-persistent data.

## :busts_in_silhouette: Team

This theme is maintained by the following person(s) and a bunch of [awesome contributors](https://github.com/lpadula/brolit-shell/graphs/contributors).

[![Leandro Padula](https://github.com/lpadula.png?size=100)](https://github.com/lpadula) |
--- |
[Leandro Padula](https://github.com/lpadula) |

## :warning: License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.
