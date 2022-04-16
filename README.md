# Postman Collection SDK [![Build Status](https://travis-ci.com/postmanlabs/postman-collection.svg?branch=develop)](https://travis-ci.com/postmanlabs/postman-collection) [![codecov](https://codecov.io/gh/postmanlabs/postman-collection/branch/develop/graph/badge.svg)](https://codecov.io/gh/postmanlabs/postman-collection)

Postman Collection SDK é um módulo NodeJS que permite que um desenvolvedor trabalhe com Postman Collections. Usando este módulo, um desenvolvedor pode criar coleções, manipulá-las e exportá-las em um formato que os aplicativos Postman e os tempos de execução da CLI do Postman (como [Newman](https://github.com/postmanlabs/newman)) podem consumir.

Uma coleção permite agrupar solicitações individuais. Essas solicitações podem ser organizadas em pastas para espelhar com precisão sua API. As solicitações também podem armazenar respostas de amostra quando salvas em uma coleção. Você também pode adicionar metadados como nome e descrição para que todas as informações que um desenvolvedor precisa para usar sua API estejam disponíveis facilmente.

Para saber mais sobre as Coleções do Postman, visite a [seção de documentação da coleção no site do Postman](https://www.getpostman.com/collection).

> The new [Collection Format v2](http://blog.getpostman.com/2015/06/05/travelogue-of-postman-collection-format-v2/)
> builds a stronger foundation for improving your productivity while working with APIs. We want your feedback and iron
> out issues before this goes into the Postman Apps.

## Installing the SDK

O SDK do Postman Collection pode ser instalado usando o NPM ou diretamente do repositório git em seus projetos NodeJS. Se estiver instalando a partir do NPM, o comando a seguir instala o SDK e salva em seu `package.json`

```terminal
> npm install postman-collection --save
```


## Getting Started

In this example snippet we will get started by loading a collection from a file and output the same in console.

```javascript
var fs = require('fs'), // needed to read JSON file from disk
	Collection = require('postman-collection').Collection,
	myCollection;

// Load a collection to memory from a JSON file on disk (say, sample-collection.json)
myCollection = new Collection(JSON.parse(fs.readFileSync('sample-collection.json').toString()));

// log items at root level of the collection
console.log(myCollection.toJSON());
```

After loading the collection from file, one can do a lot more using the functions that are available in the SDK. To know
more about these functions, head over to
[Collection SDK Docs](http://www.postmanlabs.com/postman-collection).

## Postman Collection Schema

The collection schema outlines the JSON definition of data structure accepted by the constructor of each properties of
this SDK. In other words, this SDK provides JavaScript level object manipulation for the JSON structure defined by
Postman Collection Format in [http://schema.postman.com/](http://schema.postman.com/).

| Schema Version | Compatible SDK Versions |
|----------------|-------------------------|
| 1.0            | none                    |
| 2.0            | <3.0                    |
| 2.1            | >= 3.0                  |

Conceptually, a JSON input to the constructor of an SDK property should provide similar output when that property
instance's `.toJSON()` is called.
