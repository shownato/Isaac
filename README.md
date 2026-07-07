# Site do Isaac Roberto — Modelo Infantil

Portfólio online do Isaac. Este repositório contém o site pronto para publicar
gratuitamente pelo **GitHub Pages**.

## Arquivos

- `index.html` — o site (abre sozinho quando alguém acessa o endereço).
- `og-isaac.jpg` — imagem que aparece no preview ao compartilhar o link (WhatsApp, Instagram, etc.).

---

## Como publicar de graça (GitHub Pages)

### Passo 1 — Criar o repositório
1. Entre no site https://github.com e faça login (ou crie sua conta gratuita).
2. Clique no botão **New** (novo repositório).
3. Dê um nome, por exemplo `isaac-roberto`.
4. Deixe marcado como **Public** e clique em **Create repository**.

### Passo 2 — Enviar os arquivos (sem linha de comando)
1. Dentro do repositório recém-criado, clique em **Add file → Upload files**.
2. Arraste os arquivos `index.html` e `og-isaac.jpg` para a área de upload.
3. Escreva uma mensagem simples (ex.: "primeira versão") e clique em **Commit changes**.

### Passo 3 — Ativar o GitHub Pages
1. No repositório, vá em **Settings** (Configurações).
2. No menu lateral, clique em **Pages**.
3. Em **Branch**, selecione `main` e a pasta `/ (root)`, depois clique em **Save**.
4. Aguarde cerca de 1 minuto. O endereço do site vai aparecer no topo dessa página,
   no formato: `https://SEU-USUARIO.github.io/isaac-roberto/`

Pronto — o site está no ar!

---

## Passo 4 — Ativar o preview de compartilhamento (importante)

Abra o `index.html` e troque, nas linhas do topo, todo `https://SEU-DOMINIO.com.br`
pelo endereço real do seu site (o que apareceu no Passo 3). São algumas linhas
marcadas com o comentário "Preview de compartilhamento".

Exemplo: se o seu endereço for `https://mariasilva.github.io/isaac-roberto/`, então:

    <meta property="og:url" content="https://mariasilva.github.io/isaac-roberto/">
    <meta property="og:image" content="https://mariasilva.github.io/isaac-roberto/og-isaac.jpg">

(faça o mesmo nas outras linhas que tiverem `SEU-DOMINIO`).

Depois é só salvar/enviar de novo. Para forçar o WhatsApp/Facebook a mostrarem
a imagem nova, cole o link em https://developers.facebook.com/tools/debug/ e
clique em **Scrape Again**.

---

## Como atualizar depois (de qualquer lugar)

Você pode editar direto pelo site do GitHub:
1. Entre no repositório, clique no arquivo `index.html`.
2. Clique no ícone de lápis (**Edit**).
3. Faça a alteração e clique em **Commit changes**.
4. O site atualiza sozinho em ~1 minuto.

---

## Observações de segurança

- O contato do site é sempre pelo responsável.
- A localização aparece só em nível de cidade (sem endereço, escola ou rotina).
- Qualquer imagem em um site público pode ser salva por qualquer pessoa — escolha
  com cuidado quais fotos ficam na versão pública.
