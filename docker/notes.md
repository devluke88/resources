# Notes

## MySQL image

```
// Example creation of MySQL DB running on Docker
docker pull mysql:8.0.25
docker run --name local_service_dashboard -p 3306:3306 -e MYSQL_ROOT_PASSWORD=admin1234 -d mysql:8.0.25

// Example MySQL Workbench setup:
Connection Name: local_service_dashboard
Hostname: 127.0.0.1
Port: 3306
Username: root
```
