---
layout: post
title:  "Introdução Express"
description: "Simples Hello World usando Express com NodeJS, uma introdução baseada na documentação."
date:   2016-12-01
category: "nodejs"
author: "David Alves"
avatar: "https://avatars1.githubusercontent.com/u/4975560?s=460&v=4"
---



<p>Salve galera! Primeiro post vou ensinar como fazer um simples Hello World usando Node.js e Express, pra quem não sabe o Express é um framework para o Node.js que fornece um conjunto de recursos para aplicações web e móveis. </p>

<p>Supondo que você já tenha o Node.js instalado na sua máquina vamos fazer a instalação do Express via NPM digitando o comando no terminal.</p>

{% highlight ruby %}
$ npm install express -g
{% endhighlight %}

<p>Usando o parâmetro -g estamos instalando o Express em modo global, assim da próxima vez que for usar, basta apenas fazer o require na aplicação sem a necessidade de instalar novamente.
Próximo passo é criar um diretório onde ficarão todos os arquivos da aplicação, navegue até o diretório, crie um arquivo chamado app.js e nele inclua o seguinte código:</p>

{% highlight ruby %}
var express = require('express');
var app = express();

app.get('/', function (req, res) {
  res.send('Hello World!');
});

app.listen(3000, function () {
  console.log('Example app listening on port 3000!');
});
{% endhighlight %}

<p>O código inicia um servidor na porta 3000 e fica aguardando por conexões. Ele irá responder com a mensagem Hello World! à solicitação da rota raiz, no caso / e para qualquer rota que não seja a / ele irá responder com erro 404.
Para executar a aplicação digite o comado no terminal.</p>

{% highlight ruby %}
$ node app.js
{% endhighlight %}

<p>Em seguida navegue até a página http://localhost:3000/ em um navegador para ver a aplicação em funcionamento.</p>
