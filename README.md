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

#### Dont use configs for setting environment of drone

use configs like:
```
    configs:
      - source: drone-agent-env
        target: /.env
```

**This will not take effect. Please use the way of environment.**

like:
```
    environment:
      - DRONE_OPEN=true
      - DRONE_SERVER_HOST=${DRONE_SERVER_HOST}
      - DRONE_SERVER_PROTO=${DRONE_SERVER_PROTO}
      - DRONE_TLS_AUTOCERT=false
      - DRONE_GIT_ALWAYS_AUTH=true
      - DRONE_GITEA_SERVER=${DRONE_GITEA_SERVER}
```

When I find a solution, I will update it.

*****

#### drone/first

drone pipeline test for `test` `build` `publish-docker` `deploy`

#### drone/second

drone pipeline test for `manual deployment` by `drone cli`

```
# get last build number:
$ drone build last abc/go_demo

# manual deploy
$ drone build promote abc/go_demo 42 prod
```

*****
