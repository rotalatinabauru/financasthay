# 💜 Finanças da Thay

App de controle financeiro pessoal feito para o **celular**. Abre no navegador, instala na
tela inicial como um aplicativo de verdade e **funciona sem internet**.

Os dados ficam salvos **automaticamente no próprio aparelho**. Sem login, sem nuvem, sem custo.

---

## 📁 Os arquivos

```
index.html               ← o app inteiro (HTML + CSS + JavaScript num arquivo só)
manifest.json            ← faz virar aplicativo instalável
sw.js                    ← faz funcionar offline
icon-192.png             ← ícone
icon-512.png             ← ícone
icon-maskable-512.png    ← ícone
```

Nenhuma pasta, nenhuma biblioteca, nenhum `npm install`, nenhum build.
**O `index.html` sozinho já roda o app completo** — os outros arquivos só servem para instalar
no celular e funcionar offline.

---

## 📲 Colocar no ar (GitHub Pages)

1. No repositório, clique em **Add file → Upload files** (num repositório vazio, o link é
   **"uploading an existing file"** dentro da caixa azul).
2. Arraste **os 6 arquivos acima**, soltos — não a pasta que os contém. O `index.html` precisa
   ficar na raiz do repositório.
3. Clique em **Commit changes**.
4. Vá em **Settings → Pages** → *Source*: `Deploy from a branch` → *Branch*: `main` e `/ (root)`
   → **Save**.
5. Em um ou dois minutos o endereço aparece no topo dessa página.

### Instalar no celular

Abra o endereço **no Safari** (iPhone) ou no Chrome (Android). O próprio app mostra uma
barrinha **"Instalar na tela inicial"** com o passo a passo ilustrado. Se ela dispensar,
o guia continua disponível em **Ajustes → Como instalar no celular**.

Manualmente:

- **iPhone (Safari):** botão compartilhar → **Adicionar à Tela de Início** → **Adicionar**
- **Android (Chrome):** menu ⋮ → **Instalar aplicativo**

O ícone da tela inicial já vem **embutido dentro do `index.html`** — mesmo subindo só esse
arquivo, a logo aparece certinha no celular.

---

## 🚀 Como usar

Na primeira vez o app abre uma **configuração rápida**: nome, quanto tem em cada banco e as
datas de fechamento e vencimento dos dois cartões. Leva menos de um minuto e dá para refazer
depois pela engrenagem ⚙️ no canto superior direito.

**Para lançar um gasto:** toque no botão roxo `+` → digite o valor no teclado grande
(`1500` vira `R$ 15,00`) → escolha Crédito, Pix, Dinheiro ou Débito → toque na categoria →
**Salvar**.

- No **crédito**, escolha o cartão e em quantas vezes; o app mostra na hora em qual fatura vai
  cair e quanto fica cada parcela.
- No **Pix ou débito**, escolha o banco.
- Para **receitas**, mude para *Receita* no topo da tela de lançamento.
- Para **corrigir ou apagar**, toque no lançamento na lista da tela inicial.
- Os botões de **Lançar rápido** na tela inicial aprendem sozinhos os gastos mais frequentes.

### Empréstimos

Aba **Empréstimos** → *Novo empréstimo*:

- **Eu emprestei** → dinheiro que saiu e alguém precisa devolver.
- **Eu peguei** → dinheiro que entrou e ela precisa devolver.

A cada valor recebido ou pago, toque em *＋ Recebi* / *＋ Paguei*. A barrinha mostra quanto já
foi quitado e o app avisa quando a data combinada passou.

---

## ✨ O que tem dentro

| | |
|---|---|
| 💳 **Formas de pagamento** | Crédito, Pix, débito e dinheiro |
| 🏦 **Bancos** | Banco do Brasil, Nubank, Inter e carteira de dinheiro, cada um com saldo próprio |
| 🧾 **Cartões** | Cartão BB e Cartão Nubank, com fechamento, vencimento e limite |
| ➗ **Parcelamento** | Até 24x, distribuído nas faturas certas, sem perder centavo no arredondamento |
| 📅 **Faturas** | Fatura aberta, próximas faturas, histórico do que já foi pago |
| 🤝 **Empréstimos** | Feitos e tomados, com pagamentos parciais e aviso de atraso |
| 🎯 **Orçamento** | Limite mensal por categoria, com alerta ao se aproximar |
| 📊 **Relatórios** | Por categoria, forma de pagamento, banco, maiores gastos e 6 meses de evolução |
| 🔁 **Contas fixas** | Marque "repetir todo mês" e o lançamento se cria sozinho |
| 🔍 **Busca** | Encontre qualquer lançamento pelo nome ou categoria |
| 💾 **Backup** | Exporta `.json` (backup completo) e `.csv` (abre no Excel) |
| 🌙 **Temas** | Escuro e claro |

---

## 💾 Sobre os dados

Ficam no armazenamento local do navegador do celular (`localStorage`), gravados a cada toque.

- ✅ Ninguém mais vê. Nem o GitHub, nem eu.
- ✅ Funciona sem internet.
- ⚠️ Se limpar os dados do navegador ou trocar de celular, os dados vão junto.

### ⚠️ Importante no iPhone: Safari e app instalado são dois lugares

No iOS, o Safari e o app adicionado à tela inicial guardam dados em **áreas separadas**. Lançar
algo no Safari não faz aparecer no app instalado, e vice-versa. **Escolha um e use sempre o
mesmo** — de preferência o app instalado, porque o Safari apaga o armazenamento de sites que
ficam mais de 7 dias sem serem abertos (regra do próprio iOS), enquanto o app instalado não sofre
com isso.

Para levar os dados de um para o outro: **Ajustes → 🔄 Transferir dados**. No lugar que tem os
lançamentos, toque em *Copiar meus dados*; no outro, cole no campo e toque em *Trazer os dados*
(ou *Juntar*, se os dois lados tiverem coisas diferentes).

### Proteções contra perda

- O app guarda **cópias automáticas dos últimos 3 dias** no aparelho — veja em
  *Ajustes → 🛟 Recuperar dados*.
- Antes de qualquer restauração, o estado atual também é salvo.
- Se o arquivo de dados ficar ilegível, o app **não sobrescreve** — guarda o original para resgate.
- A cada 20 dias sem backup, a tela inicial lembra de fazer um.

Mesmo assim: **uma vez por mês, Ajustes → Baixar backup (.json)** e guarde no iCloud Drive.

---

## 🔧 Personalizar

Tudo está dentro do `index.html`:

- **Cores:** bloco `:root` no começo do `<style>`.
- **Bancos, cartões e categorias iniciais:** função `defaults()` no `<script>`.
- **Categorias novas:** direto no app, em *Ajustes → Categorias*.

Para testar no computador: `python3 -m http.server 8000` e abra `http://localhost:8000`.
(Também funciona abrindo o `index.html` com dois cliques — só o modo offline exige um servidor.)

---

Feito com 💜 para a Thaynara.
