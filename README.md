# Processamento de Linguagem Natural (PLN) - Extração de Recursos Textuais (Fauna Marinha)

Este repositório contém as atividades práticas desenvolvidas para a disciplina de Sistemas de Recuperação de Informação (SRI). O objetivo principal do projeto é aplicar um pipeline completo de Processamento de Linguagem Natural (PLN) utilizando a biblioteca **spaCy** e modelos baseados em **BERT** sobre uma base de dados real de ocorrências e monitoramento de fauna litorânea no estado de Santa Catarina.

## 📁 Estrutura do Repositório

* `data/`: Diretório contendo a base de dados inicial e os arquivos processados gerados em formato compacto (`.zip`).
    * `documentos.csv`: Dataset original contendo 1964 relatórios narrativos de ocorrências de fauna marinha.
    * `dataset.zip`: Dados processados, limpos e segmentados em sentenças individuais.
    * `datasetpos.zip`: Dataset anotado com tags morfológicas de Part-of-Speech (POS Tagging).
    * `datasetner.zip`: Dataset com o Reconhecimento de Entidades Nomeadas (NER) concluído.
* `1_1_Segmentacao_Limpeza_v1.ipynb`: Notebook responsável pela higienização do texto bruto (eliminação de tags HTML, normalização de pontuações repetidas e espaços sobressalentes) e segmentação de sentenças.
* `1_2_GerarPOS_v1.ipynb`: Notebook focado na análise morfológica e etiquetagem das classes gramaticais (POS).
* `1_3_NER_spaCy_v1.ipynb`: Notebook voltado para o Reconhecimento de Entidades Nomeadas (NER), extraindo localizações geográficas, instituições e táxons.
* `2_1_AnaliseDados_v1.ipynb`: Notebook para consolidação estatística, agregação de termos e geração de gráficos baseados nos recursos linguísticos extraídos.

## 🚀 Características do Corpus e Pipeline

1.  **Geração do Corpus Narrativo:** Dados tabulares reais de monitoramento de fauna marinha em SC foram convertidos em textos corridos, estruturados com conectivos naturais e delimitados por identificadores únicos (`id;documento`).
2.  **Tratamento de Ruídos Propositais:** Cada documento foi envolvido com tags HTML (`<b>`, `</b><br>`) e repetições de caracteres (como `, ,,`) para testar de forma rigorosa as expressões regulares (RegEx) de limpeza do pipeline.
3.  **Controle de Volumetria (BERT):** Todos os 1964 documentos foram otimizados textualmente para manterem-se rigorosamente abaixo do limite crítico de 512 tokens por linha, garantindo que nenhum registro fosse descartado pelo tokenizador do BERT.
4.  **Extração Gramatical (POS):** Mapeamento via pipeline do `spaCy` para identificar a função sintática das palavras, destacando núcleos textuais repetitivos como substantivos (`NOUN` - *indivíduo, monitoramento, espécie*) e verbos (`VERB` - *registrado, encontrado*).
5.  **Extração de Entidades Semânticas (NER):** Localização automática de informações geográficas críticas e dados estruturais, classificando de forma automatizada entidades como Localidades (`LOC` - *Penha, Bombinhas, Laguna, Santa Catarina*) e Organizações (`ORG` - *Trecho 04, Trecho 05*).

## 🛠️ Tecnologias Utilizadas

* Python 3
* Jupyter Notebooks / Google Colab
* Pandas (Manipulação de dados estruturados)
* spaCy (Processamento de Linguagem Natural e Modelos de Linguagem)
* ftfy (Normalização de codificação de texto)
