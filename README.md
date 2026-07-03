# Mineração de dados educacionais para apoio à validação de aprendizagem ao final de módulos 

Repositório contendo o código-fonte e as instruções de replicação do projeto final da disciplina de Ciência de Dados Apoiada por IA, do Instituto Militar de Engenharia (IME).

## Descrição do Projeto
Este script implementa um algoritmo de Mineração de Dados Educacionais utilizando o algoritmo K-Means para agrupar e priorizar tópicos matemáticos. A abordagem cruza a taxa de erro com métricas de esforço do aluno (tempo de resposta, tentativas e uso de dicas) extraídas do *ASSISTments Data Set 2012-2013*, agregando os resultados por módulos pedagógicos para apoiar o planejamento docente.

## Requisitos e Dependências
- Python 3.8+
- pandas
- numpy
- scikit-learn

## Como replicar o experimento

1. **Clone este repositório** ou faça o download do arquivo executável.
2. **Base de dados:** Faça o download do *ASSISTments Data Set 2012-2013* e coloque-o em seu diretório.
3. **Configuração de caminhos:** O script está configurado nativamente para rodar no Google Colab, lendo dados do Google Drive. Caso execute localmente, altere as variáveis `CAMINHO_ARQUIVO` e `PASTA_SAIDA` no bloco de "Configurações Gerais" no início do código.
4. **Execução:** Rode o script. O código realizará automaticamente:
   - Limpeza e filtragem da base bruta.
   - Agregação por *skill* (tópico matemático).
   - Clusterização K-Means (k=3).
   - Cálculo do Score de Prioridade Local (SPL) por módulo.
   - Levantamento de hipóteses comportamentais.

## Arquivos de Saída
O script exportará relatórios em `.csv` na pasta de saída configurada. Os principais arquivos para análise são:
- `06_resumo_perfis_globais.csv`: Estatísticas consolidadas dos três perfis gerados.
- `09_resumo_comparativo_modulos.csv`: Comparação quantitativa entre as recomendações do método e do *baseline*.
- `11_topicos_recomendados_metodo_proposto.csv`: A lista final contendo a priorização de tópicos para revisão.
