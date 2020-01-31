---
layout: post
title:  "Verificando conexões ativas no Postgres"
description: "Como verificar quais são as conexões que estão ativas no Postgres."
date:   2020-01-31
category: "database"
author: "David Alves"
avatar: "https://avatars1.githubusercontent.com/u/4975560?s=460&v=4"
---



<p>Muitas vezes precisamos realizar alguma operação no banco de dados, seja executar uma query ou atualizar o sistema 
então é retornado um erro informando que a tabela já está em uso, checamos e aparentemente nenhuma aplicação está aberta. 
Para isso podemos usar a query:</p>

{% highlight sql %}
select * from pg_stat_activity;
{% endhighlight %}

<figure>
  <img src="https://raw.githubusercontent.com/david27alves/david27alves.github.io/master/_posts/img/pgactivity.png" alt="GAD">
  <figcaption>Fig1. - GAD</figcaption>
</figure>
