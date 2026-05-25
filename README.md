# Processamento de Linguagem Natural (PLN) - Extração de Recursos Textuais

Este repositório contém as atividades práticas desenvolvidas para a disciplina Tópicos Especiais do curso de Tecnologia Analise e Desenvolvimento de Sistemas, para a matéria de Sistemas de Recuperação de Informação (SRI). O objetivo principal do projeto é aplicar um pipeline completo de Processamento de Linguagem Natural (PLN) sobre um conjunto de dados brutos utilizando notbooks desenvolvidos em Python.

## 📁 Estrutura do Repositório

* `data/`: Diretório contendo a base de dados inicial e os arquivos processados gerados em formato compacto (`.zip`).
    * `documentos.csv`: Dataset bruto original contendo 20 notícias jornalísticas.
    * `dataset.zip`: Dados limpos e segmentados em sentenças.
    * `datasetpos.zip`: Dataset anotado com tags de Part-of-Speech (POS).
    * `datasetner.zip`: Dataset com as Entidades Nomeadas (NER) identificadas.
* `1_1_Segmentacao_Limpeza_v1.ipynb`: Notebook responsável pela higienização do texto bruto (remoção de tags HTML, espaços sobressalentes e normalização) e segmentação de sentenças.
* `1_2_GerarPOS_v1.ipynb`: Notebook focado na análise morfológica e etiquetagem gramatical (POS Tagging).
* `1_3_NER_spaCy_v1.ipynb`: Notebook para o Reconhecimento de Entidades Nomeadas (NER), extraindo atores, locais e organizações do texto.
* `2_1_AnaliseDados_v1.ipynb`: Notebook de consolidação estatística e geração de gráficos baseados nos recursos extraídos.

## 🚀 Pipeline de Processamento

1.  **Limpeza e Segmentação:** O texto bruto passa por uma esteira de limpeza que elimina ruídos de formatação web e descarta documentos que excedam o limite de 512 tokens (restrição do tokenizador do BERT).
2.  **Anotação Linguística (POS):** Mapeamento gramatical automatizado via pipeline do `spaCy`, classificando núcleos de texto como substantivos (`NOUN`), verbos (`VERB`), adjetivos (`ADJ`), entre outros.
3.  **Extração de Entidades (NER):** Identificação e rotulação de informações semânticas cruciais no texto, separando entidades como Pessoas (`PER`), Organizações (`ORG`) e Datas (`DATE`).
4.  **Análise Quantitativa:** Agregação dos dados gerados para visualização da distribuição de termos e entidades mais frequentes no corpus.

## 🛠️ Tecnologias Utilizadas

* Python 3
* Jupyter Notebooks / Google Colab
* Pandas (Manipulação de dados estruturados)
* spaCy (Processamento de Linguagem Natural)
* ftfy (Normalização de codificação de texto)
