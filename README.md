# gelato_magico
projeto de criação de um modelo de regressão para prever vendas de sorvetes baseadas na temperatura

#Somos a Gelato Mágico 🍨. Estamos sediados em uma cidade litorânea. Vendemos sorvetes diariamente e percebemos que o volume destas vendas está fortemente relacionado com a temperatura. Porém, não temos planejamento para produzir uma quantidade adequada de sorvetes que dê lucro sem desperdícios. Então, vamos criar um modelo de machine learning para melhorar nossa produção com os objetivos de evitar desperdícios e otimizar as vendas.

Para tanto, vamos criar uma estrutura no Azure Machine Learning para elaborar, testar e validar nosso modelo. Primeiro, precisamos preparar o ambiente de desenvolvimento deste projeto seguindo os seguintes passos:
1. Criar uma conta no Azure Machine Learning e criar um grupo de recursos em uma assinatura ativa
2. Criar um Machine Learning que estará vinculado ao grupo de recuros que criei

Após a criação do Grupo de Recuros e do Machine Learning:
1. Acesso meu ambiente criado e insiro minha base de dados no recurso notebook
2. Acesso menu -> compute para criar uma instãncia para realização de testes no jupyter notebook: selecionar CPU e uma virtual machine
3. Criar um cluster nas com settings: dedicado, CPU, virtual machine com memoria otimizada
4. Criar um dataset com os dados da sorveteria Gelato Magico com settings: temperatura e vendas
5. executar o modelo com Automated Ml com settings: task type: linear regression, target: vendas, limits-> max nodes:1 , minutes : 15 max, validation: automatic, compute: compute cluster, algorithm: XBoostRegressor (em additional configuration settings). execução em submit job.
6. Criar um designer: data: sorvetes, split data com settings: split 20%; columns transform  com settings:vendas, temperaturas; train model com settings: linear regression, seed: 1; evaluate model com settings: score model; label column com settings: vendas, explain: no; . execução em review + submit
7. Verificar o trabalho dos jobs gerados e, estando encerrados, realizar o deploy. Com o deploy realizado o REST ENDPOINT é disponibilizado para accesso por uma web service ou um endpoint.


