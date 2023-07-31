# API GraphQL e ferramenta de visualização dos dados do Portal de Dados do IFPB

:bookmark_tabs: Este projeto é fruto do meu Trabalho de Conclusão de Curso do Curso (TCC) Superior de Tecnologia em Análise e Desenvolvimento de Sistemas pelo Instituto Federal de Educação, Ciência e Tecnologia da Paraíba - Campus Cajazeiras. 

## Sobre o projeto

ℹ️ O [**Portal de Dados do IFPB**](https://dados.ifpb.edu.br/) conta com uma lista de conjuntos de dados sobre informações importantes, como alunos, servidores, projetos de extensão e pesquisa, cursos e etc., da instituição. Todos os dados de uma instituição pública governamental **devem ser disponibilizados utilizando os meios que a Tecnologia da Informação (TI) proporciona**, para fins de transparência, conforme a Lei de Acesso à Informação (LAI).

Embora o Portal de Dados do IFPB publique seus conjuntos de dados online nesse portal, os mesmos contam com mecanismos de busca e filtros limitados, nos arquivos .CSV (arquivos separados por vírgulas) ou não são legíveis (arquivos .JSON - *JavaScript Object Notation*). 

💡 Como proposta de facilitar o acesso aos dados, o projeto desse TCC implementa uma API utilizando GraphQL, para consultas mais específicas e rápidas, resolvendo problemas de alto tráfego de dados desnecessários na rede em conjuntos de dados com grande volume de informações e dispõe de uma aplicação complementar para visualização dos dados, consruída com React.

### 🔧 Tecnologias utilizadas 

**Backend:**

<div>
  <div>
    <figure>
      <img src="https://user-images.githubusercontent.com/25181517/192107856-aa92c8b1-b615-47c3-9141-ed0d29a90239.png" alt="GraphQL" style="width: 5%">
      <figcaption>GraphQL</figcaption>
    </figure>
  </div>
  <div>
    <figure>
      <img src="https://user-images.githubusercontent.com/25181517/183568594-85e280a7-0d7e-4d1a-9028-c8c2209e073c.png" alt="Node.JS" style="width: 5%">
      <figcaption>Node.JS</figcaption>
  </figure>
  </div>
  <div>
    <figure>
      <img src="https://user-images.githubusercontent.com/25181517/183859966-a3462d8d-1bc7-4880-b353-e2cbed900ed6.png" alt="Express" style="width: 5%">
      <figcaption>Express</figcaption>
    </figure>
  </div>
</div>

**Frontend:**

<div>
    <figure>
      <img src="https://user-images.githubusercontent.com/25181517/183897015-94a058a6-b86e-4e42-a37f-bf92061753e5.png" alt="React" style="width: 5%">
      <figcaption>React</figcaption>
    </figure>
  </div>

**Banco de Dados:**

<div>
    <figure>
      <img src="https://user-images.githubusercontent.com/25181517/182884177-d48a8579-2cd0-447a-b9a6-ffc7cb02560e.png" alt="MongoDB" style="width: 5%">
      <figcaption>MongoDB ou MongoDB Atlas</figcaption>
    </figure>
  </div>
  
**Ferramentas:**

<div>
    <figure>
      <img src="https://user-images.githubusercontent.com/25181517/192108891-d86b6220-e232-423a-bf5f-90903e6887c3.png" alt="Visual Studio Code" style="width: 5%">
      <figcaption>
        Visual Studio Code
      </figcaption>
    </figure>
  </div>

<div>
    <figure>
      <img src="https://user-images.githubusercontent.com/25181517/192108372-f71d70ac-7ae6-4c0d-8395-51d8870c2ef0.png" alt="Git" style="width: 5%">
      <figcaption>
        Git
      </figcaption>
    </figure>
  </div>

<div>
    <figure>
      <img src="https://user-images.githubusercontent.com/25181517/192108374-8da61ba1-99ec-41d7-80b8-fb2f7c0a4948.png" alt="GitHub" style="width: 5%">
      <figcaption>
        GitHub
      </figcaption>
    </figure>
  </div>

## ▶️ Executando

Primeiro, clone este repositório:

```
  git clone https://github.com/moacirdavidag/tcc-ads-api-graphql.git
```

Com o repositório clonado, siga as seguintes etapas para rodar o backend e o frontend:

### Executando o backend

Dentro do repositório clonado, vá até o direitório do backend:

```
  cd ./backend-tcc-ads
```

Em seguida, baixe todas as dependências do projeto:

```
  npm install
```

Logo após, crie um arquivo chamado **.env** para configurar as variáveis de ambiente e coloque os seguintes pares chave-valor:

```
// Rodando em modo local

DB_PORT = número da porta
DB_NAME = dadosifpb

// Rodando em modo produção

DB_PRODUCTION_USERNAME= Nome do usuário de acesso do Banco de Dados MongoAtlas
DB_PRODUCTION_PASSWORD= Senha do usuário de acesso do Banco de Dados MongoAtlas

// Configuração do ambiente

PORT = Porta para rodar a API
NODE_ENV= development (para deploy) ou local (rodando em servidor local)
```

#### Importando os dados para o banco de dados

É preciso carregar o banco de dados com os dados dos conjuntos. Para isso, dentro do repositório ***backend-tcc-ads***, siga as seguintes etapas:

1- Vá ao diretório **./src/resources/data/**:

```
  cd ./src/resources/data
```

2- Utilize o comando **mongoimport** da ferramenta MongoDB Shell (Para saber mais e como instalar, clique [aqui](https://www.mongodb.com/docs/database-tools/installation/installation/)).

```
mongoimport --uri <uri> --db dadosifpb --collection nomeColecao --file ./nomeArquivo.json  --jsonArray
```

 Em que:
   <ul>
     <li> --uri: é o endereço do banco de dados. Troque <uri> pelo link de conexão do seu banco; </li>
      <li> --db: nome do banco de dados. O valor recomendado é dadosifpb;</li>
      <li> --collection: nome da coleção. O valor aqui será o nome do conjunto de dados que importaremos. <b>Cada conjunto de dados tem um nome de sua coleção exato</b>; </li>
       <li> --file : nome do arquivo json que contém os dados corretos de cada coleção. Exemplo: para a coleção alunos, o valor deste campo é ./alunos.json . </li>
   </ul>

**Nomes exatos das coleções dos conjuntos de dados**

No comando de importação dos dados, é preciso passar o nome da coleção em que os dados serão importados. Eles prexisam ser exatamente iguais ao nome que foi implementado nos *models* da API. Cada conjunto de dado com seus respectivos nomes da coleção estão abaixo:

<ul>
  <li>Alunos: alunos</li>
  <li>Bolsas estudantis: bolsas</li>
  <li>Campi: campis</li>
  <li>Cursos: cursos</li>
  <li>Patrimônio: patrimonios</li>
  <li>Projetos de Extensão: projetosdeextensaos</li>
  <li>Projetos de Pesquisa: projetosdepesquisas</li>
  <li>Servidores: servidores</li>
  <li>Setores: setores</li>
  <li>Versões do SUAP: versoessuap</li>
</ul>

**Após feita as configurações acima:**

Para iniciar o servidor da API, dentro do diretório ./backend-tcc-ads, rode o seguinte comando:

```
  npm start
```

### Executando o frontend

Dentro do repositório clonado, vá até o direitório do frontend:

```
  cd ./frontend-tcc-ads
```

Em seguida, baixe todas as dependências do projeto:

```
  npm install
```

Logo após, crie um arquivo chamado **.env** para configurar as variáveis de ambiente e coloque os seguintes pares chave-valor:

```
REACT_API_URL= URL da API do backend (normalmente localhost://4000 ou porta específicada no .env do backend)
NODE_ENV=d evelopment (modo produção) ou local (rodando localment)
```
Feito as etapas acima, execute o seguinte comando para executar o frontend:

```
  npm start
```


