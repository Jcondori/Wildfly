# Wildfly

## Credenciales

 - User : `root`
 - Password : `root`

## Uso Simple

Para arrancar en modo independiente
```bash
sudo docker run -p 8080:8080 -p 9990:9990 -d jcondori/wildfly
```

## Uso con despliegue con Scanner

Para crear un contenedor con acceso al despliegue con scanner, que funciona dejando los war en la carpeta `deployments`.

Creamos una carpera para colocar los WAR y damos permisos
```bash
mkdir /home/deployments
chmod 0777 /home/deployments
```
Creamos el contenedor especificando la ruta para el scanner.
```bash
sudo docker run -p 8080:8080 -p 9990:9990 -v /home/deployments:/opt/jboss/wildfly/standalone/deployments -d jcondori/wildfly
```