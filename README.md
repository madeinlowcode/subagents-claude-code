# Sub-Agents para Claude Code

Uma coleção de sub-agentes especializados para uso com Claude Code, cada um projetado para tarefas específicas de desenvolvimento de software.

## Instalação

Para usar estes agentes no seu projeto, copie a pasta `agents` para `.claude/agents/` no seu projeto:

```bash
mkdir -p .claude/agents
cp agents/*.md .claude/agents/
```

## Agentes Disponíveis

### 1. Documentation Sync Agent (`documentation-sync-agent.md`)

**Cor:** Verde | **Modelo:** Opus

Agente especializado em manter a documentação do projeto sempre atualizada e sincronizada. Responsável por:

- Rastrear progresso de desenvolvimento
- Documentar bugs encontrados
- Registrar decisões arquiteturais (ADRs)
- Manter o mapa do codebase (`codebase-map.json`)
- Criar arquivos `CLAUDE.md` contextuais em diretórios importantes

**Quando usar:**
- Após completar implementação de features
- Quando bugs são encontrados e corrigidos
- Ao tomar decisões arquiteturais importantes
- Para entender a estrutura do projeto

---

### 2. E2E Testing Specialist (`e2e-testing-specialist.md`)

**Cor:** Rosa | **Modelo:** Opus

Especialista em testes end-to-end automatizados, detecção de bugs e validação de funcionalidades. Utiliza MCP Chrome DevTools ou Playwright para:

- Executar testes E2E completos
- Identificar e documentar falhas
- Criar planos de correção detalhados
- Validar fluxos de usuário críticos
- Testar responsividade e compatibilidade cross-browser

**Quando usar:**
- Após implementar novas features ou componentes
- Para reproduzir e documentar bugs
- Antes de releases (testes de regressão)
- Para validar fluxos críticos (autenticação, pagamentos)

---

### 3. Fullstack Dev Specialist (`fullstack-dev-specialist.md`)

**Cor:** Ciano | **Modelo:** Opus

Desenvolvedor fullstack experiente que implementa código real, funcional e consistente. Utiliza MCPs (Supabase, Context7, Serena) para:

- Entender contexto do projeto antes de codificar
- Implementar código personalizado para cada aplicação
- Seguir padrões e convenções existentes
- Integrar frontend, backend e banco de dados

**Quando usar:**
- Implementar features que envolvem frontend e backend
- Criar endpoints de API com integração de banco
- Integrar serviços de terceiros (webhooks, APIs)
- Implementar lógica funcional após aprovação de design

---

### 4. Security Code Reviewer (`security-code-reviewer.md`)

**Cor:** Amarelo | **Modelo:** Opus

Especialista em segurança de aplicações e revisão de código. Foco em:

- Análise OWASP Top 10
- Identificação de vulnerabilidades (SQL Injection, XSS, etc.)
- Auditoria de autenticação e autorização
- Análise de práticas criptográficas
- Criação de planos de remediação

**Quando usar:**
- Após implementar código sensível à segurança
- Ao criar sistemas de autenticação
- Para endpoints de API que manipulam dados sensíveis
- Antes de deploy para produção
- Auditorias gerais de segurança

---

### 5. Senior Software Engineer (`senior-software-engineer.md`)

**Cor:** Azul | **Modelo:** Opus

Engenheiro de software sênior com 15+ anos de experiência. Especializado em:

- Implementação de features full-stack
- Código de qualidade de produção
- Correção de bugs complexos
- Refatoração seguindo SOLID
- Criação de testes automatizados
- Code reviews detalhados

**Quando usar:**
- Implementar novas features
- Corrigir bugs complexos (memory leaks, race conditions)
- Refatorar código seguindo boas práticas
- Criar testes unitários e de integração
- Revisar pull requests

---

### 6. Software Architect (`software-architect.md`)

**Cor:** Vermelho | **Modelo:** Opus

Arquiteto de software sênior especializado em sistemas de alta escala. Responsável por:

- Identificar gargalos de infraestrutura
- Analisar problemas de escalabilidade
- Avaliar segurança e resiliência
- Documentar decisões arquiteturais (ADRs)
- Definir métricas e SLIs/SLOs

**Quando usar:**
- Antes de homologação/produção
- Ao planejar features de alta escala
- Quando há problemas de performance
- Para decisões arquiteturais importantes
- Migrações de infraestrutura

---

## Como Usar

Os agentes são invocados automaticamente pelo Claude Code quando o contexto é apropriado. Você também pode solicitar explicitamente:

```
Use o agente security-code-reviewer para analisar este código
```

## Estrutura do Projeto

```
.
├── README.md
└── agents/
    ├── documentation-sync-agent.md
    ├── e2e-testing-specialist.md
    ├── fullstack-dev-specialist.md
    ├── security-code-reviewer.md
    ├── senior-software-engineer.md
    └── software-architect.md
```

## Requisitos

- Claude Code CLI
- Modelo: Claude Opus (recomendado para todos os agentes)

## MCPs Recomendados

Para melhor funcionamento dos agentes, recomenda-se configurar:

- **MCP Supabase** - Para operações de banco de dados
- **MCP Playwright** - Para testes E2E e validação de UI
- **MCP Sequential-Thinking** - Para raciocínio complexo

## Licença

MIT

---

Desenvolvido por [Made in Low Code](https://github.com/madeinlowcode)
