# 📁 PROJECT MEMORY – <Site Isaac> 

> **Objetivo:** Centralizar o conhecimento compartilhado entre todas as IAs (e humanos) que atuam neste repositório.
> Mantenha este arquivo versionado (git) e atualize sempre que houver decisões, decisões de arquitetura, convenções, tarefas abertas, etc.

---

## 1️⃣  Visão Geral do Projeto
| Item | Descrição |
|------|-----------|
| **Nome** | \<Site Isaac\> |
| **Objetivo principal** | \<Construção de um site de modelo para criança isaac\> |
| **Público‑alvo / Usuários** | \<Familiares, empresas e agencias de modelos.\> |
| **Stack principal** | Linguagem, framework, banco, infra, etc. |
| **Repositório** | `git@...` / `https://g...` |
| **Branch principal** | `main` / `main` / `trunk` … |
| **Deploy / CI** | CI/CD, ambiente de staging/prod, etc. |

---

## 2️⃣  Decisões de Arquitetura & Decisões Técnicas (ADR)

| # | Título | Contexto / Decisão | Alternativas consideradas | Consequências / Trade‑offs | Data | Autor |
|---|--------|--------------------|---------------------------|----------------------------|------|-------|
| 001 | Ex.: *Escolha do ORM* | Usar **Prisma** p/ type‑safety… | TypeORM, Sequelize | Type‑safety, migrações automáticas | 2025‑08‑15 | @seu‑usuario |
| 002 | … | … | … | … | … | … |

> **Dica:** siga o modelo **ADR (Architecture Decision Record)** – título, contexto, decisão, consequências.

---

## 3️⃣  Convenções & Padrões do Projeto
| Área | Convenção | Referência / Exemplo |
|------|-----------|----------------------|
| **Commits** | Conventional Commits (`feat:`, `fix:`, `chore:`) | `feat(auth): add JWT refresh` |
| **Branches** | `feature/`, `fix/`, `chore/`, `release/` | `feature/auth-jwt` |
| **Lint / Formatter** | ESLint + Prettier (config `eslint.config.js`, `.prettierrc`) | |
| **Testes** | Jest + React Testing Library; cobertura mínima 80% | |
| **Estilo de código** | TypeScript strict, ESLint `airbnb-base` | |
| **Commits assinados** | `git commit -S` (GPG) | |
| **Branching strategy** | Trunk‑based / Git‑Flow (escolha uma) | |

---

## 4️⃣  Estrutura de Pastas (exemplo)

```
repo-root/
├─ .github/                # workflows CI/CD
├─ docs/                   # documentação viva (ADR, diagrama, etc.)
├─ src/
│   ├─ app/                # entry‑points (Next.js, Nest, etc.)
│   ├─ domain/             # domínio puro (entities, value‑objects)
│   ├─ infra/              # infra (DB, HTTP clients, queues)
│   └─ presentation/       # controllers, resolvers, UI components
├─ tests/
│   ├─ unit/
│   ├─ integration/
│   └─ e2e/
├─ docker/
├─ PROJECT_MEMORY.md   ← **este arquivo**
└─ README.md
```

---

## 5️⃣  Tarefas / Backlog (Kanban leve)

| ID | Título | Tipo | Status | Prioridade | Responsável | Observações |
|----|--------|------|--------|------------|-------------|-------------|
| #1 | Configurar CI/CD | chore | ✅ Done | Alta | @dev1 | GitHub Actions |
| #2 | Implementar autenticação JWT | feat | 🚧 In‑progress | Alta | @dev2 | Usar Prisma + JWT |
| #3 | Testes de integração API | test | ⏳ Todo | Média | @dev3 |  |

> **Dica:** Mantenha esse quadro sincronizado com o seu quadro Kanban (GitHub Projects, Jira, Trello, etc.) – copie‑cole as linhas principais aqui para que qualquer IA tenha visão rápida.

---

