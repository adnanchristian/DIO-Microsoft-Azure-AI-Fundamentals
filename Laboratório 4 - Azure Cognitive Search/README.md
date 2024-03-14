# Explorando indexação com Azure AI Search (UI)

O Desafio de Projeto foi baseado no seguinte contexto: *Imagine que você trabalhe para a Fourth Coffee, uma rede nacional de cafés. Você é solicitado a ajudar a criar uma solução de mineração de conhecimento que facilite a pesquisa de insights sobre as experiências do cliente. Você decide criar um índice do Azure AI Search usando dados extraídos de avaliações de clientes.*

Após seguir o passo a passo do tutorial, disponível neste [link](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html), foram obtidos os seguintes resultados e insights.

## Exemplos de buscas

Com a indexação dos documentos da pasta *files* concluída, é possível realizar *queries* de busca. 

### Contagem de documentos

```json
{
    "search": "*",
    "count": true
}
```

O resultado desta *query* retorna informações extraídas de todos os documentos indexados e a quantidade de documentos por meio de um arquivo *.json*. É possível visualizar esse arquivo (*count.json*) na pasta *outputs* deste repositório.

### Filtro de localização

```json
{
    "search": "locations:'Chicago'",
    "count": true
}
```

Nesta outra *query* é feita a filtragem das avaliações por meio da localização. Essa localização foi extraída por meio da IA, no momento da indexação, o que permitiu realizar esse tipo de busca agora. O retorno da busca pode ser visualizado no arquivo *location.json*.

### Filtro de sentimento

```json
{
    "search": "sentiment:'negative'",
    "count": true
}
```

Por fim, nesta *query* é feita a filtragem das avaliações por meio do sentimento, algo que vimos no móduloo anterior. O retorno da busca pode ser visualizado no arquivo *negative.json*. Vale destacar que os resultado retornado são ordenado por compatibilidade com *query* por meio do atributo `@search.score`, algo muito interessante!

### Revisando a base de conhecimento

É possível visualizar como o Azure armazena o conhecimento obtido por meio da indexação realizada. No caso de imagens, os recursos de Visão Computacional são utilizados na interpretação da imagem e extração de conhecimento presente nelas para futura utilização em buscas. O arquivo *imagem.json* é um exemplo de como o Azure extraiu uma das imagens contidas nos documentos.

Além disso, o Azure organiza todas essa base de conhecimento por meio de tabelas e que identificam os atributos que selecionamos na configuração da nossa indexação, como Imagens, Palavras-Chaves, Sentimento e outros.

### Considerações finais

Por meio da prática realizada, ficou compreensível o quanto esse recurso pode ajudar na extração de informações em documentos de maneira fácil e prática. Isso poupa horas de trabalhos repetitivos e cansativos, retornando conhecimento de fácil compreensão, graças a união da Nuvem com a Inteligência Artificial.