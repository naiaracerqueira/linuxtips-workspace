# Linux

## Conceitos
- Kernel: comunicação entre o hardware e o sistema, é a espinha dorsal
- Unix: família de sistemas operativos multitarefa e multiutilizador desenvolvida originalmente na década de 1960/1970

## História
1983 - Richard Stallman - Criação do projeto GNU (GNU's not UNIX), com objetivo de ser um SO livre. O projeto começou a desenvolver todos os componentes necessários: compilador (GCC), editor de texto (Emacs), shell (Bash) e várias bibliotecas essenciais.
Fundou também o Free Software Foundation (software livre, não referente a gratis) e a licença GPL, que define algumas liberdades:
- Executar o programa
- Estudar e modificar o código-fonte
- Redistribuir cópias
- Distribuir as versões modificadas

90's - No início dos anos 90, o Projeto GNU tinha quase todos os componentes necessários para um sistema operacional completo - exceto um kernel funcional.

1991 - Linus Torvalds - Começou a desenvolver um kernel como hobby, inspirado pelo sistema operacional educacional MINIX (que iria virar proprietário). Kernel é a espinha dorsal do sistema operacional, é o responsável pela comunicação entre o sistema e o hardware, é nele que temos os drives/módulos.

1992 - O kernel Linux foi combinado com os utilitários e programas do Projeto GNU, criando o que tecnicamente deveria ser chamado de "GNU/Linux" - um sistema operacional completo e livre.

Quando você pensa em servidores, cloud, containers, IoT, smartphones (Android) e supercomputadores, está pensando em Linux - mesmo que não saiba disso. Mais de 90% da infraestrutura da internet roda Linux. Quase 100% das empresas Fortune 500 usam Linux nos seus ambientes. E tem mais: 100% dos supercomputadores do TOP500 rodam Linux!

Distribuições: Linux + bibliotecas + ferramentas em um instalador.
- Ubuntu Server: servidores como, VM, EC2, módulo Kubernets
- Debian: mais estáveis, com softwares mais testados (mas mais antigos)
- Alpine: para rodar containers (é mais enxuta)
- Chainguard Wolfi: undistro para rodar containers (é mais enxuta)
- RedHat: enterprise, ambiente de produção corporativo
- Amazon Linux: para AWS
