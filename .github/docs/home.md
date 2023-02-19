<!-- markdownlint-disable MD010 -->

# Page Home

> Voltar para o [`index`](./%40index.md).

## `index.tsx`

- A tag `<label>` em HTML tem como propósito fornecer uma descrição associada a um elemento de formulário, como um campo de texto, caixa de seleção ou botão de rádio. A tag `<label>` é usada para ajudar a descrever o propósito de um elemento de formulário para os usuários, especialmente aqueles com necessidades de acessibilidade, como pessoas com baixa visão ou cegas que usam leitor de tela. Ao colocar um rótulo no formulário, você pode fornecer informações adicionais sobre o que o usuário deve inserir ou selecionar, sem a necessidade de explicar isso em outro lugar na página. Isso pode ajudar a tornar o formulário mais fácil de preencher e mais acessível para todos os usuários. Você pode colocar um elemento de formulário dentro da tag `<label>`, usando o atributo "for" na tag `<label>` para vincular o elemento de formulário ao rótulo. Isso permite que os usuários cliquem no rótulo para selecionar o elemento de formulário associado. Além disso, o rótulo também pode ser estilizado usando CSS, para destacar a descrição do elemento de formulário.
- `<TaskInput />` e `<MinutesAmountInput />` são componentes que carregam todas as propriedades da tag HTML `<input>`. Foram definidas com o uso da função `styles()`.
- `{...register('task')}` e `{...register('minutesAmount', { valueAsNumber: true })}` - forma de se passar o hook form para dentro dos inputs do formulário.
- `import { zodResolver } from '@hookform/resolvers/zod'` - integração de React Hook Form com módulo de validação de dados. Há uma integração específicar com o módulo _zod_.
- `resolver: zodResolver(newCycleFormValidationSchema)` = forma de se passar um schema de validação dentro do hook form.
- `zod.object` - a validação de dados é feita a partir de um objeto, dado que a função `register()` do React Hook Form transforma os dados de tarefas e minutos para dentro um objeto.
- `defaultValues: {task: '',minutesAmount: 0,},` - definição de valores inicias para dentro do resolver
- `type NewCycleFormData = zod.infer<typeof newCycleFormValidationSchema>` - inferência de tipagem _generic_ para dentro do _schema validation_: um objeto com dados do tipo `string` e `number`. O `typeof` referência uma variável de javascript para dentro da inferência.
- `reset` - função do React Hook Form que reseta os valores dos formulário para os valores de `defaultValues` dentro do _resolver_.
- `useState<Cycle[]>([])` - é importante iniciar um estado com o mesmo tipo de dados que será armazenado.
- `const id = String(new Date().getTime())` - estratégia de criação de id para impedir repetição de id. O método `getTime()` retorna um número em milisegundos, que depois será transformado em uma `string`.
- `setCycles((state) => [...state, newCycle])` - o valor de estado é configurado no formato de uma função. Pega-se o estado atual dentro de uma variável de ciclos, de forma que a lista anterior de ciclo seja sobreposta pelo total de ciclos atual.
- `setActiveCycleId(id)` - definição do ciclo mais recente como o ciclo ativo.
- `Math.floor(currentSeconds / 60)` - arrendondar número "cheio" para baixo
- `currentSeconds % 60` - operador de resto. Quando segundos sobram e que não caibam dentro de uma divisão exata.
- O método `padStart()` em JavaScript é usado para preencher uma string com um determinado caractere, até que a string atinja um comprimento especificado. Ele é usado para formatar a string para um comprimento fixo, adicionando caracteres de preenchimento no início da string, se necessário. O objetivo do método `padStart()` é garantir que uma string tenha um comprimento mínimo especificado e que seja preenchida com um caractere específico no início da string, se necessário. Isso é útil em situações em que é importante que a string tenha um comprimento fixo, como ao formatar dados de entrada em uma tabela ou ao exibir valores numéricos com um número fixo de dígitos. O método `padStart()` é particularmente útil em situações em que o comprimento da string pode variar, mas é importante manter uma formatação consistente. Ele pode ajudar a tornar o código mais legível e a garantir que as saídas estejam formatadas corretamente.
- `useEffect()` -> Side-effect(efeito colateral). O `useEffect()` é um hook do React que permite executar código em resposta a mudanças em componentes ou em eventos no ciclo de vida de um componente. O propósito do `useEffect` é permitir que o desenvolvedor especifique como um componente deve responder a mudanças em seu estado ou nas propriedades recebidas, ou como ele deve reagir a eventos externos, como requisições assíncronas, timers ou atualizações no navegador. Com o `useEffect`, é possível definir o comportamento de um componente de forma declarativa, sem se preocupar com os detalhes de implementação. Ao usar o `useEffect`, o desenvolvedor pode definir o código que deve ser executado em resposta a uma ou mais dependências. Essas dependências podem ser definidas como um array de valores que o `useEffect` deve observar. Quando alguma das dependências mudar, o código dentro do `useEffect` é executado. Isso é particularmente útil para operações que exigem comunicação assíncrona com a API, manipulação do DOM, gerenciamento de eventos ou outras operações que podem afetar o estado do componente. O useEffect pode ser usado para muitas coisas, como atualizar o estado, disparar efeitos visuais, atualizar o DOM, definir ou remover eventos, entre outras coisas. Ele é uma ferramenta muito útil para garantir que a lógica de um componente esteja sempre atualizada e respondendo adequadamente às mudanças em seu estado ou nas propriedades recebidas.
- `Date` como tipagem no Typescript representa data e horário.
- Traduzindo a expressão abaixo: se o ciclo de contagem de tempo estiver ativo, o método `setAmountSecondsPassed()` monitorado pelo `useState()`, o método `differenceInSeconds()` compara a diferença do tempo atual com o tempo de quando o ciclo foi iniciado. E cada vez que a variável `activeCycle` mudar, a contagem de tempo será reiniciada.

