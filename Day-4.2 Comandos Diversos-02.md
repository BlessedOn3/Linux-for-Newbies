#### Comando more
O comando `more` é utilizado no terminal do Unix/Linux para visualizar o conteúdo de um arquivo de texto, mas de forma paginada, o que significa que ele exibe uma página por vez. Isso é útil especialmente para arquivos longos, já que permite visualizar o conteúdo de forma mais organizada e controlada.

Quando você utiliza o comando `more`, o arquivo é exibido página por página e você pode navegar pelas páginas pressionando a tecla Espaço para avançar para a próxima página, a tecla Enter para avançar uma linha por vez ou a tecla Q para sair do visualizador.

Por exemplo, para visualizar o conteúdo de um arquivo chamado `exemplo.txt`, você pode usar o seguinte comando:

```
more exemplo.txt
```

Isso exibirá o conteúdo do arquivo `exemplo.txt` uma página por vez, permitindo que você o leia de forma mais fácil.



#### Comando less

O comando `less` é uma versão mais avançada do comando `more`. 
Algumas das principais características do `less` incluem:

1. **Navegação bidirecional**: Além de rolar para frente através das páginas do arquivo, você também pode rolar para trás, o que não é possível com o `more`.

2. **Pesquisa**: Você pode pesquisar por texto dentro do arquivo pressionando `/` seguido do termo de pesquisa e pressionando Enter. O `less` destacará todas as ocorrências encontradas.

3. **Avanço e retrocesso por linhas**: Além de avançar e retroceder por páginas, você também pode rolar uma linha por vez para cima ou para baixo usando as teclas de seta ou as teclas Page Up e Page Down.

4. **Visualização de números de linha**: Por padrão, o `less` exibe os números de linha à esquerda, o que pode ser útil para referência.

Para usar o `less`, basta digitar `less` seguido do nome do arquivo que você deseja visualizar. Por exemplo:

```
less exemplo.txt
```

Depois de abrir o arquivo com o `less`, você pode usar as teclas de navegação e pesquisa mencionadas anteriormente para interagir com o conteúdo do arquivo. Quando terminar de visualizar o arquivo, você pode pressionar `q` para sair do `less` e voltar ao prompt do terminal.


####  Comando sort

**Exemplo do comando sort**

```
sort list.txt 
```

![[Pasted image 20240423123746.png]]

```
sort -r = inverte a classificao da listagem
sort -n = classifica em ordem numerica
sort lista.txt -c = verifica se a lista esta ordenada ou nao e retorna como ordenado ou desordenado.
sort -(n) =usa uma numeração de colunas baseada em zero para especificar a coluna a ser ordenada
sort -t = define um delimitador de qual ele vai ordenar
sort -k (n) = usa uma numeração de colunas baseada em um
```

###### Entendendo o sort -c 

No comando

```shell
sort lista.txt | sort -n -c
```

o segundo `sort -n -c` não garante que a lista esteja ordenada numericamente porque o primeiro `sort` não foi especificado para ordenar numericamente. O `sort -n -c` simplesmente verifica se a lista está ordenada numericamente, mas não a ordena numericamente antes disso.

A correção para esse exemplo seria:

```shell
sort -n lista.txt | sort -n -c
```

Aqui, o primeiro `sort -n` ordena numericamente a lista antes de passá-la para o segundo `sort -n -c`, que então verifica se está ordenada numericamente.

##### Entendendo sort por colunas

Ao usar o comando `sort` sem especificar uma coluna específica, ele irá ordenar os itens da lista considerando a primeira coluna como padrão. Isso é equivalente a especificar `sort +0`, onde a numeração das colunas começa em zero.

Para ordenar pela segunda coluna, podemos utilizar `sort +1`, considerando que a numeração das colunas segue a lógica de 0 para a primeira coluna, 1 para a segunda, e assim por diante:

```shell
cat lista_nova.txt | sort +1
Jeferson Fernando
Guia Foca
Vai LinuxTips
Gleydson Mazioli
LinuxTips Vai!
```

Podemos também utilizar um delimitador para definir onde as colunas começam e terminam. Por exemplo, ao definir "F" como delimitador, o `sort` entenderá que tudo antes da letra "F" pertence à primeira coluna (0), e tudo após a letra "F" pertence à segunda coluna (1):

```shell
cat lista_nova.txt | sort +1 -t "F"
Gleydson Mazioli
LinuxTips Vai!
Vai LinuxTips
Jeferson Fernando
Guia Foca
```

Além disso, o comando `sort -k` é similar ao `sort +n`, mas com a numeração das colunas começando em 1. Por exemplo, para ordenar pela primeira coluna, usaríamos:

```shell
cat lista_nova.txt | sort -k 1
Gleydson Mazioli
Guia Foca
Jeferson Fernando
LinuxTips Vai!
Vai LinuxTips
```

Substituindo o "1" por "2", poderíamos ordenar pela segunda coluna, e assim por diante.

#### Comando tail
O comando `tail` é usado para visualizar o final de um arquivo, o que é semelhante ao comando `head`, que permite visualizar as primeiras linhas. Enquanto o `head` exibe as 10 primeiras linhas por padrão, o `tail` exibe as 10 últimas linhas por padrão.

- `tail <arquivo>`: Mostra as últimas 10 linhas do arquivo.
- `tail -n <número>`: Define o número de linhas a serem mostradas na saída do comando.
- `tail -f`: Mostra as últimas linhas do arquivo em tempo real, útil para visualizar atualizações recentes, como logs em tempo real.


#### Comando Time

O time e um comando de retorno o tempo de execucao de um comando

```shell
time <comando> 

root@DebianServer:/home/bless# time ls

real	0m0.004s
user	0m0.001s
sys	0m0.004s
root@DebianServer:/home/bless# 
```


#### Comando touch

permite voce criar um arquivo vazio e permite tambem modificado a hora e a data do arquivo que foi criado

```
touch <nome do arquivo> = ira criar um novo arquivo

touch -t mmddaa <arquivo> = modifica a data do arquivo

touch -a -t = modifica o access time que e o time de ultimo acesso do arquivo

```

![[Pasted image 20240423200215.png]]

```shell
touch -t 10120815 arquivo 
root@DebianServer:/tmp# ls -la arquivo 
-rw-r--r-- 1 root root 0 Oct 12  2024 arquivo
root@DebianServer:/tmp# 
```




##### Comando uptime

O comando `uptime` exibe o tempo de funcionamento do sistema desde o último reinício.

![[Pasted image 20240423201807.png]]



##### Comando dmesg

O comando `dmesg` acessa o ring buffer do kernel, uma área reservada para armazenar as últimas mensagens do contexto do kernel. Por padrão, exibe aproximadamente 64 KB de mensagens.

![[Pasted image 20240423202118.png]]

```
dmesg -t: Retorna mensagens sem o timestamp.

dmesg --color=never: Retorna mensagens sem cor

dmesg --color=auto: Retorna mensagens com cor.

dmesg -w: Similar ao tail -f, mostra as últimas linhas do dmesg em tempo real.

dmesg -T: Transforma o timestamp do boot para data/hora legível.

dmesg -c: Limpa as mensagens do buffer do kernel.

```


##### Comando echo
O comando echo imprime uma mensagem na tela

```shell
echo -n = suprime a quebra de linha
echo -e = ativa a interpretação de caracteres especiais.

```