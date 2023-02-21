# Contexto CyclesContext

> Voltar para o [`index`](./%40index.md)

**Hook**: É uma função que permite a gente acessar as funcionalidades do React dentro dela, funcionalidades como o estado, outros hooks como useEffect, useCallback, useMemo, useContext. Ou seja, o Hook é uma forma de a gente reaproveitar uma lógica específica e compartilhar funcionamento entre componentes, sem precisar reescrever o código toda vez. Por isso criamos um hook para a Context, para não precisar ficar importando a Context e o useContext toda vez. Mas apesar de compartilhar funcionalidade, ele não compartilha estado.

**Context**: É uma forma de repassar e compartilhar dados entre diversos componentes. Apesar de parecer com a ideia de Hook, como dito acima o Hook não compartilha estado, mas a Context, por possuir um provider, irá compartilhar essa mesma informação entre diversos componentes. É ideal quando você quer a mesma informação em vários componentes distintos.

**Reducer**: É uma alternativa para o useState e é legal utilizar ele quando temos muita complexidade na regra de alteração do estado, muitas formas de alterá-lo. Ele ajuda a gente a separar a nossa regra de alteração de estado de forma mais desacoplada do restante do código, e se algum dia precisarmos trocar a regra de alteração desse estado, apenas precisariamos trocar no reducer.

- `interface CreateCycleData` - interface de entrada dos dados pelo formulário controlado. Será utilizada pela interface de contexto `CyclesContextType`
- `interface Cycle` - interface com mais camadas de abstração responsável por tipar criações e interrupções de ciclos de tempo. Também será utilizada pela interface de contexto `CyclesContextType`.
- `interface CyclesContextType` a interface que será consumida pelo arquivo `App.tsx`. Contém todas as abstrações e funcionalidades. Por isso, seus valores são passadoss para dentro da contexto criado `CyclesContext`.
- `CyclesContextProvider({ children }` - a propriedade especial `children` é criada dentro do próprio react através da tipagem `children: ReactNode`. Isso acontece porque as rotas estão dentro do contexto. É uma forma de referenciar o contexto com as rotas. É uma propriedade que representa todo o valor que foi passado entre as tags de abertura e fechamento de um componente.
- Em React, o tipo `ReactNode` é usado para representar qualquer tipo de conteúdo que pode ser renderizado como um nó na árvore de componentes do React. Isso inclui elementos JSX, strings, números, arrays de elementos JSX ou strings, e até mesmo `null` ou `undefined`.
- `const activeCycle = cycles.find((cycle) => cycle.id === activeCycleId)` - percorre o vetor de clicos e retorna o id do ciclo ativo.
- O `useReducer` é um hook do React que é usado para gerenciar estados complexos em um componente. Ele é uma alternativa ao `useState` para lidar com situações em que o estado do componente possui múltiplos valores relacionados. O `useReducer` segue o padrão do reducer da programação funcional, em que um estado atual é atualizado com base em uma ação, resultando em um novo estado. Ele recebe dois argumentos: um estado inicial e uma função de redução. A função de redução recebe dois argumentos: o estado atual e a ação a ser executada. A função de redução retorna um novo estado com base na ação fornecida.
- `useReducer((state: Cycle[], action: any)` - é importante definir o estado do reducer como um ciclo, pois esse será a "entidade" momitorada pelo React e a que sofrerá as ações.
- É muito comum que dentro do `dispatch()` seja enviado um objeto com os parâmetros `type` dando o nome da ação a ser realizada, e o `payload`, com os dados do novo ciclo. São recomendações da própria comunidade.
- `if (action.type === 'ADD_NEW_CYCLE') {return [...state, action.payload.newCycle]}` - transcrevendo: se a ação do reducer for 'criar novo ciclo', será retornado todos os estados já monitorado pelo React mais o novo ciclo que foi adicionado.
