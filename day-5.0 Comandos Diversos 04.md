##### Comando chattr

Claro, aqui está uma explicação mais detalhada e algumas correções:

O comando `chattr` no Linux é usado para alterar os atributos do sistema de arquivos, incluindo diretórios e arquivos. Você também pode listar esses atributos usando o comando `lsattr`.

### Lista de Atributos:

- **`+i`**: Adiciona o atributo "imutável", impedindo que o arquivo seja alterado, renomeado ou excluído, mesmo por usuários com permissões de superusuário (root). Por exemplo:
  ```
  chattr +i arquivo
  ```
- **`-i`**: Remove o atributo "imutável" de um arquivo ou diretório.

- **`+a`**: Adiciona o atributo "append-only" (somente adicionar), permitindo que novos dados sejam adicionados ao arquivo, mas não permitindo alterações nos dados existentes ou remoção do arquivo.

- **`-a`**: Remove o atributo "append-only" de um arquivo ou diretório.

- **`+R`**: Aplica as alterações recursivamente em diretórios e seus conteúdos.

- **`=aie`**: Adiciona os atributos "append-only" e "imutável" simultaneamente.
 
- **`+c`**:O atributo "+c" no comando `chattr` do Linux é usado para habilitar ou desabilitar a compressão de dados no arquivo ou diretório especificado. Quando o atributo "+c" é definido para um arquivo, ele indica que o conteúdo do arquivo deve ser compactado automaticamente pelo sistema de arquivos quando possível.

- `+s`:O atributo "+s" no comando `chattr` do Linux é usado para definir o atributo "secure deletion" (exclusão segura) em arquivos ou diretórios

- `+S`: sysnc de de forma imediata, em outras palavras(Esse atributo especifica que novas alocações de blocos de disco para arquivos dentro desse diretório devem ser feitas de forma a otimizar a busca no diretório.)

- `-D`: Realiza a sincronização imediata em diretórios, similar à função do `+S`.

### Exemplo de Uso:

Suponha que você tenha um arquivo chamado "teste" e deseje torná-lo imutável para evitar modificações acidentais ou maliciosas:

1. Visualize os atributos atuais do arquivo usando `lsattr`:
   ```
   lsattr teste
   ----i--------e---- teste
   ```

2. Para adicionar o atributo "imutável" ao arquivo:
   ```
   chattr +i teste
   ```

3. Agora, tente remover ou modificar o arquivo:
   ```
   rm -f teste
   # Resultará em: Operation not permitted

   echo "Nova linha" >> teste
   # Resultará em: Operation not permitted
   ```

4. Para remover o atributo "imutável" do arquivo:
   ```
   chattr -i teste
   ```

Após isso, você poderá remover ou modificar o arquivo normalmente.

Esses comandos são úteis em situações onde você deseja proteger arquivos críticos ou diretórios importantes contra alterações não autorizadas.

![[Pasted image 20240425225534.png]]



###### Comando cut

O comando `cut` é uma ferramenta muito útil em sistemas baseados em Unix/Linux para cortar (ou extrair) partes específicas de linhas de texto de arquivos ou da entrada padrão. Ele é frequentemente usado para cortar colunas de texto de arquivos de texto delimitados por espaço ou tabulação. 

Por exemplo, suponha que temos um arquivo chamado `dados.txt` com o seguinte conteúdo:

```
João Silva 30
Maria Souza 25
Carlos Santos 35
```

Se quisermos extrair apenas os nomes das pessoas desse arquivo, podemos usar o `cut` da seguinte forma:

```bash
cut -d ' ' -f 1,2 dados.txt
```

Neste comando, `-d ' '` especifica que o delimitador é um espaço em branco, e `-f 1,2` indica que queremos cortar a primeira e a segunda colunas do arquivo.

Isso resultaria na saída:

```
João Silva
Maria Souza
Carlos Santos
```

```
cut

cut -d ":" = informa o delimitador por exemplo o delimitor sera o : .
-f  =  especifica qual coluna/campo quer extrair do arquivo.
-b  = saída dos bytes
-c  = saida de caracteres

```

![[Pasted image 20240425234148.png]]

"Também podemos trazer duas colunas, separadas por vírgula."
```
❯ cut -d ":" -f 1,7 /etc/passwd

root:/usr/bin/bash
bin:/usr/bin/nologin
daemon:/usr/bin/nologin
mail:/usr/bin/nologin
ftp:/usr/bin/nologin
http:/usr/bin/nologin
nobody:/usr/bin/nologin
dbus:/usr/bin/nologin
systemd-coredump:/usr/bin/nologin
systemd-network:/usr/bin/nologin
systemd-oom:/usr/bin/nologin
systemd-journal-remote:/usr/bin/nologin
systemd-resolve:/usr/bin/nologin
systemd-timesync:/usr/bin/nologin
tss:/usr/bin/nologin
uuidd:/usr/bin/nologin
dhcpcd:/usr/bin/nologin
bless:/usr/bin/zsh
avahi:/usr/bin/nologin
polkitd:/usr/bin/nologin
git:/usr/bin/git-shell
geoclue:/usr/bin/nologin
rtkit:/usr/bin/nologin
sddm:/usr/bin/nologin
flatpak:/usr/bin/nologin
mpd:/usr/bin/nologin
qemu:/usr/bin/nologin
brltty:/usr/bin/nologin
gluster:/usr/bin/nologin
rpc:/usr/bin/nologin
openvpn:/usr/bin/nologin

```

Também podemos estabelecer um intervalo.


```
cut -d ":" -f 1-3,7 /etc/passwd
root:x:0:/usr/bin/bash
bin:x:1:/usr/bin/nologin
daemon:x:2:/usr/bin/nologin
mail:x:8:/usr/bin/nologin
ftp:x:14:/usr/bin/nologin
http:x:33:/usr/bin/nologin
nobody:x:65534:/usr/bin/nologin
dbus:x:81:/usr/bin/nologin
systemd-coredump:x:980:/usr/bin/nologin
systemd-network:x:979:/usr/bin/nologin
systemd-oom:x:978:/usr/bin/nologin
systemd-journal-remote:x:977:/usr/bin/nologin
systemd-resolve:x:976:/usr/bin/nologin
systemd-timesync:x:975:/usr/bin/nologin
tss:x:974:/usr/bin/nologin
uuidd:x:68:/usr/bin/nologin
dhcpcd:x:973:/usr/bin/nologin
bless:x:1000:/usr/bin/zsh
avahi:x:972:/usr/bin/nologin
polkitd:x:102:/usr/bin/nologin
git:x:971:/usr/bin/git-shell
geoclue:x:969:/usr/bin/nologin
rtkit:x:133:/usr/bin/nologin
sddm:x:968:/usr/bin/nologin
flatpak:x:967:/usr/bin/nologin
mpd:x:45:/usr/bin/nologin
qemu:x:966:/usr/bin/nologin
brltty:x:964:/usr/bin/nologin
gluster:x:963:/usr/bin/nologin
rpc:x:32:/usr/bin/nologin
openvpn:x:962:/usr/bin/nologin
```

o cut tambem pode usar a sintaxe e bits

Traga a saída dos bytes 1 a 4 no arquivo /etc/passwd.

```
cut -b 1-4 /etc/passwd
```



##### Comando cmp






