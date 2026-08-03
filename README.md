# 💜 Finanças da Thay

App de controle financeiro pessoal feito para o **celular**. Funciona no navegador,
pode ser instalado na tela inicial como um aplicativo de verdade e **funciona sem internet**.

Todos os dados ficam salvos **automaticamente no próprio aparelho** — nada vai para a nuvem,
nada precisa de login, nada tem custo.

---

## ✨ O que ele faz

| Recurso | Descrição |
|---|---|
| 💳 **Crédito, Pix, débito e dinheiro** | Lançamento em 4 toques: valor → forma de pagamento → categoria → salvar |
| 🏦 **3 bancos** | Banco do Brasil, Nubank e Inter, mais a carteira de dinheiro em espécie |
| 🧾 **2 cartões de crédito** | Cartão BB e Cartão Nubank, cada um com seu dia de fechamento e vencimento |
| ➗ **Compras parceladas** | Divide automaticamente nas faturas certas, sem perder centavo |
| 📅 **Faturas** | Mostra a fatura aberta, o que ainda vai vencer e o limite usado |
| 🤝 **Empréstimos** | Dinheiro que ela emprestou e dinheiro que ela pegou com amigos e parentes, com pagamentos parciais |
| 🎯 **Orçamento por categoria** | Define um limite mensal e avisa quando está estourando |
| 📊 **Relatórios** | Gasto por categoria, por forma de pagamento, por banco e evolução de 6 meses |
| 🔁 **Contas fixas** | Marca uma despesa como "repetir todo mês" e ela se lança sozinha |
| 💾 **Backup** | Exporta tudo em `.json` (backup completo) ou `.csv` (para abrir no Excel) |
| 🌙 **Tema claro e escuro** | Toque em *Ajustes* para trocar |

---

## 📲 Como colocar no celular (o jeito mais fácil)

### 1. Subir para o GitHub

Se você já tem o Git instalado no computador:

```bash
git clone https://github.com/SEU-USUARIO/financas-thay.git   # ou crie o repositório vazio no site
# copie os arquivos deste projeto para dentro da pasta
git add .
git commit -m "primeira versão do app"
git push
```

Se preferir **sem comando nenhum**:

1. Acesse [github.com/new](https://github.com/new) e crie um repositório chamado `financas-thay` (deixe **Public**).
2. Na página do repositório, clique em **Add file → Upload files**.
3. Arraste **todos os arquivos e pastas** deste projeto (`index.html`, `manifest.json`, `sw.js`, e as pastas `css`, `js`, `icons`).
4. Clique em **Commit changes**.

### 2. Ligar o GitHub Pages

1. No repositório, vá em **Settings → Pages**.
2. Em *Source*, escolha **Deploy from a branch**.
3. Em *Branch*, escolha **main** e a pasta **/ (root)**. Clique em **Save**.
4. Espere ~1 minuto. O endereço aparece no topo da página:

```
https://SEU-USUARIO.github.io/financas-thay/
```

### 3. Instalar no celular

Abra esse endereço no celular e:

- **Android (Chrome):** menu ⋮ → **Instalar aplicativo** / *Adicionar à tela inicial*
- **iPhone (Safari):** botão compartilhar → **Adicionar à Tela de Início**

Pronto. O ícone fica junto dos outros apps e abre em tela cheia, sem barra de navegador.

> 💡 Dá para usar direto no navegador também, sem instalar. Instalar só deixa mais rápido e permite usar sem internet.

---

## 🚀 Como usar no dia a dia

1. **Toque no botão roxo `+`** no meio da barra de baixo.
2. **Digite o valor** no teclado grande (não precisa de vírgula: `1500` vira `R$ 15,00`).
3. **Escolha como pagou**: Crédito, Pix, Dinheiro ou Débito.
   - No crédito, escolha o cartão e o número de parcelas — o app já diz em qual fatura vai cair.
   - No Pix/débito, escolha o banco.
4. **Toque na categoria** e em **Salvar**. Pronto, já está salvo.

Para **receitas** (salário, venda, pix recebido), é o mesmo caminho: toque em `+` e mude para **Receita** no topo.

Para **corrigir ou apagar** um lançamento, é só tocar nele na lista da tela inicial.

### Empréstimos

Na aba **Empréstimos** → *Novo empréstimo*:

- **Eu emprestei** → dinheiro que saiu e que alguém deve devolver.
- **Eu peguei** → dinheiro que entrou e que ela precisa devolver.

Sempre que receber (ou pagar) uma parte, toque em *Recebi um valor* / *Paguei um valor*.
A barrinha mostra quanto já foi quitado e o app avisa quando a data combinada passou.

### Primeira configuração (leva 2 minutos)

Vá em **Relatórios → ⚙️ Ajustes** e preencha:

- O **saldo inicial** de cada banco (quanto tem hoje na conta).
- O **dia de fechamento e vencimento** de cada cartão (está na fatura ou no app do banco).
- O **limite** de cada cartão (opcional, serve para a barrinha de limite usado).
- Os **orçamentos** por categoria (opcional).

---

## 💾 Sobre os dados e o backup

Os dados ficam no armazenamento local do navegador do celular (`localStorage`), salvos
automaticamente a cada toque. Isso significa:

- ✅ Ninguém além dela vê os dados. Nem eu, nem o GitHub.
- ✅ Funciona sem internet.
- ⚠️ Se ela **limpar os dados do navegador** ou trocar de celular, os dados vão junto.

Por isso: **uma vez por mês, entre em Ajustes e toque em "Baixar backup (.json)"**.
Para restaurar em outro aparelho, é só abrir o app lá e usar *Restaurar backup*.

---

## 🗂 Estrutura do projeto

```
financas-thay/
├── index.html         # a tela do app
├── manifest.json      # faz virar aplicativo instalável
├── sw.js              # service worker: faz funcionar offline
├── css/styles.css     # visual
├── js/app.js          # toda a lógica (dados, faturas, relatórios)
└── icons/             # ícones do app
```

Não usa nenhuma biblioteca externa, não precisa de `npm install`, não precisa de build.
É HTML, CSS e JavaScript puro — abre direto.

### Rodar no computador para testar

```bash
python3 -m http.server 8000
# depois abra http://localhost:8000
```

---

## 🔧 Personalizar

- **Trocar bancos ou cartões:** edite a função `defaults()` no começo de `js/app.js`.
- **Mudar cores:** as variáveis de cor estão no topo de `css/styles.css` (`:root`).
- **Adicionar categorias:** direto pelo app, em *Ajustes → Categorias*.

---

Feito com 💜 para a Thaynara.
