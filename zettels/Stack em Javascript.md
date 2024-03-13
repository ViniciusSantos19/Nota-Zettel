080220241420
Status: #idea #Permanent 
Tags: #Programação #Javascript 
# Stack em Javascript
A stack, também conhecida como "pilha de chamadas", é uma estrutura de dados fundamental em JavaScript (e em muitas outras linguagens de programação). Ela é responsável por rastrear as chamadas de função durante a execução do programa. Compreender o funcionamento da stack é essencial para entender como JavaScript lida com a execução de funções e o contexto de execução.

## Conceito
1. **Estrutura de Dados LIFO:** A stack em JavaScript opera no princípio Last-In-First-Out (LIFO), ou seja, o último elemento inserido é o primeiro a ser removido. Isso significa que as chamadas de função são empilhadas (adicionadas ao topo da stack) quando são feitas e desempilhadas (removidas do topo da stack) quando retornam.
2. **Armazenamento de Contexto de Execução:** Cada chamada de função cria um novo contexto de execução, que contém informações como variáveis locais, parâmetros e referência ao contexto pai. Esses contextos de execução são empilhados na stack conforme as funções são chamadas e são desempilhados quando as funções retornam.
## Funcionamento
1. **Chamada de Função:** Quando uma função é chamada em JavaScript, um novo contexto de execução é criado para essa função e empilhado na stack. Isso inclui a alocação de memória para as variáveis locais da função e a manutenção da referência ao contexto de execução pai.
2. **Execução da Função:** A função em execução tem acesso aos seus parâmetros, variáveis locais e quaisquer variáveis ​​do escopo externo (escopo de fechamento). Todas as operações e cálculos dentro da função são executados dentro do contexto de execução atual na stack.
3. **Retorno da Função:** Quando uma função retorna, seu contexto de execução é desempilhado da stack. Isso libera a memória alocada para as variáveis locais e encerra o contexto de execução da função. O controle retorna para a função chamadora, que pode continuar sua execução de onde parou.

## Importância
1. **Rastreamento de Chamadas de Função:** A stack em JavaScript fornece um mecanismo para rastrear as chamadas de função e manter o contexto de execução associado a cada chamada de função. Isso é fundamental para a execução de funções de forma ordenada e para garantir que o controle retorne corretamente após o término de uma função.
2. **Gestão de Contexto de Execução:** A stack gerencia eficientemente os contextos de execução das funções, garantindo que as variáveis locais e os parâmetros sejam acessíveis apenas dentro do escopo da função e que não haja conflitos entre os contextos de execução de funções diferentes.
3. 1. **Controle de Fluxo de Execução:** A stack determina o fluxo de execução do programa, garantindo que as funções sejam chamadas e retornem na ordem correta. Isso é essencial para garantir a execução correta do código e evitar erros de lógica.

## Resumo
Em resumo, a stack em JavaScript desempenha um papel fundamental na execução de funções e no controle de fluxo do programa, garantindo que as chamadas de função sejam rastreadas de forma ordenada e que o contexto de execução seja gerenciado de maneira eficiente durante a execução do código.

*
## References
[[O Heap em Javascript]]
[[Event Queue]]
[[zettels/Como o JavaScript funciona]]
*
