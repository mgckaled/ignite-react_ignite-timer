# Page History

> Voltar para o [`index`](./%40index.md).

## `index.tsx`

- `<tr key={cycle.id}>` - key na primeira tag do método `map()` baseado no timestamp em milisegundos.
- Em TypeScript, o operador `&&` é usado para avaliar uma expressão lógica condicional. Ele é conhecido como "operador de curto-circuito" porque, se a primeira expressão na operação `&&` é avaliada como falsa, a segunda expressão não é avaliada. Se a primeira expressão é avaliada como verdadeira, então a segunda expressão é avaliada e o resultado final é o valor da segunda expressão. Esse operador foi utilizado para considerar as possibilidades de status do ciclo.

## `styles.ts`

- A propriedade CSS `border-collapse: collapse` é usada para mesclar os limites (bordas) de células de uma tabela, para que elas sejam exibidas como uma única borda ao invés de várias bordas separadas. Isso resulta em uma aparência mais limpa e organizada da tabela. Além disso, a mesclagem de bordas pode ajudar a economizar espaço na página, pois a largura da borda é compartilhada entre as células adjacentes. O valor `collapse` é o valor padrão para a propriedade `border-collapse`, o que significa que as bordas das células são mescladas por padrão, a menos que a propriedade seja definida como `separate`.
- `border-radius: 9999px;` - cria uma forma de círculo para o elemento, pois o valor 9999px é grande o suficiente para tornar os cantos do elemento muito arredondados.
- `as const` ao final da constante confere a constante a exclusividade dos mapeamento das cores.
- `statusColor: keyof typeof STATUS_COLORS` - as cores disponíveis são as "keys" do objeto `STATUS_COLORS`. O operador `typeof` em Typescript é usado para obter o tipo de uma variável ou expressão em tempo de compilação, permitindo que os programadores escrevam código mais seguro e confiável.
