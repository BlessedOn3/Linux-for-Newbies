### Comando Date
``clear = limpar a tela``

`date = saida do horario atual`

`date -u = saida do horario UTC `

`date -s 08:43  =  altera o horario`

`date 101007452020 (MES/DIA/HORA/ANO)`

`hwclock --systohc = define horario de acordo com a BIOS`

`date +%d = saida monstra somente o numero do dia`

`date +%d-%y`
![[Pasted image 20240421181132.png]]

```bash
date +%d-%m-%Y
```
![[Pasted image 20240421181456.png]]

%y - curto
%Y - Por extenso

%T - hora
%J  - numero do diia do ano
![[Pasted image 20240421181632.png]]
-----------------------------------------


## Comando df
Comando df monstra cada comando montado em seu SO linux

![[Pasted image 20240421181956.png]]

```
# df -h formando mais humano, com M KB Gb
# df -H fica com formato de tamanho comercial
#df -l mostra somentes os sistemas de arquivos locais(nao mostra os montado via rede)
#df -m define a saida em MEGABYTE
#df -a incluir os pseudo filemsystem
#df -i mostra a saida com os inodes dos pontos de montagem
#df -T mostra qual sistema de arquivo utilizado em cada particao
#df -t ext4  = exibe a saida de sistema de arquivo determinada no proximo argumento

```


### Comando ln

```
ln /bin/ls ls - cria um hard link

ln -s /bin/ls ls-link
```
![[Pasted image 20240421184308.png]]
*Curiosidade : ao usar o comando `cp -l` ele copiara os arquivos usando hardlink*

**Características do Hard Link:**

1. **Referência direta para o inode:** Um hard link é uma referência direta para o inode do arquivo original.
  
2. **Localização:** Todos os hard links e o arquivo original estão no mesmo sistema de arquivos.

3. **Atualizações:** Alterações no arquivo original são refletidas em todos os hard links, pois todos compartilham o mesmo inode.
  
4. **Tamanho:** Não adiciona sobrecarga de tamanho ao sistema de arquivos, pois apenas cria uma nova entrada no diretório.
  
5. **Permissões:** Compartilha as mesmas permissões e atributos do arquivo original.

**Características do Link Simbólico:**

1. **Referência para o caminho:** Um link simbólico é um tipo especial de arquivo que contém o caminho para o arquivo original.
  
2. **Localização:** Pode atravessar sistemas de arquivos, apontando para arquivos em diferentes partições ou dispositivos.
  
3. **Atualizações:** Se o arquivo original for excluído ou movido, o link simbólico se tornará inútil, pois aponta apenas para um caminho de localização.
  
4. **Tamanho:** Adiciona um tamanho extra ao sistema de arquivos, pois precisa armazenar o caminho completo do arquivo original.
  
5. **Permissões:** As permissões do link simbólico são independentes das do arquivo original.


#### Comando du
comando exebi o a ocupacao do tamanho de cada arquvio na particao montada.

```
du -h -- exebi com blocos de 1024
du -H -- exibe com blocos de 1000
du -s -- sumarica, retorna o total bem utilizado como du -hs
du -k -- mostra em kbytes
du -m -- mostra em megabytes
du ---inodes - exebi a saida com inodes
du -c -- adiciona o total no final
```


#### Comando find

```
find <dir da pesquica> <parameter>

-name = nome
--maxdepth 2 = define que sera buscado em ate 2 dos dir
--mindepth 4 = define que sera buscado no minimo de 4 dos dir
-type f = procura por tipo no caso arquivo (file).
---------------------
Pesquisa por data

create time - quando foi criado
modified time - quando foi modificado
access time - quando foi acessado

time - dia
min  - minuto

-ctime n - criado a n dias atras
-mtime  n - alterado a n dias atras 
-atime n - acessado a n dias atras

-cmin  n - criado a n min atras
-mmin  n - modificado a n min atras
-amin  n - acessado a n min atras

--------------------- Pesquisa por GID/UID/user

-gid <numero do gid>
-uid <numero do uid>
-user <nome do usuario>
-group <nome do grupo>
--------------------Pesquisa pesquisa por links
-links <quantidades de link como referencias>

--------------------Pesquisa a partir do tamanho
-size 1000    - busca por exato mil blocos
-size -1000   - busca por menos de mil blocos
-size +1000   - busca por mais  de mil blocos
-size 1000k   - busca exato mil kbytes
-size -1000k  - busca por menos de mil kbytes
-size +1000k  - busca por mais  de mil kbytes
-size 1000c   - busca exato de mil bytes
-size -1000c  - busca por menos de mil bytes
-size +1000c  - busca por mais  de mil bytes

---------------------Pesquisa por tipo
-type f - pesquisa por tipo de arquivo
-type d - pesquisa por diretorio
-type b - pesquisa por dispositivo de bloco
-type c - pesquisa por dispositivo de caracter
-type s - pesquisa por socket
-type l - link simbolico

```

