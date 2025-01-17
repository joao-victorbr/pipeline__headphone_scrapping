# Projeto de pipeline de dados com webscrapping

### Resumo
O objetivo desse projeto é fazer uma pesquisa de mercado na categoria de headphones dentro da plataforma Magazineluiza.

O projeto deve avaliar os seguintes pontos:
1) Quais são as marcas mais encontradas até a 10 página de busca?
2) Qual é o preço médio por marca?
3) Qual é a pontuação de satisfação por marca?
4) Quais são os produtos com maiores descontos?

Os resultados devem ser exibidos em um dashboard com informações originadas de um banco de dados.

### Processo da pipeline

![Imagem github](https://github.com/user-attachments/assets/f4e6b783-b71b-478d-ad14-5d00037c274c)

- A pipeline começa a partir de um processo de webscrapping feito com a biblioteca Scrapy. Os dados coletados geram um arquivo .jsonl;
- Em seguida, os dados coletados são tratados e enriquecidos com a biblioteca Pandas. O tratamento resulta em uma saída para um banco de dados com o uso da biblioteca SQLite3.
- Por último, os dados são lidos do arquivo .db e carregados em um dashboard com a utilização da biblioteca Streamlit.

### Execução:
- Para executar o web scrapping:
``scrapy crawl magazineluiza -o ../data/data_extracted.jsonl``

- Para executar o tratamento:
``python transformacao/tratamento.py``

- Para executar o dashboard:
``streamlit run ../src/dashboard/app.py``

Obs.: O output do comando acima exibe um link de localhost. Pressione "ctrl + click" para gerar o dashboard no navegador.
  
### Demonstração do dashboard 
https://github.com/joao-victorbr/pipeline_headphone_scrapping/assets/96805016/6546c31a-59a8-4776-a7cb-cddec61b7948

Obs.: Com o passar do tempo após a publicação desse código, é possível que o html da página de busca se modifique pelos criadores. Isso ocasionará em erro da etapa de coleta de dados do site. Nesse caso, a etapa de web scrapping deve ser atualizada.
