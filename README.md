## Plano de Sprints para Aplicação de Avaliação Física

Este roadmap foi pensado para um **desenvolvedor solo** e contempla 8 sprints semanais (mais um sprint de preparação) do MVP ao lançamento.

---

### Sprint 0 – Preparação (2 dias)
**Objetivo:** Sentar as bases para acelerar o desenvolvimento.  
**Entregáveis:**
- Repositório GitHub configurado (branch por feature + PRs)
- Documento com user stories essenciais  
- Wireframes esboçados (Figma ou papel)  

**Ferramentas:** VS Code, Git, Figma (ou Miro)

---

### Sprint 1 – Infra & Autenticação (1 semana)
**Stack sugerido:**
- Next.js + TypeScript (front & back juntos)  
- Supabase (Auth, Postgres, Storage)  
- Tailwind CSS  

**Tarefas:**
1. Bootstrap do projeto Next.js + TypeScript  
2. Configurar Supabase Auth (e‑mail/senha)  
3. Layout básico de login/logout  

---

### Sprint 2 – CRUD de Alunos (1 semana)
**Entregáveis:**
- Tabela `alunos` no Supabase (dados pessoais)  
- Endpoints REST em `/api/alunos` (GET, POST, PUT, DELETE)  
- Tela de listagem, criação e edição de alunos  

**Tarefas:**
1. Definir esquema SQL em Supabase (`nome`, `gênero`, `dt_nasc`, `registro`, `freq_treino`, `objetivo`)  
2. Hooks React (SWR ou React Query) para consumir a API  
3. Formulários com React Hook Form + Yup  

---

### Sprint 3 – Registro de Avaliações (1 semana)
**Entregáveis:**
- Migrations no Supabase para tabelas: `avaliacoes`, `antropometria`, `dobras`, etc.  
- CRUD de avaliações ligadas a um aluno  
- UI de formulário multi‑step (tabs ou wizard)  

**Tarefas:**
1. Criar migrations para cada entidade  
2. Endpoints em `/api/avaliacoes/[id]`  
3. Formulário dividido por categorias:  
   - Antropometria  
   - Dobras cutâneas  
   - Testes funcionais  

---

### Sprint 4 – Cálculos Automáticos (1 semana)
**Entregáveis:**
- Módulo `lib/calculos.ts` com fórmulas (Siri, Jackson & Pollock)  
- Chamada automática dos cálculos após salvar dobras  
- Exibição dos resultados na UI  

**Tarefas:**
1. Implementar funções para massa gorda, massa magra e %gordura  
2. Testes unitários com Jest  

---

### Sprint 5 – Relatórios (1 semana)
**Entregáveis:**
- Geração de PDF via **Puppeteer** ou **html-pdf**  
- Botão “Exportar PDF” na tela de avaliação  
- (Opcional) Exportação Excel com **SheetJS**  

**Tarefas:**
1. Criar template HTML/CSS para o relatório  
2. Endpoint `/api/relatorio/[avaliacao]?format=pdf`  
3. Implementar download direto pelo front  

---

### Sprint 6 – Upload de Imagens Posturais (1 semana)
**Entregáveis:**
- Integração com storage do Supabase para fotos  
- Upload via formulário e armazenamento de URLs  
- Galeria de imagens + campo de comentários posturais  

**Tarefas:**
1. Componente `<FileInput>` para múltiplas imagens  
2. Endpoint de upload para bucket Supabase  
3. Exibição de previews e formulário de observações  

---

### Sprint 7 – UX, Responsividade e Polimento (1 semana)
**Entregáveis:**
- Layout responsivo (mobile / desktop)  
- Componentes de UI refinados (shadcn/ui ou Chakra UI)  
- Validações completas em todos os formulários  

**Tarefas:**
1. Ajustar breakpoints, espaçamentos e tipografia  
2. Feedback visual em botões, loading states  
3. Revisão de acessibilidade (labels, contrastes)  

---

### Sprint 8 – Testes, Deploy e Lançamento (1 semana)
**Entregáveis:**
- Cobertura mínima de testes unitários (≥ 60 %)  
- Deploy automático no Vercel (GitHub → Vercel)  
- Checklist de lançamento: domínio, SSL, variáveis de ambiente  

**Tarefas:**
1. Configurar GitHub Actions (lint, build, testes)  
2. Ajustar variáveis do Supabase (URLs, chaves)  
3. Smoke tests pós‑deploy e ajuste rápido de bugs  

---

## Dicas para um Desenvolvedor Solo
- **Evite complexidade:** use Next.js + Supabase para unificar front/back e reduzir boilerplate.  
- **Reaproveite código:** crie componentes genéricos (Inputs, Tables, Modals).  
- **Automatize:** utilize a CLI do Supabase para migrations/seeds.  
- **Itere rápido:** mantenha sempre o MVP rodando e só depois adicione “luxos”.  
- **Foque na UX:** uma aplicação bem usável vale mais que muitos recursos inacabados.
