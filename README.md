# ATVD01-BIM4
## ATIVIDADE AVALIATIVA, REFERENTE A NOTA PARCIAL DO QUARTO BIMESTRE DA DISCIPLINA DE DESENVOLVIMENTO DE SISTEMAS PARA A INTERNET 
### ALUNAS: ANNY JULIANE CARVALHO DE ARAUJO E LUIZA LIRA 
#### TUTORIAL SOBRE VALIDAÇÃO DE ENTRADAS

    
    
   
       
#####       A priori é importante conceituar o que é uma verificação de dados, e por quais motivos ela deve estar presente na estrutura dos nossos projetos para que assim evitemos possíveis complicações futuras quando o projeto for entregue ao usuário. Em tecnologia de informações temos uma pequena tese, que pode até ser citada como regra absoluta do desenvolvimento de sistemas para a internet, a mesma é de que não existe garantia alguma da segurança ou utilidade (benéfica ou maléfica) dquela informação no sistema e quais serão suas consequências no funcionamento do script, outro fator importante que colabora para a obrigatoriedade da verificação é a incerteza de ue se  os dados estão ou não nos formatos e tipos necessários para a sua aplicação.  
 
   
   A ferramenta  nas quais iremos utilizar para que consigamos validar a entrada de dados da rorma correta em nosso scipt pode variar de acordo com a sua escolha, existem algumas opções, a primeira a ser citada é a verificação manual, que sem sombras de dúvidas é a mais trabalhosa, mais complexa e a que vai lhe roubar mais tempo. Já um método mais eficaz e também o mesmo no qual iremos lhe instruir a utilizar hoje aqui. A biblioteca, podem ser utilizada várias bibliotecas para atender a essa necessidade, mas a biblioteca na qual iremos priorizar hoje, já que na diante de uma análise em aspectos gerais, é a que melhor atende a necessidade apresentada para nós hoje.É o express-validator, com um nome bem auto explicativo.
   
    Antes de dar início as primeiras instruções de como iremos aplicar a biblioteca express-validator, precisamos apresentar uma pequena conceituação do que é a express-validator, a mesma é uma biblioteca que pode ser utilizada no node.js trazendo o express em anexo, o seu principal uso é a validação de dados, que também é o pilar estrutural pelo qual todo o nosso trabalho é sustentado.
    
    
    
     Para a realizarmos a instalação da biblioteca iremos utilizar o seguinte comando:
     
   <pre><code>npm install --save express-validator</code></pre>
   
    Agora é preciso entender como o processo de validação dos dados ocorre dentro do projeto, para que as informações sejam averiguadas de acordo com a necessidade do sistema. Para que o procedimento de validação de dados se inicie, primordialmente existe uma necessidade de importação de uma variável "body" que vai ter como função dentro do script a validação de dados de entrada, e o validationResult, que armazenará o resultado da entrada, afirmando se a mesma é válida ou não.
    
     Logo a seguir desse procedimento, a necessidade de colocar a validação como um middleware na request, se mostra aparente, e é possível realizar o desenvolvimento deste processo utilizando um array antes do request e response, da forma a seguir:
     

    
     
     
