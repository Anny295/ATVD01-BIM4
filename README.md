# ATVD01-BIM4
## ATIVIDADE AVALIATIVA, REFERENTE A NOTA PARCIAL DO QUARTO BIMESTRE DA DISCIPLINA DE DESENVOLVIMENTO DE SISTEMAS PARA A INTERNET 
### ALUNAS: ANNY JULIANE CARVALHO DE ARAUJO E LUIZA LIRA MARQUES
#### TUTORIAL SOBRE VALIDAÇÃO DE ENTRADAS

A priori é importante conceituar o que é uma verificação de dados, e por quais motivos ela deve estar presente na estrutura dos nossos projetos para que assim evitemos possíveis complicações futuras quando o projeto for entregue ao usuário. Em tecnologia de informações temos uma pequena tese, que pode até ser citada como regra absoluta do desenvolvimento de sistemas para a internet, a mesma é de que não existe garantia alguma da segurança ou utilidade (benéfica ou maléfica) dquela informação no sistema e quais serão suas consequências no funcionamento do script, outro fator importante que colabora para a obrigatoriedade da verificação é a incerteza de ue se  os dados estão ou não nos formatos e tipos necessários para a sua aplicação.  

A ferramenta  nas quais iremos utilizar para que consigamos validar a entrada de dados da rorma correta em nosso scipt pode variar de acordo com a sua escolha, existem algumas opções, a primeira a ser citada é a verificação manual, que sem sombras de dúvidas é a mais trabalhosa, mais complexa e a que vai lhe roubar mais tempo. Já um método mais eficaz e também o mesmo no qual iremos lhe instruir a utilizar hoje aqui. A biblioteca, podem ser utilizada várias bibliotecas para atender a essa necessidade, mas a biblioteca na qual iremos priorizar hoje, já que na diante de uma análise em aspectos gerais, é a que melhor atende a necessidade apresentada para nós hoje.É o express-validator, com um nome bem auto explicativo.
   
Antes de dar início as primeiras instruções de como iremos aplicar a biblioteca express-validator, precisamos apresentar uma pequena conceituação do que é a express-validator, a mesma é uma biblioteca que pode ser utilizada no node.js trazendo o express em anexo, o seu principal uso é a validação de dados, que também é o pilar estrutural pelo qual todo o nosso trabalho é sustentado.
  
Para a realizarmos a instalação da biblioteca iremos utilizar o seguinte comando:
     
   <pre><code>npm install --save express-validator</code></pre>
   
Agora é preciso entender como o processo de validação dos dados ocorre dentro do projeto, para que as informações sejam averiguadas de acordo com a necessidade do sistema. Para que o procedimento de validação de dados se inicie, primordialmente existe uma necessidade de importação de uma variável "body" que vai ter como função dentro do script a validação de dados de entrada, e o validationResult, que armazenará o resultado da entrada, afirmando se a mesma é válida ou não.
    
Logo a seguir desse procedimento, a necessidade de colocar a validação como um middleware na request, se mostra aparente, e é possível realizar o desenvolvimento deste processo utilizando um array antes do request e response, da forma a seguir:
     
     
![alt text](https://i.imgur.com/g1DKfb0.png)
     
Quandi o Insomnia é utilizado para fazer um request para a rota/user, com a ausência dos dados necessários, esse será o retorno apresentado pelo script:
     
![alt text](https://imgur.com/8KIFHYC.png)

Para que o procedimento apresnetado corra de maneira ininterrupta, existe a necessidade de se rer uma API de pouca complexibilidade (no mínimo ) rodado no sistema.

Esse processo no qual concluimos parte do mesmo, é o fragmento que quando implementado no projeto irá impedir que o script continue funcionando com dados inválidos e assim gerando possíveis erros nas conclusões finais, ou até mesmo no desenvolvimento do mesmo. Em caso de um erro validádo, o recomendado a priori é retornar uma mensagem para o usuário indicando um código de status HTTP, para que o mesmo esteja ciente o que ocasionol o erro no sistema no qual o usuário esteja manuseando. 

Os códigos HTTP cuja a necessidade é mais acesa, podem variar, mas os que iremos trabalhar estão unidas e organizadas em cinco classes:

1. Respostas de informação (100-199),
2. Respostas de sucesso (200-299),
3. Redirecionamentos (300-399)
4. Erros do cliente (400-499)
5. Erros do servidor (500-599)

As respostas de erro, com o intuito de notificar o usuário uma falha no sistema causada pela inserção de informação correta feita pelo usuário estão armazenadas na classes 4 e aqui poderemos citar algumas bastante usuais:

**400 Bad Request**

Quando o usuário recebe essa resposta o usuário deve se atentar ao fato de que o servidor não coseguiu interpretar a sua requisição, devido ao fato da mesma ter sido desenvolvida com uma requisição inválida. 

**401 unathorized **

Essa resposta é apresentacda pelo sistema quando existe uma necessidade de autenticação não feita pelo usuário 

**404 not found** 

O código citado no título do tópico, sem sombra de dúvidas é o mais comum na internet em consequência da frequência que ele ocorre em comparação aos outros. O mesmo indica que o servidor não conseguiu encontrar o recurso solicitado pelo usuário.

Essas serão as respostas que o script deve retorna ao usuário sempre que ocorram erros no processamento, essas respostas não são as únicas existentes, somente algumas, mas todas devem abraçar os códigos de status HTPP que são um padrão universal no desenvolvimento de sistemas para a internet. E para garantir que a entradas de dados inválidos sejam evitadas a todo custo as vezes se mostra necessária a criação de uma validação personalizada, já que a possibilidade das existentes não conseguirem atender a todas as necessidades do desenvolvedor. E é válido salientar que a biblioteca escolhida aceita um validador personalizado para cada campo.

![alt text](https://imgur.com/Uwevx9e.png)

Aqui acima podemos ver um exemplo que mostra na prática a melhor maneira de agregar tudo no qual explicamos de maneira simples e compacta, o exemplo utilizado apresenta a necessidade de entrada de um email válido, um nome que seja maior que três caracteres, a idade do usuário e que o mesmo informe uma senha com mais de 8 caracteres.

Primoridialmente o primeiro aspecto a ser observado é o de que é necessário mais de uma validação para o campo email, essa validação é simples e compacta e pode ser aplicada em qualquer campo do projeto, de maneira simples a ser explicada pode se conceituar essa parte do código como uma validação sem singularidades, ou seja, uma validação de email padrão e também temos uma validação personalizada para aumentar a garantia de que possíveis erros de entrada ocorram.
     
Também tem as validações de nome e senha que precisam ter um número mínimo de caracteres, e a última validação é que a idade precisa ser um número, caso contrário irá retornar erro.

Caso tudo esteja válido irá retornar a mensagem “Tudo válido”, aqui nessa etapa onde é impresso a mensagem, que poderia ser adicionado a lógica para salvar esse registro no banco de dados e retornar ao usuário.     

    
**REFERÊNCIAS BIBLIOGRÁFICAS**

https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status
https://www.luiztools.com.br/post/tutorial-de-validacao-de-input-de-dados-em-node-js/
https://www.devmedia.com.br/blocos-try-catch/7339
https://experienceleague.adobe.com/docs/contributor/contributor-guide/writing-essentials/markdown.html?lang=pt-BR#listas-numeradas-e-listas-de-itens
https://programandosolucoes.dev.br/2020/11/10/valida-api-express-validator/


