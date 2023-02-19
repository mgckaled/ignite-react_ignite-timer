# Contexto CyclesContext

> Voltar para o [`index`](./%40index.md)

- `interface CreateCycleData` - interface de entrada dos dados pelo formulário controlado. Será utilizada pela interface de contexto `CyclesContextType`
- `interface Cycle` - interface com mais camadas de abstração responsável por tipar criações e interrupções de ciclos de tempo. Também será utilizada pela interface de contexto `CyclesContextType`.
- `interface CyclesContextType` a interface que será consumida pelo arquivo `App.tsx`. Contém todas as abstrações e funcionalidades. Por isso, seus valores são passadoss para dentro da contexto criado `CyclesContext`.
- `CyclesContextProvider({ children }` - a propriedade especial `children` é criada dentro do próprio react através da tipagem `children: ReactNode`. Isso acontece porque as rotas estão dentro do contexto. É uma forma de referenciar o contexto com as rotas.
- Em React, o tipo `ReactNode` é usado para representar qualquer tipo de conteúdo que pode ser renderizado como um nó na árvore de componentes do React. Isso inclui elementos JSX, strings, números, arrays de elementos JSX ou strings, e até mesmo `null` ou `undefined`.
- `const activeCycle = cycles.find((cycle) => cycle.id === activeCycleId)` - percorre o vetor de clicos e retorna o id do ciclo ativo.
