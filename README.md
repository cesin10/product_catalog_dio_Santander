# Microserviços - Dio Santander

### Aula :
"Construindo um projeto com arquitetura baseada em microserviços usando Spring Cloud"


## Arquitetura de microserviços



Essa arquitetura separa a responsabilidade do software em partes independentes que comunicam entre si de forma transparente ao usuário final. 

Tal comunicação pode ser realizada com serviço de mensageria entre os serviços de forma que garante a operacionalidade do sistema não travando e não apresentando para o usuário uma experiência ruim quando há falhas. 

Com a mensageria pode-se conifgurar um ambiente que em caso de falha de um serviço específico as informações de um servixo X fica armazenada em um pool (fila) e assim que o serviço Y suber denovo o usuário não perde a informação.

Esse projeto demonstra como fazer isso utilizando o Redis e o Elasticsearhc, com um serviço que cataloga produto, onde as informações do produto estão sendo armazenadas no Elasticsearch, e o carrinho de compras em outro serviço utilizando o Rdis que é um banco de dados de cache.

O Service Discovery é o mensageiro que tem a responsabilidade de fazer a comunicação entre os microserviços, o catalogo de produto, e o carrinho de compras (Elasticsearch e Redis) .

Para comunicação externa e/ou autenticação, temos outra serviço importante que é o Gateway, que gerencia 
as infomação que são trocadas entre o front-end e back-end como por exemplo as requisições API.

