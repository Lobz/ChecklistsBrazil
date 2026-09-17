# ChecklistsBrazil
Listas de espécies de plantas das Unidades de Conservação (UCs) do Brasil - resultados do [IntegraFlora](http://github.com/Lobz/IntegraFlora)

## Resumos dos dados
Compilamos uma lista de 3410 UCs do Brasil, sendo que  os estados com maior número de UCs listadas são Rio de Janeiro (367), Minas Gerais (367), São Paulo (357) e Bahia (305). Os outros estados têm todos menos de 200 UCs, com a maioria tendo menos de 100, e dois estados (Roraima e Sergipe) tem menos de 20 UCs. Essa lista não é completa, devido a indisponibilidade de dados sobre UCs brasileiras, especialmente as UCs municipais, que raramente são registradas no CNUC.

Dessas 3410 UCs, apenas 10% tem 20 ou mais registros, o que indica uma falta de estudos florísticos na maioria das UCs brasileiras. Além disso, as UCs com 20 ou mais registros estão concentradas em apenas 3 estados (São Paulo, Rio de Janeiro e Amazonas), enquanto a grande maioria dos estados contém apenas uma ou duas UCs com 20 ou mais registros, e nenhuma UC com 200 ou mais registros. Apenas 47 UCs tem 2000 ou mais registros, e 43 delas estão nesses três estados.

Parte desse padrão parece estar associado ao tipo e tamanho das UC. As reservas particulares de patrimônio natural (RPPNs) são numerosas, mas muito pouco estudadas. Das 1385 RPPNs listadas, apenas 31 parecem ter sido foco de algum estudo. Em comparação, dos 262 parques estaduais do país, 65 tem mais de 20 registros.

No total, essas listas contém 19110 espécies registradas em alguma UC do Brasil, com 17640 espécies nativas. As espécies nativas encontradas nessas UCs representam 38% de todas as espécies nativas listadas na Flora & Funga do Brasil. Também em taxonomia há um viés de coleta, com algumas famílias melhor representadas do que outras. Por exemplo, temos registros em UCs de 69 (82%) das 84 espécies de _Hymenophyllaceae_ e 560 (52%) das espécies de _Myrtaceae_, mas apenas 88 (14%) espécies de _Euriocaulaceae_ e 62 (20%) espécies de _Cactaceae_.


## Metodologia e fontes de dados

Para gerar as listas de UCs de cada estado brasileiro, usamos uma combinação de listas disponibilizadas pelo Cadastro Nacional de UCs (CNUC), Instituto Chico Mendes de Biodiversidade (ICMBio) e Instituto Florestal (IF). Apesar de nossos esforços para minimizar problemas, combinação dessas listas pode ocasionalmente gerar duplicação de UCs com variações no nome. As listas finais de UCs para cada estado estão nos arquivos de nome "UCsummary.csv" dentro de cada pasta. Além disso, usamos uma combinação de arquivos com tabelas de nomes alternativos e variações de nomes para as UCs, que foram compiladas manualmente por nossa equipe. Esses arquivos de dados e tabelas estão todos no repositório [IntegraFlora](http://github.com/Lobz/IntegraFlora).

Os dados de ocorrência foram baixados dos seguintes repositórios:
- [GBIF](https://www.gbif.org/)
- [Reflora](https://reflora.jbrj.gov.br/)
- [SpeciesLink](https://specieslink.net/search/)
- [JABOT](https://jabot.jbrj.gov.br/v3/consulta.php)

Nos casos do JABOT e Reflora, baixamos todos os dados disponíveis através do [IPT](https://ipt.jbrj.gov.br). No caso do SpeciesLink e do GBIF, restringimos a dados do Brasil, e do reino _Plantae_.

Os dados foram padronizados e organizados com uso do pacote R [plantR](http://github.com/LimaRAF/plantR), e os nomes científicos foram padronizados de acordo com a Flora & Funga do Brasil sempre que possível, e de acordo com a World Flora Online ou com a World Checklist of Vascular Plants, caso contrário.

Os registros foram associados a cada UC usando uma combinação de buscas por expressões regulares nos campos de localidade e cruzamento dos dados de GPS com os mapas georreferenciados disponibilizados pelo CNUC. As expressões regulares foram geradas a partir dos nomes das UCs e dos nomes alternativos, e nomes de localidades pertencentes às UCs, de forma a contemplar variações na escrita e problemas de encoding. As listas completas de registros associados a cada UC não estão disponíveis devido ao volume dos dados.

Os registros que melhor representam cada táxon foram selecionados de acordo com um Critério de Confiança que leva em conta a forma de associação à UC (_eg_, registros que contém o nome da UC têm maior confiança que aqueles que tem apenas coordenadas GPS), a especialidade do identificador (_ie_, damos maior confiança a registros identificados por especialistas na família), quão recente o registro é, se há material em herbário e se há imagem disponível para verificação. Até 5 outros registros de cada táxon estão listados no arquivo extra de cada UC, caso necessário.

Estas listas não foram verificadas manualmente, e podem conter erros. Para listas verificadas manualmente por uma equipe de especialistas, consulte o [Catálogo de Plantas das UCs do Brasil](http://https://catalogo-ucs-brasil.jbrj.gov.br/). As listas que disponibilizamos aqui foram geradas no formato requisitado pelo Catálogo, com o intuito de alimentarem o Catálogo após verificação manual.

Mais detalhes sobre a metodologia estão explicados no repositório da ferramenta [IntegraFlora](http://github.com/Lobz/IntegraFlora), criada para gerar essas listas.


## Apoio

Este projeto foi financiada pela FAPESP como parte do projeto 2024/07747-9 - "Aprimoramento e integração de bases de dados geoespaciais sobre a flora paulista", filiado ao Biota Síntese.

## Citação

_Geração de listas de espécies para todas as Unidades de Conservação do Brasil_,
Mali Oz C. Salles (autor correspondente),
Renato A. F. Lima,
Renata Ivanauskas,
Thuane Bochorny,
Katê Ocano,
Guilherme S. Grittz,
Pablo Pains,
Andre M. Pereira,
Marisa Domingos
