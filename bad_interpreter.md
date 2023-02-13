# Erro: /bin/bash^M: bad interpreter: No such file or directory (Linux)

- Utilizando o sistema Windows para criar um script (script.sh).
- Quando foi executa-lo no Linux, foi agraciado com o erro: /bin/bash^M: bad interpreter: No such file or directory. 
- O problema ocorre devido as diferenças no registro da quebra de linha feito pelo Windows e pelo Linux. 
- Para resolver, vamos utilizar uma expressão regular e o comando SED:

## Solução para resolver este problema sem muito esforço.
<code>sed -i -e 's/\r$//' meu_script.sh</code></br>

## Explicando rapidamente o que este comando faz:

sed: nome do programa que estamos utilizando (sed = Stream Editor);</br>

-i: Salva as alterações do arquivo. Gera um backup automatico se você fornecer uma extensão;</br>

-e <expressão regular>: Adiciona um comando a ser executado no script. Pode ser utilizado varias vezes, para adicionar multiplos comandos;</br>

‘s/\r$//’: Remove os caracteres de Carriage Return (\r) que estão no arquivo, deixando apenas os Line Feed (\n). </br>

O que vai resolver o problema.
