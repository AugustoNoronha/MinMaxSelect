# MaxMin Selector #
## Execução ##
Para executar o codigo execute o cmd no local do arquivo main.py 
insira o comando :
`python  main.py`
no seu cmd 

## Explicação linha a linha ##

1. `def max_min_select(arr, left, right):`
   - Define a função max_min_select com os paramentros arr, left e right
 
2.`if left == right:`
  - Verifica se o valor de left==right ( oque indica apenas um item no arrey )
    
3.`return arr[left], arr[left]`
  - Retorna o valor dos arrays finalizando a execução do algoritimo
    
4.`if right == left + 1:`
  - Verifica se Existem apenas 2 valores
    
5.`if arr[left] < arr[right]:`
  - Compara qual dos 2 valores
    
6.`return arr[left], arr[right]`
  - retorna arr com os dados em suas devidas posiçoes caso `arr[left] < arr[right]`
    
        else:
7.`return arr[right], arr[left]`
  - retorna arr com os dados em suas devidas posiçoes caso `arr[left] > arr[right]`
    
8.`mid = (left + right) // 2`
  - variavel mid recebe o valor de (left + right)/2
    
9.`min1, max1 = max_min_select(arr, left, mid)`
   min2, max2 = max_min_select(arr, mid + 1, right)`
 - A função é chamado de forma recursiva para as 2 metades do array, caracterizando o paradgma de dividir para conquistar 

10.`return min(min1, min2), max(max1, max2)`
  - retorna o minimo e o maximo fazendo a interpolação dos resultados 

`if __name__ == "__main__":`
   arr = [3, 1, 9, 7, 2, 8, 4, 6, 5]
    min_val, max_val = max_min_select(arr, 0, len(arr) - 1)
    print(f"Menor elemento: {min_val}")
    print(f"Maior elemento: {max_val}")`

## Análise Técnica de algoritimo ##

### Análise da Complexidade pelo Método de Contagem de Operações ###

O algoritmo faz comparações principalmente em duas etapas:

Divisão: A cada chamada recursiva, o problema é dividido ao meio.

Combinação: Depois, os valores das duas metades são comparados para encontrar o menor e o maior de todos.

Para um array de tamanho n, funciona da seguinte forma:

 - O array é dividido sucessivamente até sobrarem apenas 1 ou 2 elementos.

 - Como a divisão é feita ao meio, a profundidade da recursão é log(n).

 - Em cada nível, são feitas cerca de n comparações no total.

Por isso, o número total de comparações fica O(n) – ou seja, cresce linearmente com o tamanho do array.

### Análise pelo Teorema Mestre ###

A relação de recorrência é:
T(n) = 2T(n/2) + O(1)

Passo a passo:

Identificando os parâmetros:

- a = 2 → Número de chamadas recursivas.

- b = 2 → Fator de divisão do problema.

- f(n) = O(1) → Custo das operações fora da recursão.

Calculando log_b(a):

- log₂(2) = 1

Comparando com f(n):

- f(n) = O(1), que é equivalente a O(n⁰).

- Como 1 > 0, estamos no Caso 1 do Teorema Mestre.

Conclusão:

- Pelo Caso 1, a complexidade é O(n^log_b(a)) = O(n¹) = O(n).

Portanto, o algoritmo tem complexidade linear O(n) 

