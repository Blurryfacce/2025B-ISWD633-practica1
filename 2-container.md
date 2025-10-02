# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```

<img width="559" height="68" alt="image" src="https://github.com/user-attachments/assets/4ecac919-384d-4c7f-bc2a-303e53a8635a" />

Crear el contenedor  **srv-web** usando la imagen nginx version alpine
# COMPLETAR

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
# COMPLETAR

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

<img width="959" height="118" alt="image" src="https://github.com/user-attachments/assets/479d8bea-5393-4e03-a33b-bd7a96c05451" />


### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```

C:\Users\LabP4E001>docker start srv-web
srv-web


<img width="639" height="55" alt="image" src="https://github.com/user-attachments/assets/d7e15883-7554-48cb-89e9-5d3c61e94253" />

Iniciar el contenedor srv-web 
# COMPLETAR

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

<img width="923" height="72" alt="image" src="https://github.com/user-attachments/assets/453ccf4c-a57d-4d3b-8744-d13ed20ffdc3" />


### Para detener un contenedor

```
docker stop <nombre contenedor>
```

C:\Users\LabP4E001>docker stop srv-web

srv-web

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```

<img width="936" height="424" alt="image" src="https://github.com/user-attachments/assets/57867005-1d8a-40c5-bada-3f01dd9e8e9c" />



Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
# COMPLETAR

**¿Qué sucede luego de la ejecución del comando?**

Se ejecuta el contenedor en primer plano y se captura la entrada estandar de la terminal.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```

C:\Users\LabP4E001>docker run -d --name srv-web3 nginx:alpine

7bffb0612030e112e1b86ec787d67bc8af5f44553bacd6ef4069175d218e7562


Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
# COMPLETAR

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```

<img width="1035" height="167" alt="image" src="https://github.com/user-attachments/assets/35c7857c-7d4d-4220-a335-252e4462386f" />


Verificar que el contenedor que se eliminó
# COMPLETAR

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
<img width="1072" height="154" alt="image" src="https://github.com/user-attachments/assets/3a4e941d-8788-4aea-a40e-a420b297ebf4" />


### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
C:\Users\LabP4E001>docker inspect srv-web
```
[
    {
        "Id": "55061c86b415f3a063b1478dda3aac5693ffb5fda27d84671339d90b32392204",
        "Created": "2025-10-02T22:19:42.237656546Z",
        "Path": "/docker-entrypoint.sh",
        "Args": [
            "nginx",
            "-g",
            "daemon off;"
        ],
        "State": {
            "Status": "exited",
            "Running": false,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 0,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2025-10-02T22:19:42.319907516Z",
            "FinishedAt": "2025-10-02T22:21:46.423852579Z"
        },
        "Image": "sha256:42a516af16b852e33b7682d5ef8acbd5d13fe08fecadc7ed98605ba5e3b26ab8",
        "ResolvConfPath": "/var/lib/docker/containers/55061c86b415f3a063b1478dda3aac5693ffb5fda27d84671339d90b32392204/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/55061c86b415f3a063b1478dda3aac5693ffb5fda27d84671339d90b32392204/hostname",
        "HostsPath": "/var/lib/docker/containers/55061c86b415f3a063b1478dda3aac5693ffb5fda27d84671339d90b32392204/hosts",
        "LogPath": "/var/lib/docker/containers/55061c86b415f3a063b1478dda3aac5693ffb5fda27d84671339d90b32392204/55061c86b415f3a063b1478dda3aac5693ffb5fda27d84671339d90b32392204-json.log",
        "Name": "/srv-web",
        "RestartCount": 0,
        "Driver": "overlayfs",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "bridge",
            "PortBindings": {},
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "ConsoleSize": [
                30,
                120
            ],
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "private",
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": [],
            "BlkioDeviceWriteBps": [],
            "BlkioDeviceReadIOps": [],
            "BlkioDeviceWriteIOps": [],
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": null,
            "PidsLimit": null,
            "Ulimits": [],
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/interrupts",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware",
                "/sys/devices/virtual/powercap"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": null,
            "Name": "overlayfs"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "55061c86b415",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": true,
            "AttachStderr": true,
            "ExposedPorts": {
                "80/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "NGINX_VERSION=1.29.1",
                "PKG_RELEASE=1",
                "DYNPKG_RELEASE=1",
                "NJS_VERSION=0.9.1",
                "NJS_RELEASE=1"
            ],
            "Cmd": [
                "nginx",
                "-g",
                "daemon off;"
            ],
            "Image": "nginx:alpine",
            "Volumes": null,
            "WorkingDir": "/",
            "Entrypoint": [
                "/docker-entrypoint.sh"
            ],
            "OnBuild": null,
            "Labels": {
                "maintainer": "NGINX Docker Maintainers \u003cdocker-maint@nginx.com\u003e"
            },
            "StopSignal": "SIGQUIT"
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "",
            "SandboxKey": "",
            "Ports": {},
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "",
            "Gateway": "",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "",
            "IPPrefixLen": 0,
            "IPv6Gateway": "",
            "MacAddress": "",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "MacAddress": "",
                    "DriverOpts": null,
                    "GwPriority": 0,
                    "NetworkID": "e5990afe022f693bee8a4563b6cfae5a9e2db495226a34cf638b451a51ad418e",
                    "EndpointID": "",
                    "Gateway": "",
                    "IPAddress": "",
                    "IPPrefixLen": 0,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "DNSNames": null
                }
            }
        },
        "ImageManifestDescriptor": {
            "mediaType": "application/vnd.oci.image.manifest.v1+json",
            "digest": "sha256:60e48a050b6408d0c5dd59b98b6e36bf0937a0bbe99304e3e9c0e63b7563443a",
            "size": 2495,
            "annotations": {
                "com.docker.official-images.bashbrew.arch": "amd64",
                "org.opencontainers.image.base.digest": "sha256:94f11b88c5d30105df2236d818a2dd50577bd2314f70374ae53ccaec61ac34f0",
                "org.opencontainers.image.base.name": "nginx:1.29.1-alpine-slim",
                "org.opencontainers.image.created": "2025-08-13T18:57:48Z",
                "org.opencontainers.image.revision": "5a4ad48c733b365d69a4d1c9946a9d8480469c7f",
                "org.opencontainers.image.source": "https://github.com/nginx/docker-nginx.git#5a4ad48c733b365d69a4d1c9946a9d8480469c7f:mainline/alpine",
                "org.opencontainers.image.url": "https://hub.docker.com/_/nginx",
                "org.opencontainers.image.version": "1.29.1-alpine"
            },
            "platform": {
                "architecture": "amd64",
                "os": "linux"
            }
        }
    }
]

```

