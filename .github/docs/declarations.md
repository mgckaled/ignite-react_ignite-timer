# Arquivos `src\@types`

> Voltar para o [`index`](./%40index.md).

## `styled.d.ts`

- Arquivo de definição de tipagem.
- A tipagem detro de `defaultTheme` é criada automaticamente dentro do _Typescript_. A key `typeof` é uma forma de acessar as tipagem inferida dentro `defaltTheme` para guardar dentro de `ThemeType`.
- `declare module` são keys utilizadas para declaração de tipagens. Dentro dessa declaração interface `DefalutTheme` é extendida por `ThemeType`
