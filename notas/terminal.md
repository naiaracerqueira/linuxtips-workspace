# Terminal (Alpine)

- Shell: interpretador de comandos, conversa com o kernel
- Bash: um tipo de shell.
- FHS: Filesystem Hierarchy Standard

## Diretórios Linux
Listar o que tem no diretório raiz (/), mesmo sem estar nele:
```
$ ls /
```

Para entrar na pasta var, não precisa da barra pq a barra se refere ao diretório raiz:
```
$ cd var
```

Histórico de comandos
```
$ history
```

## Administração de usuários

Cria usuário e grupo, e adiciona usuário a grupo
```
$ sudo adduser estudante
$ sudo addgroup devops
$ sudo usermod -aG devops estudante
$ id estudante
```

Cria diretório de projeto, arquivo de configuração e altera proprietário
```
$ mkdir /opt/projeto
$ touch /opt/projeto/config.yml
$ chmod 750 /opt/projeto
$ chown -R estudante:devops /opt/projeto
```

