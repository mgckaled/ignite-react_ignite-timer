# Layout Default

> Voltar para o [`index`](./%40index.md).

O objetivo deste componente é utlizar o layout do componente _Header_ como padrão, dado que ele estará presente em todas as páginas, independentement das rotas.

## `index.tsx`

- `<Outlet />` - deve ser usado em elementos de rota pai para renderizar seus elementos de rota filho. Isso permite que a interface do usuário aninhada apareça quando as rotas filhas são renderizadas. Se a rota pai corresponder exatamente, ela renderizará uma rota de índice filho ou nada se não houver rota de índice. Vai substituir a página definida pelas rotas.

## `styles.ts`
