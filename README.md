### docker swarm of drone test

#### tree

```
➜ tree -a
.
├── composes
│   ├── gitdrone
│   │   ├── .env
│   │   └── docker-compose-gitdrone.yml
│   ├── gitdrone-test
│   │   ├── .env
│   │   ├── docker-compose-drone.yml
│   │   ├── docker-compose-git.yml
│   │   └── docker-compose.yml
│   └── swirl
│       └── docker-compose-swirl.yml
├── swarms
│   ├── docker-swarm-swirl.yml
│   ├── drone-agent
│   │   ├── .env
│   │   └── docker-swarm-drone-agent.yml
│   ├── gitdrone
│   │   ├── .agent-env
│   │   ├── .server-env
│   │   └── docker-swarm-gitdrone.yml
│   ├── gitdrone-ip
│   │   ├── .agent-env
│   │   ├── .server-env
│   │   └── docker-swarm-gitdrone-ip.yml
│   ├── gitdrone-ip-config
│   │   ├── agent-env
│   │   ├── docker-swarm-ip-config.yml
│   │   └── server-env
│   ├── gitdrone-ip-env
│   │   ├── .env
│   │   ├── docker-swarm-gitdrone-ip-env-nfs.yml
│   │   └── docker-swarm-gitdrone-ip-env.yml
│   └── gitdrone-used
│       ├── .env
│       └── docker-swarm-git-drone-nfs.yml
└── traefik
    ├── docker-swarm-traefik.yml
    └── traefik.toml
```

*****

