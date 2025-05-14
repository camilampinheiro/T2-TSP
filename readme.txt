*****************************************************************************************************
T290 - Resolução de Problemas com Grafos
Orientador: Prof. Me Ricardo Carubbi
*****************************************************************************************************

Trabalho 2: Problema do Caixeiro Viajante

Horas para completar o trabalho (opcional):

Q1. Explique como você implementou a heurística de inserção pelo vizinho mais próximo.
Comente também como você atualiza as ligações da lista encadeada circular após inserir o novo ponto.


Resposta:

Q2. Explique como você implementou a heurística de menor aumento.
Liste apenas as diferenças em relação à heurística de inserção pelo vizinho mais próximo.

Resposta:

Q3. Explique por que é melhor usar uma lista encadeada circular em vez de um vetor.
Considere a complexidade das operações de inserção e remoção de pontos.

Resposta:

Q4. Preencha os comprimentos calculados pelas suas heurísticas.

| Arquivo de dados | Vizinho mais próximo | Menor aumento |
| ---------------- | -------------------- | ------------- |
| tsp10.txt        | 1566.1363            | 1655.7462     |
| tsp100.txt       | 7389.9297            | 4887.2190     |
| tsp1000.txt      | 27868.7106           | 17265.6282    |
| usa13509.txt     | 77449.9794           | 45074.7769    |
| tsp85900.txt     | 125660.3433          | 82621.6659    |

Q5. Realize duas análises de tempo

Comente se o valor de \(b\) encontrado é coerente com a análise teórica da complexidade de seu algoritmo.

- Estime o tempo de execução (em segundos) de cada heurística como uma função de \(n\), usando expressões da forma: \(a \times n^b\), onde \(b\) é um inteiro.
- Explique como você determinou cada uma das respostas.
- Para obter seus pontos de dados, execute as duas heurísticas para \(n = 1000\) e dobre \(n\) repetidamente até que o tempo de execução ultrapasse 60 segundos.
- Você pode usar o **TSPTimer** para ajudar, conforme indicado na lista de verificação.
- Se usar, execute com a opção **-Xint** para desativar otimizações do compilador.
- Se para \(n = 1000\) o tempo já ultrapassar 60 segundos, seu código está muito lento. Veja a lista de verificação para sugestões de correção.

| n     | Tempo vizinho mais próximo (s)  | Tempo menor aumento (s)  |
| ----  | ------------------------------  | -----------------------  |
| 1000  |             0.026               |          0.059           |
| 2000  |             0.088               |          0.231           |
| 3000  |             0.198               |          0.547           |
| 4000  |             0.346               |          0.908           |
| 5000  |             0.538               |          1.413           |
| 6000  |             0.764               |          2.04            |
| 7000  |             1.038               |          2.788           |
| 8000  |             1.356               |          3.641           |
| 9000  |             1.709               |          4.578           |
| 10000 |             2.147               |          5.686           |
| 20000 |             8.587               |          23.108          |
| 30000 |             19.981              |          54.139          |
| 35000 |             26.569              |          70.811          |
| 50000 |             53.817              |          144.307         |
| 60000 |             79.602              |          210.132         |

