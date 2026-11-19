# Organizaê

Aplicação web de gerenciamento de tarefas que roda direto no navegador, sem frameworks. Trabalho Prático Individual — HTML, CSS e JavaScript.

🔗 **Aplicação publicada:** https://SEU-USUARIO.github.io/organizae/

## Funcionalidades implementadas

- Cadastrar tarefas com título, descrição, prioridade (baixa, média, alta) e prazo.
- Listar, editar (em janela de diálogo), concluir/reabrir e excluir (com confirmação).
- Filtros por status: todas, pendentes e concluídas.
- Contadores de total, pendentes e concluídas.
- Busca por texto e botão para remover todas as concluídas.
- Persistência no navegador com `localStorage`: os dados continuam ao recarregar a página.
- Validação do formulário, mensagens de feedback (toasts), estados vazios e destaque para tarefas atrasadas.
- Layout responsivo e acessível (rótulos, foco visível, navegação por teclado, `aria-live`).

## Como executar

1. Clone o repositório: `git clone https://github.com/SEU-USUARIO/organizae.git`
2. Abra a pasta `organizae` e dê duplo clique em `index.html` (ou use a extensão Live Server do VS Code).

Não há dependências nem etapa de build.

## Tecnologias utilizadas

- HTML5 semântico (`header`, `main`, `section`, `form`, `ul`, `dialog`, `footer`)
- CSS3 (variáveis CSS, Grid, Flexbox, media queries)
- JavaScript puro (DOM, eventos, `localStorage`)
- Git e GitHub / GitHub Pages

## Estrutura

```
organizae/
├── index.html
├── css/style.css
├── js/app.js
├── assets/favicon.svg
├── README.md
└── LICENSE
```

## Principais decisões de implementação

- **Estado único + renderização:** o array `tarefas` é a fonte da verdade; `renderizar()` redesenha lista, contadores e mensagens a partir dele e toda alteração chama `salvar()`.
- **Segurança:** o conteúdo digitado é inserido com `textContent` (nunca `innerHTML`), evitando injeção de HTML.
- **Delegação de eventos:** um único listener na lista trata editar, excluir e concluir.
- **`<dialog>` nativo** para edição e confirmação de exclusão, com foco e tecla Esc tratados pelo navegador.
- **Ordenação:** pendentes primeiro, depois por prioridade e prazo.
- **CSS organizado** por seções com variáveis para cores e raios, e abordagem responsiva simples (layout fluido + um breakpoint).

## Licença

MIT — veja o arquivo [LICENSE](LICENSE).
