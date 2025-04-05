# 📘 Guia de Comandos Git

Este guia contém os comandos Git mais utilizados, com uma breve descrição de cada um para facilitar seu uso no dia a dia.

---

## 📦 1. Configuração Inicial

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```
> Define nome e email do usuário globalmente (usado em todos os repositórios).

```bash
git config --global core.editor "code --wait"
```
> Define o editor padrão (ex: VS Code).

```bash
git config --list
```
> Lista todas as configurações atuais do Git.

---

## 📁 2. Inicializando um Repositório

```bash
git init
```
> Inicializa um novo repositório Git na pasta atual.

```bash
git clone <url>
```
> Clona um repositório remoto existente para a máquina local.

---

## 📄 3. Status e Histórico

```bash
git status
```
> Mostra o estado atual dos arquivos (modificados, staged, untracked etc).

```bash
git log
```
> Exibe o histórico de commits.

```bash
git log --oneline
```
> Mostra o histórico em uma linha por commit.

---

## ✍️ 4. Trabalhando com Commits

```bash
git add <arquivo>
```
> Adiciona arquivo específico à área de stage.

```bash
git add .
```
> Adiciona todas as alterações na pasta atual à área de stage.

```bash
git commit -m "Mensagem do commit"
```
> Cria um novo commit com a mensagem fornecida.

```bash
git commit --amend
```
> Altera o último commit (mensagem ou arquivos).

---

## 🌿 5. Branches

```bash
git branch
```
> Lista todas as branches locais.

```bash
git branch <nome>
```
> Cria uma nova branch.

```bash
git checkout <nome>
```
> Muda para a branch especificada.

```bash
git checkout -b <nome>
```
> Cria e muda para uma nova branch.

```bash
git merge <branch>
```
> Mescla a branch especificada na atual.

```bash
git branch -d <nome>
```
> Deleta a branch local.

---

## 🔄 6. Trabalhando com Repositórios Remotos

```bash
git remote add origin <url>
```
> Adiciona um repositório remoto com o nome "origin".

```bash
git push origin <branch>
```
> Envia as alterações da branch para o repositório remoto.

```bash
git push -u origin <branch>
```
> Envia a branch e define o upstream (link com branch remota).

```bash
git pull
```
> Puxa alterações do repositório remoto e faz merge.

```bash
git fetch
```
> Puxa as alterações do remoto sem aplicar.

---

## ♻️ 7. Revertendo Mudanças

```bash
git checkout -- <arquivo>
```
> Desfaz alterações locais no arquivo.

```bash
git reset HEAD <arquivo>
```
> Remove o arquivo da área de stage (não desfaz alterações locais).

```bash
git revert <hash_do_commit>
```
> Cria um novo commit revertendo um commit anterior.

```bash
git reset --hard <hash>
```
> Volta o repositório para um estado anterior (⚠️ PERIGOSO).

---

## 🧪 8. Stash (Guardando Mudanças Temporárias)

```bash
git stash
```
> Salva mudanças não commitadas temporariamente.

```bash
git stash apply
```
> Restaura a última stash salva.

```bash
git stash list
```
> Lista todas as stashes salvas.

```bash
git stash drop
```
> Remove a stash mais recente.

---

## 🧼 9. Limpeza

```bash
git clean -f
```
> Remove arquivos não rastreados (⚠️ Cuidado!).

```bash
git gc
```
> Executa coleta de lixo e otimiza o repositório.

---

## 🔐 10. Outros Comandos Úteis

```bash
git show
```
> Mostra detalhes do último commit ou de um objeto.

```bash
git diff
```
> Mostra as diferenças entre arquivos ou commits.

```bash
git tag <nome>
```
> Cria uma tag para marcar um ponto específico no histórico.

```bash
git blame <arquivo>
```
> Mostra quem fez cada alteração em cada linha de um arquivo.


# Conflitos:

> Faça um fetch para atualizar as referências do repositório remoto

```bash
git fetch origin
```

> Force o pull mantendo suas alterações locais, mas permitindo conflitos

```bash
git pull --no-rebase
```

> Alternativamente, se você preferir usar rebase em vez de merge:

```bash
git pull --rebase
```

> Adicione os arquivos resolvidos ao staging

```bash
git add <arquivos-resolvidos>
```

> ou adicione todos os arquivos
```bash
git add .
```
> Se estiver usando merge (pull padrão)

```bash
git commit -m "Resolução de conflitos"
```

> Se estiver usando rebase

```bash
git rebase --continue
```

---
