# Simulador de Rede de Roteadores com Algoritmo de Dijkstra

## 📝 Descrição

Este projeto é uma aplicação de console desenvolvida em C que simula o funcionamento de uma rede de roteadores. A aplicação permite construir uma topologia de rede,
definindo roteadores e as latências(custos) das conexões entre eles. A principal funcionalidade é calcular e exibir o caminho de menor latência entre dois roteadores
utilizando o **Algoritmo de Dijkstra**.

## ✨ Funcionalidades

O programa oferece um menu no console com as opções:

1.  **Adicionar roteador**: Permite adicionar um novo roteador à topologia da rede.
2.  **Conectar roteadores**: Cria uma conexão bidirecional entre dois roteadores, definindo um valor de latência em milissegundos entre eles.
3.  **Ping**: Calcula o caminho com a menor latência acumulada entre um roteador de origem e um de destino, exibindo o percurso completo (ex: `R1 -> R3 -> R5`) e a latência total.
4.  **Mostrar matriz**: Exibe uma matriz de adjacência que representa toda a rede, mostrando a latência entre um roteador e outro. Conexões inexistentes são marcadas com `*`.
5.  **Sair**: Encerra a aplicação.

## 🧠 Conceitos e Algoritmos Implementados

* **Grafos Ponderados**: A rede é representada por um grafo, onde os roteadores são as **vértices** e as conexões são as **arestas**. A latência representa o **peso** de cada aresta.
* **Matriz de Adjacência**: A estrutura de dados `Grafo` utiliza uma matriz `latencia[MAX][MAX]` para guardar os pesos das arestas, permitindo uma representação clara e direta das conexões.
* **Algoritmo de Dijkstra**: Implementado na função `ping`, este é a parte principal do projeto. Ele é usado para encontrar o caminho mais curto (de menor latência) de um único vértice de origem para todos os outros vértices no grafo.

## 🚀 Tecnologias Utilizadas

* **Linguagem C (Padrão C99/C11)**
* **Biblioteca Padrão:** `stdio.h` e `string.h`.

## ⚙️ Como Compilar e Executar

### Pré-requisitos

* Um compilador C, como o **GCC**, que é padrão na maioria dos sistemas Linux e pode ser facilmente instalado no Windows e no macOS.

### Passos

1.  **Salve o código:** Tenha certeza de que o código-fonte está salvo em um arquivo chamado `Latencia.c`.

2.  **Abra um terminal** na pasta onde o arquivo foi salvo.

3.  **Compile o programa** usando o seguinte comando:
    ```bash
    gcc Latencia.c -o Latencia
    ```
    * `gcc Latencia.c`: Invoca o compilador para o arquivo de origem.
    * `-o Latencia`: Especifica que o arquivo executável gerado deve se chamar `Latencia`.

4.  **Execute a aplicação:**
    ```bash
    ./Latencia
    ```
O programa será iniciado e o menu de opções será exibido.

## 📂 Estrutura do Código

* **`main()`**: Função principal que controla o loop do menu e a interação com o usuário.
* **`adicionar_roteador()`**: Adiciona um novo vértice ao grafo.
* **`conectar()`**: Adiciona uma aresta ponderada entre dois vértices.
* **`ping()`**: Implementa o Algoritmo de Dijkstra para encontrar e exibir o caminho de menor latência.
* **`mostrarMatriz()`**: Apresenta a matriz de adjacência do grafo.
* **`encontrar_indice()`**: Função utilitária para buscar o índice de um roteador no array a partir do seu nome.
