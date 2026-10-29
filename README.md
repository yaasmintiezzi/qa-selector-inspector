# QA Selector Inspector

Ferramenta para **mapear seletores de elementos web de forma rápida**, pensada para quem faz automação de testes (Cypress, Playwright e Selenium).

Você clica no elemento na própria página e a ferramenta lê o HTML, lista todos os seletores possíveis e já entrega o comando pronto para o framework que você usa.

## O que ela faz

- Lista os seletores do elemento clicado: `id`, `name`, `formcontrolname`, `placeholder`, `data-*`, `aria-label`, `class`, texto, além de versões em **CSS** e **XPath**
- Mostra se cada seletor é **único** na página (verde) ou se **se repete** (laranja, ex.: `4x`)
- Quando o seletor se repete, já inclui o índice no comando (`.eq()`, `.nth()`, `.get()`)
- Sugere seletores **combinados** e por **escopo** (ancestral + elemento) quando nenhum atributo sozinho é único
- Gera o código pronto para **Cypress, Playwright, Selenium Java e Selenium Python**
- Para **listas e comboboxes** (`ng-select`, `mat-select`, `select`, `role="combobox"`), mostra o nome do campo e a sequência pronta: abrir a lista e escolher a primeira opção ou uma opção por texto
- Botão **Copiar** em cada item

## Como instalar (bookmarklet)

1. Abra o arquivo [`bookmarklet/bookmarklet.txt`](bookmarklet/bookmarklet.txt) e copie **todo** o conteúdo.
2. No Chrome, clique com o botão direito na barra de favoritos e escolha **Adicionar página**.
3. Dê o nome **Seletor** e cole o conteúdo no campo **URL**. Salve.

## Como usar

1. Abra a página que você está automatizando e clique no favorito **Seletor**.
2. Passe o mouse (o elemento fica azul) e clique no elemento desejado.
3. Escolha a aba do seu framework e clique em **Copiar** no que você quer usar.
4. Botões do painel: **▲ pai** (sobe um nível), **Pausar/Retomar** (para navegar na página), **Só únicos** e **✕**. A tecla `Esc` também fecha.

Alguns sites bloqueiam bookmarklets (política de segurança). Nesse caso, cole o conteúdo de [`src/qa-selector-inspector.js`](src/qa-selector-inspector.js) no Console do navegador (F12).

## Limitações

- Elementos dentro de iframes ou de Shadow DOM fechado não são alcançados
- As opções de lista seguem as classes padrão de cada biblioteca; bibliotecas customizadas podem precisar de ajuste
- No Cypress, XPath exige o plugin `cypress-xpath`

## Feedback

Testou? Me conta o que achou! Abra uma **Issue** aqui no repositório com bugs, sugestões ou o HTML de um elemento que não funcionou.

## Estrutura

```
qa-selector-inspector/
├── README.md
├── LICENSE
├── bookmarklet/
│   └── bookmarklet.txt              (versão para instalar como favorito)
└── src/
    └── qa-selector-inspector.js  (código legível)
```

## Autora

Criado por **Yasmin Tiezzi**, com apoio do Claude (IA da Anthropic).

## Licença

[MIT](LICENSE). Você pode usar, copiar e modificar livremente, desde que mantenha o aviso de copyright com o nome da autora.
