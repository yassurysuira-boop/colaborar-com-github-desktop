<!-- step-7-rebase-check -->

## Passo 7: Mantenha sua branch atualizada (Update from main / Rebase)

Enquanto você revisava o seu trabalho, **um colega enviou uma alteração para a `main`** (adicionou um arquivo de novidades da equipe). Agora a sua branch está **desatualizada** em relação à `main`. Antes de mesclar, é uma boa prática trazer essas atualizações para a sua branch — isso evita surpresas e reduz conflitos no momento do merge. 🔄

### 📖 Teoria: Por que e como atualizar a branch?

Quando a `main` avança e a sua branch não, elas **divergem**. O GitHub Desktop oferece duas formas de colocar sua branch em dia:

- **Update from main** (*Merge*): traz a `main` para dentro da sua branch criando um **commit de merge**. É simples, seguro e preserva o histórico exatamente como aconteceu.

- **Rebase current branch** (*Rebase*): **reaplica os seus commits por cima** da `main` atualizada, como se você tivesse começado a trabalhar agora. O histórico fica **linear** e mais limpo, sem commits de merge.

```diff
  Merge (Update from main):          Rebase:
  main:  A───B───C                   main:  A───B───C
              \   \                                  \
  branch:      D───M (merge)         branch:          D'──E'
```

> [!TIP]
> Regra prática da equipe: use **Update from main** quando estiver em dúvida (é o mais seguro). Use **Rebase** quando quiser um histórico linear e a branch ainda for **só sua**.

> [!IMPORTANT]
> **Nunca faça rebase de uma branch compartilhada** que outras pessoas já estão usando. O rebase reescreve o histórico (os commits ganham novos identificadores), o que bagunça o trabalho de quem baixou a branch antiga.

### ⌨️ Atividade: Atualize a sua branch pela `main`

1. No GitHub Desktop, clique em **Fetch origin** para baixar as últimas mudanças do servidor.

   <br/>

   > 🪧 **Observação importante**: o **Fetch** baixa o commit novo para a `main`, mas ele **ainda não aparece** no histórico da sua branch `add-project-files` — e isso é esperado! O commit está na `main`, não na sua branch. É justamente isso que vamos resolver agora. (Se quiser confirmar, selecione a branch **`main`** em **Current Branch** e veja o commit `Novidades da equipe` na aba **History**; depois volte para a `add-project-files`.)

2. Confirme que a branch `add-project-files` está selecionada em **Current Branch**.

3. Escolha **uma** das opções no menu **Branch** do topo:

   - **Branch → Update from main** — traz a `main` para a sua branch criando um **commit de merge**, **ou**
   - **Branch → Rebase current branch...** e selecione **`main`** — reaplica seus commits por cima da `main`.

   <br/>

   > 🪧 **Observação**: como o arquivo enviado pelo colega é **diferente** dos seus, não haverá conflito — a sua branch apenas incorpora o commit novo da `main`. (Resolver conflitos de verdade vem em um passo mais adiante. 😉)

4. **Agora sim**: abra a aba **History** com a `add-project-files` selecionada e confirme que o commit `Novidades da equipe` passou a fazer parte da sua branch. ✅

5. Envie a atualização: se você fez **Update from main**, basta um **Push origin** normal. Se fez **rebase**, o Desktop pode pedir um **Push** com a opção **force-with-lease** (porque o histórico foi reescrito) — confirme.

> [!NOTE]
> O **Update from main** cria um commit de merge com uma mensagem automática (ex.: `Merge branch 'main'...`). Não se preocupe: o hook de commits que você ativou no passo 3 **ignora** commits de merge e de revert, então essa operação não será bloqueada.

### ✅ Marque este passo como concluído

1. Vá ao início deste comentário com as instruções deste passo.
2. Clique no menu **`···`** no canto superior direito do comentário e escolha **Edit**.
3. Marque a caixa trocando `[ ]` por `[x]` e clique em **Update comment**. Obs: deve ser exatamente `[x]`.

- [ ] Atualizei minha branch pela `main` usando **Update from main** ou **Rebase current branch**.

A Mona verá sua atualização e compartilhará o próximo passo. 🚀

<details>
<summary>Com dificuldades? 🤷</summary><br/>

- Clique em **Fetch origin** primeiro; sem isso o Desktop não sabe que a `main` mudou.
- Após um **rebase**, é normal o Desktop pedir um push com **force-with-lease**. Isso é esperado porque o histórico da sua branch foi reescrito.
- Em caso de conflito inesperado, o Desktop avisa e permite resolvê-lo antes de continuar.

</details>
