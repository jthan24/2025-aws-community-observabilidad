# 2025-aws-community-observabilidad


## Arquitectura desplegada
- https://catalog.workshops.aws/serverless-patterns/en-US/module1


## Subir el grafana-oss
docker run --name grafana --rm -p 3000:3000 -e "GF_SECURITY_ADMIN_PASSWORD=pass" -e "GF_USERS_ALLOW_SIGN_UP=false" grafana/grafana-oss

### Configurar el DS

#### En AWS
Se debe crear un usuario
- En a IAM y creamos un usuario
- Al usuario se le debe agregar la politica de CloudWatchReadOnlyAccess
- Al usuario se debe agregar una AccessKey en el tab de Security Credentials

#### En Grafana
Se debe agregar una fuente de datos (DataSource)
- En Connections, agregar una nueva conexion de tipo CloudWatch
- Authentication Provider, seleccionar `Access & Secret Key`
    - Ingresar los datos obtenidos en los pasos de AWS
    - Default region us-east-1
- Guardar


## Configurar los dashboards
Ahora agregar los dashboard

- https://grafana.com/grafana/dashboards/17741-aws-dynamodb/
- https://grafana.com/grafana/dashboards/593-aws-lambda/
- https://grafana.com/grafana/dashboards/11267-aws-lambda/
- https://grafana.com/grafana/dashboards/19734-aws-lambda-insights/

## Referencia
- https://grafana.com/docs/grafana/latest/datasources/aws-cloudwatch/
