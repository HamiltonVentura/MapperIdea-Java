
# MapperIdea

# Índice

1. [Introdução](#introdução)
    1. [Pré-Requisitos](#Pré-Requisitos)
    2. [Principais conceitos](#Principais-conceitos-MaperIDea)
2. [Softwares Utilizados](#SOFTWARES-UTILIZADOS)
3. [Instalação e uso da ferramenta](#INSTALAÇÃO-E-USO-DA-FERRAMENTA)
4. [Classes e atributos](#Classes-e-atributos)
5. [Mapeando Códigos](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/mapeando-codigo.md)
6. [Referências](#referências)

## Introdução

MapperIdea é uma ferramenta que automatiza a geração de código em conjunto com o Freemind, uma ferramenta de mapas mentais. Usando MapperIdea, é possível converter mapas mentais em código, o que facilita o desenvolvimento de software e aproxima os stakeholders do projeto, tornando a colaboração mais eficiente e compreensível para todos os envolvidos.

### Mapperidea
__Finalidade da Ferramenta :__
Agilizar o desenvolvimento de Software com mapas mentais, possibilitando reaproveitamento de código através da arquitetura modelada pelo Desenvolvedor / Analista.
*Ideia : "Criar na unha  apenas uma vez"*
#### Pré-Requisitos
>[!IMPORTANT]
>**Para modeladores de regras de negócio** <br>
> Conceito de classes, atributos e propriedade<br>
> Os principais conceitos de Orientação a objetos

#### Principais conceitos MaperIDea
>[!IMPORTANT]
>**Para programdores**<br>
> 1 - O **XML** é de extrema importância pois os documentos gerados pela Estrutura gerada são em mm que é um tipo de arquivo  Em sua base XML.<br>
> 2 - O **XPATH** Básico é essência para utilização do MI (MapperIdea) , através dele é possível correr os documentos XML. <br>
> 3 - O **XQUERY** facilita o entendimento da aplicação das funções dentro de Mapperidea.<br>
> 4 - **Orientação a Objetos** os principais conceitos.

## SOFTWARES UTILIZADOS 
- NODE 12 
- Freemind 1.0 + pacote de icones 

> O mapeamento é um processo em que os membros da equipe de desenvolvimento podem executar, envolve "copiar" o codigo traduzindo-o em mapas mentais, 
> os quais poderão se alterados atualizados uma vez montados, sem necessidade de alterar código "na unha".

Após efetuar os mapeamentos, é necessário executar via linha de comando a geração de códigos, que é uma conversão do codigo mapeado em codigos práticos.
A baixo é uma ilustração de como é o processo de criação dos mapas.

```mermaid
flowchart LR
    Gerar-mapa --> Arquitetura  
    Mapas-Mentais-Freemind -->Regra-de-negocio;
    Mapas-Mentais-Freemind --> Gerar-mapa;
    Regra-de-negocio --> Classes-atributos;
    Regra-de-negocio --> funções;
    Regra-de-negocio --> pacotes;
    Arquitetura --->PHP;
    Arquitetura --->JAVA;
    Arquitetura --->Html;
    Arquitetura --->JAVASCRIPT;     
```
O fluxo de utilização dos mapas mentais funciona da seguinte forma, O Mapperidea utiliza o código gerado pelos mapas mentais, sobe para o servidor essas informações, e como retorno ele traz o código escrito na arquitetura escolhida que foi construida.

```mermaid
flowchart LR
    sobe-mapa-regras-de-negócio --> servidor;
    sobe-mapa-da-arquitetura --> servidor;
    servidor --> retorna-código-escrito;   
```
A idéia principal é após mapeamento do código da arquitetura, alterar apenas os mapas mentais de regra de negócio, automatizando assim os processos referentes a codificação do sistema em construção ou alteração.



## INSTALAÇÃO E USO DA FERRAMENTA
#### Instalar antes o node versão 14
  **Para Linux**
~~~bash
sudo apt install npm
~~~
**para Windows**
~~~bash
choco install nodejs-lts --version=14.17.6
~~~

~~~bash
npm install mapperidea-cli -g
~~~

- teste usando o comando 

~~~bash
mi -h
~~~

 - Na sequência utilize  com os dados fornecidos pela Mapperidea para autorizar seus acessos.
```authorize|a <email> <machine> <server>```


### Observações: ###

- inicialize o projeto com o nome do projeto e o nome do arquivo

~~~bash
mi init <nome do projeto> <arquivo.mm>
~~~

Atualize o projeto subindo as informações para o servidor

~~~bash
mi push <nome do projeto>
~~~
![gif](imagens/push.gif)

O fluxo repetitivo do projeto é sempre alterar o arquivo, dar um push no servidor para atualização, e então utilizar o comando para geração de código.



### ICONOGRAFIA ####

Para adicionar um ícone a qualquer um de seus nós em seu mapa mental utilize a tecla de atalho "Alt + I" o qual abrirá uma tela de icones, você poderá clicar no ícone desejado ou poderá utilizar as teclas de talhos. Acompanhe a baixo os ícones mais utilizados para mapeamentos de regra de negócio.<br>

<img src="https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/telaIcones.png" alt="Imagem telas de ícones" width="200">


## Package
![Texto alternativo](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/Package.png)
O ícone Package, siginifica pacote, indica diretórios. Todas as vezes que existir esse icone nos mapas mentais significa que existe um diretório, isso ajuda a organizar
e melhorar o entendimento do código.Pela padonização das teclas utilize **A tecla p**


## Direct-to-Field
![Texto alternativo](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/Mapping.directToField.png)
O icone **Direct to Field**, representa o campo de entrada de dados, por exempo: A Classe Vendedor possúi nome, e sobrenome, logo nome e sobrenome apresentarão esses icones de **Direct To Field**, quando no sistema vocês adicionarem esse campo será necessário na Arquitetura do software, identificar o icone e então executar alguma ação, como por exemplo criar um campo input. **Utilize a tecla D**

## Icon-Descriptor-Class
![Texto alternativo](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/Descriptor.class.png)
Ícone de descrição de classe, em seu nó adicione esse ícone para indicar que é uma classe comum. Tecla de talho **alt+c**

## Icon-Descriptor-Bean
![Texto alternativo](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/Descriptor.bean.png)
Ícone de descrição de classe Bean, em seu nó adicione esse ícone para indicar que é uma classe do tipo Bean. Tecla de atalho **alt+b**

## Icon-One-to-Many
![Texto alternativo](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/Mapping.oneToMany.png)
Uma determinada classe pode ter subclasses, inferindo a relação "Um parar muitos", um exemplo simples seria 
uma classe "Orçamento" que contem diversos itens/produtos. como tecla de atalho utilize **alt+o**

## Icon-Many-to-one
![Texto alternativo](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/Mapping.manyToOne.png)
Uma determinada classe pode ser o item de uma classe pai, para isso utilizamos icone Muitos para um.**alt+d**

## Icon one-to-one
![Texto alternativo](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/Mapping.oneToOne.png)
O ícone one-to-one indica que existe a relação um para um. Por exemplo classe Empregado possui vinculo com um computador, assim sendo, não possuiria vinculos com mais computadores estabelecendo a relação um para um. Tecla de atalho **alt+r**

## Icon element
![Texto alternativo](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/element.png)
O ícone element é utilizado para diversas indicações, mas principalmente com palavras chaves do Mapperidea e em momentos como descritivos de algumas funcionalidade. **alt+e**

## Classes e atributos

Para iniciar vamos utilizar os icones de pacote, definindo o nó com o nome "peso" e um sub nó que conterá as classes domainTeste
![exemplo mapa](/imagens/classe.png)

Perceba os pontos principais dessa classe Carro: 
O ícone class, pode ser utilzado quando a classe não é persistida no banco de dados. 
Nesse exemplo a classe carro contem os atributos, placa, modelo, cor e ano. Após 
cada atributo temos as propriedades, podendo ser texto, Inteiro, ou número.

O @ é interpretado como linhas de orientação para banco de dados e também para titulos que podem ser exibidos posteriormente em tela. 

## Relação entre classes 

As relações entre as classes podem ser definidas como one to one (um para um) / one to many(um para muitos) e many to one (muitos para um). 

#### Relação um para um 
Um exemplo pode ser de uma pessoa que possui um passaporte, ou seja a relação é de um para um, pois um passaporte pode ser de apenas uma pessoa e uma pessoa pode ter apenas um passsaporte.

No mapperidea utilizando o freemind ficaria algo assim: 
![exemploum](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/imagens/umparaum.png)

# MAPEAMENTO DE CÓDIGOS.
Para mapear códigos é necessário primeiramentes criar nós com as palavras chaves. Lembrese de adicionar a tag element em cada palavra.
**alt + e** ![Texto alternativo](https://github.com/HamiltonVentura/MapperIdea-Java/blob/main/icones/element.png)


```mermaid
flowchart LR
    config --> mapperidea;
    mapperidea --> generators;
   
```
Aṕos os **generators** pode se criar o nome dos geradores que o usuário esteja produzindo, esses nomes dependenm de como o arquiteto/Analista decidir. obs. os nomes variaveis estão em verde.

```mermaid
    flowchart LR
        br.com.projeto --> config
        config --> mapperidea;
        mapperidea --> generators;
        generators --> JAVA;
        generators --> jsonServer;
        JAVA --> JavaDomainModel;
        jsonServer --> dbJson;

style JAVA fill:#9f6,stroke:#333,stroke-width:2px;
style jsonServer fill:#9f6,stroke:#333,stroke-width:2px;
style JavaDomainModel fill:#9f6,stroke:#333,stroke-width:2px;
style dbJson fill:#9f6,stroke:#333,stroke-width:2px;
```

COnhecer a estrutura de código é enssencial para mapear com eficiência.

## Estrutura e mapeamento (geradores)

### patterns e start
São os padrões, o código que será escrito literalemente.

 ```mermaid
flowchart LR
     JAVA --> domainModelJAVA;
     domainModelJAVA --> patterns;
     patterns --> padraoIncio;
     patterns --> padraoFim;
     padraoIncio --> B["{"];
     padraoFim --> F["}"];
style padraoIncio fill:#9f6,stroke:#333,stroke-width:2px;
style padraoFim fill:#9f6,stroke:#333,stroke-width:2px;
```

### start
São os padrões, o código que será escrito literalemente.

 ```mermaid
flowchart LR
     JAVA --> domainModelJAVA;
     domainModelJAVA --> patterns;
     patterns --> padraoIncio;
     patterns --> padraoFim;
     patterns --> start;
     padraoIncio --> B["{"];
     padraoFim --> F["}"];
     start --> match --> classes
     start --> body
     body --> write-pattern --> padrraoInicio;
style padraoIncio fill:#9f6,stroke:#333,stroke-width:2px;
style padraoFim fill:#9f6,stroke:#333,stroke-width:2px;
```

A princípio é fácil gerar os códigos dessa forma, em um lado colocamos o código como deve ser escrito, no caso com o nó patterns, e em seguida adicionamos a sequencia no start denro do do body com a palara chave write pattern.
os retangulos que estãod e verde devem contar a tag green antes no nome através da tecla de atalho **alt + v**
e icone de <> deve pode ser inserido através das teclas de atalho **alt + e** 

![image](https://github.com/user-attachments/assets/34a6cb7e-ec3b-488b-ad68-18595a467bae)


## Exemplo
![gif](imagens/geracaoex1.gif)


## Pontos positivos e negativos da Ferramentas. ##

### Positivo: 

#### 1 - Útil para automação de códigos legados.
A ideia é interessante ao se aplicar em softwares legados, levando-se em consideração rotinas bem definidas que os mesmos já possuem. A ideia de ser visual pode aproximar os interessados no projeto (stakeholders) facilitando o entendimento em certo nível.
#### 2 - Simplicidade no Comando de linhas.
São poucos comandos de linha no terminal para geração de código, ou seja após a arquitetura e classes mapeadas, se torna fácil "gerar" os códigos por linha de comando.
#### 3 - Iconografia Bem definida.
A iconografia com base nos cursos dados pela mapperidea deixa definido alguns padrões visuais que facilitam o entendimento deixando também em aberto a possibilidade de seguir os pŕoprios padrões.
### 4 - Documentação de funções
A documentação de funções xpath, mi e xquery, o que facilita nas consultas.


### Negativos: 
 
#### 1  Ferramentas desatualizadas
Exemplo do Node, e o Freemind, A MAPPERIDEA usa essas ferramentas com versões mais antigas.

#### 3  Tempo de construção da arquitetura muito elevados.
Na minha experiência tive que modelar um software desde o fundamento. Levando-se em consideração que muitas vezes a construção de um software é um processo que exige modificações, muitas vezes na ideia da arquitetura, pode tornar o mapeamento um problema em vez de solução.

#### 4  Ausência de um mapeamento reverso
Ao se trabalhar com a ferramenta percebi que se a ideia é automatizar tudo, por que não subir a classe e mapeala automaticamente?
Senti dificuldade de ferramentas que facilitasem um pouco mais as coisas.

#### 5 Arquivos se corrompem com facilidade.
Em diversas situações meus arquivos corromperam, apesar de fazer commits com frequência, acabei perdendo alterações importantes que fiz em lote

#### 6 Pouca documentação de apoio.
Com relação a documentação escrita, tem-se uma documentação parcial, com as principais funções, mas ausentes de iconografia, e Exemplos documentados de código que possam facilitar o entendimento.    

### Observações e Recomendações
Vejo com uma solução viável a códigos legados, mas não como uma opção para arquitetura para início de projetos grandes, pois na minha visão a demanda para digitar código e redigitar no mapa, atualizar tudo caso haja alterações siginificativa no projeto, Torna moroso a entrega final. 

### Minha Opinião 
A MapperIdea aparenta ser uma ferramenta pouco intuitiva no que diz respeito ao mapeamento entre telas, classes e banco de dados. Na minha experiência, a criação direta desses elementos se mostrou melhor do que o uso da ferramenta.

No entanto, a MapperIdea possui mapeamentos pré-definidos, que podem ser entendidos como módulos. Esses módulos têm o potencial de facilitar a geração de projetos base, integrando tecnologias como Spring Boot e Angular. Apesar de não ter conseguido explorar esses módulos diretamente, percebi que a ferramenta pode contribuir para um fluxo de trabalho mais eficiente, desde que o desenvolvedor consiga adaptá-la às suas necessidades e criar na própria ferramenta sua arquitetura.

O principal fator a ser considerado é o custo-benefício, levando em conta o tempo de aprendizado necessário e o investimento na ferramenta.

Atualmente, o mercado oferece diversas alternativas e conjuntos de ferramentas para otimizar a geração de código e a produtividade do desenvolvedor. A MapperIdea se destaca por buscar a integração dessas ferramentas por meio da tecnologia desenvolvida.

No entanto, devido à sua complexidade, percebi que, em alguns casos, a geração direta do código pode ser uma abordagem mais eficiente. A introdução de um nível adicional de complexidade ao projeto pode impactar o tempo de entrega, tornando essencial avaliar se os benefícios da ferramenta justificam o investimento em aprendizado e adaptação.
