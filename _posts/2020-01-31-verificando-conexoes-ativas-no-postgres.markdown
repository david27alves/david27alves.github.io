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
</figure>

<p>O Postgres vai listar todas as conexões ativas no momento, são exibidas informações como o nome da aplicação que está acessando(application_name), o ip da máquina(client_addr), qual query está sendo executada(query) e uma delas é o ID do processo(pid). </p>
<p>Para finalizar a conexão desejada basta usar a seguinte query passando o pid como parâmetro. Dessa forma será encerrada a conexão que está ativa.</p>

{% highlight sql %}
select pg_terminate_backend(pid);
{% endhighlight %}

<p>Também podemos encerrar todas mantendo apenas a sua conexão ativa.</p>

{% highlight sql %}
select pg_terminate_backend(pid) from pg_stat_activity where pid <> pg_backend_pid();
{% endhighlight %}
