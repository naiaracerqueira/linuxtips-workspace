# Docker

- É um projeto open source: qualquer pessoa pode visualizar o código e contribuir com melhorias para o Docker.
- Container: forma de isolar (sem impactar as outras aplicações) recursos para um determinado fim. Agrupamento de uma aplicação junto com suas dependências, que compartilham o kernel do sistema operacional do host.
    - Recursos: CPU, memória, filesystem (diretórios), processos (PIDs), usuários, etc.
- Portabilidade: não importa em qual ambiente você criou o seu container, ele irá rodar em qualquer outro que possua, no caso, o Docker instalado.
- É tipo um chroot mais elaborado.
- Cgroups: módulo do kernel Linux. Limita os recursos: dá x de memória e y de cpu para cada processo.
- Namespaces: módulo do kernel Linux. Responsável por fazer com que o sistema seja o mais isolado possível ("fecha a caixinha").
- Chroot: Isolamento de usuários em um determinado filesystem / estrutura de diretórios e esse usuário achar que o que ele tem acesso a tudo do sistema.
- LXC (Linux containers): pai do docker = chroot, namespaces e cgroups.
- Docker popularizou e facilitou os containers.

## Comandos

| Comando | Obs |
| -- | -- |
| lsns | Lista os namespaces |


## Cgroups