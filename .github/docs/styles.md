# Arquivos `src\styles`

> Voltar para o [`index`](./%40index.md).

## `themes\default.ts`

- Padronização de tokens de estilização.

## `\global.ts`

- a função `createGlobalStyle` oriunda do módulo _styled-components_ cria um componente com as definições globais de estilização. Pode-se repetir as padronizações em `CSS` para dentro de um componente
- `${(props) => props.theme[<token>]}` - padrão de código para inclusão dos tokens de cores. O parâmetro `props` é uma referência dentro do `DefaultTheme` utilizada para se ter acesso a propriedade `theme` da interface `ThemeProps` nativa do módulo _styled-components_.