```bash
#exemplo
find /usr -mindepth 3 -maxdepth 4 -type f -name mc 
```

#### Comando free

Exibe a memoria livre do sistema operacional,memoria ram fisica e a memoria em swap

![[Pasted image 20240422222449.png]]


- **Total:** Representa a quantidade total de memória disponível no sistema.
  
- **Used:** Indica a quantidade de memória atualmente em uso pelo sistema.

- **Free:** Refere-se à quantidade de memória disponível e não utilizada no momento.

- **Shared Buff/Cache:** Esta coluna representa a quantidade de memória que está sendo compartilhada para acelerar as operações do sistema. Isso inclui tanto a memória usada para cache, que armazena dados de programas frequentemente acessados para acelerar o acesso, quanto o buffer, que é usado como cache de disco para dados recentemente lidos ou escritos. Esses recursos de cache e buffer ajudam a otimizar o desempenho do sistema, melhorando a velocidade de acesso a programas e arquivos.


1. **Mostrar em kilobytes:**
```bash
free --killo
```
Este comando mostra a saída em kilobytes.

2. **Mostrar em megabytes:**
```bash
free --mega
```
Este comando mostra a saída em megabytes.

3. **Usar o padrão de 1024 (kibi):**
```bash
free --kibi
```
Este comando utiliza o padrão de 1024 para representar os valores.

4. **Padrão de 1024 para megabytes (mebi):**
```bash
free --mebi
```
Este comando utiliza o padrão de 1024 para representar os valores em megabytes.

5. **Mostrar em gigabytes:**
```bash
free --giga
```
Este comando mostra a saída em gigabytes.

6. **Padrão de 1024 para gigabytes**
```bash
free --gibi
```
Este comando utiliza o padrão de 1024 para representar os valores em gigabytes.

7. **Mostra o padrao em megabytes em um intervalo de tempo**
```shell
free --mega -s 1
```
Este comando utiliza o padrão de mega monstrando a saida a cada 1 segundo

O comando `free` obtém as informações sobre o uso da memória diretamente do arquivo `/proc/meminfo`. Ele usa esses dados para apresentar as estatísticas de memória no sistema de forma mais acessível e compreensível.


#### Comando grep
Para realizar buscas por expressões dentro de um arquivo ou na entrada padrão, podemos usar o comando `grep`. Ele é especialmente útil para filtrar e exibir linhas que correspondem a determinadas expressões em arquivos ou na saída de outros comandos.

![[Pasted image 20240422224600.png]]

```

- grep -v : Inverte a busca, mostrando linhas que não correspondem ao padrão especificado.

- grep -f : Permite buscar por padrões em um arquivo usando expressões fornecidas em outro arquivo.

- grep -i : Ignora diferenças entre maiúsculas e minúsculas durante a busca.

- grep -E : Realiza a pesquisa por expressões regulares, interpretando o padrão como uma expressão regular.

- grep -F : Realiza a pesquisa por caracteres exatos, sem interpretá-los como expressões regulares.

- grep -r : Realiza uma pesquisa de forma recursiva.

- grep -h : uculta o nome dos arquivos.

- grep -l : lista somente o nome dos arquivos.

- grep -n : Retorna o numero da linha do arquivo que contem a expressao.
```



```shell
grep -iE '^www-data.*nologin$' /etc/passwd
```

O caractere `^` indica que a pesquisa deve começar com a string subsequente, enquanto o caractere `$` indica que a pesquisa deve terminar com a string anterior.




#### Comando head

O comando `head` é usado para exibir as primeiras linhas de um arquivo. Por padrão, ele exibe as 10 primeiras linhas, mas você pode especificar um número diferente de linhas usando a opção `-n`, seguida pelo número desejado de linhas.

```
-n = exibe o numero de linhas
-c = exibe o numero de bytes

```

