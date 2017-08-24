# certbot-apache
An ansible role to install certbot with the apache plugin on Debian and CentOS/RHEL-like systems.

## Role Variables

	certbot_generate_certificates: true
	certbot_register_email: your@email.com
	certbot_certificate_domains: "{{ domains }}"

If certbot_generate_certificates is true, certbot will automatically generate certificates for those domains and configure vhost files.

## Example Playbook

	- hosts servers

	  vars: 

		certbot_generate_certificates: true
		certbot_register_email: your@email.com
	  	certbot_certificate_domains:
	  		- domain1.com
	  		- domain2.com

  		roles:
		    - { role: certbot-apache, become: yes }
