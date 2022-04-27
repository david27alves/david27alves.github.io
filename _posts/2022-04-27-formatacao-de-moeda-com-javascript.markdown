---
layout: post
title: "Formatação de moeda com JavaScript"
description: "Como formatar moeda usando API nativa do JavaScript"
date: 2022-04-27
category: "javascript"
author: "David Alves"
avatar: "https://avatars1.githubusercontent.com/u/4975560?s=460&v=4"
---

<p>Recentemente em um dos projetos que estou desenvolvendo senti a necessidade de fazer a formatação de um valor em float 4499.00 para reais R$ 4.499,00. Eis que então começo a dar uma pesquisada no Google e me deparo com uma API nativa do JavaScript que até então eu não conhecia, a Intl API.</p>

<p>Basicamente essa é uma API de internacionalização nativa do JavaScript que ajuda na formatação de valores como moeda, datas e horas.</p>

### NumberFormat 

<p>Seguindo no meu problema eu precisava formatar um valor de float para reais, a API fornece o método NumberFormat o que tornou muito simples resolver o meu problema.</p>

{% highlight ruby %}
let numberFormat = new Intl.NumberFormat('pt-BR', {
	style: 'currency',
	currency: 'BRL'
}).format(4499.00)

console.log(numberFormat)

// R$ 4.499,00
{% endhighlight %}

<p>A função recebe alguns parâmetros, o primeiro deles é o locales, que recebe uma string com a tag da linguagem ‘pt-BR’, ele segue o padrão BCP 47, o segundo parâmetro é um objeto com dois atributos:</p>

<p>style: o estilo do formato que será utilizado, podemos ter “decimal” para formato de números simples, “currency” para formato de moeda e “percent” para formato percentual.</p>
<p>currency: qual moeda será utilizada para a formatação, ‘BRL’ para real brasileiro, ‘EUR’ para euro, ‘USD’ para dolar americano, ele segue o padrão ISO 4217.</p>

### DateTimeFormat 

<p>A API Intl também permite realizar a formatação de data e horas com a função DateTimeFormat segue um pequeno exemplo de uso:</p>

{% highlight ruby %}
let dateFormat = new Intl.DateTimeFormat('pt-BR').format(Date.now())

console.log(dateFormat)

//27/04/2022
{% endhighlight %}
