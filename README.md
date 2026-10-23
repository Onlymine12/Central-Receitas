# 365 Receitas para Quem Tem Diabetes

App web de página única (sem servidor, sem banco de dados, sem build). Pronto para hospedar em qualquer hospedagem de arquivos estáticos.

## Conteúdo do pacote

```
index.html   App completo: estilos, código, as 80 receitas e os 3 bônus embutidos
img/         Todas as imagens usadas pelo app
README.md    Este arquivo
```

Dentro de `img/`:

- `<id-da-receita>/`: foto do prato pronto e dos passos de cada receita. Cada `.webp` tem uma cópia `.jpg`, usada em navegadores sem suporte a WebP.
- `categoria/` e `categorias/`: capas e banners das 8 categorias.
- `banner-home.webp`: banner da tela inicial.
- `bonus/compras/`, `bonus/cardapio/` e `bonus/substituicoes/`: banners e capas dos bônus.

## Como hospedar

1. Extraia o ZIP.
2. Envie **o arquivo `index.html` e a pasta `img`** para a raiz do site (ou para uma subpasta). Os dois precisam ficar lado a lado.
3. Acesse o endereço do site. Não há configuração adicional.

Funciona em hospedagens estáticas como Netlify, Vercel, GitHub Pages, Cloudflare Pages, Hostinger e cPanel. Também abre localmente com dois cliques no `index.html`.

Observações:

- Os nomes de arquivos e pastas diferenciam maiúsculas e minúsculas em servidores Linux. Não renomeie nada.
- A navegação usa endereços com `#` (ex.: `#/receita/...`), então não é preciso configurar redirecionamentos.
- A única dependência externa é a fonte do Google Fonts. Sem internet, o app usa a fonte do sistema.

## O que existe no app

- 8 categorias com 10 receitas cada (80 receitas), com busca, filtros, informação nutricional e passo a passo com fotos.
- Bônus 1, Lista de Compras Essenciais: 50 itens com busca, filtros, marcação, quantidades, exportação em TXT e impressão.
- Bônus 2, Cardápio de 30 Dias: 120 sugestões de refeições, navegação por dia, exportação em TXT e impressão.
- Bônus 3, Guia de Substituições: 30 ideias em 5 categorias, com busca, filtros, exportação em TXT e impressão.

As marcações da lista de compras ficam salvas no navegador de quem usa (`localStorage`), não em um servidor.

## Antes de publicar

- **Links de download:** os campos `arquivo:'#'` das categorias e dos bônus, marcados com `/* COLAR LINK REAL AQUI */` no `index.html`, ainda não têm o link real.
- **Peso das imagens:** a pasta `img` tem cerca de 112 MB. As imagens dos bônus são PNG de 2 a 2,7 MB cada. Convertê-las para WebP deixa as páginas dos bônus mais rápidas no celular. Se converter, atualize os nomes dos arquivos dentro do `index.html`.

## Como editar

Todo o conteúdo está dentro do `index.html`:

- Categorias: procure `const CATEGORIAS`.
- Bônus: procure `const BONUS`.
- Receitas: blocos `window.RECEITAS_...`.
- Dados dos bônus: `window.COMPRAS_ESSENCIAIS`, `window.CARDAPIO_30_DIAS` e `window.GUIA_SUBSTITUICOES`.

Para trocar uma imagem, substitua o arquivo em `img/` mantendo o mesmo nome.

## Aviso

Conteúdo educativo. As receitas, o cardápio e as substituições não substituem a orientação da equipe de saúde. Os avisos exibidos no app devem ser mantidos.
