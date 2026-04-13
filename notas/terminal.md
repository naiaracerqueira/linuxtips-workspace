# Terminal (Alpine)

- Shell: interpretador de comandos, conversa com o kernel. Tipos de shell:
    - Bash
    - ZSH
    - Ohmyzsh
- FHS: Filesystem Hierarchy Standard
- Montar: disponibilizar para uso
- PID: Process identification, id de cada processo em execução.

## Comandos básicos

| Comando | Obs |
| -- | -- |
| sudo | Permissões do root por tempo limitado |
| sudo su - | Assume como root |
| exit | Sai do root |
| clear | Apaga os comandos, *ctrl+l* |
| ls | Lista diretórios e arquivos |
| ls -l | "Large", mostra detalhes de tamanho e permissão |
| ls -a | "All", todos os arquivos, inclusive os ocultos |
| ls -h | "Human readable", formata tamanho |
| ls -R | Recursivo, mostra tudo que tem dentro |
| ls -d *diretorio* | Apenas o diretório |
| cwd | Mostra path |
| cd | "Change directory" |
| cd *dir* | Vai para diretório "dir" |
| cd .. | Caminho relativo: volta um nível de diretório |
| cd ../../ | Caminho relativo: volta dois níveis de diretório |
| cd - | Volta para o diretório anterior |
| echo | Imprime na tela o que eu mando |
| >> | Altera (sobrescreve) saída padrão para |
| > | Append |
| tree | Ver a estrturura de diretórios até o / |
| history | Ver histórico de comandos |
| ps -ef | Vê processos em execução e PIDs |
| alias | Lista todos os apelidos |
| alias *apelido*='*comando*' | Dá um apelido X para um comando. Ex: alias ll='ls -lha' |
| free -m | Mostra memória do computador em megas (ou -g em gigas) |

O comando `ls -lha` retorna:
```
drwxr-xr-x   4 root root 4.0K Apr  2 14:44 boot
```
Que são
- d → significa que é um diretório
    - \- → arquivos de texto
    - l → link simbólico
    - b → dispositivo de bloco
    - c → dispositivo de caractere
    - s → socket
- rwxr-xr-x → permissões
- 4 → nível naquele arquivo ou diretório, arquivo = 1
- root → usuário dono do arquivo
- root → grupo dono do arquivo
- 4.0K → tamanho do arquivo diretório, originalmente em bytes (-h transforma)
- Apr  2 14:44 → data de criação
- boot → nome do diretório ou arquivo

Ou
```
lrwxrwxrwx  1 root root       22 Oct 24 03:46  zoom -> /opt/zoom/ZoomLauncher
```
- l → significa que é um link simbólico
- rwx → permissões do dono do arquivo: read, write, execute
- rwx → permissões do grupo do dono do arquivo: read, write, execute
- rwx → permissões dos outros: read, write, execute
- zoom -> /opt/zoom/ZoomLauncher → é o link simbólico que aponta para o opt/zoom/

## Manipulação de arquivos

| Comando | Obs |
| -- | -- |
| ls *.csv | Lista os arquivos com extensão .csv |
| ls arq-?.csv | Lista os arquivos com um caractere após 'arq-' no nome |
| ls arq-[1,2,3].csv | Lista os arquivos com nome arq-1.csv, arq-3.csv ou arq-3.csv |
| mkdir | "Make directory", cria diretório |
| mkdir -p /A/B/C/ | Cria diretório encadeado começando pelo diretório pai |
| cp *origem* *destino* | Copia arquivo |
| cp -r *origem* *destino* | Copia diretório |
| mv *origem* *destino* | Move arquivo |
| mv -r *origem* *destino* | Move diretório |
| mv *nome_inicial* *nome_final* | Renomeia arquivo |
| rm *nome_arquivo* | Remove arquivo |
| rm *nome_diretorio/** | Remove tudo dentro do diretório, mas não o diretório |
| rm -r *nome_diretorio* | Remove diretório de forma recursiva |
| rm -f *nome_diretorio* | Força remoção de diretório (sem perguntar 'yes' no meio do caminho) |
| touch | Cria arquivo vazio |
| touch arq-{1..10}.txt | Cria arquivos com nome arq-1.txt até o arq-10.txt |
| find *diretorio* -name *nome* -type *tipo* | Encontra aquivo dentro do diretório de tipo diretorio (d), arquivo (f) |
| find *diretorio* -type *tipo* -size *{+,-}tamanho* | Encontra aquivo de tamanho X (exemplo, +10k, para maiores de 10k) |
| find *diretorio* -mtime *{+,-}dias* | Encontra aquivos modificados a X dias (exemplo, +20, para mais de 20 dias) |
| find *diretorio* -iname *nome* -delete | Encontra aquivo com nome ignorando o case sensitive e o remove |
| find *diretorio* -name *nome* -exec ls -lha | Encontra aquivo e executa o ls -lha |
| cat | Visualizar conteúdo do arquivo |
| nano / vim | Abre conteúdo do arquivo |
| source | Lê alguns arquivos específicos |
| tail | Lê 10 últimas linhas do arquivo |

**Empacotar e compactar**
| Comando | Obs |
| -- | -- |
| tar -z | Compacta em formato *.gzip |
| tar -f | Fica sempre no final, indica o arquivo que será criado |
| tar -v | Verboso |
| tar -c | Cria um pacote |
| tar -czf *path_arquivo.tar.gz* *diretorio_a_ser_compactado* | Compacta e comprime o diretório |
| tar -t | Visualiza conteúdo do pacote |
| tar -tzf *arquivo.tar.gz* | Ver conteúdo do arquivo |
| tar -x | Descompacta |
| tar -xzf *arquivo.tar.gz* | Descompacta o arquivo |
| gzip | Compacta projetos |
| gzip -d | Descompata projetos |

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
| /boot	| Arquivos de inicialização do sistema |
| /dev	| Dispositivos que podem ser de caractere (transferem informações) ou de bloco (armazenam informações) e diretório |
| /etc	| "Editable text configuration": configurações do sistema |
| /home	| Diretório dos outros usuários |
| /lib	| Bibliotecas do sistema (*.so) |
| /lib/modules | Módulos do kernel |
| /media | Tipo USB, CD-ROM |
| /opt | Instalações que não fazem parte da distribuição por default |
| /proc | Informações dinâmicas sobre o sistema; diretórios numéricas se referem aos PIDs |
| /root	| Diretório do usuário administrador do sistema |
| /run | Informações sobre processos em execução |
| /sbin | Binários que somente o root (s = super) pode usar |
| /sys | Informações dinâmicas sobre o kernel |
| /tmp | Diretório temporário (apaga no boot) |
| /usr | Diretório com diretórios similares ao do raiz, mas de uso universal (todos os usuários) |
| /var	| Dados variáveis como logs, mensagens, impressão, cache, etc. |
| /var/log | Arquivos de log do sistema |

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
