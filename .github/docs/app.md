# `App.tsx`

> Voltar para o [`index`](./%40index.md).

- `<ThemeProvider theme={defaultTheme}>`(Context Provider) - apesar de não mostrar configurações aparentes, recebe os tokens de cores definidasna constante `defaultTheme`.
- `</BrowserRouter>`(Context Provider) - contexto do módulo _react-router-dom_ onde o componente da rotas definidas para o aplicativo (`<Routes />`) deve ser inserido para que as configurações de rotas sejam implementadas.
- `<CyclesContextProvider>` - a inclusão do contexto dos ciclos por volta das rotas garante acesso a todas as funcionalidades, abstrações, estados a serem monitorados e tipagens do contexto pelo aplicativo.
