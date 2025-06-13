# Análise de Consumo de Materiais e Detecção de Anomalias

## Objetivo

O objetivo deste projeto é **identificar anomalias nos registros de consumo de materiais** em unidades operacionais de um hospital (ou outro setor) para detectar inconsistências que possam impactar a eficiência do estoque. Muitas vezes, falhas nos registros de consumo podem resultar em **estoques incorretos**, seja por **excesso** ou **falta** de materiais, afetando diretamente a operação e os custos da instituição. 

Neste projeto, são simulados registros de **entrada e saída de materiais**, e **técnicas de análise estatística** são aplicadas para detectar desvios significativos e **identificar padrões fora do comportamento esperado**. São usadas métricas como **Z-score**, **intervalo interquartil (IQR)**, e **desvios padrão** para detectar outliers e garantir a visibilidade dos estoques.

No final, o código cria um relatório de **alertas** para indicar itens que estão **em falta** ou **em excesso**, e uma simulação de impacto financeiro é realizada para destacar como falhas de registro podem afetar o custo operacional.

## Tecnologias Utilizadas

- **Python 3.x**
- Bibliotecas:
  - `pandas`: Manipulação de dados e DataFrame.
  - `numpy`: Cálculos matemáticos, como médias, desvios padrão e arredondamentos.
  - `bisect`: Para ajudar na separação de itens em falta e excesso.

## Estrutura do Código

O código está estruturado em **etapas sequenciais**, onde os dados são carregados, o consumo diário é calculado, o estoque ideal é determinado e, por fim, uma análise é realizada para identificar itens em falta ou em excesso.

### Como Funciona:

1. **Carregamento dos Dados**:
   O código carrega os dados do arquivo Excel que contém informações sobre o consumo de materiais e o estoque de cada um.

2. **Cálculo do Consumo Diário**:
   Para cada material, é calculado o **consumo diário**. O consumo é obtido subtraindo o estoque no final do dia pelo estoque inicial, garantindo que o valor do consumo não seja negativo.

3. **Cálculo do Estoque Ideal**:
   O estoque ideal é calculado com base em um **lead time** (tempo de reposição) de 7 dias, além de um fator de segurança baseado no desvio padrão do consumo.

4. **Comparação entre Estoque Real e Ideal**:
   O código compara o estoque real (último valor registrado) com o estoque ideal e identifica itens que estão **em falta** (estoque real abaixo do ideal) e **em excesso** (estoque real acima do ideal).

5. **Relatório de Alertas**:
   A função de análise gera um relatório com a lista de itens em falta e em excesso, e imprime essas informações no console.

---

## Como Usar

### Pré-requisitos

1. Clone este repositório para o seu computador:
   ```bash
   git clone https://github.com/usuario/nome-do-repositorio.git
   ```
   Ou faça download para sua máquina, extraia o arquivo zip, e abra no seu editor de código.
2. Instale as dependências necessárias
   ```pip install pandas numpy```

3. Configuração do Caminho do Arquivo
No código, há a linha abaixo, que carrega o arquivo Excel.
python
Copy
```df = pd.read_excel('C:\\Users\\hreal\\OneDrive - Infinera\\Desktop\\DasaMatHosp.xlsx')```

4. Rode o arquivo e os resultados serão exibidos!
