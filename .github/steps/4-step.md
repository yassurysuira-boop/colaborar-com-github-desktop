<!-- step-4-gitignore-check -->

## Passo 4: Ignorando arquivos com `.gitignore`

Nem tudo que aparece na sua pasta deve ir para o repositório. Arquivos temporários, dependências baixadas, segredos e configurações pessoais do seu computador **não** pertencem ao histórico do projeto. Para isso existe o `.gitignore`. 🙈

### 📖 Teoria: O que é o `.gitignore`?

O `.gitignore` é um arquivo de texto que lista **padrões de arquivos e pastas que o Git deve ignorar**. Arquivos que casam com esses padrões nunca aparecem em **Changes** e nunca são commitados.

Por que isso importa:

- **Evita lixo no repositório**: pastas como `node_modules/`, builds e logs.
- **Protege segredos**: arquivos `.env`, chaves e senhas **nunca** devem ser versionados.
- **Reduz conflitos**: arquivos específicos do seu sistema operacional ou editor (como `.DS_Store`, `Thumbs.db`, `.vscode/`) atrapalham os colegas.

A sintaxe é simples — um padrão por linha:

```gitignore
# Comentários começam com #

# Esse padrão ignora uma pasta inteira, nesse caso a pasta node_modules
node_modules/

#  Esse padrão ignora todos os arquivos com uma extensão, no caso arquivos .log
*.log

#  Esse padrão ignora um arquivo específico, nesse caso o arquivo .env
.env

# Arquivos de sistema operacional / editor
.DS_Store
Thumbs.db
.vscode/
```

> [!TIP]
> O site [gitignore.io](https://www.toptal.com/developers/gitignore) gera arquivos `.gitignore` prontos para a sua linguagem e ferramentas. O GitHub também oferece modelos ao criar um repositório.

> [!IMPORTANT]
> O `.gitignore` só afeta arquivos que **ainda não** foram commitados. Se um arquivo já está no histórico, adicioná-lo ao `.gitignore` não o remove — é preciso removê-lo do controle de versão primeiro.

### ⌨️ Atividade: Crie um `.gitignore`

1. Confirme que você está na branch `add-project-files` no GitHub Desktop.

2. No seu editor, crie um arquivo chamado exatamente `.gitignore` na **raiz** do repositório com algum conteúdo, por exemplo:

   ```gitignore
   # Dependências
   node_modules/

   # Logs
   *.log

   # Variáveis de ambiente e segredos
   .env

   # Arquivos de sistema
   .DS_Store
   Thumbs.db
   ```

   Salve o arquivo.

3. De volta ao GitHub Desktop, o `.gitignore` aparecerá em **Changes**. Commite usando a política que você aprendeu:

   ```txt
   chore: adiciona arquivo .gitignore
   ```

4. Clique em **Push origin** para enviar.

### ✅ Marque este passo como concluído

1. clique no checkbox abaixo.

Se não funcionar,

1. Vá ao início deste comentário com as instruções deste passo.
2. Clique no menu **`···`** no canto superior direito do comentário e escolha **Edit**.
3. Marque a caixa trocando `[ ]` por `[x]` e clique em **Update comment**. Obs: deve ser exatamente `[x]`.

- [ ] Criei um arquivo `.gitignore`, commitei seguindo a política e enviei (push).

A Mona verá sua atualização e compartilhará o próximo passo. 🚀

<details>
<summary>Com dificuldades? 🤷</summary><br/>

- O arquivo precisa se chamar exatamente `.gitignore` (com o ponto no início e sem extensão).
- Alguns editores escondem arquivos que começam com ponto; ative a exibição de arquivos ocultos se não o vir.
- Se um arquivo que você quer ignorar continua aparecendo, confirme que o padrão no `.gitignore` está correto e que o arquivo ainda não havia sido commitado antes.

</details>
