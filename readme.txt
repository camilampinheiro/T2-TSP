*****************************************************************************************************
T290 - Resolução de Problemas com Grafos
Orientador: Prof. Me Ricardo Carubbi
*****************************************************************************************************

Trabalho 2: Problema do Caixeiro Viajante

Horas para completar o trabalho (opcional):

Q1. Explique como você implementou a heurística de inserção pelo vizinho mais próximo.
Comente também como você atualiza as ligações da lista encadeada circular após inserir o novo ponto.

Resposta: 
Implementamos a heurística de inserção pelo vizinho mais próximo da seguinte maneira:
O código começa buscando entre todos os pontos já inseridos no tour, aquele que está mais próximo do novo ponto a ser adicionado. 
Começando do ponto inicial, percorremos a lista encadeada circular comparando as distâncias entre o novo 
ponto e cada ponto do tour. O ponto com a menor distância é armazenado como o "mais próximo", e ao final da 
busca o novo ponto é inserido logo após ele na lista. Para atualizar a lista encadeada circular, o novo nó 
tem seu ponteiro next direcionado para o próximo nó do ponto mais próximo encontrado. Em seguida, o ponteiro 
next do ponto mais próximo é ajustado para apontar para o novo nó. Isso garante que a estrutura continue circular 
e que o novo ponto seja corretamente incluído no percurso.

Q2. Explique como você implementou a heurística de menor aumento.
Liste apenas as diferenças em relação à heurística de inserção pelo vizinho mais próximo.

Resposta: 
Implementamos a heurística de menor aumento da seguinte maneira: 
O código começa percorrendo todas as arestas do tour (de cada ponto para o próximo) 
e calculando quanto a distância total aumentaria se o novo ponto fosse inserido entre eles. Para cada par de pontos 
consecutivos, usamos a fórmula: dist(a, p) + dist(p, b) - dist(a, b), isso representa o custo adicional de inserir 
p entre a e b. O ponto é então inserido no local onde esse aumento é o menor possível, mantendo a estrutura circular da 
lista encadeada. Diferente da heurística do vizinho mais próximo, que apenas encontra o ponto já existente mais próximo 
do novo e insere p depois dele, a heurística do menor aumento analisa todas as posições possíveis no tour e escolhe aquela 
que menos impacta a distância total, mesmo que o ponto inserido não esteja próximo de nenhum dos anteriores. Isso torna o 
resultado geralmente mais eficiente, pois considera o impacto global da inserção em vez de uma decisão local baseada apenas na proximidade.

Q3. Explique por que é melhor usar uma lista encadeada circular em vez de um vetor.
Considere a complexidade das operações de inserção e remoção de pontos.

Resposta:
A lista encadeada circular é melhor que um vetor nesse contexto porque permite inserir e remover pontos do tour com 
complexidade constante O(1), desde que tenhamos a referência do nó anterior. Em uma lista encadeada, basta ajustar os ponteiros 
(next) para incluir ou excluir um ponto, sem necessidade de deslocar os demais elementos. Já com um vetor (array), inserir ou remover 
um ponto exige deslocar todos os elementos à frente ou atrás da posição afetada, resultando em complexidade O(n) no pior caso. 
Isso torna o uso de vetor ineficiente para aplicações como o TSP, onde inserções frequentes são feitas em posições intermediárias. 
Além disso, a lista circular facilita a navegação contínua pelo tour, já que o último elemento aponta de volta para o primeiro, eliminando 
verificações extras de fim de lista.

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

