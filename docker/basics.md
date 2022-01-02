# Basics

## Basic Commands



| # | Command                                        | Description                                                                                                                                                      |
| - | ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | `docker build .`                               | Build the image from the Dockerfile found in the project directory                                                                                               |
| 2 | `docker run -p [port_no]:[port_no] [image_id]` | Run built docker image with `-p` flag (to publish, open port so we can reach from outside) and use image id, for example: `docker run -p 3000:3000 417916cb028c` |
| 3 | `docker ps`                                    | List all the containers                                                                                                                                          |
| 4 | `docker stop [container_name]`                 | Stop given docker image, based on it's name, for example: `docker stop relaxed_andrew`                                                                           |
| 5 | `docker run [image_from_hub]`                  | This command will run local image, if note found it will pull it from DockerHub, e.g. `docker run node`                                                          |
| 6 | `docker ps -a`                                 | Show all processes (ps)                                                                                                                                          |
| 7 | `docker run -it node`                          | Access interactive section of Node instance, where you can run basic commands, node api, etc.                                                                    |
| 8 | `docker run --help`                            | Shows all available option for command `docker run` and explains all available flags.                                                                            |

## Containers

| # | Commmand                                                         | Description                                                                                                                                                               |
| - | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | `docker run -p 8000:80 -d [image_id]`                            | Run container in the detached mode, this doesn't block your terminal so you can run different commands, but you can't see the output.                                     |
| 2 | `docker attach [container_name]`                                 | You can switch on the attach mode, which will show you the p=output in the console, so you can see printed statments, etc. Example use: `docker attach determined_swartz` |
| 3 | `docker logs [container_name]`                                   | See the container's logs (you can see past logs), but stay in detached mode.                                                                                              |
| 4 | `docker logs -f [container_name]`                                | See the logs and activate the attach mode (now you will be able to see the future logs).                                                                                  |
| 5 | `docker start -a [container_name]`                               | Start container in the attach mode (you can see output). Example use: `docker start -a determined_swartz`                                                                 |
| 6 | `docker run -i -t [image_id]` or use `docker run -it [image_id]` | Run container in interactive mode which allows STDIN, you can provide input to the terminal window.                                                                       |
| 7 | `docker start -a -i [container_name]`                            | Start the container in attach mode and with option allowing to input data in terminal (I want to input something mode).                                                   |
| 8 | `docker rm [container_name]`                                     | Remove container that was previously stopped. You can pass multiple images names after rm, seperated by whitespace.                                                       |

## Images

| # | Command                                          | Description                                                                                                                                        |
| - | ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | `docker images`                                  | List all images.                                                                                                                                   |
| 2 | `docker rmi [image_id]`                          | Remove image and all its layers. Remember that container needs to be remove first for this command to work. Example use: `docker rmi 430b0f5674df` |
| 3 | `docker image prune`                             | Remove all unused images.                                                                                                                          |
| 4 | `docker run -p [port]:[port] -d --rm [image_id]` | Run image on port 3000 in dettached mode and remove container when is being stopped. Example use: `docker run -p 3000:80 -d --rm 430b0f5674df`     |

