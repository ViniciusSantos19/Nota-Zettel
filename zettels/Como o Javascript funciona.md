080220241440
Status: #idea
Tags: #Permanent
# Como o Javascript funciona
JavaScript é uma linguagem de programação single-threaded, que utiliza um modelo de execução assíncrona e baseada em eventos. Para entender como o JavaScript opera, é importante compreender o papel de quatro componentes principais: heap, stack, queue e event loop.

**Heap (Heap):**

O heap em JavaScript é uma área de memória dinâmica onde os objetos são alocados durante a execução do programa. É usado para armazenar objetos e estruturas de dados complexas que podem ser referenciadas por meio de variáveis e referências. A alocação e liberação de memória no heap são gerenciadas automaticamente pelo coletor de lixo (garbage collector) do JavaScript.

**Stack (Pilha de Chamadas):**

A stack é uma estrutura de dados que rastreia as chamadas de função durante a execução do programa. Cada vez que uma função é chamada, um novo contexto de execução é criado e empilhado na stack. Isso inclui informações como variáveis locais, parâmetros e referência ao contexto de execução pai. Quando uma função retorna, seu contexto de execução é desempilhado da stack. A stack opera no modelo Last-In-First-Out (LIFO), o que significa que a última função a entrar na stack é a primeira a sair.

**Queue (Fila de Eventos):**

A queue, ou fila de eventos, é uma estrutura de dados onde eventos assíncronos são enfileirados para processamento. Isso inclui eventos como cliques do mouse, respostas de solicitações de rede, temporizadores, entre outros. Quando um evento ocorre, ele é colocado na fila de eventos para processamento futuro.

**Event Loop (Loop de Eventos):**

O event loop é um mecanismo que continua a verificar a stack e a queue em busca de novos eventos para processar. Ele garante que o código assíncrono seja executado no momento apropriado, coordenando a execução entre a stack e a queue. Quando a stack está vazia, o event loop verifica se há eventos na queue. Se houver, ele retira os eventos da queue e os envia para processamento, empilhando as funções de callback associadas na stack conforme necessário.

## Relação entre os componentes
1. Durante a execução do código, as chamadas de função são empilhadas na stack.
2. Se uma função contém operações assíncronas, como temporizadores (`setTimeout`) ou operações de I/O, elas são enviadas para a queue.
3. O event loop continua a verificar a stack e a queue. Quando a stack está vazia, ele retira os eventos da queue e os envia para processamento, empilhando as funções de callback associadas na stack conforme necessário.
4. A execução de eventos assíncronos permite que o código JavaScript seja não bloqueante, garantindo que operações demoradas não impeçam a execução do restante do código.

*
## References
[[zettels/Como o Javascript funciona|Como o Javascript funciona]]
[[Stack em Javascript]]
[[O Heap em Javascript]]
[[Event Queue]]
*
