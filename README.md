# Soma de Prefixo (Prefix Sum)

## Explicação

O algoritmo de Soma de Prefixo, também conhecido como Scan, é um método para calcular a soma acumulada de elementos em um array de dados. Isso significa que para cada posição do array, armazenamos a soma de todos os elementos até aquela posição, inclusive.

### Benefícios:

- **Cálculo rápido de somas em intervalos:** Após construir a lista de prefixo, podemos calcular a soma dos elementos entre quaisquer dois índices i e j (com i <= j) em tempo constante, utilizando a fórmula: soma(i, j) = prefixo[j] - prefixo[i - 1].
  
- **Eficiência:** O processo de construir a lista de prefixo tem uma complexidade de tempo linear, O(n), onde n é o tamanho do array.

## Passo a Passo

### Inicialização:

1. Crie um novo array prefixo com o mesmo tamanho do array original.
2. Defina o primeiro elemento de prefixo como sendo igual ao primeiro elemento do array original: `prefixo[0] = array[0]`.

### Iteração e cálculo:

1. Percorra o array original do segundo elemento até o final.
2. Para cada posição i, calcule o valor de prefixo[i] como a soma do elemento atual array[i] com o valor da posição anterior no array prefixo: `prefixo[i] = prefixo[i - 1] + array[i]`.

### Utilização:

Com o array prefixo construído, você pode calcular a soma de qualquer intervalo [i, j] (com i <= j) em tempo constante usando a fórmula: `soma(i, j) = prefixo[j] - prefixo[i - 1]`.

## Código C++

```cpp
#include<bits/stdc++.h>
using namespace std;

void preencherLista(int array[], int prefixSoma[], int n){
    prefixSoma[0] = array[0];
    
    for(int i = 1; i < n; i++){
        prefixSoma[i] = prefixSoma[i - 1] + array[i];
    }
}

int main()
{
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    
    int array[] = {1,2,3,4,5};
    int n = sizeof(array) / sizeof(array[0]);
    int prefixSoma[n];
    
    preencherLista(array, prefixSoma, n);
    
    for(int i = 0; i < n; i++){
        cout << prefixSoma[i] << ' ';
    }
    
    cout << endl;
    
    return 0;
}
```

Este código em C++ preenche um array de soma de prefixo e imprime os elementos resultantes.
