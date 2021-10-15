# Introdução ao framework Spring Boot 

## O que é Spring Boot?


* 1. O que é Spring Boot e quais problemas ele resolve?
* 2. Auto Configuration;
* 3. FataJar/UberJar  

### Requisitos Básicos    

* Java 8 ou superior
* Maven
* IntelliJ IDEA  

### O que Spring Boot?

* O Spring Boot é uma ferramenta que visa facilitar o processo de configuração e publicação de aplicações que utilizem o ecossistema Spring;
* Criado pela Spring Source em 2012;
* Facilita setup de projetos Spring;
* Faz a interpretação de todas as dependências;
* Sem necessidade de criar arquivos de configuração.  

###  Problemas do Spring

* Configurações de bens em arquivos xml;
* Dispatcher Servlet e view resolver em web.xml;
* Setup Manunal de Banco de dados;
* Muito tempo gasto em configuração;
* Perda de foco e valor.  

### Quais problemas o Spring Boot resolve? 


* Produtividade: Setup simplificado de projeto;
#### Spring Initializr
O **spring Initializr** é uma ferramenta online que possibilita escolher todas as dependências necessárias. É possível optar pelo **maven** ou pelo **gradle** que são **gerenciadores de dependências**.
#### Starters
Os starters adiciona um conjunto de depências, bem como suas configurações automaticamente através do auto configuration e todo o setup referente a dependência.
A dependência  **spring-boot-starter-web** é um conjundo de depências auto configuráveis pelo Spring Boot. 
Nesse conjunto teremeos por exemplo o mvc, o tomcat e etc.  

* Execução simplificada: sem deploy em servidor externo.

* Configuração: arquivo externo para configuração  como para banco de dados, segurança e de log.
O arquivo** application.properties **que também pode ser em formato yml permite de maneira declarativa realizar as configurações.

* Valor: maior tempo em desenvolvimento

  ### Criando o Hello World no Spring Boot
1. Criar o projeto:
`http://start.spring.io`

2. Escolher o gerenciador de dependência:
**Maven**
3. Escolher a linguagem:
**Java**
4. Escolher a versão mais estável do Spring Boot:
**2.5**
5. Editar o Group:
**com.naiara**

6. Selecionar dendência:
**Spring Web**
7. Fazer gerar e fazer o download clicando em:
**Generate**
8. Extrair o arquivo e abrir na IDE.

### application.properties
Na pastar src > main > resources encontraremos o arquivo **application** aonde nós podemores adicionar todas as dependências de configurações do nosso projeto como: Informações de banco de dados, portas que desejamos rodar no nosso servidor, habitilitar e desabilitar logs, e etc.

### Hello World

9. Criar um novo pacote dentro do pacote com.naiara e nomeá-lo:
new>package
10. Criar uma classe neste mesmo pacote e nomeá-la como HelloControler.
new>class
11. Adicionar a notação @RestController (A notação que indica o controle irá retorna somente texto e identifica o controle como REST):
12. Dentro da public class hello controler crie o código:
`public String helloMessage(){ return "Hello, World!"}`
13. Adicionar a notação @Getmapping (A notação mapeia a operação Get no REST):
@GetMapping("/")
13. Abra a pasta do projeto no terminal e dê run:
`mvn spring:boot= run`

#Auto Configuration
##Configuração manual
* Muito tempo era gasto na configuração manual, com isso haviam múltiplos arquivos XML;
* Configuração manual do Spring MVC:Dispatcher Servlet, web.xml, spring-mvc.xml;
* Configuração manual dos beans Spring;
* aplicado também ao Spring Data, Spring Security, e etc.
## Auto configuration
* Starters: dependências simplificadas e auto configuráveis. Ao instalar a dependência Starter-web outra configurações de outras dependências são incluídos, sendo o starter-web um link para outras dependências, outro arquivo xml onde ele tem outras dependências;
* Spring boot detecta as dependência e as configura para nós;

:fire: Pesquise: Servidor de aplicação?

## Antes do Spring Boot

* Spring tradicional: war precisa de servidor de aplicação;
* Dependência de um container web ou servidor de aplicação;
* Complexidade para configurações;
* Atualizações frequentes, junto com a versão;
* Gerenciamento manual de configurações.

## FatJar/UberJar  

* Artefato do projeto pronto para execução;
* Container web embutido na geração e execução (Tomcat);
* Deploy embarcado com outros containers são opcionais;
* Dependências principais do projeto embarcados;
* Execução direta através de um único java - jar;

` mvn package && -jar target/spring-boot-exemple-0.1.0.jar`

* Podemos também gerar o war tradicional.

* Build o projeto .jar:
`mvn clean package`# Gerar artefatos, testes unitários e empacotar
`cd  target`
`java - jar springboot.jar ` # como é fatJar engloba todas as configurações e dependências e faz o run
* Para trocar para war é só ir no arquivo pom.xml e substituir de jar para war e build o projeto. 
<packaging>war<packaging>
Build: 
`mvn clean package`#Gerar artefatos, testes unitários e empacotar
`cd  target` 
* Encontrar o apache na raiz do projeto com o comando `ll`
`mv target/springboot.war apache-tomcat(...)/webapps`
`ll apache-tomcat(...)/webapps`
`cd apache-tomcat(...)`
`ll`
`cd bin`
`ll`
`./startup.sh`



