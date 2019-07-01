# wcm_io_devops.apache_service

This role controls an Apache service on Linux servers. This role
supports a "restricted" mode when your User on the target host has not
the appropriate privilege escalation rights and has to work with e.g.
`sudo`.

## Requirements

This role requires Ansible 2.4 or higher and works with Apache 2.2 or
higher. The role requires an Apache service that can be controlled with
the Ansible `service` module to be installed on the target machine when
not running in restricted mode.

## Role Variables

Available variables are listed below, along with their default values:

    apache_service_restricted_mode: false

Enables / disables the restricted mode to work with customized commands like sudo.

    apache_service_state: started

Desired state of the service.

    # apache_service_name:

The name of the service to be controlled (OS family related).

    # apache_service_start_command:

Overwrites the default (service manager related) start command.

    # apache_service_stop_command:

Overwrites the default (service manager related) stop command.

    # apache_service_status_command:

Overwrites the default (service manager related) status command.

## Dependencies

This role has no hard dependencies.

## Example Playbook

Stops the `apache2` service:

	- hosts: webserver
	  roles:
	    - role: wcm_io_devops.apache_service
	      apache_service_state: stopped

## License

Apache 2.0