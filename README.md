# O que aprendi?
_Durante a aula, aprendemos sobre os comandos Batch e suas funções. Neste documento, explicarei detalhadamente o processo e o resultado final do meu aprendizado._
### Descrição do Script
O scriptch tem como principal objetivo criar diretórios e arquivos, além de navegar entre eles. Nesse script, em particular, organizamos um código para criar um calendário feito de pastas com base nos meses do ano e subpastas numeradas de 1 até o número de dias daquele mês. Sendo assim, ao invés de criar manualmente, o script realiza isso de forma automática, o que pode economizar tempo e garantir que a estrutura de arquivos seja criada corretamente, com menos erros, automatizando também a organização e estruturação dessas pastas.

## Código
![image](https://github.com/user-attachments/assets/dbf37f69-660e-418f-891d-cb0ac8a379e7)
### - @echo off
Esse comando desativa a exibição dos comandos no prompt de comando, ou seja, apenas os resultados das instruções serão mostrados, e não o próprio código do script.
### - echo %1
Esse comando exibe o valor do primeiro argumento passado ao script. O %1, no caso, se refere a 2025.
### - echo %2
Exibe o valor do segundo argumento passado ao script. Da mesma forma que o %1, o %2 refere-se ao segundo parâmetro passado ao script na execução. 
Por exemplo, calendario.bat 2025 **2**
### - mkdir %1 e mkdir %2
Cria um diretório com o nome do primeiro argumento (%1) ou do segundo (%2). Isso cria uma pasta no sistema com o nome que foi passado ao script.
### - cd %1 e cd %2
O comando cd altera o diretório atual para o especificado.
___
![image](https://github.com/user-attachments/assets/b563871c-9746-4822-be6a-f4f891e119d4)
### if %month%==X set days=Y
Cada bloco de código if %month%==X set days=Y verifica o número do mês e define o número de dias (days) correspondente a ele. Por exemplo:
Se o mês for fevereiro (%month%==2), a variável days será definida como 28, pois o mês de fevereiro normalmente tem 28 dias.
### for /L %%D in (1,1,%days%) do (
Esse comando é um loop que irá iterar de 1 até o número de dias do mês (%days%). O parâmetro /L especifica que é um loop de números inteiros.
O loop começa em %%D=1 e vai até %%D=%days% (valor definido no passo anterior).
O %%D é a variável do loop, e a cada iteração ela vai receber um número de 1 até o número de dias do mês.
### mkdir %%D
Dentro do loop, esse comando cria uma pasta numerada com o número atual de %%D. Então, por exemplo, se o mês for fevereiro (28 dias), serão criadas 28 pastas com os nomes de 1 a 28 dentro da pasta %2.

## Desafios e soluções
#### DESAFIO: Como a programação é de um calendário, dentro de cada mês seria necessário criar de 28 a 31 subpastas, o que exigiria muito mais trabalho. 
#### SOLUÇÃO: Então, usando o comando "if $month%==x set days==y" o processo ficou bem mais rápido.

## Conclusão
O Scriptch funciona muito bem, entretanto, entre as melhorias possíveis, estão tratar anos bissextos, o script assume que fevereiro tem 28 dias, mas em anos bissextos, fevereiro tem 29 dias. Adicionar uma verificação para anos bissextos tornaria o script mais preciso.
Ao criar o script, aprendi a usar comandos Batch para automatizar a criação de pastas e arquivos, tornando o processo mais rápido e sem erros. Isso facilita a organização de arquivos, como projetos e backups.
