# CLAUDE.md — Guia para IAs neste repositório

Leia isto antes de fazer qualquer alteração. O objetivo é você entregar exatamente
o que foi pedido, rápido e sem quebrar o site.

## O que é o projeto

Site de portfólio do **Isaac Roberto**, modelo infantil (4 anos). Página única,
publicada gratuitamente pelo **GitHub Pages** em https://shownato.github.io/Isaac/.

## Tecnologia (importante — não invente)

- **HTML estático puro.** Um único arquivo `index.html` contém a página inteira,
  com o CSS no `<style>` inline (no `<head>`) e o JavaScript no `<script>` no final.
- **SEM framework, SEM build, SEM npm, SEM ferramentas.** Não há passo de compilação.
  O que está no `index.html` é o que vai pro ar. Não sugira React, Vue, Tailwind,
  bundlers, TypeScript, etc. — não é esse tipo de projeto.
- Deploy é automático: ao mesclar na branch `main`, o GitHub Pages reconstrói o
  site em ~1 minuto.

## Estrutura de arquivos

- `index.html` — o site inteiro (HTML + CSS inline + JS inline).
- `img/` — fotos do Isaac (`isaac-1.jpg`, `isaac-2.jpg`, `isaac-3.jpg`).
- `og-isaac.jpg` — imagem do preview de compartilhamento (WhatsApp/Instagram).
- `README.md` — instruções de publicação para leigos.
- `CLAUDE.md` — este guia.

## Convenções de código

- **Todo o CSS fica no `<style>` inline do `index.html`.** Cores são variáveis CSS
  no `:root` (ex.: `--blue`, `--ink`, `--sky`). Reutilize as variáveis existentes.
- **Não crie arquivos `.css` externos.** Já tentaram isso: viraram código morto,
  nunca linkado, com fontes/cores erradas. Se precisar mexer no estilo, edite o
  `<style>` inline.
- Fontes usadas: **Fraunces** (títulos serif), **Mulish** (corpo), **Dancing Script**
  (cursiva). Não troque sem ser pedido.
- Sempre respeite `prefers-reduced-motion` em animações novas.

## Fluxo de trabalho (siga sempre)

1. **Entenda o pedido primeiro.** Se estiver ambíguo, pergunte antes de codar.
   Faça só o que foi pedido — nada de "melhorias" extras não solicitadas no mesmo commit.
2. Crie uma branch: `git checkout -b tipo/descricao` (`feat/`, `fix/`, `tweak/`,
   `docs/`, `chore/`).
3. Faça a alteração **mínima** que resolve o pedido.
4. **Verifique de verdade** antes de finalizar (veja abaixo). Não peça pro usuário
   testar manualmente — teste você.
5. Commit com mensagem clara no formato `tipo: descrição curta`, faça push e abra um PR.
6. O merge do PR é decisão do usuário. Não mescle por conta própria sem ele pedir.
7. Depois do merge, confirme que o site está no ar (`curl` no endereço).

## Como verificar

- Para testar comportamento (JS, cliques, layout): suba um servidor estático local
  e teste no navegador. Não confie só em ler o código.
- Para conferir o site publicado:
  `curl -s -o /dev/null -w "%{http_code}" https://shownato.github.io/Isaac/`

## Regras rígidas

- **Não** adicione ferramentas de build, dependências ou frameworks.
- **Não** crie CSS/JS em arquivos separados sem linká-los e testá-los no site.
- **Não** commite arquivos de anotação/memória de IA, rascunhos ou templates genéricos.
- **Não** misture mudanças não relacionadas num mesmo commit/PR — um PR, um assunto.
- **Cuidado com dados da criança:** o site é público. Mantenha localização só a nível
  de cidade (sem endereço, escola ou rotina). Contato é sempre via responsável.
  Não adicione informações pessoais sensíveis.
