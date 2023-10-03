# Como fomentar o paradigma do aprendizado contínuo no sistema conversacional
## Introdução
Atualmente, um problema muito recorrente em algoritmos de machine learning utilizados para sistemas conversacionais é a falta de atualização de dados, fazendo com que o modelo se torne ultrapassado com o tempo, e seja cada vez menos adequado e eficaz para atender às necessidades dos usuários. Isso porque, com o decorrer do tempo, conceitos são reelaborados, novas informações surgem e tendencias passam por resignificações, além do próprio público que utiliza o sistema passar por mudanças de preferências e até mesmo sentir a necessidade de fontes mais recentes e atualizadas. Logo, um conceito importante que aborda esse problema é o "concept drift", que diz respeito à manutenção de modelos por meio da atualização contínua de dados e novos treinamentos.

## Solução
É proposta a solução de um sistema conversacional de aprendizagem contínua que, a partir da utilização da técnica de Web Scrapping, é capaz de coletar dados e manter sua base atualizada constantemente, a partir da análise de feedbacks negativos ou positivos enviados por usuários quando finalizam uma conversa, apontando exatamente aonde a solução deve agir para coletar dados mais adequados para aquele contexto.

Segue o diagrama de blocos que descreve a solução:
<img width="755" alt="image" src="https://github.com/anaclaralmz/pesquisa-aprendizado-continuo/assets/99202282/fa0b75f9-93f8-4932-a166-d00f2c5c30b5">
### Descrição dos blocos
- <b>Usuário</b>: responsável por fazer a interação com o sistema conversacional, e enviar um input que irá acionar o algoritmo desenvolvido para achar uma resposta, através do cálculo da similaridade do cosseno entre o input e os documentos da base de dados;
- <b>Sistema NLP</b>: responsável pelo tratamento de textos, tanto recebidos como input do usuário, como o tratamento dos documentos mantidos na base de dados. É utilizado sempre que um novo documento é adicionado à base de dados;
- <b>Banco de dados</b>: armazena todos os dados coletados, inclusive do web scraping, e envia os documentos similares à busca para o backend da aplicação;
- <b>Backend</b>: recebe documentos do banco de dados, e os direciona para o front-end (usuário);
- <b>Feedbacks</b>: responsáveis por disparar -se for negativo- um evento que ativa o web scraping, para atualizar a base de dados, ja que os dados ja existêntes não são relevantes o suficiente para atender à pergunta realizada;
- <b>Web scraping</b>: faz uma busca na web, em sites confiáveis pré-definidos, utilizando o texto de input ja tratado, para coletar novos dados em relação àquele contexto, e os envia para a base de dados.

## Conclusão
A abordagem de aprendizado contínuo proposta pode ajudar a manter sistemas conversacionais atualizados e eficazes ao longo do tempo. No entanto, requer um esforço significativo em termos de coleta de dados, detecção de concept drift, treinamento de modelos e avaliação contínua, além de uma arquitetura bem elaborada para sustentar esse processo sem prejudicar a latência e disponibilidade do sistema. 
Implementar essa solução exigiria recursos de engenharia e dados, mas é fundamental para fornecer uma experiência de alta qualidade ao usuário final, e destacar-se em relação a sistemas conversacionais que estão ficando pra trás com a desatualização.

## Referências
Joel Jang, Seonghyeon Ye, Sohee Yang, Joongbo Shin, Janghoon Han, Gyeonghun Kim, Stanley Jungkyu Choi, Minjoon Seo, KAIST AI, LG AI Research. Towards Continual Knowlage Learning of Language Models. arXiv:2110.03215v4 [cs.CL] 24 May 2022
https://arxiv.org/pdf/2110.03215.pdf

A. S. Iwashita and J. P. Papa, "An Overview on Concept Drift Learning," in IEEE Access, vol. 7, pp. 1532-1547, 2019, doi: 10.1109/ACCESS.2018.2886026.

https://ieeexplore.ieee.org/document/8571222

S. D. S. Sirisuriya, "Importance of Web Scraping as a Data Source for Machine Learning Algorithms - Review," 2023 IEEE 17th International Conference on Industrial and Information Systems (ICIIS), Peradeniya, Sri Lanka, 2023, pp. 134-139, doi: 10.1109/ICIIS58898.2023.10253502.

https://ieeexplore.ieee.org/abstract/document/10253502
