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

MapperIdea é uma ferramenta que automatiza a geração de código em conjunto com o Freemind, uma ferramenta de mapas mentais. Usando MapperIdea, é possível converter mapas mentais em código, [...]

### Mapperidea
__Finalidade da Ferramenta:__
Agilizar o desenvolvimento de Software com mapas mentais, possibilitando reaproveitamento de código através da arquitetura modelada pelo Desenvolvedor / Analista.
*Ideia: "Criar na unha apenas uma vez"*
* observação: não recomendo a ferramenta para desenvolver softwares do zero. Extremamente moroso.

#### Pré-Requisitos
>[!IMPORTANT]
>**Para modeladores de regras de negócio** <br>
> Conceito de classes, atributos e propriedade<br>
> Os principais conceitos de Orientação a objetos

#### Principais conceitos MaperIDea
>[!IMPORTANT]
>**Para programadores**<br>
> 1 - O **XML** é de extrema importância pois os documentos gerados pela Estrutura gerada são em mm que é um tipo de arquivo Em sua base XML.<br>
> 2 - O **XPATH** Básico é essencial para utilização do MI (MapperIdea), através dele é possível percorrer os documentos XML. <br>
> 3 - O **XQUERY** facilita o entendimento da aplicação das funções dentro de Mapperidea.<br>
> 4 - **Orientação a Objetos** os principais conceitos.

## SOFTWARES UTILIZADOS 
- NODE 12 
- Freemind 1.0 + pacote de ícones 

> O mapeamento é um processo em que os membros da equipe de desenvolvimento podem executar, envolve "copiar" o código traduzindo-o em mapas mentais, 
> os quais poderão ser alterados e atualizados uma vez montados, sem necessidade de alterar código "na unha".

Após efetuar os mapeamentos, é necessário executar via linha de comando a geração de códigos, que é uma conversão do código mapeado em códigos práticos.
Abaixo é uma ilustração de como é o processo de criação dos mapas.

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