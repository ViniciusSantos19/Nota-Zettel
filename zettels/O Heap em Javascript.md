080220241407
Status: #idea
Tags: #Programação #Javascript  
# O Heap em Javascript
O "heap" em JavaScript é uma área de memória dinâmica onde os objetos são alocados durante a execução do programa. É uma parte da memória do computador reservada para armazenar dados que não são acessados por meio de variáveis diretamente, mas sim por meio de referências aos objetos.

## Contceito
1. **Alocação Dinâmica:** O heap em JavaScript é utilizado para alocação dinâmica de memória, o que significa que a quantidade de memória necessária para armazenar objetos pode variar durante a execução do programa.
2. 1. **Gerenciamento Automático de Memória:** Em JavaScript, o gerenciamento de memória é feito automaticamente pelo mecanismo de coleta de lixo (garbage collector). O garbage collector identifica e remove os objetos não utilizados do heap, liberando assim a memória alocada para esses objetos.
## Funcionamento
1. **Alocação de Objetos:** Quando um objeto é criado em JavaScript usando a palavra-chave `new` ou de outras maneiras, ele é alocado no heap. O tamanho do objeto e sua estrutura determinam a quantidade de memória alocada para ele.
2. **Referências:** Os objetos no heap são acessados por meio de referências. As variáveis em JavaScript não armazenam os objetos diretamente, mas sim referências aos objetos no heap. Quando uma variável é atribuída a um objeto, ela armazena um endereço de memória que aponta para a localização do objeto no heap.
3. **Coleta de Lixo:** O garbage collector é responsável por identificar os objetos no heap que não são mais acessíveis pelo programa e liberar a memória alocada para esses objetos. Isso ocorre periodicamente, de forma automática, para evitar vazamentos de memória e garantir a eficiência do uso da memória.
## Importância
1. **Eficiência de Memória:** O heap permite uma alocação dinâmica de memória, o que significa que o programa pode alocar a quantidade necessária de memória para armazenar objetos conforme necessário, sem a necessidade de prever a quantidade exata de memória necessária antecipadamente.
2. **Flexibilidade:** O heap oferece flexibilidade na manipulação de dados em JavaScript, permitindo a criação e manipulação dinâmica de objetos durante a execução do programa.
3. **Garantia de Integridade:** O garbage collector garante a integridade do heap, removendo objetos não utilizados e liberando memória alocada, o que ajuda a evitar vazamentos de memória e outros problemas relacionados à gestão de memória.
*
## References
[[Event Queue]]
[[O Heap em Javascript]]
*
