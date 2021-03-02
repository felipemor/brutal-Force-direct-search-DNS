Para agilizar o processo de pesquisa direta de DNS é
importante termos scripts que automatizem esse
processo, por exemplo, o processo de busca de
subdomínios é algo que pode tomar muito tempo de
um atacante e com scripts é possível obter resultados
rapidamente.
Vamos criar um script que realize esta tarefa.
Primeiramente, crie ou baixe um arquivo com nomes
de subdomínios. Como demonstrado abaixo, utilize o
editor de sua preferência:
www
mail
docs
ftp
tribo
painel
...
Agora que temos uma lista com subdomínios, vamos
criar o script que irá consultar o nosso arquivo sub-
domains.lst.
Para criar o script, utilize um editor de texto e digite os
códigos abaixo:

#!/bin/bash
for url in $(cat sub-domains.lst);
do host $url.$1 |grep "has address"
done


#!/bin/bash : Indica a shell que o script irá
utilizar para processar os comandos.


for url in $(cat sub-domains.lst): Cria uma
variável que irá verificar os nomes dentro do
arquivo sub-domains.lst.

do host $url.$1 |grep "has address": aplica o
comando host na variável criado anteriormente e
mostra apenas os resultados que serão
encontrados, fazendo com que os nomes que ele
não encontrar não sejam apresentados na tela.
done: 

Finaliza o script.
