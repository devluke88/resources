# Basics

## Basic Commands



| # | Command                                            | Description                                                                                                                                                      |
| - | -------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | `docker build .`                                   | Build the image from the Dockerfile found in the project directory                                                                                               |
| 2 | `docker run` -p \[port_no]:\[port_no] `[image_id]` | Run built docker image with `-p` flag (to publish, open port so we can reach from outside) and use image id, for example: `docker run -p 3000:3000 417916cb028c` |
| 3 | `docker ps`                                        | List all the containers                                                                                                                                          |
| 4 | `docker stop [image_name]`                         | Stop given docker image, based on it's name, for example: `docker stop relaxed_andrew`                                                                           |

