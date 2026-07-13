---
name: security-audit
description: Use SEMPRE que o usuário mencionar auditoria de segurança, security review, OWASP, vulnerabilidade, segurança do código, segurança da aplicação, segredos hardcoded, chave de API exposta, .env commitado, token vazado, SQL injection, XSS, CSRF, autenticação fraca, RLS Supabase, Row Level Security, CORS aberto, S3 público, bucket exposto, dependências vulneráveis, npm audit, pip audit, secrets em log, segurança de infra, pentesting, hardening, "meu sistema é seguro", "alguém pode invadir", revisar segurança, security audit, ou pedido relacionado a segurança aplicacional. Esta skill executa auditoria estruturada OWASP Top 10 2025 sobre código, repositório ou descrição de infra, classifica achados por severidade e prescreve correções específicas.
---

# Security Audit

Auditoria de segurança aplicacional seguindo OWASP Top 10 2025 e boas práticas modernas. Analisa código, repositórios, configurações e descrições de infra para encontrar vulnerabilidades reais e prescrever correções específicas.

## Quando usar

Use SEMPRE que o usuário:
- Pedir "revisar segurança", "auditoria de segurança", "security review"
- Mencionar possível vazamento de credencial
- Mostrar código que lida com auth, sessão, query, upload, pagamento
- Questionar se Supabase/Firebase/AWS está bem configurado
- Pedir hardening antes de produção
- Mencionar pentest, OWASP, CVE, CVSS

## O que esta skill faz

1. Varre código contra OWASP Top 10 2025
2. Procura padrões de vazamento de segredo
3. Avalia auth, autorização, sessão, criptografia
4. Avalia configuração de infra (CORS, S3, RLS, headers)
5. Classifica achados: CRÍTICO / ALTO / MÉDIO / BAIXO / INFO
6. Prescreve correção específica + referência (CWE, OWASP)

## OWASP Top 10 2025 — checklist aplicado

### A01 — Broken Access Control
- [ ] Endpoints sem verificação de autorização
- [ ] IDOR (Insecure Direct Object Reference) — `/api/users/123` sem validar dono
- [ ] RLS Supabase desabilitado em tabela com PII
- [ ] Forçar role no client (`isAdmin` vindo do front)
- [ ] JWT sem validação de claims server-side

### A02 — Cryptographic Failures
- [ ] Senhas em texto plano ou MD5/SHA1
- [ ] HTTPS não obrigatório
- [ ] Chaves criptográficas hardcoded
- [ ] PII transmitida sem criptografia
- [ ] Uso de algoritmos depreciados (DES, RC4)

### A03 — Injection (SQL, NoSQL, Command, LDAP)
- [ ] Queries com concatenação de string
- [ ] Falta de prepared statements
- [ ] `eval()`, `exec()`, `child_process` com input de usuário
- [ ] NoSQL injection em Mongo (`$where`, `$regex` com input cru)
- [ ] Prompt injection em LLM sem sanitização

### A04 — Insecure Design
- [ ] Falta de rate limiting em endpoints sensíveis (login, OTP, esqueci senha)
- [ ] Sem MFA em conta admin
- [ ] Recuperação de senha por pergunta secreta
- [ ] Fluxo de pagamento sem idempotência

### A05 — Security Misconfiguration
- [ ] CORS `Access-Control-Allow-Origin: *` com `credentials: true`
- [ ] Headers de segurança ausentes (CSP, HSTS, X-Frame-Options, X-Content-Type-Options)
- [ ] Stack trace exposto em produção
- [ ] DEBUG=true em produção (Django, Flask, Rails)
- [ ] Buckets S3/GCS públicos sem necessidade
- [ ] Portas administrativas expostas (5432, 3306, 27017, 6379, 22)

### A06 — Vulnerable & Outdated Components
- [ ] Dependências com CVE conhecida (`npm audit`, `pip-audit`, `snyk test`)
- [ ] Imagem Docker desatualizada
- [ ] Lockfile desatualizado há > 6 meses

### A07 — Identification & Authentication Failures
- [ ] Login sem proteção contra brute force
- [ ] Cookies de sessão sem `HttpOnly`, `Secure`, `SameSite`
- [ ] JWT em localStorage (vulnerável a XSS)
- [ ] Token de sessão sem expiração ou renovação
- [ ] Falta de logout server-side (token continua válido)

### A08 — Software & Data Integrity Failures
- [ ] CI/CD que executa código de PR sem revisão (`pull_request_target`)
- [ ] `npm install` de pacote sem lockfile
- [ ] Deserialização insegura (`pickle`, `unserialize`)
- [ ] Webhook sem verificação de assinatura

### A09 — Security Logging & Monitoring Failures
- [ ] Senhas, tokens, PII em log
- [ ] Sem log de eventos críticos (login, mudança de senha, transação)
- [ ] Sem alerta para múltiplas falhas de login

