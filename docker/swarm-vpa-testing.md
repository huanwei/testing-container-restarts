
## swarm vpa testing
```$xslt
$ docker service ls
ID                  NAME                MODE                REPLICAS            IMAGE                     PORTS
4ma8x5on6d80        http                replicated          2/2                 katacoda/docker-http-server:v1   *:80->80/tcp
$
$ docker ps
CONTAINER ID        IMAGE                            COMMANDCREATED             STATUS              PORTS               NAMES
79eb7f720687        katacoda/docker-http-server:v1   "/app"27 minutes ago      Up 27 minutes       80/tcp              http.2.xhd2z65m2lknj8009c787pj9j
f8f828379fd0        katacoda/docker-http-server:v1   "/app"27 minutes ago      Up 27 minutes       80/tcp              http.1.wg44v4tizby9jhvo8ofgo38ir
$
$ docker update 79eb7f720687 -m 1500M --memory-swap 1500M
79eb7f720687
$
$ docker ps
CONTAINER ID        IMAGE                            COMMANDCREATED             STATUS              PORTS               NAMES
79eb7f720687        katacoda/docker-http-server:v1   "/app"28 minutes ago      Up 28 minutes       80/tcp              http.2.xhd2z65m2lknj8009c787pj9j
f8f828379fd0        katacoda/docker-http-server:v1   "/app"28 minutes ago      Up 28 minutes       80/tcp              http.1.wg44v4tizby9jhvo8ofgo38ir


```

```$xslt
$ docker inspect 79eb7f720687
[
    {
        "Id": "79eb7f7206876b6a65cb3f10e61ea4d084f10a0580a2f6e2b85540c7b1cf372b",
        "Created": "2020-03-12T15:58:19.950277826Z",
        "Path": "/app",
        "Args": [],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 3741,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2020-03-12T15:58:24.060972962Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:0d6ee549ae1314ff0c0b8fea18042f3891250ba6b920fc714563be624e3c62a3",
        "ResolvConfPath": "/var/lib/docker/containers/79eb7f7206876b6a65cb3f10e61ea4d084f10a0580a2f6e2b85540c7b1cf372b/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/79eb7f7206876b6a65cb3f10e61ea4d084f10a0580a2f6e2b85540c7b1cf372b/hostname",
        "HostsPath": "/var/lib/docker/containers/79eb7f7206876b6a65cb3f10e61ea4d084f10a0580a2f6e2b85540c7b1cf372b/hosts",
        "LogPath": "/var/lib/docker/containers/79eb7f7206876b6a65cb3f10e61ea4d084f10a0580a2f6e2b85540c7b1cf372b/79eb7f7206876b6a65cb3f10e61ea4d084f10a0580a2f6e2b85540c7b1cf372b-json.log",
        "Name": "/http.2.xhd2z65m2lknj8009c787pj9j",
        "RestartCount": 0,
        "Driver": "overlay",
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
            "NetworkMode": "default",
            "PortBindings": {},
            "RestartPolicy": {
                "Name": "",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "Dns": null,
            "DnsOptions": null,
            "DnsSearch": null,
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "shareable",
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
            "ConsoleSize": [
                0,
                0
            ],
            "Isolation": "default",
            "CpuShares": 0,
            "Memory": 1572864000,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": null,
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": null,
            "DeviceCgroupRules": null,
            "DiskQuota": 0,
            "KernelMemory": 0,
            "MemoryReservation": 0,
            "MemorySwap": 1572864000,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": 0,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay/abc57ca04d11754f3ccdd4a555acf5d355e6544b491e456aaf60e2a6f4ff95b3/root",
                "MergedDir": "/var/lib/docker/overlay/4f21a79101d2853e1e6b39f68af9578b1131d9e661611d6e279af6910f56211b/merged",
                "UpperDir": "/var/lib/docker/overlay/4f21a79101d2853e1e6b39f68af9578b1131d9e661611d6e279af6910f56211b/upper",
                "WorkDir": "/var/lib/docker/overlay/4f21a79101d2853e1e6b39f68af9578b1131d9e661611d6e279af6910f56211b/work"
            },
            "Name": "overlay"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "79eb7f720687",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "80/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": [
                "/app"
            ],
            "Image": "katacoda/docker-http-server:v1@sha256:4d7bfcb1e38912d286c5cda63aeddc850a4be16127094ffacbb7abfc6298c5fa",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {
                "com.docker.swarm.node.id": "5s4dfe7g7x1veyskw80cqqu6k",
                "com.docker.swarm.service.id": "4ma8x5on6d80vlq1agk4ay6t6",
                "com.docker.swarm.service.name": "http",
                "com.docker.swarm.task": "",
                "com.docker.swarm.task.id": "xhd2z65m2lknj8009c787pj9j",
                "com.docker.swarm.task.name": "http.2.xhd2z65m2lknj8009c787pj9j"
            }
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "1accd1bf9be82aa325debcdd80f1ba4fb50dba31ddcebe1c325660f5662d9890",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "80/tcp": null
            },
            "SandboxKey": "/var/run/docker/netns/1accd1bf9be8",
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
                "ingress": {
                    "IPAMConfig": {
                        "IPv4Address": "10.255.0.10"
                    },
                    "Links": null,
                    "Aliases": [
                        "79eb7f720687"
                    ],
                    "NetworkID": "w91st2tvylxyc1rsts9dtfhw6",
                    "EndpointID": "114a176c3a948297953b7918ad180000ea9c242eab18926ff54422a4a77a391b",
                    "Gateway": "",
                    "IPAddress": "10.255.0.10",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:0a:ff:00:0a",
                    "DriverOpts": null
                }
            }
        }
    }
]
```

