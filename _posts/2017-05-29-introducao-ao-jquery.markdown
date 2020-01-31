---
layout: post
title:  "Introdução ao JQuery"
description: "Uma breve introdução ao JQuery, um dos mais populares frameworks Java Script."
date:   2017-05-29
category: "javascript"
author: "David Alves"
avatar: "https://avatars1.githubusercontent.com/u/4975560?s=460&v=4"
---


<p class="intro"><span class="dropcap">N</span>esse post vou dar uma breve introdução ao JQuery, um poderoso framework javascript capaz de criar animações, manipular eventos e simplificar o processo de criação com javascript.</p>
<figure>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/fd/JQuery-Logo.svg/512px-JQuery-Logo.svg.png" alt="GAD">
</figure>

<p>Não é atoa que o slogan do JQuery é "Write less, do more.", ele surgiu para simplificar a maneira como escrevemos JavaScrip, veja o exemplo de um código escrito em JavaScript puro e o código escrito em JQuery.</p>

<p>Pegar o conteúdo de uma div com o id="content" e armazear em uma variável usando JavaScript puro.</p>

{% highlight ruby %}
var content = document.getElementById("#content").innerHTML;
{% endhighlight %}

<p>O mesmo código escrito usando JQuery</p>
{% highlight ruby %}
var content = $("#content").innerHTML;
{% endhighlight %}
