# 🤔 Bullying ou Brincadeira?

Jogo educativo interativo, em português, que ajuda crianças e adolescentes a diferenciarem **uma brincadeira saudável** de **bullying e cyberbullying**. A pessoa lê situações do dia a dia escolar e decide, em cada uma, se é *brincadeira* 💚 ou *bullying* 💔 — recebendo, em seguida, uma explicação em linguagem acessível.

Feito como material de apoio para ações de conscientização sobre bullying (turmas do 7º ano / ensino fundamental).

---

## ✨ Destaques

- **10 situações** reais de convívio escolar (recreio, aniversário, almoço, sala de aula, grupo do celular, piscina…).
- **Feedback explicado** a cada resposta: mostra a classificação correta e o *porquê*, sempre reforçando empatia e respeito.
- **"3 perguntas mágicas"** — uma dica opcional que ensina o critério para diferenciar brincadeira de bullying.
- **Cenários ilustrados no desktop** — cada situação ganha uma cena em SVG, desenhada na hora, exibida abaixo da pergunta (o celular mantém o layout compacto).
- **Telas finais** sobre direitos da criança, a importância de pedir ajuda e uma mensagem de encerramento.
- **100% self-contained** — um único arquivo HTML, sem build, sem dependências instaláveis e sem imagens externas.
- **Responsivo e acessível** — funciona bem no celular e respeita `prefers-reduced-motion`.

---

## 🎮 Como funciona

1. **Início** — tela de boas-vindas com o botão *Começar*.
2. **Rodada** — para cada uma das 10 situações, a pessoa escolhe **Brincadeira** ou **Bullying**.
3. **Revelação** — aparece a resposta certa com uma explicação curta e acolhedora.
4. **Encerramento** — três telas finais: *Você tem direitos!* → *Peça ajuda. Sempre.* → mensagem final, com opção de **jogar de novo**.

Uma barra de progresso (bolinhas) no topo mostra em que ponto do jogo a pessoa está.

---

## 🖼️ Cenários no desktop

Em telas com largura **≥ 820px**, cada pergunta exibe uma **cena ilustrada** logo abaixo do texto da situação, antes dos botões de resposta.

- As ilustrações são **SVG geradas por um pequeno kit de componentes** (`kid()`, `face()`, `hair()`, `bubble()` e cenários como sala de aula, mesa do almoço, piscina e celular), tudo embutido no próprio arquivo.
- **Nenhuma imagem externa** é carregada — ideal para funcionar offline e em qualquer hospedagem estática.
- No celular, o cenário fica oculto para manter a leitura leve e rápida.

---

## 🚀 Como rodar localmente

Por ser um arquivo estático, basta abrir no navegador:

```bash
git clone https://github.com/seu-usuario/bullying-ou-brincadeira.git
cd bullying-ou-brincadeira
# abra o index.html no navegador (duplo clique já funciona)
```

Se quiser servir via HTTP local (recomendado para testar como em produção):

```bash
# Python 3
python3 -m http.server 8000
# depois acesse http://localhost:8000
```

---

## 🌐 Como publicar no GitHub Pages

1. Renomeie o arquivo do jogo para **`index.html`** (se ainda não estiver com esse nome).
2. Faça o commit e o push para o seu repositório.
3. Em **Settings → Pages**, selecione a branch (ex.: `main`) e a pasta `/root`.
4. Aguarde alguns instantes e acesse o endereço gerado.

---

## 🛠️ Tecnologias

- **HTML5** semântico
- **CSS3** (Flexbox, Grid, media queries, animações, `prefers-reduced-motion`)
- **JavaScript** puro (Vanilla JS) — sem frameworks nem dependências
- **SVG** gerado dinamicamente para os cenários
- Tipografia: [Fredoka](https://fonts.google.com/specimen/Fredoka) + [Nunito](https://fonts.google.com/specimen/Nunito) via Google Fonts

---

## 📁 Estrutura

```
bullying-ou-brincadeira/
├── index.html   # o jogo inteiro (HTML + CSS + JS + cenários SVG)
└── README.md
```

Tudo vive em um único arquivo, então é fácil de ler, versionar e hospedar.

---

## ✏️ Personalização

### Editar ou adicionar situações

As situações ficam no array `situations`, dentro do `<script>`:

```js
const situations = [
  {
    emoji: "😄",
    text: "Ana e Bia fazem cócegas uma na outra e as duas caem na risada.",
    answer: "brinc", // "brinc" (brincadeira) ou "bully" (bullying)
    reason: "As duas riem juntas e ficam felizes. Brincadeira é quando todo mundo se diverte."
  },
  // ...adicione novas situações aqui
];
```

Ao adicionar uma nova situação, inclua também um cenário correspondente no array `scenes` (ou deixe sem — o jogo funciona normalmente exibindo só o emoji).

### Trocar as cores

A paleta está centralizada nas variáveis CSS em `:root` (`--brinc`, `--bully`, `--sky`, `--sun`, etc.), no início do `<style>`.

---

## ♿ Acessibilidade

- Região de conteúdo com `aria-live="polite"` para leitores de tela.
- Foco visível nos botões (`:focus-visible`).
- Animações desativadas para quem usa `prefers-reduced-motion`.
- Contraste e tamanhos de fonte pensados para leitura infantil.

---

## 📚 Contexto educativo

O jogo reforça, de forma lúdica, que **respeitar o outro é um direito de todos**. No Brasil, o bullying e o cyberbullying não são apenas atitudes erradas — desde 2024 são **crimes** (Lei nº 14.811/2024, que inclui o art. 146-A no Código Penal), além de existir a Lei nº 13.185/2015, que institui o Programa de Combate à Intimidação Sistemática.

A mensagem central é sempre a mesma: **pedir ajuda não é ser dedo-duro — é coragem e cuidado.** Em casos de violação de direitos, o **Disque 100** (Direitos Humanos) recebe denúncias gratuitamente e de forma anônima.

---

## 🤝 Contribuindo

Sugestões de novas situações, melhorias de acessibilidade e traduções são bem-vindas! Abra uma *issue* ou um *pull request*.

---

## 📄 Licença

Distribuído sob a licença **MIT** — sinta-se à vontade para usar, adaptar e compartilhar em escolas e projetos educativos.

---