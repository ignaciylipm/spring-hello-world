# Ejemplo aplicacion SprintBoot
Arrancar la aplicación y test
```
mvn sprint-boot:run
curl http://localhost:8080/
curl http://localhost:8080/info
```
Construir la aplicacion
```
mvn clean package
```
Construir la imagen
```
docker build -t sp-hello:1.0 .
```

Test del contenedor 
```
docker run -ti -p 8090:8080 sp-hello:1.0 
curl http://localhost:8090/
curl http://localhost:8090/info
```

Subir la imagen
```
docker login ghcr.io -u ignaciyl
docker tag sp-hello:1.0 ghcr.io/ignaciyl/sp-hello:1.0 
docker push ghcr.io/ignaciyl/sp-hello:1.0 
```