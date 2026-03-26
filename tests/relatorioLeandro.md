# Relatório de Configuração de Ambiente - Leandro (Tester)

## 1. 📌 Identificação

| Campo | Valor |
|-------|-------|
| Nome do sistema | Openest - Plataforma de Conexão |
| Versão testada | Sprint 0 - Configuração de Ambiente |
| Data dos testes | 11/03/2026 |
| Responsável pelos testes | Leandro Soares |
| Ambiente | Windows 11, PostgreSQL 15.x, Node.js 20.20.1 |

## 2. 🎯 Objetivo dos testes

Configurar todo o ambiente necessário para executar os testes do projeto, garantindo que o tester consiga rodar a aplicação localmente e validar as funcionalidades.

## 3. 🧪 Escopo

### O que foi testado

| Item | Status |
|------|--------|
| Instalação de ferramentas (Git, Node.js, PostgreSQL, VS Code) | ✅ |
| Clonagem dos repositórios (api, web, docs) | ✅ |
| Criação do banco de dados `openest_dev` | ✅ |
| Criação do usuário `openest_user` com permissões | ✅ |
| Configuração do PostgreSQL | ✅ |

### O que não foi testado / não foi possível executar

| Item | Motivo |
|------|--------|
| `npm install` no backend | Repositório `openest-api` sem package.json (apenas estrutura inicial) |
| Configuração do `.env` no backend | Código do backend ainda não implementado |
| `npm run dev` no backend | Backend sem código funcional |
| `npm install` no frontend | Repositório `openest-web` sem package.json (apenas estrutura inicial) |
| Configuração do `.env` no frontend | Código do frontend ainda não implementado |
| `npm run dev` no frontend | Frontend sem código funcional |
| Teste da rota `GET /health` | Backend inexistente no momento |

## 4. 📋 Configurações realizadas

| ID | Descrição | Status |
|----|-----------|--------|
| CF01 | Instalação do Git 2.51.2.windows.1 | ✅ |
| CF02 | Instalação do Node.js 20.20.1 LTS | ✅ |
| CF03 | Instalação do PostgreSQL 15.x | ✅ |
| CF04 | Clonagem do repositório `openest-api` | ✅ |
| CF05 | Clonagem do repositório `openest-web` | ✅ |
| CF06 | Clonagem do repositório `openest-docs` | ✅ |
| CF07 | Criação do banco `openest_dev` | ✅ |
| CF08 | Criação do usuário `openest_user` com senha | ✅ |
| CF09 | Concessão de permissões ao usuário no banco | ✅ |

## 5. 🐞 Problemas encontrados

| ID do problema | Descrição | Severidade | Status |
|----------------|-----------|------------|--------|
| PROB-001 | Repositórios sem código funcional (ausência de package.json e estrutura de código) | Alta | Aguardando implementação dos devs |
| PROB-002 | Ausência de arquivos `.env.example` nos repositórios | Média | Sugerido como melhoria |

## 6. 📊 Evidências

| ID | Descrição | Tipo |
|----|-----------|------|
| EV01 | Ferramentas instaladas listadas e validadas | 📝 Log |
| EV02 | PostgreSQL configurado com banco e usuário | 📸 Screenshot |
| EV03 | Repositórios clonados nos diretórios corretos | 📝 Log |

## 7. ✅ Conclusão

| Pergunta | Resposta |
|----------|----------|
| O ambiente de desenvolvimento está preparado? | ✅ Parcialmente |
| Precisa de ações futuras? | ✅ Sim |
| Qual o status atual? | Ambiente base configurado, mas aguardando implementação do código nos repositórios para dar continuidade aos testes funcionais. |

### 📌 Recomendações

1. **Priorizar a implementação inicial dos repositórios** (criação de `package.json`, estrutura de pastas e código básico) para que os testes possam avançar.
2. **Criar arquivos `.env.example`** em ambos os repositórios (api e web) para facilitar a configuração do ambiente.
3. **Após a implementação**, executar `npm install` em cada repositório e configurar os `.env` para validar a integração completa.

# Relatório de Testes de Frontend - Leandro (Tester)
-----------------------
## 1. 📌 Identificação

| Campo | Valor |
|-------|-------|
| Nome do sistema | Openest - Plataforma de Conexão |
| Versão testada | Sprint 1 - Versão Web (MVP) |
| Data dos testes | 26/03/2026 |
| Responsável pelos testes | Leandro Soares |
| Ambiente | Windows 11, Chrome (navegador), localhost:5173 (frontend), localhost:3000 (backend - não disponível) |

## 2. 🎯 Objetivo dos testes

Validar as funcionalidades de frontend da plataforma Openest, com foco em:

- Validações de formulário (cadastro e login)
- Comportamento visual e feedback ao usuário
- Navegação entre etapas do cadastro

**Observação:** Os testes de integração com backend (autenticação, upload de foto, match, chat) não foram realizados devido à indisponibilidade do backend no momento da execução.

## 3. 🧪 Escopo

### O que foi testado

| Item | Status |
|------|--------|
| Tela de cadastro (Etapas 1, 2 e 3) | ✅ |
| Validações de campos obrigatórios | ✅ |
| Validações de formato (email, senha, data) | ✅ |
| Navegação entre etapas | ✅ |
| Tela de login | ✅ |
| Validações de campos obrigatórios (login) | ✅ |
| Feedback visual de erros | ✅ |
| Responsividade básica | ✅ |
| Mensagens de erro amigáveis | ✅ |

