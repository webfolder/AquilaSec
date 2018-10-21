---
layout: post
title: "Hacking em Sistema Escolar do DF - Acadêmico Total"
date: 2018-03-09 17:10:00
tags: [Web-hacking, Security]
---

![](https://aquila0day.github.io/assets/img/NovasImagensDay/TitleOFFSET.jpg "TitleOFFSET")



O Acadêmico Total é um aplicativo inteligente, criado para os responsáveis de um aluno monitorarem em tempo real sua entrada e saída do colégio, usado também para visualizar notas e a frequência do aluno. Esse aplicativo é utilizado inclusive pelos professores e funcionários para registrar ocorrências e algumas outras funções utilitárias a todos os seus usuários.

Fazendo as pesquisas no site fui com o objetivo de identificar, analisar e catalogar vulnerabilidades envolvidas na aplicação web do Acadêmico Total, levando em conta a integridade, confidencialidade e disponibilidade das informações. Foi feita a classificação e organização das irregularidades encontradas.

Com uma análise não tão profunda na Aplicação Web e no App do Acadêmico Total, consegui notar algumas vulnerabilidades que poderiam prejudicar o site a ponto de comprometê-lo.

#### • Vulnerabilidade – Cross-Site Scripting (XSS)

Começando na Aplicação Web, onde se encontra o blog dos professores, avistei uma simples falha de Cross-site scripting (XSS), que foi localizada a partir da manipulação com o método GET no parâmetro "<i>nome</i>". Esta vulnerabilidade permite a um atacante executar códigos <i>client-side</i> (lado do cliente) e efetuar ataques de engenharia social (persuasão) para obtenção de informações sigilosas.


![Alt da minha Imagem](https://aquila0day.github.io/assets/img/NovasImagensDay/XssHel.jpg "Academy")


#### • Vulnerabilidade – Broken Authentication and Session Management

Não se limitando na primeira falha comecei a analisar as requisições feitas pelo app. Observando os tráfegos, foi possível notar a entrada de um parâmetro nomeado de "<i>matricula</i>" com o valor da minha matrícula no caso (Sou estudante de uma das escolas clientes do Acadêmico Total).


![Alt da minha Imagem](https://aquila0day.github.io/assets/img/NovasImagensDay/Requisi%C3%A7%C3%A3oAcademico2.jpg "Req")

Fazendo uns testes nesse parâmetro, consegui manipular com o valor de outras matrículas de alunos, possibilitando a visualização de suas notas, o uso da função controle de acesso entre outras utilidades abaixo.


![Alt da minha Imagem](https://aquila0day.github.io/assets/img/NovasImagensDay/MinhaContaAcademico2.jpg "Req")

#### • Vulnerabilidade – Exposição de Dados Sensíveis

Examinando as requisições, evidentemente foi possível ver os diretórios no qual o aplicativo chamava para trabalhar em suas funções.

Requisição feita por uma das funções do site.


![Alt da minha Imagem](https://aquila0day.github.io/assets/img/NovasImagensDay/ReqADM.jpg "Adm")


Com algumas dessas funções era possível fazer manipulações de dados e a visualização de informações sigilosas do site. Em vista dos fatos elencados encontrei uma função específica para os administradores do Aplicativo/Site, no qual disponibilizava a senha do Banco de Dados MYSQL e do servidor FTP.

![Alt da minha Imagem](https://aquila0day.github.io/assets/img/NovasImagensDay/BankAccount.jpg "Contas")

Com essas informações foi possível entrar dentro do Banco de dados e do Servidor FTP, dando a possiblidade de modificar notas, faltas, ocorrências entre várias outras funções.

##### Conexão via FTP

![Alt da minha Imagem](https://aquila0day.github.io/assets/img/NovasImagensDay/FTPConnection.jpg "Conexão FTP")

##### Conexão via MYSQL

![Alt da minha Imagem](https://aquila0day.github.io/assets/img/NovasImagensDay/MysqlConnection.jpg "Conexão Mysql")


Por fim em decorrência das falhas mencionadas, eu reportei todas elas para a empresa. Eles me autorizaram a postar esse artigo. Portanto as falhas citadas JÁ FORAM CORRIGIDAS pela equipe.

A Aplicação Web/Aplicativo apresenta essas vulnerabilidades citadas, que acabam por deixar um invasor externo tomar controle sobre o servidor. Após a correção das falhas, o aplicativo ganhou uma "camada" de segurança a mais, evitando ataques de pessoas mal-intencionadas e se tornando mais seguro para seus clientes.


#### AVISO: Todas as falhas encontradas foram corrigidas

{% highlight ruby %}
As falhas foram reportadas em 28/02/18 e corrigidas em 05/03/18.
{% endhighlight %}

<br>
##### Referência:

Jhonathan -> 
<a href="https://lab.insightsecurity.com.br/school-hacking-vulnerabilidade-aplicativo-academico-total/">Aqui</a>