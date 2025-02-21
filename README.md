📦 Assistente de Delivery com AWS Step Functions e Bedrock

Este projeto faz parte do Bootcamp Engenharia de Prompt da DIO, no desafio Criando um Assistente de Delivery com AWS Step Functions e Bedrock. Ele utiliza AWS Step Functions para orquestrar chamadas ao Amazon Bedrock, criando um fluxo automatizado de sugestões para um jantar romântico.

🚀 Tecnologias Utilizadas

AWS Step Functions: Para orquestração dos fluxos de execução.

Amazon Bedrock: Para processamento de linguagem natural com o modelo Amazon Titan Text Express v1.

📜 Descrição do Fluxo

Este assistente faz três chamadas ao Amazon Bedrock para gerar sugestões:

Sugestão de acompanhamentos para um jantar romântico com macarrão.

Sugestão de bebidas ideais para acompanhar o jantar.

Sugestão de um local perfeito para um jantar romântico.

🔗 Estrutura do Step Functions

1️⃣ Invoke model with prompt 1: Pergunta quais são três itens que combinam com um jantar romântico de macarrão.
2️⃣ Pass 1: Conecta a primeira e a segunda chamada do modelo.
3️⃣ Invoke model with prompt 2: Pergunta quais bebidas acompanham um jantar romântico.
4️⃣ Pass 2: Conecta a segunda e a terceira chamada do modelo.
5️⃣ Invoke model with prompt 3: Pergunta qual seria o local perfeito para um jantar romântico.
6️⃣ Success: Consolida os resultados em um único retorno.

📂 Estrutura do Código

{
"StartAt": "Invoke model with prompt 1",
"States": {
"Invoke model with prompt 1": { "Type": "Task", "Resource": "arn:aws:states:::bedrock:invokeModel", ... },
"Pass 1": { "Type": "Pass", "Next": "Invoke model with prompt 2" },
"Invoke model with prompt 2": { "Type": "Task", "Resource": "arn:aws:states:::bedrock:invokeModel", ... },
"Pass 2": { "Type": "Pass", "Next": "Invoke model with prompt 3" },
"Invoke model with prompt 3": { "Type": "Task", "Resource": "arn:aws:states:::bedrock:invokeModel", ... },
"Success": { "Type": "Pass", "End": true }
}
}

🛠 Como Executar

Acesse o AWS Step Functions

Crie uma nova State Machine e cole o JSON deste repositório.

Execute o fluxo e aguarde as respostas do Amazon Bedrock.

Confira os resultados consolidados ao final do fluxo.

🎯 Objetivo

Demonstrar como utilizar AWS Step Functions e Amazon Bedrock para criar um fluxo de automação inteligente, integrando modelos de IA para assistentes de delivery ou recomendações gastronômicas.

📜 Autor

<img style="border-radius: 80px;" src="https://glaulher.github.io/assets/img/sample/avatar.jpeg" width="150px;" alt=""/>
 <h4>Glaulher Medeiros</h4>

<p align="left">
<span style="inline-block;">
  <a href="https://www.linkedin.com/in/glaulher-medeiros-03799967/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" ></a>
</span>
<span style="inline-block;">
  <a href="https://glaulher.github.io/" target="_blank"><img src="https://img.shields.io/badge/github.io-gray?style=for-the-badge&logo=github&logoColor=white" ></a>
</span>

<span style="inline-block;">
  <a href="https://terminaldopenguin.blogspot.com/" target="_blank"><img src="https://img.shields.io/badge/blog-orange?style=for-the-badge&logo=blogger&logoColor=white"></a>
</span>
</p>
