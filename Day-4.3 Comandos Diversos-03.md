##### Comando su

O comando su permite elevar os privilegios de usuarios comuns para o usuario root
```shell
su

su -  = Logo como root, eliminando todas as variaveis de ambiente e inicia um ambiente completamente novo,tornando uma pratica mais segura.
su - <user> -s /bin/bash = loga on o usuario especificado com o shell /bin/bash, o que poderia especificar outro shell tambem

```


###### Comando sudo

O comando "sudo" também possibilita a elevação de privilégios para o superusuário. Sua vantagem está em permitir especificar quais usuários podem elevar seus privilégios para o root, adicionando-os ao grupo "sudo".

```shell

adduser <user> sudo: Adiciona um usuário ao grupo "sudo".

deluser <user> sudo: Remove um usuário do grupo "sudo".

sudo su: Faz login como usuário root usando as credenciais do usuário atual.


```


###### Comando sync

*O comando "sync" permite que os buffers (cache de dados a serem gravados na memória) sejam sincronizados e escritos do kernel para o disco.*


##### comando uname
O comando "uname" exibe informações sobre o sistema operacional. Ele pode fornecer detalhes como o nome do kernel, a versão, o tipo de hardware e outras informações relacionadas ao sistema.

```shell

- `uname -a`: Retorna informações completas do sistema operacional, incluindo nome e versão do kernel, arquitetura e compilação.
- `uname -s`: Exibe o nome do kernel.
- `uname -n`: Mostra o nome da máquina na rede (hostname).
- `uname -r`: Apresenta a versão atual do kernel.
- `uname -v`: Indica a data em que o kernel foi compilado.
- `uname -m`: Informa a arquitetura utilizada no kernel.

```


##### Comando reboot
O comando reboot basicamente reinicia a maquina

```
- `systemctl reboot`: Reinicia o sistema, outra sintaxe para o comando "reboot".

- `reboot -f`: Reinicia o sistema forçadamente, sem fechar os programas primeiro.

- `shutdown -r now`: Reinicia o sistema usando o comando "shutdown".

- `echo b > /proc/sysrq-trigger`: Reinicia o sistema interagindo diretamente com o kernel.




```



###### comando halt

O comando halt  basicamente reinicia a maquina

```shell
- `halt`: Desliga o sistema.
- `systemctl halt`: Outra forma de desligar o sistema.
- `shutdown -h now`: Desliga o sistema usando o comando "shutdown".
- `echo o > /proc/sysrq-trigger`: Desliga o sistema interagindo diretamente com o kernel.
- `shutdown -h <horario>` (por exemplo, `shutdown -h 09:40`): Agenda o desligamento da máquina para um horário específico.
- `shutdown -h +10`: Desliga a máquina em 10 minutos.
- `shutdown -c`: Cancela o desligamento ou reinício agendado.
```



###### Comando wc
O comando "wc" é usado para contar o número de palavras, bytes e linhas em um arquivo ou na entrada padrão.

```shell
❯ wc /etc/passwd
  31   68 1697 /etc/passwd
```

*1697 - o tamanho do arquivo*

*31   - numero de linhas dos arquivo*

*68  -  numero de palavras dentro do arquivo*


```
wc -l = retorna o numero de linhas

wc -c = retorna o numero de bytes

wc -w = retorna o numero de palavras

```



###### Comando seq


```
seq 10
```
- Enumera a sequência de 1 até 10.

```
seq 2 10
```
- Enumera a sequência de 2 até 10.

```
seq 2 2 10
```
- Inicia a partir do número 2, avançando de 2 em 2 até o número 10. O segundo "2" representa o intervalo entre os números.

```
seq -w 15
```
- O comando "seq -w" é utilizado para imprimir uma sequência de números com preenchimento de zeros à esquerda.