## 6️⃣  Decisões de Design / UI / UX
| Tela / Fluxo | Decisão | Referência (Figma, Storybook) | Observações |
|--------------|---------|-------------------------------|-------------|
| Login | JWT + HttpOnly cookie | Figma → `Login v3` | Refresh token rotativo |
| Dashboard | Grid responsivo 12 colunas | Storybook `DashboardGrid` |  |

---

## 7️⃣  Dados & Migrações (Schema, Migrações, Seeds)

| Entidade | Tabela / Coleção | Campos principais | Relacionamentos | Migração (arquivo) |
|----------|------------------|-------------------|-----------------|--------------------|
| User | `users` | `id, email, passwordHash, role` | `hasMany Post` | `20250815_create_users.ts` |
| Post | `posts` | `id, title, content, authorId` | `belongsTo User` | `20250816_create_posts.ts` |

> **Dica:** Mantenha o arquivo de *schema* (Prisma schema, TypeORM entities, Mongoose models) versionado e referencie o nome do arquivo de migração aqui.

---

## 8️⃣  Segurança & Compliance
| Tópico | Decisão / Política | Referência |
|--------|--------------------|------------|
| Autenticação | JWT + HttpOnly cookie, rotação de refresh token | ADR #001 |
| Autorização | RBAC (roles: admin, editor, viewer) | `src/auth/rbac.ts` |
| LGPD / LGPD‑like | Consentimento de cookies, direito ao esquecimento | `docs/compliance/lgpd.md` |
| Segurança de segredos | Vault / GitHub Secrets, nunca commitado | `.github/workflows/secret-scan.yml` |

---

## 9️⃣  Observabilidade (Logs, Métricas, Traces)

| Ferramenta | Configuração | Dashboards / Alertas |
|------------|--------------|----------------------|
| Logs | Winston + Loki | Grafana Loki dashboard |
| Métricas | Prometheus + OpenTelemetry | Grafana “Service Overview” |
| Traces | Jaeger / Tempo | Alertas de latência > 500 ms |
| Alertas | Alertmanager → Slack / PagerDuty | |

---

## 🔟  Checklist de On‑boarding para Novas IAs / Desenvolvedores

- [ ] Clone o repo e rode `npm ci` / `yarn install`
- [ ] Leia `PROJECT_MEMORY.md` (este arquivo) por inteiro
- [ ] Rode `npm run dev` / `docker compose up` e valide health‑check
- [ ] Execute `npm test` – cobertura ≥ 80 %
- [ ] Revise `ADR/*.md` para entender decisões arquiteturais
- [ ] Abra uma issue “Onboarding – <seu nome>” e marque como *Done* ao finalizar

---

## 📌  Notas Livres / Anotações Livres
> *Qualquer observação rápida, ideias, dívidas técnicas, links úteis, etc.*

- **Ideia:** migrar logs para OpenTelemetry nativo no próximo sprint.
- **Dívida:** remover `any` do `src/utils/helpers.ts` (issue #42).
- **Link útil:** [Guia de Conventional Commits](https://www.conventionalcommits.org/pt-br/)

---

### 📌 Como manter este arquivo vivo
1. **Commit a cada decisão relevante** (ADR, mudança de convenção, nova task).
2. **Revise a cada sprint** (revise a seção *Backlog* e *On‑boarding*).
3. **Mantenha versionado** – assim qualquer IA (ou humano) que clone o repo terá o contexto atualizado.

---

## 📚  Referências Externas (links úteis)

- Repositório: `https://github.com/your-org/your-repo`
- Documentação da arquitetura: `docs/architecture.md`
- CI/CD: `.github/workflows/ci.yml`
- Storybook: `https://your-storybook.example.com`
- Figma: `https://www.figma.com/file/…`

---

> **Lembre‑se:** este arquivo é *vivo*. Atualize sempre que houver decisão, mudança de convenção, nova task relevante ou onboarding de novo membro/IA.

---