# Arquivo `Router.tsx`

> Voltar para o [`index`](./%40index.md).

- `<Routes></Routes>` - componente que representa um contexto onde dever ser inseridos os componentes `<Route />` de cada rota.
- parâmentro `path=""` de `<Route />` é utilizado para indicar o "endereço"
- paramentro `element={}` utilziado para incluir o arquivo para o qual o endereço da página é direcionado.
- A primira `<Route />` aninhada em `<Routes></Routes>` tem como parâmetros `path="/" element={<DefaultLayout />}` para considerar o layout padrão com o componente _Header_.