### O que não foi testado

| Item | Motivo |
|------|--------|
| Endpoints de autenticação (POST /register, POST /login) | Backend não disponível |
| Upload de foto para Cloudinary | Backend não disponível |
| Fluxo completo de cadastro com persistência no banco | Backend não disponível |
| Fluxo completo de login com redirecionamento | Backend não disponível |
| Persistência de sessão (token JWT) | Backend não disponível |
| Chat e sistema de matches | Backend não disponível |
| Área administrativa | Backend não disponível |
| Testes automatizados (Jest/Vitest) | Aguardando estabilização do ambiente |

**Motivo geral:** Backend não estava rodando no momento dos testes. Aguardando correção da configuração do `.env` e dependências.

## 4. 📋 Casos de teste

### Cadastro - Etapa 1

| ID | Descrição | Passos | Resultado esperado | Resultado obtido | Status |
|----|-----------|--------|-------------------|-----------------|--------|
| CT01 | Email vazio | Deixar email em branco, clicar em "Próximo" | Mensagem de erro | Mensagem de erro exibida | ✅ |
| CT02 | Email sem @ | Digitar "testeemail", clicar em "Próximo" | Mensagem de erro | Mensagem de erro exibida | ✅ |
| CT03 | Senha vazia | Deixar senha em branco, clicar em "Próximo" | Mensagem de erro | Mensagem de erro exibida | ✅ |
| CT04 | Senha muito curta | Digitar "123", clicar em "Próximo" | Mensagem de erro (mínimo 6) | Mensagem de erro exibida | ✅ |
| CT05 | Confirmar senha diferente | Senha "123456", confirmar "12345", clicar em "Próximo" | Mensagem de erro | Mensagem de erro exibida | ✅ |
| CT06 | Todos campos válidos | Email válido, senha 6+, confirmação igual | Botão "Próximo" habilita | Botão habilitado | ✅ |

### Cadastro - Etapa 2

| ID | Descrição | Passos | Resultado esperado | Resultado obtido | Status |
|----|-----------|--------|-------------------|-----------------|--------|
| CT07 | Nome vazio | Deixar nome em branco, clicar em "Próximo" | Mensagem de erro | Mensagem de erro exibida | ✅ |
| CT08 | Data de nascimento vazia | Deixar data em branco, clicar em "Próximo" | Mensagem de erro | Mensagem de erro exibida | ✅ |
| CT09 | Data futura | Digitar "15/05/2030", clicar em "Próximo" | Mensagem de erro | Avançou sem erro | ❌ |
| CT10 | Data inválida | Digitar "31/02/2030", clicar em "Próximo" | Mensagem de erro | Mensagem de erro exibida | ✅ |
| CT11 | Bio vazia | Deixar bio em branco | Não deve gerar erro | Nenhum erro, campo opcional | ✅ |

### Cadastro - Etapa 3

| ID | Descrição | Passos | Resultado esperado | Resultado obtido | Status |
|----|-----------|--------|-------------------|-----------------|--------|
| CT12 | Foto opcional | Não selecionar foto, clicar em "Finalizar" | Prossegue sem erro | Prosseguiu | ✅ |
| CT13 | Status de relacionamento | Selecionar uma opção | Opção selecionada | Seleção funcionou | ✅ |

### Login

| ID | Descrição | Passos | Resultado esperado | Resultado obtido | Status |
|----|-----------|--------|-------------------|-----------------|--------|
| CT14 | Email vazio | Deixar email em branco, clicar em "Entrar" | Mensagem de erro | Mensagem de erro exibida | ✅ |
| CT15 | Senha vazia | Deixar senha em branco, clicar em "Entrar" | Mensagem de erro | Mensagem de erro exibida | ✅ |
| CT16 | Campos válidos | Preencher email e senha | Botão "Entrar" habilita | Botão habilitado | ✅ |

## 5. 🐞 Bugs encontrados

| ID do bug | Descrição | Passo a passo para reproduzir | Severidade | Status |
|-----------|-----------|-------------------------------|------------|--------|
| BUG-001 | Validação de data futura não bloqueia corretamente | 1. Acessar tela de cadastro (etapa 2)<br>2. Selecionar data: 15/05/2030 (ano futuro, dia/mês válido)<br>3. Tentar avançar | Média | Aberto (comunicado ao dev) |

### Observação adicional

- ✅ Datas com dia/mês inexistente (ex: 31/02/2030) são corretamente bloqueadas
- ❌ Datas com ano futuro (ex: 15/05/2030) não são bloqueadas, permitindo avançar

## 6. 📊 Evidências

| ID | Descrição | Tipo |
|----|-----------|------|
| EV01 | Tela de cadastro etapa 1 - validações funcionando | 📸 Screenshot |
| EV02 | Tela de cadastro etapa 2 - validações (data futura bug) | 📸 Screenshot |
| EV03 | Tela de login - validações funcionando | 📸 Screenshot |

*Screenshots anexados separadamente*

## 7. ✅ Conclusão

| Pergunta | Resposta |
|----------|----------|
| O sistema está apto para produção? | ❌ Não |
| Precisa de ajustes? | ✅ Sim |
| Qual o nível de qualidade atual? | Parcial - Frontend apresenta boa qualidade nas validações básicas, porém o backend não está funcional, impedindo testes de integração. Foi identificado 1 bug de validação de data futura que precisa ser corrigido. |