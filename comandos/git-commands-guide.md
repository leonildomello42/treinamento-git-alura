# Guia Completo de Comandos Git

Este documento serve como referência para os comandos mais utilizados do Git, desde configuração inicial até operações avançadas.

## Configuração Inicial

```bash
# Configurar nome de usuário global
git config --global user.name "Seu Nome"

# Configurar email global
git config --global user.email "seu.email@exemplo.com"

# Configurar editor padrão
git config --global core.editor "nome-do-editor"

# Configurar ferramenta de merge padrão
git config --global merge.tool "nome-da-ferramenta"

# Visualizar configurações
git config --list
```

## Criação e Clonagem de Repositórios

```bash
# Inicializar um repositório Git
git init

# Clonar um repositório existente
git clone <url-do-repositório>

# Clonar um repositório específico com nome personalizado
git clone <url-do-repositório> <diretório-destino>

# Clonar um repositório mas apenas um branch específico
git clone --single-branch --branch <nome-do-branch> <url-do-repositório>
```

## Operações Básicas

```bash
# Verificar o status dos arquivos
git status

# Adicionar um arquivo específico ao staging
git add <arquivo>

# Adicionar todos os arquivos modificados ao staging
git add .

# Adicionar alterações interativamente
git add -p

# Fazer commit das alterações no staging
git commit -m "Mensagem do commit"

# Adicionar todos os arquivos modificados e fazer commit
git commit -am "Mensagem do commit"

# Modificar o último commit
git commit --amend
```

## Branches

```bash
# Listar branches locais
git branch

# Listar todos os branches (locais e remotos)
git branch -a

# Criar um novo branch
git branch <nome-do-branch>

# Deletar um branch local
git branch -d <nome-do-branch>

# Forçar a deleção de um branch local
git branch -D <nome-do-branch>

# Renomear o branch atual
git branch -m <novo-nome>

# Trocar para outro branch
git checkout <nome-do-branch>

# Criar e trocar para um novo branch
git checkout -b <nome-do-branch>

# Voltar para o branch anterior
git checkout -
```

## Remoto

```bash
# Mostrar repositórios remotos
git remote -v

# Adicionar um novo repositório remoto
git remote add <nome> <url>

# Remover um repositório remoto
git remote remove <nome>

# Renomear um repositório remoto
git remote rename <nome-antigo> <novo-nome>

# Buscar alterações do repositório remoto
git fetch <remoto>

# Buscar alterações de todos os remotos
git fetch --all

# Fazer pull (buscar e mesclar) do remoto
git pull <remoto> <branch>

# Fazer push para o remoto
git push <remoto> <branch>

# Fazer push e configurar o upstream
git push -u <remoto> <branch>

# Fazer push forçado (use com cuidado!)
git push --force <remoto> <branch>
```

## Merge e Rebase

```bash
# Fazer merge de um branch no branch atual
git merge <branch>

# Abortar um merge em andamento
git merge --abort

# Fazer rebase do branch atual em cima de outro
git rebase <branch>

# Rebase interativo
git rebase -i <commit>

# Continuar um rebase após resolver conflitos
git rebase --continue

# Abortar um rebase
git rebase --abort
```

## Histórico e Logs

```bash
# Visualizar histórico de commits
git log

# Visualizar histórico com gráfico
git log --graph

# Visualizar histórico resumido
git log --oneline

# Visualizar histórico com estatísticas
git log --stat

# Visualizar histórico de um arquivo específico
git log <arquivo>

# Mostrar alterações em um commit específico
git show <hash-do-commit>

# Visualizar alterações não commitadas
git diff

# Visualizar alterações no staging
git diff --staged
```

## Desfazer Alterações

```bash
# Descartar alterações de um arquivo específico
git checkout -- <arquivo>

# Descartar todas as alterações locais
git checkout -- .

# Resetar o staging mantendo as alterações locais
git reset

# Resetar o staging e descartar alterações de arquivos específicos
git reset <arquivo>

# Reverter para um commit específico mantendo o histórico
git revert <hash-do-commit>

# Resetar para um commit específico (soft - mantém alterações no staging)
git reset --soft <hash-do-commit>

# Resetar para um commit específico (mixed - default, mantém alterações fora do staging)
git reset --mixed <hash-do-commit>

# Resetar para um commit específico (hard - descarta todas as alterações)
git reset --hard <hash-do-commit>
```

## Stash

```bash
# Salvar alterações temporárias
git stash

# Listar stashes
git stash list

# Aplicar o stash mais recente
git stash apply

# Aplicar um stash específico
git stash apply stash@{n}

# Aplicar e remover o stash mais recente
git stash pop

# Remover o stash mais recente
git stash drop

# Remover um stash específico
git stash drop stash@{n}

# Criar um branch a partir de um stash
git stash branch <nome-do-branch>
```

## Tags

```bash
# Listar tags
git tag

# Criar uma tag leve
git tag <nome-da-tag>

# Criar uma tag anotada
git tag -a <nome-da-tag> -m "Mensagem da tag"

# Criar uma tag para um commit específico
git tag <nome-da-tag> <hash-do-commit>

# Enviar tags para o remoto
git push --tags

# Enviar uma tag específica
git push <remoto> <nome-da-tag>

# Deletar uma tag local
git tag -d <nome-da-tag>

# Deletar uma tag remota
git push <remoto> --delete <nome-da-tag>
```

## Submodules

```bash
# Adicionar um submódulo
git submodule add <url> <diretório>

# Inicializar submódulos
git submodule init

# Atualizar submódulos
git submodule update

# Inicializar e atualizar todos os submódulos
git submodule update --init --recursive

# Executar comando em todos os submódulos
git submodule foreach '<comando>'
```

## Cherry-Pick

```bash
# Aplicar um commit específico ao branch atual
git cherry-pick <hash-do-commit>

# Cherry-pick sem fazer commit
git cherry-pick -n <hash-do-commit>
```

## Bisect

```bash
# Iniciar a busca binária
git bisect start

# Marcar um commit como ruim
git bisect bad [<hash-do-commit>]

# Marcar um commit como bom
git bisect good [<hash-do-commit>]

# Resetar a busca bisect
git bisect reset
```

## Limpeza e Manutenção

```bash
# Remover arquivos não rastreados
git clean -f

# Remover arquivos não rastreados e diretórios
git clean -fd

# Mostrar o que seria removido sem realmente remover
git clean -n

# Compactar o repositório
git gc

# Verificar integridade do repositório
git fsck

# Verificar quais objetos ocupam espaço
git count-objects -v
```

## Fluxos de Trabalho Avançados

```bash
# Criar e verificar uma pull request localmente
git fetch origin pull/<id>/head:<branch>
git checkout <branch>

# Salvar temporariamente o estado atual (alternativa ao stash)
git worktree add <diretório> <branch>

# Listar worktrees
git worktree list

# Remover um worktree
git worktree remove <diretório>
```

Este guia cobre a maioria dos comandos Git comuns e avançados. Lembre-se de consultar a documentação oficial para detalhes específicos ou casos de uso mais complexos.