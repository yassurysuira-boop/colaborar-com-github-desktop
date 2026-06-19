<!-- step-9-undo-check -->

## Passo 9: Desfazer com segurança (Undo, Discard e Revert)

Errar faz parte! 😅 O importante é saber **desfazer com segurança**, sem perder trabalho nem bagunçar o histórico dos colegas. O GitHub Desktop oferece a ferramenta certa para cada situação, dependendo de **que estágio** está a alteração que você quer desfazer.

### 📖 Teoria: a ferramenta certa para cada estágio

| Situação | Ferramenta | O que faz |
| :--- | :--- | :--- |
| Alteração **ainda não commitada** | **Discard changes** | Descarta as edições não salvas no histórico, voltando o arquivo ao último commit. |
| Commit feito mas **ainda não enviado** (push) | **Undo** | Desfaz o último commit e devolve as mudanças para a área de alterações, para você ajustar. |
| Commit **já enviado / mesclado** | **Revert** | Cria um **novo commit** que desfaz as mudanças de um commit anterior, sem reescrever o histórico. |

- **Discard changes**: na aba **Changes**, clique com o botão direito no arquivo → **Discard changes**.
- **Undo**: logo após um commit, use o botão **Undo** no canto inferior esquerdo (você já viu ele no passo do primeiro commit!).
- **Revert**: na aba **History**, clique com o botão direito no commit → **Revert changes in commit**.

> [!TIP]
> No GitHub.com, um pull request já mesclado também pode ser desfeito: abra o pull request e clique em **Revert**, que cria automaticamente um novo pull request com as mudanças invertidas.

### ⌨️ Atividade: Pratique o Revert

Vamos reverter, com segurança, um commit que já está na `main`.

1. No GitHub Desktop, selecione a branch **`main`** e clique em **Fetch origin** / **Pull origin** para garantir que está atualizada.

2. Abra a aba **History**.

3. Escolha um commit que você queira desfazer (por exemplo, uma alteração de teste), clique com o **botão direito** sobre ele e selecione **Revert changes in commit**.

   <br/>

   > 🪧 **Observação**: o Desktop cria um **novo commit** chamado algo como `Revert "..."`. O histórico original é preservado — você só adicionou um commit que desfaz o anterior.

4. Clique em **Push origin** para enviar o revert.

> [!NOTE]
> Não quer alterar a `main` agora? Sem problema: você também pode apenas **praticar o Discard changes** — faça uma edição qualquer em um arquivo, e descarte-a pelo botão direito → **Discard changes**. O importante é entender quando usar cada ferramenta.

### ✅ Marque este passo como concluído

1. Vá ao início deste comentário com as instruções deste passo.
2. Clique no menu **`···`** no canto superior direito do comentário e escolha **Edit**.
3. Marque a caixa trocando `[ ]` por `[x]` e clique em **Update comment**. Obs: deve ser exatamente `[x]`.

- [ ] Entendi a diferença entre **Discard**, **Undo** e **Revert** e pratiquei um deles.

A Mona verá sua atualização e compartilhará o próximo passo. 🚀

<details>
<summary>Com dificuldades? 🤷</summary><br/>

- Se a aba **History** estiver vazia, confirme que você selecionou a branch certa e deu **Fetch/Pull**.
- Lembre-se: **Undo** some depois que você faz o push. Para mudanças já enviadas, a opção correta é **Revert**.
- O **Revert** não apaga o commit original — ele adiciona um commit novo que desfaz aquelas alterações.

</details>
