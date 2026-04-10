# Terminal (Alpine)

- Shell: interpretador de comandos, conversa com o kernel
- Bash: um tipo de shell.
- FHS: Filesystem Hierarchy Standard
- Montar: disponibilizar para uso
- PID: Process identification, id de cada processo em execução. Para ver os processos:
```
ps -ef
```

## Comandos

| Comando | Obs |
| -- | -- |
| clear | Apaga os comandos, *ctrl+l* |
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
| mkdir | "Make directory", cria diretório |
| mkdir -p | Cria diretório encadeado |
| cp *origem* *destino* | Copia arquivo |
| cp -r *origem* *destino* | Copia diretório |
| mv *origem* *destino* | Move arquivo |
| mv -r *origem* *destino* | Move diretório |
| mv *nome inicial* *nome final* | Renomeia arquivo |
| rm *nome do arquivo* | Remove arquivo |
| rm -r *nome do diretório* | Remove diretório de forma recursiva |
| rm -f *nome do diretório* | Força remoção de diretório |
| touch | Cria arquivo vazio |
| echo | Imprime na tela o que eu mando |
| >> | Altera (sobrescreve) saída padrão para |
| > | Append |
| tree | Ver a estrturura de diretórios até o / |
| history | Ver histórico de comandos |
| cat | Visualizar conteúdo do arquivo |
| source | Lê alguns arquivos específicos |
| alias | Lista todos os apelidos |
| alias *apelido*='*comando*' | Dá um apelido X para um comando. Ex: alias ll='ls -lha' |

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

## Atalhos

| Atalho | Obs |
| -- | -- |
| ctrl+l | Apaga os comandos |
| ctrl+r | Busca no histórico de comandos |
| ctrl+w | Remove ultimo bloco de comando de um comando já digitado |
| ctrl+d | Fecha o terminal |
| ctrl+a | Vai para início do comando |
| ctrl+e | Vai para final do comando |
| ctrl+c | Para comando que está rodando |

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
| /etc	| Configuração do sistema |
| /lib	| Bibliotecas do sistema (*.so) |
| /lib/modules | Módulos do kernel |
| /var	| Dados variáveis como logs, mensagens, impressão, cache, etc. |
| /var/log | Arquivos de log do sistema |
| /media | Tipo USB, CD-ROM |
| /opt | Instalações que não fazem parte da distribuição por default |
| /proc | Informações dinâmicas sobre o sistema; diretórios numéricas se referem aos PIDs |
| /run | Informações sobre processos em execução |
| /sbin | Binários que somente o root (s = super) pode usar |
| /sys | Informações dinâmicas sobre o kernel |
| /tmp | Diretório temporário (apaga no reboot) |
| /usr | Diretório com diretórios similares ao do raiz, mas de uso universal (todos os usuários) |

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

## Manipulação de arquivos


