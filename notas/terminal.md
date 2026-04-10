# Terminal (Alpine)

- Shell: interpretador de comandos, conversa com o kernel
- Bash: um tipo de shell.
- FHS: Filesystem Hierarchy Standard

## Comandos

| Comando | Obs |
| -- | -- |
| ls | Lista diretórios e arquivos |
| ls -l | Detalhes de tamanho e permissão |
| ls -a | Aquivos ocultos |
| ls -h | "Human readable" |
| cwd | Mostra path |
| cd | "Change directory" |
| cd *dir* | Vai para diretório "dir" |
| cd .. | Caminho relativo: volta um nível de diretório |
| cd ../../ | Caminho relativo: volta dois níveis de diretório |
| cd - | Volta para o diretório anterior |
| cat | Visualiza conteudo do arquivo |
| mkdir | Cria pasta |
| echo | Imprime na tela o que eu mando |
| >> | Altera saída padrão para |
| > | Append |
| tree | Ver a estrturura de diretórios até o / |
| history | Ver histórico de comandos |

O comando `ls -lha` retorna:
```
drwxr-xr-x   4 root root 4.0K Apr  2 14:44 boot
```
Que são
- d → significa que é um diretório
    - **\-** → arquivos de texto
    - l → link simbólico
    - b → dispositivo de bloco
    - c → dispositivo de caractere
    - s → socket
- rwxr-xr-x → permissões
- 4 → nível
- root → usuário
- root → grupo
- 4.0K → tamanho do arquivo diretório
- Apr  2 14:44 → data
- boot → nome do diretório

Ou
```
lrwxrwxrwx  1 root root       22 Oct 24 03:46  zoom -> /opt/zoom/ZoomLauncher
```
- l → significa que é um link simbólico
- rwx → permissões do dono do arquivo: read, write, execute
- rwx → permissões do grupo do dono do arquivo: read, write, execute
- rwx → permissões dos outros: read, write, execute
- zoom -> /opt/zoom/ZoomLauncher → é o link simbólico que aponta para o opt/zoom/

## Diretórios Linux

**Organização por níveis**

| Exemplo | Nível |
| -- | -- |
| /	| primeiro nível |
| /var | segundo nível |
| /var/log | terceiro nível |

**Principais diretórios**

| Diretórios | Obs |
| -- | -- |
| /	| Diretório raiz |
| /bin	| Binários: executáveis (verde) e link simbolicos / atalhos (azul claro) |
| /root	| Diretório do usuário administrador do sistema |
| /home	| Diretório dos outros usuários |
| /dev	| Dispositivos (magenta) que podem ser de caractere (transferem informações) ou de bloco (armazenam informações) e diretório (azul escuro) |
| /etc	| Configuração do |
| /lib	| Bibliotecas do sistema|
| /var	| |
| /var/log | Arquivos de log do sistema |
| / | |

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

