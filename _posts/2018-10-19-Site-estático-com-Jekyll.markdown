---
layout: post
title: "Criando Site Estático com Jekyll"
date: 2018-10-19 23:00:00
tags: [Web, Site, Jekyll]
---
<br>

<h2> O que é Jekyll? </h2>
Jekyll é um software que foi programado na linguagem Ruby, que gera sites estáticos de forma simples, rápida e segura. A tecnologia é aplicada geralmente para sites individuais como blogs, projetos e artigos científicos.

Esse Software é muito utilizado por ser flexível e fácil de se configurar, basta saber um pouco de HTML. O software não utiliza banco de dados. Usa arquivos com extensão Markdown, que converte alguns códigos simples em outros códigos "complexos" em HTML, o que torna mais simples de se usar.<br>
A aplicação fica bem rápida ao utilizar o Jekyll por ser um site estático.

<h2> YAML </h2>

O YAML<i>("YAML Ain’t Markup Language")</i> é uma maneira de armazenamento dados em uma aplicação específica que outros utilitários podem analisar, o próprio YAML não faz nada sozinho.

Pode-se criar novas variáveis e configurá-las, essas variáveis são reutilizáveis de acordo com a estrutura dos arquivos


<h5> Exemplo </h5>

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

<h1> YAML Front Matter </h1>
Existe também o conhecido como YAML Front Matter, que tem que ser incluído logo no início do código, e tem que estar em um arquivo cujo seu formato seja <i>.yml</i>

A estrutura deve ser utilizada como o código de <b>exemplo</b> escrito abaixo:

<h5> Exemplo </h5>

{% highlight python %}

---
layout: default
title: "Digite o título aqui"
date: 2018-10-29 00:00:00
---

{% endhighlight %}


<h2>Instalação</h2>

Vamos para a parte prática né? É a melhor parte haha<br>
Começaremos instalando o Jekyll

{% highlight python %}

$ apt-get install jekyll 

{% endhighlight %}

ou

{% highlight python %}

$ gem install bundler jekyll

{% endhighlight %}

Após a instação do Jekyll, você irá criar um diretório aonde servirá como suporte para seu servidor local.

{% highlight python %}

$ jekyll new nome-do-diretorio

{% endhighlight %}

{% highlight python %}

$ cd nome-do-diretorio

{% endhighlight %}

Logo em seguida, já criado seu diretório, basta você rodar seu site/blog e trabalhar na estrutura do mesmo. para isso é necessário um servidor local, e é isso que nós iremos fazer, é bem simples basta digitar o seguinte comando.

{% highlight python %}

$ jekyll server

{% endhighlight %}

Pronto, seu servidor, está funcionando localmente. Basta jogar o link apresentado no terminal no seu navegador e colocar a mão ma massa, haha.


<h2>Jekyll Themes</h2>

Existe uma forma bem bacana de se criar um site usando temas que o Jekyll e algumas pessoas disponibilizam, segue o link abaixo para ver alguns dos temas disponíveis.

<a href="http://jekyllthemes.org/">Theme I</a>

<a href="https://jekyllthemes.io/">Theme II</a>

<a href="http://themes.jekyllrc.org/">Theme III</a>
