<img src="https://storage.googleapis.com/golden-wind/experts-club/capa-github.svg" />

# Como funciona e Quando usar ElasticSearch

Nessa aula o objetivo será mostrada como é o funcionamento do ElasticSearch e todos os outros produtos do ElasticStack. O ElasticSearch é muito mais que um mecanismo de busca inteligente.  É o mais importante quando usar e como devemos escala o ElasticSearch no seu projeto. 

**Cenário**: Vamos imaginar que precise de uma busca de texto, que nela me retorne as categorias dessa palavra ou frase. Por exemplo: Notebook
Eu quero que retorne as todas as marcas, tamanho de tela e tecnologia

**Requisitos**:
Extensão do Chorme (Colab)

https://chrome.google.com/webstore/detail/open-in-colab/iogfkhleblhcpcekbiedikdehleodpjo

### Script usado:

Para instalar
```
!pip install tensorflow-io
!pip install elasticsearch
```

depois

```
%%bash

wget -q https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-oss-7.9.2-linux-x86_64.tar.gz
wget -q https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-oss-7.9.2-linux-x86_64.tar.gz.sha512
tar -xzf elasticsearch-oss-7.9.2-linux-x86_64.tar.gz
sudo chown -R daemon:daemon elasticsearch-7.9.2/
shasum -a 512 -c elasticsearch-oss-7.9.2-linux-x86_64.tar.gz.sha512 
```

````
sudo -H -u daemon elasticsearch-7.9.2/bin/elasticsearch
````

**Para verificar se foi criado**
````
%%bash

curl -sX GET "localhost:9200/"
````

**Para criar um doc***
````
%%bash
curl -XPUT localhost:9200/movies/_doc/200002?pretty -H 'Content-Type: application/json' -d '
{
  "title" : "Harry Potter 22",
  "generes" : ["Adventure","Fantasy"],
  "year" : 2022
}
'
````

**Para verificar o indice**

````
%%bash
curl -XGET localhost:9200/movies/_search?q=title:harry -H 'Content-Type: application/json'
````


## Expert

| [<img src="https://avatars.githubusercontent.com/u/57687300?s=400&u=79494f446d1fa4c328e4a7902ec790e9179a4889&v=4" width="75px;"/>](https://github.com/samantadearaujo") |
| :-: |
|[Sam](https://github.com/samantadearaujo)|
