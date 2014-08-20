Processo de abertura de bases de dados
====

Este é o processo que será executado em cada projeto de abertura de dados
(por exemplo, o projeto da abertura de uma base de dados de um sistema de
informação de uma área de negócio específica). A depender da capacidade
da instituição, poderá ser executada uma ou mais instâncias desse processo
simultaneamente em um dado momento.


[<img alt="Diagrama do processo de abertura de um conjunto de dados" src="https://raw.githubusercontent.com/dadosgovbr/kit/master/public/img/Processo%20Publica%C3%A7%C3%A3o%20Dados%20Abertos.png">](https://raw.githubusercontent.com/dadosgovbr/kit/master/public/img/Processo%20Publica%C3%A7%C3%A3o%20Dados%20Abertos%20-%20com%20titulo.png)

## Documento Plano de Dados Abertos

O Plano de Dados Abertos da instituição norteará o processo de abertura de
dados quanto ao escopo, prazo estimado, partes interessadas, entre outros.
Deve-se trazer do Plano de Dados Abertos para o Projeto de Abertura de Dados
as suas partes que tratem dos seguintes aspectos:

* Escopo
  * dos dados: qual é (ou quais são) as bases de dados, quais são as tabelas,
    planilhas, parte ou secção dos dados é viável para essa iteração do
    processo de abertura;
  * de granularidade: se os dados serão separados por algum critério
    temporal ou espacial;
  * qualidade mínima aceitável para os produtos do projeto, definindo, por
    exemplo:
    * a forma de disponibilização dos dados (se será desenvolvida uma API de
      dados abertos ou se serão apenas disponibilizados arquivos com as
      extrações, por exemplo);
    * se será estabelecido algum relacionamento dos dados com uma fonte
      externa de dados abertos ou não;
    * se será realizada processo de higienização dos dados (por exemplo,
      correção de inconsistências ou de registros duplicados);
* Prazo estimado, considerando:
    * compromissos que possam ter sido assumidos em
      outros planos além do PDA (ex.: planejamento estratégico institucional e
      de tecnologia da informação, plano diretor de tecnologia da informação,
      plano de ação da Parceria para Governo Aberto, etc.);
    * capacidade de execução do projeto (quantitativo de pessoal capacitado,
      infraestrutura tecnológica, maturidade com o processo de abertura de
      dados);
* Partes interessadas: representante do comitê que acompanha a execução do
    PDA, gestor da área responsável pelas bases de dados, especialistas com
    conhecimento do negócio, gestor da área de TI, desenvolvedores,
    analistas de dados, entre outros.

Caso o Plano de Dados Abertos tenha sido omisso em relação a algum desses
aspectos, eles deverão ser definidos durante a
[reunião de início de projeto](#reuni%C3%A3o-de-in%C3%ADcio-de-projeto).

*Insumo para:*

* [Reunião de início de projeto](#reuni%C3%A3o-de-in%C3%ADcio-de-projeto)
* [Decidir qualidade mínima](#decidir-qualidade-m%C3%ADnima)

## Reunião de início de projeto

Nessa primeira reunião entre as partes interessadas no projeto serão definidos
o escopo e o prazo estimado do projeto, respeitadas as definições existentes no
[Plano de Dados Abertos](#documento-plano-de-dados-abertos) da instituição.

Serão definidos também as responsabilidades de cada um no projeto, a forma de
acompanhamento do projeto e a periodicidade de reuniões.

Um aspecto que tem grande impacto no escopo e prazo estimados para o projeto é
a escolha da forma de publicação dos dados. Por exemplo, desenvolver uma API de
dados abertos requer um maior esforço que simplesmente publicar arquivos. Mas,
se o volume de dados é grande, pode ser vantajoso para o cidadão poder se
utilizar dos métodos de consulta e filtros que uma API pode oferecer para
receber apenas os dados que lhe interessam.

*Próximo passo:* [Solicitar documentação](#solicitar-documenta%C3%A7%C3%A3o)

## Solicitar documentação

Solicitar esquema e documentação da base de dados. Ex.: modelos UML ou
entidade-relacionamento, dicionário de dados, etc. Todo tipo de documentação
ajuda às equipes de implementação a entender, em conjunto com especialistas
de negócio, a melhor forma de estruturar os dados para sua publicação.

*Próximo passo:* [Definir estrutura dos dados](#definir-estrutura-dos-dados)

## Definir estrutura dos dados

Definir campos e estrutura dos dados.

Nessa etapa também são definidos os formatos de saída dos dados. XML, CSV e
JSON são úteis para situações específicas.

As planilhas CSV têm a vantagem de poderem ser facilmente abertas em qualquer
editor de planilhas, tais como Calc e Excel, inclusive por uma pessoa que não
tenha conhecimentos de programação. Além disso, são igualmente fáceis de serem
consumidas por aplicações.

Os arquivos XML e JSON têm a vantagem de possibilitarem a validação de vários
tipos de dados, tais como números inteiros ou decimais. Além disso, permitem
aninhar as estruturas de dados em hierarquias, o que facilita trabalhar com os
dados em comparação com a estrutura plana de colunas do CSV.

Em caso de publicação de planilhas CSV, definir e escrever a documentação de
quais são e o que significam as colunas, bem como quais são os tipos de dados
aceitáveis em cada coluna de cada planilha.

Em caso de publicação de arquivos XML ou JSON, definir a estrutura básica do
documento. É possível, mas não necessário, estabelecer documentos XML Schema
ou JSON Schema para validação.

*Próximo passo:* [Realizar extração](#realizar-extra%C3%A7%C3%A3o)

## Realizar extração

Realizar extração inicial dos dados, a partir do ambiente de produção da base
de dados, para o local onde a base será disponibilizada como dados abertos.

Por exemplo, se tiver sido decidido publicar os dados em arquivos csv, essa
etapa contempla hospedar a extração em csv em um servidor de arquivos para a
web. Se tiver sido decidido publicar uma API de dados abertos, essa etapa
contempla a carga da base de dados que é acessada diretamente pela camada de
aplicação da API.

*Próximo passo:* [Decidir qualidade mínima](#decidir-qualidade-m%C3%ADnima)

## Decidir qualidade mínima

A partir do momento em que os dados estejam à disposição para verificação da
equipe técnica de implementação e dos especialistas de negócio, será avaliada
a necessidade de higienização dos dados antes da publicação.

Definir por acordo entre as partes interessadas a qualidade mínima dos dados
abertos publicados, de forma a viabilizar a sua publicação tempestiva dentro
da capacidade da instituição.

*Próximo passo:* [Atualização automática](#atualiza%C3%A7%C3%A3o-autom%C3%A1tica)

## Atualização automática

Definir e implementar processo automático e periódico de atualização dos dados.
Esta etapa contempla a negociação do intervalo de periodicidade e fluxo dos
dados entre os ambientes que compõem a arquitetura da solução de abertura de
dados, bem como a criação de scripts de transformação carga (ETL).

*Próximo passo:* [Homologar solução](#homologar-solu%C3%A7%C3%A3o)

## Homologar solução

Nesta etapa será verificada a conformidade da solução de abertura de dados
desenvolvida com as definições de escopo e especificações realizadas no
decorrer do projeto, inclusive no que se refere às condições de qualidade
acordadas.

Caso haja áreas internas da instituição que tenham necessidade de acesso aos
dados, disponibilizar acesso para testes antes da homologação.

Caso sejam detectadas não-conformidades, promover novas iterações no ciclo
de desenvolvimento e de implementação do fluxo de dados de forma a saná-las.

*Próximo passo:* [Publicar na web](#publicar-na-web)

## Publicar na web

Publicar os dados na web. Disponibilizar o acesso ao público externo.

*Próximo passo:* [Catalogar no dados.gov.br](#catalogar-no-dadosgovbr)

## Catalogar no dados.gov.br

Catalogar o novo conjunto de dados no Portal Brasileiro de Dados Abertos.
