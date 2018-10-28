---
layout: post
title: "Criando Site Estático com Jekyll"
date: 2018-10-19 23:00:00
tags: [Web, Site, Jekyll]
---

# O que é Jekyll?
Jekyll é um software que feito em Ruby, cujo o objetivo é gerar sites estáticos de forma simples, rápida e segura. A tecnologia é amplamente utilizada para construção de sites pessoais, blogs, projetos e artigos científicos.

O principal atrativo do Jekyll a sua flexibilidade e facilidade de uso, basta saber um pouco de HTML e Markdown. O software não utiliza banco de dados, esse usa arquivos com extensão Markdown, que converte algumas marcações simples em em HTML, o que torna mais simples de se usar.<br>
A aplicação fica bem rápida ao utilizar o Jekyll por ser um site estático.

# YAML

O YAML (_"YAML Ain’t Markup Language"_) é uma maneira de armazenamento dados em uma aplicação específica que outros utilitários podem analisar, o próprio YAML não faz nada sozinho.

Pode-se criar novas variáveis e configurá-las, essas variáveis são reutilizáveis de acordo com a estrutura dos arquivos

## Exemplo

{% highlight python %}

# Site specific settings
title: "Title to this website"
name: "Website name"
keywords: "Key, words, about, this, website"
baseurl: ""
url: "http://website.com"
description: "Website description"
cover: "/assets/img/cover.svg"
fanpage_id: ""

# Site general settings
lang: "en"
lang_alternate: "pt_BR"
ssl: false # It will redirect to https

# Media
# Just the shortname:
disqus: test
twitter: 
facebook: 
github: 
google:

# Build settings
markdown: kramdown
permalink: /:categories/:title/


{% endhighlight %}

# YAML Front Matter

Existe também o YAML Front Matter, que tem que ser incluído logo no início do arquivo, e tem que estar em um arquivo cujo seu formato seja _*.yml_

A estrutura deve ser utilizada como o código de __exemplo__ escrito abaixo:

## Exemplo

{% highlight python %}

---
layout: default
title: "Digite o título aqui"
date: 2018-10-29 00:00:00
---

{% endhighlight %}


# Instalação

Vamos para a parte prática né? É a melhor parte haha

Começaremos instalando o Jekyll

{% highlight python %}

$ apt-get install jekyll 

{% endhighlight %}

ou

{% highlight python %}

$ gem install bundler jekyll

{% endhighlight %}

Após a instalação do Jekyll, você irá criar um diretório que servirá como suporte para seu servidor local.

{% highlight python %}

$ jekyll new nome-do-diretorio
$ cd nome-do-diretorio

{% endhighlight %}

Logo em seguida, basta você rodar seu site/blog e trabalhar na estrutura do mesmo. Para isso é necessário um executar um servidor local do Jekyll, é bem simples basta digitar o seguinte comando:

{% highlight python %}

$ jekyll server

{% endhighlight %}

Pronto, seu servidor, está funcionando localmente. Basta jogar o link apresentado no terminal no seu navegador e colocar a mão ma massa, haha.


# Jekyll Themes

Existe uma forma bem bacana de se criar um site usando temas que o Jekyll e algumas pessoas disponibilizam, segue o link abaixo para ver alguns dos temas disponíveis.


1. [Theme I]("http://jekyllthemes.org/")
2. [Theme II]("https://jekyllthemes.io/")
3. [Theme III]("http://themes.jekyllrc.org/")
