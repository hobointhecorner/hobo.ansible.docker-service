# Hobo.Ansible.Docker-Service
Configure a systemd service to run a docker container either persistently or using the OnCalendar timer event

## Variables
| Name                  | Type                      | Required | Default             | Description |
|-----------------------|---------------------------|----------|---------------------|-------------|
| service_name          | string                    | yes      |                     | Name of the service |
| container_registry    | string                    | yes      |                     | Container registry from which to pull the image |
| container_image       | string                    | yes      |                     | Image to pull |
| container_image_tag   | string                    | no       | latest              | Tag of the image to pull |
| container_dotenv_file | string                    | no       |                     | .env file to pass to the container |
| container_ports       | list(string)              | no       |                     | Ports to expose to the container |
| container_volumes     | list(string)              | no       |                     | Volumes to mount to the container |
| container_pull        | string                    | no       |  missing            | Whether the image should be updated at launch |
| registry_username     | string                    | no       |                     | Image registry username |
| registry_password     | string                    | no       |                     | Image registry password |
| service_type          | string('service'|'timer') | no       |  service            | Type of service to create |
| service_config_dir    | string                    | no       | /opt/`service_name` | Directory in which service configuration files will be placed |
| service_description   | string                    | no       |  `service_name`     | Description of the service |
| service_user          | string                    | no       |                     | User the service should run as |
| service_group         | string                    | no       |                     | Group the service should run as |
| timer_interval        | string                    | no       |                     | Interval on which timer service types will be run. Required if `service_type` is `timer` |
