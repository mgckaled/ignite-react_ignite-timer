# Component Header

> Voltar para o [`index`](./%40index.md).

## `index.tsx`

- `<NaviLink>` - uma constante do módulo _react-router-dom_ que um wrapper que indica se está 'ativo' ou não. É possível informar os caminhos de das rotas através da propriedade `to="/"`.

## `styles.ts`

- as propriedade `border-top` `border-bottom` foram incluídas para que o ícone não se mova pra cima ao aparecer a linha verde ao ser selecionado (`&:hover`).
- o `&` é um recurso originalmente desenvolvido por [LESS](https://lesscss.org/). Representa o selector do parente atual.
- `active` - pseudo-classe do _CSS_ para indicar a seleção do item.
