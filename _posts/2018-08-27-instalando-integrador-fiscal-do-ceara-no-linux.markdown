---
layout: post
title:  "Instalando Integrador Fiscal do Ceará no Linux"
description: "Como fazer a instalação da aplicação do Integrador Fiscal, responsável por gerenciar as vendas do MFE do Ceará."
date:   2018-08-27
comments: true
category: "misc"
author: "David Alves"
avatar: "https://avatars1.githubusercontent.com/u/4975560?s=460&v=4"
---

O Integrador Fiscal é uma aplicação desenvolvida pela Sefaz do Ceará que tem como finalidade gerenciar as informações que serão processadas pelo MFE (Módulo Fiscal Eletrônico). O MFE é semelhante ao SAT que é usado no estado de São Paulo, porém com algumas diferenças e bem menos estável, quem já trabalhou com ele sabe do que estou falando. 
Atualmente ele pode ser instalado tanto no Windows quanto no Linux, a versão que usamos para testes foi o Ubuntu 16.04 32 bits, pode ser instalado no 64 bits também, instalando os devidos pacotes para a arquitetura.
Os comandos devem ser executados na ordem como está descrito aqui, caso contrário corre o risco de não funcionar.

## Comando ldd
Primeiro passo é executar o comando abaixo, ele serve para listar a versão do ldd, caso seja menor que 2.12 ele não irá funcionar.
{% highlight ruby %}
ldd --version
{% endhighlight %}



## Instalação do Mono
Mono é um implementação do Framework .NET para uma ampla faixa de sistemas operacionais, dentre eles o Linux, ele será responsável por executar o nosso integrador.
Os comandos acima irão adicionar o repositório no Mono e fazer a instalação, é comum que durante a instalação demore um pouco. O pacote axel é semelhante ao wget, usaremos ele para baixar os nossos arquivos.
{% highlight ruby %}
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb http://download.mono-project.com/repo/ubuntu xenial main" | sudo tee /etc/apt/sources.list.d/mono-official.list
sudo apt update
apt list --upgradable
sudo apt-get update
sudo apt-get install mono-complete uuid-runtime axel
{% endhighlight %}



## Download dos arquivos
Agora vamos baixar e extrair arquivos de instalação.
{% highlight ruby %}
cd ~/Downloads
axel https://integrador.blob.core.windows.net/integrador/instalador-ce-sefaz-driver-linux-x64-02.04.07.tar.gz
ou 
axel http://www.sefaz.ce.gov.br/content/aplicacao/internet/download/projetomfe/instalador-ce-sefaz-driver-linux-x64-02.04.09.tar.gz
axel https://integrador.blob.core.windows.net/linuxwithoutui/sqlite-netFx-full-source-1.0.105.2.zip
axel https://integrador.blob.core.windows.net/linuxwithoutui/IntegradorLinuxServidor.zip
{% endhighlight %}



{% if page.comments %} {% endif %}