### A10 — Server-Side Request Forgery (SSRF)
- [ ] Endpoint que faz fetch de URL fornecida pelo usuário sem allowlist
- [ ] Imagem/avatar com upload por URL sem validação

## Padrões de segredo a varrer (regex)

- `AKIA[0-9A-Z]{16}` — AWS Access Key
- `sk_live_[0-9a-zA-Z]{24,}` — Stripe live
- `xox[baprs]-[0-9a-zA-Z-]{10,}` — Slack token
- `ghp_[0-9a-zA-Z]{36}` — GitHub Personal Token
- `sk-[a-zA-Z0-9]{48}` — OpenAI key
- `sk-ant-[a-zA-Z0-9-_]{50,}` — Anthropic key
- `AIza[0-9A-Za-z\-_]{35}` — Google API key
- `eyJ[A-Za-z0-9-_]+\.[A-Za-z0-9-_]+\.[A-Za-z0-9-_]+` — JWT exposto
- `mongodb(\+srv)?://[^:]+:[^@]+@` — Mongo URI com senha
- `postgres://[^:]+:[^@]+@` — Postgres URI com senha
- `BEGIN (RSA|EC|OPENSSH) PRIVATE KEY` — chave privada
- `.env`, `credentials.json`, `serviceAccount.json` commitados

## Classificação de severidade

| Severidade | Critério | Prazo correção |
|------------|----------|----------------|
| CRÍTICO | Compromete tudo, exploração trivial, dados em risco | 24h |
| ALTO | Exploração possível, impacto sério | 7 dias |
| MÉDIO | Requer condição específica, impacto moderado | 30 dias |
| BAIXO | Hardening, defesa em profundidade | 90 dias |
| INFO | Boa prática | quando possível |

## Como usar (passo a passo)

**Passo 1** — Pergunte o que pode auditar:
- Trechos de código colados
- Estrutura de pastas / arquivos sensíveis (.env, config, auth)
- Descrição de stack e infra (Supabase, AWS, Vercel)
- Resultado de `npm audit` / `pip-audit`

**Passo 2** — Aplique checklist por categoria

**Passo 3** — Devolva relatório executivo

## Formato de saída

```
RELATÓRIO DE SEGURANÇA — [Projeto/Escopo]
Data: [data] | Escopo: [o que foi analisado]

RESUMO
- Críticos: X | Altos: Y | Médios: Z | Baixos: W
- Risco geral: [Crítico/Alto/Médio/Baixo]
- Pronto para produção: [SIM/NÃO]

═══════════════════════════════
ACHADOS CRÍTICOS

[C-1] Título do achado
- Local: arquivo:linha
- CWE/OWASP: CWE-XXX / Axx
- Evidência: trecho de código
- Impacto: o que um atacante consegue
- Correção:
  ```código corrigido```
- Prazo: 24h

[C-2] ...

═══════════════════════════════
ACHADOS ALTOS

[A-1] ...

═══════════════════════════════
ACHADOS MÉDIOS

═══════════════════════════════
QUICK WINS (executar HOJE)
1. Rotacionar chave [X] vazada em [arquivo]
2. ...

RECOMENDAÇÕES ESTRUTURAIS
- Implementar pre-commit hook com gitleaks
- Habilitar Dependabot
- Adicionar SAST no CI (Semgrep, CodeQL)
```

## Exemplos práticos

**Exemplo achado CRÍTICO — RLS Supabase off:**
```
[C-1] Tabela `users` sem RLS habilitada
- Local: schema público
- CWE-284 / A01:2025
- Evidência: SELECT permitido com anon key retorna todos os usuários
- Impacto: qualquer visitante extrai PII de todos os usuários
- Correção:
  ALTER TABLE users ENABLE ROW LEVEL SECURITY;
  CREATE POLICY "users_select_own" ON users FOR SELECT USING (auth.uid() = id);
- Prazo: 24h
```

**Exemplo CRÍTICO — chave OpenAI commitada:**
```
[C-2] OPENAI_API_KEY hardcoded em src/lib/ai.ts:14
- Correção: 1) revogar chave agora em platform.openai.com; 2) mover pra .env; 3) limpar histórico git com BFG; 4) adicionar .env ao .gitignore; 5) ativar secret scanning do GitHub
- Prazo: 1h
```

## Limitações / Quando NÃO usar

- Não substitui pentest profissional para apps com alto valor
- Não consigo executar scan dinâmico (DAST) sem ferramentas
- Análise de código depende do que for compartilhado
- Compliance específica (PCI-DSS, HIPAA, LGPD avançada) exige auditor certificado
- Sempre confirme correções com testes; não confie cegamente no patch sugerido