```$xslt
$ docker service inspect http
[
    {
        "ID": "4ma8x5on6d80vlq1agk4ay6t6",
        "Version": {
            "Index": 65
        },
        "CreatedAt": "2020-03-12T15:40:19.805706746Z",
        "UpdatedAt": "2020-03-12T15:58:29.131808726Z",
        "Spec": {
            "Name": "http",
            "Labels": {},
            "TaskTemplate": {
                "ContainerSpec": {
                    "Image": "katacoda/docker-http-server:v1@sha256:4d7bfcb1e38912d286c5cda63aeddc850a4be16127094ffacbb7abfc6298c5fa",
                    "StopGracePeriod": 10000000000,
                    "DNSConfig": {},
                    "Isolation": "default"
                },
                "Resources": {
                    "Limits": {},
                    "Reservations": {
                        "MemoryBytes": 104857600
                    }
                },
                "RestartPolicy": {
                    "Condition": "any",
                    "Delay": 5000000000,
                    "MaxAttempts": 0
                },
                "Placement": {
                    "Platforms": [
                        {
                            "Architecture": "amd64",
                            "OS": "linux"
                        }
                    ]
                },
                "ForceUpdate": 0,
                "Runtime": "container"
            },
            "Mode": {
                "Replicated": {
                    "Replicas": 2
                }
            },
            "UpdateConfig": {
                "Parallelism": 1,
                "FailureAction": "pause",
                "Monitor": 5000000000,
                "MaxFailureRatio": 0,
                "Order": "stop-first"
            },
            "RollbackConfig": {
                "Parallelism": 1,
                "FailureAction": "pause",
                "Monitor": 5000000000,
                "MaxFailureRatio": 0,
                "Order": "stop-first"
            },
            "EndpointSpec": {
                "Mode": "vip",
                "Ports": [
                    {
                        "Protocol": "tcp",
                        "TargetPort": 80,
                        "PublishedPort": 80,
                        "PublishMode": "ingress"
                    }
                ]
            }
        },
        "PreviousSpec": {
            "Name": "http",
            "Labels": {},
            "TaskTemplate": {
                "ContainerSpec": {
                    "Image": "katacoda/docker-http-server:v1@sha256:4d7bfcb1e38912d286c5cda63aeddc850a4be16127094ffacbb7abfc6298c5fa",
                    "DNSConfig": {},
                    "Isolation": "default"
                },
                "Resources": {
                    "Limits": {},
                    "Reservations": {
                        "MemoryBytes": 157286400
                    }
                },
                "Placement": {
                    "Platforms": [
                        {
                            "Architecture": "amd64",
                            "OS": "linux"
                        }
                    ]
                },
                "ForceUpdate": 0,
                "Runtime": "container"
            },
            "Mode": {
                "Replicated": {
                    "Replicas": 2
                }
            },
            "EndpointSpec": {
                "Mode": "vip",
                "Ports": [
                    {
                        "Protocol": "tcp",
                        "TargetPort": 80,
                        "PublishedPort": 80,
                        "PublishMode": "ingress"
                    }
                ]
            }
        },
        "Endpoint": {
            "Spec": {
                "Mode": "vip",
                "Ports": [
                    {
                        "Protocol": "tcp",
                        "TargetPort": 80,
                        "PublishedPort": 80,
                        "PublishMode": "ingress"
                    }
                ]
            },
            "Ports": [
                {
                    "Protocol": "tcp",
                    "TargetPort": 80,
                    "PublishedPort": 80,
                    "PublishMode": "ingress"
                }
            ],
            "VirtualIPs": [
                {
                    "NetworkID": "w91st2tvylxyc1rsts9dtfhw6",
                    "Addr": "10.255.0.3/16"
                }
            ]
        },
        "UpdateStatus": {
            "State": "completed",
            "StartedAt": "2020-03-12T15:58:15.354051962Z",
            "CompletedAt": "2020-03-12T15:58:29.13178815Z",
            "Message": "update completed"
        }
    }
]
$ exit
```