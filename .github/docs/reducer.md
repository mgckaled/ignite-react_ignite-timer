# Reducer `reducer.ts`

> Voltar para o [`index`](./%40index.md).

- `(action.type === 'ADD_NEW_CYCLE') {}` - transcrevendo: se a ação do reducer for 'criar novo ciclo', será retornado todos os estados já monitorado pelo React mais o novo ciclo que foi adicionado.
- `interface CyclesState` - a interface com as informações dos estados do ciclo.
- `(action.type === 'INTERRUPT_CURRENT_CYCLE') {}` - cria-se uma data de interrupção para cada ciclo com o uso do método `map()`
- `switch (action.type) { case ...` - refatoração para evitar o uso excessivo de `if()`
- `case 'MARK_CURRENT_CYCLE_AS_FINISHED'` - cria-se uma data de finalização para cada ciclo com o uso do método `map()`.
-
