---
layout: post
title:  "Trabalhando com Spring-boot para desenvolver uma aplicação mobile"
date:   2016-02-27 22:32:29 -0300
categories: textos desenvolvimento java
---

# Introdução

O _Spring_ [^spring] é uma entidade que produz uma série de ferramentas que auxiliam no desenvolvimento Java. Seu produto mais famoso é provavelmente o Spring Framework [^springFramework], que engloba uma série de subprodutos e ideias utilizadas em larga escala por grandes softwares empresariais (framework MVC, injeção de dependências, etc...).

Depois da grande popularização do Spring, os seus produtores resolveram tentar simplificar a adoção ao introduzir o _Spring Boot_ [^springBoot]. Resumidamente, o Spring Boot é uma maneira muito rápida de se construir aplicações de qualquer tipo utilizando os recursos do Spring. É um produto excelente para a criação de protótipos, microserviços, pequenas aplicações ou até mesmo iniciar a produção de uma aplicação de grande porte. Também é uma excelente plataforma para se construir um TCC =)

Esse artigo busca introduzir o Spring Boot e apresentar uma pequena aplicação e está organizado da seguinte maneira: (1) Introdução: nesse tópico, falarei sobre o projeto que nós criaremos contando seus requisitos funcionais e não funcionais. (2) Pré-requisitos - aqui nós falaremos das ferramentas que utilizaremos e como instalá-las. (3) Implementação - por fim, com todos os pré-requisitos instalados, nós iremos fazer uma implementação simples de uma aplicação _backend_ que será usada em outro artigo para a elaboração de uma aplicação _mobile_.

### Aplicação de exemplo

Nossa aplicação de exemplo será uma *PetShop* e a arquitetura será como a seguir:

{% plantuml %}
Actor usuário as user

node smartphone {
  artifact "aplicação frontend" as frontend
}

node servidor {
  artifact "aplicação backend" as backend
  database "banco de dados" as db
}
user -> frontend
frontend -> backend
backend -> db

{% endplantuml %}

O usuário terá acesso a aplicação apenas por meio de seu smartphone. Essa aplicação (frontend) será responsável por apresentar uma interface gráfica e controlar os eventos gerados pelo usuário. Qualquer operação ou regra de negócio será gerenciada pela aplicação (backend). A comunicação entre o frontend e o backend será realizada por meio de uma API REST [^rest] a ser apresentada.

A aplicação da Petshop terá as seguintes características:

* Deverá ter uma tela principal mostrando os animais em destaque.
* Deverá ter uma opção para filtrar os animais por espécie.
* Deverá ser possível visualizar uma fotografia do animal em questão
* Deverá ter uma tela de administração de animais, na qual um administrador poderá incluir, alterar ou excluir animais.
* O administrador também poderá criar novos administradores.

Apenas a aplicação backend será descrita nesse artigo. Futuros artigos apresentarão soluções para o frontend.


# Pré-requisitos

### Maven

### Spring-boot


# Implementação

# Referencias

[^spring]: <http://www.spring.io>
[^springFramework]: <http://projects.spring.io/spring-framework/>
[^springBoot]: <http://projects.spring.io/spring-boot/>
[^rest]: <http://pt.stackoverflow.com/questions/45783/o-que-%C3%A9-rest-e-restful>