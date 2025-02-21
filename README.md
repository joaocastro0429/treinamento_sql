# Treinamento_sql

## Treinamento basico de SQL 

Introdução : 

tabela ( ou relações) : conjunto que representa um conceito do mundo real 
linha (ou tubla) : um exemplo especifico de uma tabela
colunas (ou atributos) cada caracteristica de uma tabela

Dominio de atributo : tipo da caracteristica , ex : string , int , float 

Comando basicos em sql  
Construção de Consulta 

1 - em que tabelas estão os dados necessários ? 
2 - você precisa de todas as linhas ou precisa de  um filtro ? 
3 - você precisa de todas as colunas ou somente de algumas?  

SELECT colunas
 FROM albuns 
WHERE ano = 1969

Esse padawan tá prestatando atenção ! Pra escolher todas as colunas da tabela na consulta ,
basta usar o asterisco

SELECT *
 FROM albuns 
WHERE ano = 1969

Fazendo a ordenação 

SELECT *
 FROM albuns 
WHERE ano = 1969
ORDER_BY Ano_Formacao


AGREGAÇÃO DE TABELAS : 

Um conceito muito importe ! Agregar várias linhas por 
algumas colunas  ex : banda por estilo é algo extremamente útil
para entender melhor os dados   


O conceito muda um pouco , porque até então trabalhamos com linhas sem agrupamento

Utilizamos a agregação quando queremos conhecer alguns dados de estatistica descritiva dos dados: 
contagem,média, desvio de padrão, mínimo , máximo , etc 


exemplos de análises apartir dos dados podemos fazer com agregações : 

Quantas bandas por estilos ? 
qual a média de álbuns por estilo?
Qual a média de álbuns acima de 10 ?
Quais estilos possuem mais de 1 banda com ano de formação antes de 1970 ? 


Em SQL, para agregar linhas utilizamos o comando GROUP BY 

SELECT estilo , count(nome)
FROM bandas
GROUP BY estilos


obs: Colapsar linhas no banco de dados geralmente se refere ao processo 
de agrupar várias linhas em uma única linha, consolidando informações com 
base em uma ou mais colunas. Isso é comum em consultas SQL quando usamos funções
 de agregação, como SUM(), COUNT(), MAX(), MIN() ou STRING_AGG() junto com a cláusula 
GROUP BY.


Qual a média de álbuns por estilo ? 

SELECT estilo, AVG(albuns)
FROM bandas
GROUP BY estilo


Filtros de linhas já apredemos ! Usamos WHERE

Mas quando precisamos filtrar linhas por resultados de funçoes de agregação
(count, avg, max,min...) utilizamos outros comando , o HAVING

SELECT estilo, AVG(Albuns)
FROM bandas
GROUP BY estilos 
HAVING AVG(Albuns)>10
 