```ts
useEffect(() => {
	if (activeCycle) {
		setInterval(() => {
			setAmountSecondsPassed(differenceInSeconds(new Date(), activeCycle.startDate))
		}, 1000)
	}
}, [activeCycle])
```

## `styles.ts`

- `flex: 1` em CSS é usada para definir o tamanho flexível do item flex. Ela faz parte do módulo de layout _Flexbox_ e é usada para controlar o tamanho e o comportamento de um item flex dentro de um container flexível. O valor 1 especifica que o item flex irá ocupar todo o espaço disponível no container, proporcionalmente aos outros itens flex. Por exemplo, se dois itens flex tiverem ambos o valor de `flex: 1`, cada um irá ocupar 50% do espaço disponível. Se um tiver o valor de `flex: 2`, ele irá ocupar o dobro do espaço em relação ao outro com `flex: 1`, e assim por diante. A propriedade `flex: 1` é frequentemente usada para criar colunas de largura igual ou para distribuir o espaço disponível de forma uniforme entre os itens flex. É uma notação abreviada para `flex-grow: 1` e `flex-shrink: 1`, o que significa que o item irá crescer para preencher o espaço disponível e encolher se necessário para evitar transbordar do container.
- A propriedade `flex-wrap: wrap` em CSS é usada para controlar o comportamento dos itens flex dentro de um container flexível. É parte do módulo de layout _Flexbox_. Quando o valor da propriedade `flex-wrap` é definido como _wrap_, os itens flex são permitidos quebrar para a próxima linha se houver pouco espaço na largura do container. Isso significa que, ao invés de os itens ficarem todos na mesma linha e ficarem muito estreitos, eles serão "quebrados" e colocados em linhas adicionais, mantendo a sua largura. A propriedade `flex-wrap: wrap` é útil quando você tem vários itens flex com larguras fixas e você quer garantir que eles não sejam exibidos em uma única linha muito estreita. Ao invés disso, eles serão exibidos em várias linhas, ocupando todo o espaço disponível no container. Além disso, também é útil para garantir que o conteúdo não seja cortado em dispositivos de tela menores (responsividade).
- A propriedade `overflow: hidden` em CSS tem como propósito controlar o que acontece quando o conteúdo de um elemento ultrapassa os limites do elemento. É usada para especificar como o conteúdo que não cabe dentro do elemento é tratado. Quando o valor da propriedade `overflow` é definido como _hidden_, o conteúdo que não cabe dentro do elemento é ocultado. Isso significa que o conteúdo que vai além dos limites do elemento não será exibido e não pode ser acessado ou visualizado. A propriedade `overflow: hidden` é útil para evitar que o conteúdo "transborde" do elemento, o que pode interferir na aparência e no layout da página. Além disso, também é útil para limitar o tamanho de elementos com conteúdo dinâmico, como elementos de rolagem, para que não fiquem muito grandes ou não sejam visualizados corretamente.
- `styled(BaseInput)` - é uma sintaxe usada no biblioteca de estilização chamada Styled Components, que permite a herança de estilos de um componente base para outro componente. O objetivo é aproveitar e reutilizar a estilização de um componente existente, tornando mais fácil e rápido criar novos componentes com estilos semelhantes. A função `styled()` é usada para criar um novo componente baseado em um componente existente, e o componente existente é passado como argumento para a função. O novo componente criado tem acesso a todos os estilos e propriedades do componente base, além de poder ser estilizado adicionalmente. Por exemplo, se você tem um componente base chamado `BaseInput` com algumas estilizações básicas, pode criar um novo componente de entrada estilizado usando a seguinte sintaxe:

```css
const StyledInput = styled(BaseInput)`
  /* Additional styles for StyledInput */
  background-color: yellow;
  padding: 10px;
`;
```

- `&::-webkit-calendar-picker-indicator {display: none !important;}` - retirar a seta do formulário de nomeação de tarefa.
