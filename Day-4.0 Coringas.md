### Caracter coringas

**Coringas**

```
*  - identificado nenhum, um ou mais de um carater naquela posicao
 ? - Identifica um carater naquela posicao apenas
[] - Identifica um padrao
{} - Identifica padrao de strings
^ 
```

**exemplo de uso do caracter   `*`

![[Pasted image 20240418161259.png]]


**Veja que e possivel combinar o caracter coringas com letras**
![[Pasted image 20240418161625.png]]

**exemplo de uso do caracter   `?`

![[Pasted image 20240418161713.png]]
**buscando com 2 caracteres depois da letra m**
![[Pasted image 20240418161808.png]]
**Buscando com 2 coringas **

![[Pasted image 20240418164223.png]]


**exemplo de uso do caracter   `[ ]`
lista todos que comecao com a letra m e depois vem da letra a ate z

![[Pasted image 20240418164430.png]]
**entendendo o caracter** `^`
o caracter ^ indica que tudo que vier depois dele sera ignorado.

exemplo :![[Pasted image 20240424093003.png]]
![[Pasted image 20240418164732.png]]


![[Pasted image 20240418164839.png]]



**Exemplo de uso do caracter   `{ }`

![[Pasted image 20240418165245.png]]

*repare que dentro dos conchetes tem as strings `zd,ze` o que significa quer que faco um busca que comece com x depois vem com as letras zm e ze.*

