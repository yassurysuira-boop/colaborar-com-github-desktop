<!-- step-3-commit-policy-check -->

## Passo 3: Política de commits (Conventional Commits)

No passo anterior você fez seu primeiro commit e pedimos para não se preocupar com a política de commits. Chegou a hora! 🎯 Mensagens de commit padronizadas deixam o histórico do projeto legível, facilitam a geração de changelogs e ajudam toda a equipe a entender **o que** mudou e **por quê**.

### 📖 Teoria: O que é Conventional Commits?

Nossa organização adota o padrão **[Conventional Commits](https://www.conventionalcommits.org/pt-br/)**. Toda mensagem de commit deve seguir o formato:

```txt
<tipo>(<escopo opcional>): <descrição>
```

- **tipo**: a natureza da mudança (obrigatório).
- **escopo**: a parte do projeto afetada, entre parênteses (opcional). Ex.: `(auth)`, `(login)`.
- **descrição**: um resumo curto, no imperativo, em letra minúscula.

Os **tipos válidos** na nossa política são:

| Tipo | Quando usar |
| :--- | :--- |
| `feat` | Uma nova funcionalidade. |
| `fix` | Correção de um bug. |
| `docs` | Alterações apenas na documentação. |
| `style` | Formatação, espaços, ponto e vírgula (sem mudar lógica). |
| `refactor` | Refatoração que não corrige bug nem adiciona funcionalidade. |
| `test` | Adicionar ou atualizar testes. |
| `chore` | Tarefas rotineiras (dependências, ferramentas de build). |
| `build` | Mudanças no sistema de build ou dependências externas. |
| `ci` | Mudanças em configuração ou scripts de CI. |
| `perf` | Melhorias de desempenho. |
| `revert` | Reverter um commit anterior. |

**Exemplos válidos:**

```txt
feat(login): adiciona validação do campo nome
fix: corrige cálculo de pontuação
docs: atualiza instruções de instalação
chore: adiciona arquivo de configuração do editor
```

### 🔒 Como a política é garantida: o hook `commit-msg`

Este repositório já inclui um **hook de validação** em [`.githooks/commit-msg`](../../colaborar-com-github-desktop/blob/main/.githooks/commit-msg). Ele inspeciona cada mensagem de commit e **rejeita** as que estão fora do padrão.

Mas o Git **não** usa essa pasta automaticamente — por segurança, hooks ficam desativados até você habilitá-los. Você precisa fazer isso **uma vez** em cada cópia clonada.

> [!IMPORTANT]
> Este é o único momento do exercício em que usamos a linha de comando. É um passo de configuração rápido e feito uma única vez.

1. Abra um terminal **na pasta do repositório**. No GitHub Desktop, vá em **Repository → Open in Command Prompt** (Windows) ou **Open in Terminal**.

2. Aponte o Git para a pasta de hooks do projeto e garanta que o hook seja executável, mas primeiro vamos verificar se o git está corretamente instalado, digite no terminal:

   ```bash
   git --version
   ```

3. Se aparecer a versão do Git, está tudo certo para rodar:

   ```bash
   git config core.hooksPath .githooks
   ```

4. Para conferir se deu certo, use:

   ```bash
   git config --get core.hooksPath
   ```

Se retornar .githooks, funcionou.

5. Pronto! A partir de agora, qualquer commit feito neste repositório — pela linha de comando **ou** pelo GitHub Desktop — será validado pelo hook.

### ⌨️ Atividade: Faça um commit seguindo a política

1. No seu editor, faça uma pequena alteração na branch `add-project-files` — por exemplo, adicione uma linha ao `PROJECT.md`.

2. No GitHub Desktop, escreva o **Summary** deixando de seguir o padrão Conventional Commits para ver o erro, por exemplo:

   ```txt
   adiciona seção de objetivos ao PROJECT.md
   ```
> [!NOTE]
> Se a mensagem estiver fora do padrão, o hook bloqueia o commit e mostra o formato esperado. Ajuste o **Summary** e tente novamente.
   
3. Agora vamos arrumar a mensagem de commit para subir a alteração:

   ```txt
   docs: adiciona seção de objetivos ao PROJECT.md
   ```

> [!TIP]
> Precisa explicar melhor a mudança? Escreva um título curto no **Summary** e detalhes no campo **Description** logo abaixo.

4. Clique em **Commit to add-project-files** e depois em **Push origin**.

### ✅ Marque este passo como concluído

Como a ativação do hook acontece no seu computador, confirme você mesmo:

1. Depois de ter seguido todos os passos acima marque a checkbox abaixo.
   
Ou então,

1. Vá ao início deste comentário com as instruções deste passo.
2. Clique no menu **`···`** no canto superior direito do comentário e escolha **Edit**.
3. Marque a caixa trocando `[ ]` por `[x]` e clique em **Update comment**. Obs: não deixe espaços, deve ser exatamente `[x]`.

- [ ] Ativei o hook de commits com `git config core.hooksPath .githooks` e fiz um commit seguindo o padrão Conventional Commits.

A Mona verá sua atualização e compartilhará o próximo passo. 🚀

<details>
<summary>Com dificuldades? 🤷</summary><br/>

- O formato é `<tipo>: <descrição>` — não esqueça os **dois-pontos e o espaço** após o tipo.
- Use somente os tipos da tabela acima; qualquer outro será rejeitado pelo hook.
- Rode o comando de ativação **dentro da pasta do repositório**, senão o Git não encontra a pasta `.githooks`.
- No Windows, se `chmod` não for reconhecido, use o terminal **Git Bash** (vem com o Git) ou apenas rode a primeira parte: `git config core.hooksPath .githooks`.

</details>
