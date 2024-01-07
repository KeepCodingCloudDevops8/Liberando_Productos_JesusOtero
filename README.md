## LIBERANDO PRODUCTOS

**Añadir nuevo endpoint a nuestra aplicacion:

    Se ha realizado metiendo ese codigo en el app.py

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/57418a47-2501-4dfa-a3fe-4781acd2283b)

**Creacion de test unitarios para ese endpoint:

  Se ha realizado metiendo ese codigo en el archivo de tests

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/11298320-81a8-4cfb-b8a7-a070c1ea0c32)

**Creación de pipelines de CI/CD con CircleCi para test y build&push:

  Hemos creado el directorio .circleci y dentro un config.yml haciendo sus jobs como se ve en el codigo, despues hemos ido a Circleci y hemos agregado las variables necesarias e importado el repositorio, y al   hacer cada commit, nos pasa los pipelines.

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/65902ac1-6f81-4cb8-bd3d-af9659fef785)

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/dc4548db-1c80-4008-9f08-0ff910728c57)

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/e19768df-fe13-4f6a-80b0-ed7381274f66)

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/3b2bd630-b952-4dad-b76c-93d47ba9ecea)

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/171fc85f-9999-4a24-b0cb-0016d2171e8b)

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/2c18c4f4-9e54-48f2-aa33-157a1d5c7440)

**Configuracion de monitorizacion del nuevo endpoint:

Hemos visto un poco del ejemplo del codigo en el app.py para el resto de endpoints, y lo hemos replicado, pero para nuestro nuevo endpoint.

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/90067a7d-2c3a-4d68-8ae5-47038e9d2389)

**Creacion de alertas con Slack para aviso por notificaciones:

  He seguido los apartados del lab 3 y al realizar la prueba con extress, me ha llegado la notificacion.
  
  Además de seguir los pasos para la creacion del webHook del slack, hemos agregado al values de prometheus el codigo necesario.
  
  Despues hemos ejecutado los comandos: helm repo add prometheus-community https://prometheus-community.github.io/helm-charts y helm repo update para desplegar el chart.
  
  Para la prueba de extress, seguí los pasos del lab3 tabien, como acceder al contenedor mediante el comando: kubectl -n fast-api exec --stdin --tty $POD_NAME -c fast-api-webapp -- /bin/sh
  
  Dentro hemos ejecutado apk update && apk add git go.
  
  Descargar el repositorio de github y acceder a la carpeta de este con git clone https://github.com/jaeg/NodeWrecker.git cd NodeWrecker y go build -o extress main.go
  
  Y por ultimo ejecutamos el binario obtenido para la prueba con extress: ./extress -abuse-memory -escalate -max-duration 10000000

![notificacion en slack](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/3648b744-1996-47d5-b48d-bf6ff23f8ea1)

**Nos hemos creado tambien estos manifests para desplegar la aplicacion en kubernetes con su deplyment.yaml y su service.yaml y ejecutado el kubectl apply -f .

![image](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/f3ac8cf5-1409-4d05-b280-be0501197ccd)

**En cuanto al ultimo apartado, el de Grafana, he conseguido hacer todos los pasos, o sea, levantar los puertos, crear el dashboard, pero no soy capaz de que me lleguen datos.

  He hecho los kubectl port forward de los puertos de Grafana, Prometheus y los endpoints.
  
  He accedido a grafana e importado el dashboard.

  Pero aqui no he conseguido que me pinte las metricas.

![grafana dashboard](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/d8a4fcf2-8905-4cb8-8678-527b2bfe1b95)

![grafana](https://github.com/KeepCodingCloudDevops8/Liberando_productos_JesusOtero/assets/99189407/1c6209f7-7eac-4d34-a21b-a90c30dc05d4)












