## Revisão & Guia de Consulta Rápida

_Parabéns, você concluiu o fluxo de colaboração do dia a dia no GitHub! 🎉_

<img src="https://octodex.github.com/images/jetpacktocat.png" alt="comemorar" width=160 align=right>

Guarde este comentário como uma **cola de consulta**. Sempre que esquecer onde clicar ou qual comando usar, volte aqui. 👇

### 🧭 O que cada passo faz e como executar

| # | Passo | Como fazer (GitHub Desktop, salvo indicação) |
| :--- | :--- | :--- |
| 1 | **Clonar** | `File → Clone repository...` → aba **GitHub.com** → escolha o repo → **Clone**. |
| 2 | **Branch + commit + push** | `Current Branch → New Branch` (ex.: `add-project-files`) → edite arquivos → escreva o **Summary** → **Commit** → **Publish branch**. |
| 3 | **Política de commits** | Ative o hook (1x por clone): `git config core.hooksPath .githooks`. Formato: `<tipo>(<escopo>): <descrição>`. |
| 4 | **.gitignore** | Crie um arquivo `.gitignore` na **raiz** listando o que ignorar (`node_modules/`, `.env`, `*.log`...). Commite e dê push. |
| 5 | **Abrir Pull Request** | `Branch → Create Pull Request` → no navegador confirme **base: `main` ⬅ compare: sua branch** → título + descrição → **Create pull request**. |
| 6 | **Revisar** | No PR (GitHub.com) → aba **Files changed** → leia o diff → **Submit review** → **Comment**. |
| 7 | **Atualizar a branch** | **Fetch origin** → `Branch → Update from main` (merge) **ou** `Branch → Rebase current branch...` (histórico linear). Depois **Push**. |
| 8 | **Merge do PR** | No PR → **Merge pull request** → **Confirm merge** → (opcional) **Delete branch**. Depois, na `main`: **Fetch** + **Pull origin**. |
| 9 | **Desfazer** | **Discard** (não commitado) · **Undo** (commit ainda sem push) · **Revert** (commit/PR já enviado). |
| 10 | **Issues** | Aba **Issues** → **New issue** → título claro + descrição (use os templates quando fizerem sentido). |
| 11 | **Conflito de merge** | Abra o PR → **Resolve conflicts** → remova os marcadores, deixe **uma** versão → **Mark as resolved** → **Commit merge** → **Merge**. |

### 📌 Mini-referências

<details>
<summary><b>Tipos de commit (Conventional Commits)</b></summary><br/>

| Tipo | Uso |
| :--- | :--- |
| `feat` | Nova funcionalidade |
| `fix` | Correção de bug |
| `docs` | Só documentação |
| `style` | Formatação (sem mudar lógica) |
| `refactor` | Refatoração (sem bug nem feature) |
| `test` | Testes |
| `chore` | Tarefas rotineiras |
| `build` | Build / dependências |
| `ci` | Configuração de CI |
| `perf` | Desempenho |
| `revert` | Reverter um commit |

Exemplo: `feat(login): adiciona validação do campo nome`

> O hook **ignora** commits de merge e revert — eles não precisam seguir o padrão.

</details>

<details>
<summary><b>Update from main vs. Rebase</b></summary><br/>

- **Update from main** → traz a `main` via **commit de merge**. Mais simples e seguro; use na dúvida.
- **Rebase** → **reaplica seus commits** por cima da `main`. Histórico linear; use só em branch **sua** (pode exigir push com *force-with-lease*).
- ⚠️ Nunca faça rebase de uma branch **compartilhada**.

</details>

<details>
<summary><b>Anatomia de um conflito</b></summary><br/>

```diff
 <<<<<<< main
 versão atual na main
 =======
 versão da branch sendo mesclada
 >>>>>>> sua-branch
```

Escolha o conteúdo final e **remova os três marcadores** (`<<<<<<<`, `=======`, `>>>>>>>`).

</details>

### 🔗 Onde isto vive no projeto

- Política de commits: [`.githooks/commit-msg`](../../colaborar-com-github-desktop/blob/main/.githooks/commit-msg)
- Modelo de Pull Request: [`.github/pull_request_template.md`](../../colaborar-com-github-desktop/blob/main/.github/pull_request_template.md)
- Templates de issue: [`.github/ISSUE_TEMPLATE/`](../../colaborar-com-github-desktop/tree/main/.github/ISSUE_TEMPLATE)

Bom trabalho — agora é só aplicar no dia a dia! 🚀
