# Exercício de Revisão para a Segunda Prova

1. Letra C: O modelo possui apenas 2 estados, ativado e desativado.
2. Letra D: O enunciado descreve que os dados são segmentados por similaridade.
3. Letra B: Apenas I e II.
	- $(A \land B) \to ~C$ pode ser reescrito como $\neg(A \land B) \lor C$.
	- $\neg A \to B$ pode ser reescrito como $\neg A \lor B$.
	- $A \leftrightarrow \neg B$ pode ser reescrito como $(\neg A \land B) \lor (\neg B \land A)$, está última sendo a expressão XOR.
4. Os verbos serão todos transformados no verbo "ter", pois isso é um processo de "Lematização" no qual reduz a palavra ao seu *lemma*, no caso, para a forma infinitiva.   
5. Letra A: A Busca Gulosa (*Greedy Search*) expande para os nó de menor custo a partir da função heurística, funcionando semelhante a Busca em Profundidade (DFS).
6. Letra B: A distância de *Manhattam* pode ser calculada pela fórmula $h(x) = |x_1 - x_2| + |y_1 - y_2|$ e sabendo que o quadrado verde está do posição $(1,2)$ e o objetivo em $(3,3)$, temos: $h(x) = |1 - 3| + |2 - 3| = 2 + 1 = 3$.
7. -
8. Letra C: 
	- III - A função de ativação ReLU é não linear.
9. O número ideal de *clusters* (K) é 2, pois é onde aparece o "cotovelo" no gráfico, isto é o ponto onde a distorção começa a diminuir mais lentamente.
10. Letra B:
	- I - Não é possível implementar XOR com um *perceptron*, mas sim usando *backpropagation*.
	- IV - RNA é caixa preta o que contradiz a definição de teorema.
11. Letra E: O enunciado descreve que busca determinar afinidade entre os dados e isso é associação, pois esta descobre relações frequente entre itens.
12. Letra A: $A \to B$, $C \to D$. $A$ é verdadeiro e $C$ é falso, logo $B$ é verdadeiros e não é possível concluir nada de $D$.
13. Letra A: Suporte é definido como número de transações que contem todos os itens da transação dividido pelo número de transações. 
14. Letra C: O enunciado descreve que os dados são organizado em regras de classificação.
15. Letra A