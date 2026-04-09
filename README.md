# Production usage

## Django 4 compatibility prerequisites

- Use a Horizon/OpenStack release that officially supports Django 4.
- Use Python 3 and install dependencies from `requirements.txt`.
- If you run the installer manually, use `python3`.

Run `python3 install.py VPROTECT_REST_API_URL VPROTECT_USER VPROTECT_USER_PASSWORD` on the destination server.
e.g. `python3 install.py http://localhost:8080/api admin vPr0tect`

Also, you can provide version to command to install specified package without picking the version in terminal
 by command below 
```
python3 install.py VPROTECT_REST_API_URL VPROTECT_USER VPROTECT_USER_PASSWORD VERSION
```

Examples:
```
# latest
python3 install.py http://localhost:8080/api admin vPr0tect latest

# specified version
python3 install.py http://localhost:8080/api admin vPr0tect 5.0.0-11
```

and then run `systemctl restart httpd` to apply changes by restarting Horizon on OpenStack.

If needed, the REST API URL and credentials can be modified in /usr/share/openstack-dashboard/openstack_dashboard/dashboards/vprotect/config.yaml