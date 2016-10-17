---
layout: post
title:  "PetShop com backend Spring-boot - PARTE 1 - Configurando"
date:   2016-02-27 22:32:29 -0300
categories: textos desenvolvimento java

---

# Introdução

O _Spring_ [^spring] é uma entidade que produz uma série de ferramentas que auxiliam no desenvolvimento Java. Seu produto mais famoso é provavelmente o Spring Framework [^springFramework], que engloba uma série de subprodutos e ideias utilizadas em larga escala por grandes softwares empresariais (framework MVC, injeção de dependências, etc...).

Depois da grande popularização do Spring, os seus produtores resolveram tentar simplificar a adoção ao introduzir o _Spring Boot_ [^springBoot]. Resumidamente, o Spring Boot é uma maneira muito rápida de se construir aplicações de qualquer tipo utilizando os recursos do Spring. É um produto excelente para a criação de protótipos, microserviços, pequenas aplicações ou até mesmo iniciar a produção de uma aplicação de grande porte. Também é uma excelente plataforma para se construir um TCC =)

Esse artigo busca introduzir o Spring Boot e apresentar uma pequena aplicação e está organizado da seguinte maneira: (1) Introdução: nesse tópico, falarei sobre o projeto que nós criaremos contando seus requisitos funcionais e não funcionais. (2) Pré-requisitos - aqui nós falaremos das ferramentas que utilizaremos e como instalá-las. (3) Implementação - por fim, com todos os pré-requisitos instalados, nós iremos fazer uma implementação simples de uma aplicação _backend_ que será usada em outro artigo para a elaboração de uma aplicação _mobile_.

Nessa primeira parte nós iremos preparar o ambiente e falar do nosso projeto piloto. Ao final dessa parte, você deve ser capaz de configurar todo o ambiente e baixar o código inicial para começar a desenvolver a aplicação a partir da segunda parte.

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

Para utilizarmos os exemplos desse artigo e dos próximos, será preciso ajustar o ambiente na sua máquina em alguns pequenos passos.

### Java

Todos os exemplos aqui utilizam a última versão do [Java SDK 8](http://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html). Baixe e instale a última versão para poder continuar.

### Eclipse

Esse artigo, seus exemplos e imagens foram produzidos utilizando o Eclipse, versão
Neon ([clique aqui para baixar](http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/neon1a)).

### Maven

O [Apache Maven](https://maven.apache.org/) é um gerenciador de dependências muito conhecido no universo Java. O Eclipse já vem com uma versão dele embutido, mas você pode baixar uma versão standalone [aqui](http://ftp.unicamp.br/pub/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.zip)

# Implementação

* Faça o download do código inicial [aqui](https://github.com/raphaeldovale/site-tutorials-petshop-spring-boot-part-1). Clique no botão verde "clone or download" para baixar.
* Descompacte o zip em um diretório desejado.
* Com o Eclipse, vá em "file" -> "import" e selecione "Existing maven projects"
* Na tela seguinte, selecione o diretório do projeto baixado. Depois, clique em "finished"


# Referencias

[^spring]: <http://www.spring.io>
[^springFramework]: <http://projects.spring.io/spring-framework/>
[^springBoot]: <http://projects.spring.io/spring-boot/>
[^rest]: <http://pt.stackoverflow.com/questions/45783/o-que-%C3%A9-rest-e-restful>
