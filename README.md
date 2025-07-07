````markdown
# 🛠️ Trabalhando com **Git Flow**

> Guia rápido para organizar seu fluxo de trabalho com Git Flow.
> Exemplo de tagueamento de versão.

---

## 1. Inicialização

```bash
git flow init
````

*Dica:* mantenha os prefixos sugeridos pelo próprio Git Flow (feature/, release/, hotfix/, etc.).

---

## 2. Features

### 2.1 Criar uma nova feature

```bash
git flow feature start <nome-da-feature>
```

### 2.2 Publicar a branch (caso precise subir para o repositório remoto)

```bash
git flow feature publish <nome-da-feature>
```

### 2.3 Retomar o trabalho em uma feature já existente

```bash
git flow feature pull origin <nome-da-feature>
```

### 2.4 Finalizar a feature

```bash
git add .
git commit -m "Mensagem descritiva do commit"
git flow feature finish <nome-da-feature>
```

### 2.5 Enviar alterações para a branch `develop`

```bash
git push origin develop
```

---

## 3. Releases

### 3.1 Criar uma nova release

```bash
git flow release start <novo-número-de-versão>
```

### 3.2 Finalizar a release

```bash
git flow release finish <mesmo-número-de-versão>
```

### 3.3 Enviar merge da release para `develop`

```bash
git push origin develop
```

### 3.4 Trocar para a branch `main`

```bash
git checkout main
```

### 3.5 Enviar merge da release para `main`

```bash
git push origin main
```

### 3.6 Publicar as tags criadas

```bash
git push origin --tags
```

### 4. Hotfixes

#### 4.1 Criar um hotfix

```bash
git flow hotfix start <nome-do-hotfix>
```

### 4.2 Finalizar o hotfix

```bash
git flow hotfix finish <nome-do-hotfix>
```
### 4.3 Enviar merge do hotfix para `develop`

```bash
git push origin develop
```

### 4.4 Enviar merge do hotfix para `main`

```bash
git push origin main
```

### 4.5 Publicar as tags criadas

```bash
git push origin --tags
```

---

## 📚 Referência

[Git Flow Cheat Sheet](https://danielkummer.github.io/git-flow-cheatsheet/)

```
```

## 📋 Versionamento Semântico (SemVer)

O versionamento semântico segue o padrão `MAJOR.MINOR.PATCH`:

### 🔴 **MAJOR** (Incompatibilidade)
- Mudanças que quebram a compatibilidade com versões anteriores
- Exemplo: `v1.0.0` → `v2.0.0`
- Quando: Remoção de APIs, mudanças significativas na arquitetura

### 🟡 **MINOR** (Nova Funcionalidade)
- Adição de funcionalidades mantendo compatibilidade
- Exemplo: `v1.0.0` → `v1.1.0`
- Quando: Novos recursos, melhorias que não quebram o código existente

### 🟢 **PATCH** (Correção de Bug)
- Correções de bugs mantendo compatibilidade
- Exemplo: `v1.0.0` → `v1.0.1`
- Quando: Correções de bugs, pequenas melhorias de segurança

### 📝 **Exemplos Práticos**

| Versão | Tipo | Descrição |
|--------|------|-----------|
| `v1.0.0` | Major | Primeira versão estável |
| `v1.1.0` | Minor | Adicionado sistema de login |
| `v1.1.1` | Patch | Corrigido bug no login |
| `v2.0.0` | Major | Refatoração completa da API |
