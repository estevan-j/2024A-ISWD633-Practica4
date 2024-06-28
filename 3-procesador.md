# Limitar uso de procesador
Limitar la cantidad de núcleos de CPU:
```
--cpus=<número de núcleos>
```

Asignar núcleos de CPU específicos:
```
--cpuset-cpus=<lista de núcleos>
```

**¿Como saber el numero de procesadores virtuales que tiene una máquina?**
```
wmic cpu get NumberOfCores,NumberOfLogicalProcessors
```

![image](https://github.com/estevan-j/2024A-ISWD633-Practica4/assets/94009206/52f42964-52a7-4fbf-a565-07b0989b06f5)

### Para crear y ejecutar los siguientes contenedores usar la imagen de nginx:alpine

Limitar el uso de CPU a 1.5 núcleos
```
docker run -d --name server-nginx --cpus="1.5" nginx:alpine

```

Restringir el contenedor para que use los núcleos de CPU 0 a 2:
```
docker run -d --name server-nginx --cpuset-cpus="0-2" nginx:alpine

```

Restringir el contenedor para que use los núcleos de CPU 1 y 3:
```
docker run -d --name server-nginx --cpuset-cpus="1,3" nginx:alpine

```
