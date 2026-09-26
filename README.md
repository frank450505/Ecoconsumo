# EcoConsumo (ODS 12): versão 2

Aplicação web de página única (SPA) sobre consumo e produção responsáveis, desenvolvida com React, Vite e Bootstrap para a disciplina de Desenvolvimento Web (UEMA/UEMAnet). É a continuação da versão estática em HTML5/CSS3/Bootstrap da Nota 1.

## Funcionalidades

- **Dicas**: carregadas de `public/dados/dicas.json` via Fetch, com busca em tempo real (ignora acentos), filtro por categoria e termo salvo na URL.
- **Consultar produtos**: consumo da API pública Open Food Facts por nome ou código de barras, exibindo Eco-Score, Nutri-Score, classificação NOVA, embalagem e origem. Inclui estados de carregamento, erro e lista vazia, além de ordenação.
- **Desafios**: lista carregada de `public/dados/desafios.json`, marcação de concluídos, pontuação e barra de progresso. O estado é global (Context API) e fica salvo no `localStorage`.
- **Contato**: formulário controlado com validação por campo, contador de caracteres e mensagem de sucesso.
- **Tema claro/escuro**, menu responsivo, link "pular para o conteúdo", foco visível e página 404.

## Estrutura

```
public/dados/        JSON locais (dicas e desafios)
src/components/      Navbar, Footer, CardDica, CardProduto, SeloNota, BarraProgresso, Carregando, MensagemErro, RolarParaTopo
src/pages/           Home, Dicas, Produtos, Desafios, Contato, NaoEncontrada
src/context/         DesafiosContext (estado global dos desafios)
src/hooks/           useLocalStorage, useTema
src/services/api.js  Todas as requisições Fetch e o tratamento do JSON
src/App.jsx          Rotas (react-router-dom)
```

## Como executar

Pré-requisito: Node.js 18 ou superior.

```bash
npm install
npm run dev      # abre em http://localhost:5173
npm run build    # gera a versão de produção em dist/
```

## Publicação

**Vercel (recomendado):** envie o projeto para um repositório no GitHub, acesse vercel.com, entre com a conta do GitHub, clique em *Add New > Project*, importe o repositório e clique em *Deploy*. O Vite é detectado automaticamente. O arquivo `vercel.json` já faz as rotas funcionarem ao recarregar a página.

**Netlify:** *Add new site > Import from Git*, comando de build `npm run build`, pasta `dist`. O arquivo `public/_redirects` já trata as rotas.

## Fontes e licenças

- Dados de produtos: Open Food Facts (https://world.openfoodfacts.org), base aberta sob licença ODbL.
- Referência temática: Nações Unidas, ODS 12 (https://sdgs.un.org/goals/goal12).
- Bootstrap 5.3 (licença MIT), React e React Router (licença MIT).
