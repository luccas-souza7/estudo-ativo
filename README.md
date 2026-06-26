# Estudo Ativo no Claude: Assistente de Estudos Interativo

Um prompt que transforma **qualquer conteúdo** (um PDF de aula, um tema da web ou
uma novidade da sua área) em um **widget de estudo interativo**: resumo,
comparativos visuais, flashcards e quiz, gerados de uma vez só, em português.

A ideia é simples: parar de **ler de forma passiva** (que engana, parece que
você aprendeu) e começar a **estudar de forma ativa**, sendo testado e forçado a
recuperar a informação da memória.

> 🆓 **Feito para rodar no plano gratuito do Claude.** Tudo que você precisa está
> incluído no free. As únicas diferenças do plano pago são conforto (cota maior)
> e o atalho dos Projetos, explicado no fim.

---

## 1. O que ele gera

A partir da sua entrada, o Claude devolve um widget com **4 abas**:

- 📋 **Resumo por tópico:** conceitos-chave em cards expansíveis, um por unidade.
- 📊 **Comparativos / Mapa visual:** tabelas lado a lado, grids de categorias e
  etapas numeradas para enxergar relações em vez de decorar listas.
- 🃏 **Flashcards:** 8 a 12 cartões com flip (pergunta na frente, resposta no
  verso) para revisão ativa.
- 🧠 **Quiz:** 6 a 8 questões de múltipla escolha com feedback imediato,
  explicação didática e barra de progresso.

Tudo com identidade visual **azul sobre fundo claro** e compatível com modo escuro.

---

## 2. Onde usar

Este prompt foi feito **para o Claude**, em [claude.ai](https://claude.ai), no
app de **desktop** ou no **celular**. Funciona no **plano gratuito**.

Por quê o Claude e não outra IA: a saída é um **artifact interativo** (HTML que
roda dentro da conversa). Em outras IAs (ChatGPT, Gemini) o widget pode não
renderizar igual, ou os controles de flip/quiz podem não funcionar.

---

## 3. Antes de começar (só na 1ª vez): ative 2 recursos

No plano gratuito esses recursos existem, mas podem vir desligados. Ative uma vez
e fica valendo:

1. **Artifacts**, que é o que faz o widget aparecer.
   Vá em **Configurações → Recursos (Features)**, encontre **Artifacts** e ligue.
   Ao ligar, ative também **"Code execution and file creation"** (vem junto e é
   necessário para o widget rodar).
2. **Busca na web**, usada só no modo "tema/tópico" (item 5B e 5C).
   É um **botão (toggle) na própria caixa de mensagem** ou nas configurações.
   Deixe ligado quando for estudar um tema pesquisado.

> Para estudar **a partir de PDF**, a busca na web nem é necessária: só o PDF e
> os Artifacts.

---

## 4. Como usar: passo a passo

1. Abra o [claude.ai](https://claude.ai) e comece uma **nova conversa**.
2. Abra o arquivo [`PROMPT.md`](./PROMPT.md) e copie **todo o bloco** entre as
   crases (de `# PAPEL` até o fim).
3. **Cole** na conversa.
4. Na **mesma mensagem**, faça uma das três coisas do item 5.
5. Espere o widget aparecer no painel lateral. Estude pelas abas; refaça o quiz
   quantas vezes quiser (isso **não** gasta cota; só a geração gasta).

> No gratuito você cola o prompt a cada nova conversa. Guarde o `PROMPT.md` num
> bloco de notas para colar rápido.

---

## 5. As três formas de usar

**A) Com um PDF de aula ou apostila**

Cole o prompt e **anexe o PDF** na mesma mensagem. O Claude lê o material,
identifica as unidades sozinho e monta o widget.

```
[prompt colado] + [anexar o PDF]
```

**B) Com um tema específico** (precisa da busca na web ligada)

```
[prompt colado]

Quero estudar: "Fundamentos de React Hooks"
```

**C) Com um lançamento ou novidade** (precisa da busca na web ligada)

```
[prompt colado]

Quero estudar: "O que é o Vite e como ele se compara ao Webpack"
```

---

## 6. Dicas para não estourar a cota do plano gratuito

O gratuito reseta o uso a cada ~5 horas, e **gerar o widget é a parte que mais
consome**. Estas práticas fazem a cota render:

- **Seja específico.** "CSS Grid vs Flexbox" rende muito mais que "me ensine CSS",
  e gasta menos, porque o Claude não desperdiça turnos pedindo foco.
- **PDF longo? Divida.** Acima de ~30 a 40 páginas, mande por partes (ex.:
  "unidades 1 a 3" numa conversa, "4 a 6" em outra). O prompt já avisa quando
  precisa cortar.
- **Peça ajustes pequenos, não recomeços.** "Troque a cor para azul-escuro" faz o
  Claude editar só aquele trecho. "Refaz tudo" regenera o widget inteiro e gasta
  o dobro.
- **Revisar não gasta.** Clicar nas abas, virar flashcard e refazer o quiz é
  local; só a **geração** consome mensagem.
- **Bateu o limite no meio?** Espere a janela resetar e peça "continue de onde
  parou" na mesma conversa.

---

## 7. Por que isso funciona

A diferença entre **ler** e **ser testado** é grande e bem documentada. Estudos
clássicos de psicologia cognitiva mostram que recuperar a informação da memória,
via flashcards e quizzes, fixa muito mais do que reler o material, fenômeno
conhecido como **efeito de teste** (Roediger e Karpicke, 2006).

Na prática, o prompt automatiza a parte chata (pesquisar, organizar, resumir e
escrever as perguntas) e deixa você com a parte que ensina de fato: responder,
errar e corrigir.

---

## 8. Limitações

- **PDFs escaneados (imagem)** podem não ser lidos; prefira arquivos com texto
  selecionável.
- **Materiais muito longos** são cobertos por partes; o prompt avisa quais
  unidades ficaram de fora e oferece um segundo widget.
- **Temas amplos demais** ("me ensine programação") geram resultados rasos; seja
  específico.
- O widget roda **dentro do Claude**; não é um arquivo pronto para abrir em
  qualquer navegador sem ajustes.

---

## 9. Personalização

- **Cor:** a identidade é azul por padrão. Para trocar, edite o bloco
  `IDENTIDADE VISUAL` no `PROMPT.md`.
- **Quantidade:** ajuste os intervalos de flashcards (8 a 12) e quiz (6 a 8).
- **Idioma:** fixado em português brasileiro na regra 5.

---

## 10. Opcional: plano pago (Projetos)

Se um dia você assinar, crie um **Projeto** e salve o `PROMPT.md` como instrução
fixa. Aí não precisa colar o prompt toda vez: é só abrir o projeto e mandar o
tema ou o PDF. Útil se você usar muito; **não** é necessário para nada acima.

---

## 11. Licença

Distribuído sob a **Licença MIT**, veja [`LICENSE`](./LICENSE). Pode usar,
copiar, modificar e adaptar à vontade. Uma menção ao autor é sempre bem-vinda.

---

## 12. Contato

- 💻 GitHub: [github.com/luccas-souza7](https://github.com/luccas-souza7)
- 🔗 LinkedIn: [linkedin.com/in/luccas-souza7](https://www.linkedin.com/in/luccas-souza7/)
- 📧 E-mail: luccasnsouza1@gmail.com

Dúvida, sugestão ou melhoria? Abra uma *issue* ou me chame.
