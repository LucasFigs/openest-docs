# RELATÓRIO DE TESTES AUTOMATIZADOS - OPENEST

**Projeto:** Openest  
**Responsável pelos testes:** Leandro Soares  
**Data de conclusão:** 13/05/2026  
**Ferramenta utilizada:** Cypress  

---

## 1. Escopo dos Testes

Foram desenvolvidos e executados testes automatizados para validar as principais funcionalidades da plataforma Openest, conforme as tasks definidas no backlog do projeto.

---

## 2. Resumo Geral

| Task | Descrição | Status |
|------|-----------|--------|
| L003 | Testar endpoints de autenticação | Concluído |
| L004 | Testar upload de foto | Concluído |
| L005 | Testar integracao frontend/backend | Concluído |
| L006 | Testar validacoes de formulario | Concluído |
| L007 | Testar endpoints de busca e match | Pendente (nao implementado) |
| L008 | Testar tela de perfil | Concluído |
| L009 | Testar tela de descoberta | Concluído |
| L010 | Testar modo discreto | Concluído |
| L012 | Testar chat | Concluído |
| L013 | Testar admin | Concluído |

---

## 3. Detalhamento por Task

### 3.1 L003 - Testar endpoints de autenticacao

**Descricao:** Testar cadastro e login de usuarios.

**Testes realizados:**
- Login com dados validos
- Login com senha errada
- Login com email inexistente

**Resultado:** Aprovado.

---

### 3.2 L004 - Testar upload de foto

**Descricao:** Testar envio de foto de perfil.

**Testes realizados:**
- Verificar botao de adicionar foto
- Upload de imagem com sucesso

**Resultado:** Aprovado.

---

### 3.3 L005 - Testar integracao frontend/backend

**Descricao:** Validar comunicacao entre frontend e backend no fluxo de autenticacao.

**Testes realizados:**
- Cadastro de novo usuario
- Login com sucesso e redirecionamento
- Persistencia ao recarregar pagina
- Logout (pendente - funcionalidade nao implementada)
- Rota protegida redireciona sem token

**Resultado:** Parcialmente aprovado (logout pendente).

---

### 3.4 L006 - Testar validacoes de formulario

**Descricao:** Validar mensagens de erro nos formularios.

**Testes realizados:**
- Login com email vazio
- Login com senha vazia
- Login com email invalido
- Cadastro com senha curta
- Cadastro com senhas diferentes
- Cadastro com nome vazio
- Cadastro com data vazia

**Resultado:** Aprovado.

---

### 3.5 L007 - Testar endpoints de busca e match

**Descricao:** Validar fluxo de curtidas e match entre usuarios.

**Testes realizados:** Nao foi possivel executar.

**Resultado:** Pendente. Funcionalidade nao implementada no backend no momento dos testes.

---

### 3.6 L008 - Testar tela de perfil

**Descricao:** Validar edicao de dados do perfil.

**Testes realizados:**
- Acessar tela de perfil
- Verificar campos visiveis
- Editar nome
- Editar biografia
- Alterar status (Individuo/Casal)
- Alterar idade

**Resultado:** Aprovado.

---

### 3.7 L009 - Testar tela de descoberta

**Descricao:** Validar tela de discovery, botoes e filtros.

**Testes realizados:**
- Acessar tela de descoberta
- Verificar cards de perfis
- Botao de curtir
- Botao de passar
- Botao de filtros
- Abrir modal de filtros
- Alterar distancia
- Alterar faixa etaria
- Selecionar status de relacionamento
- Selecionar interesse
- Aplicar filtros
- Curtir um perfil
- Passar um perfil

**Resultado:** Aprovado.

---

### 3.8 L010 - Testar modo discreto

**Descricao:** Validar toggle do modo discreto na interface.

**Testes realizados:**
- Acessar tela de configuracoes
- Verificar toggle do modo discreto
- Ativar modo discreto
- Desativar modo discreto
- Alternar multiplas vezes

**Resultado:** Aprovado. Efeito real na busca nao testado por falta de segundo usuario.

---

### 3.9 L012 - Testar chat

**Descricao:** Validar fluxo de match e envio de mensagens.

**Testes realizados:**
- Dar match com outro perfil
- Enviar mensagem no chat
- Voltar para tela de discovery
- Acessar lista de chats
- Entrar na conversa pela lista
- Verificar persistencia da mensagem

**Resultado:** Aprovado.

---

### 3.10 L013 - Testar admin

**Descricao:** Validar acesso e funcionalidades do painel administrativo.

**Testes realizados:**
- Login com credenciais de admin
- Acessar dashboard /admin
- Alternar para grafico de Status de Denuncias
- Voltar para grafico de Usuarios e Matches

**Resultado:** Aprovado.

---

## 4. Pendencias e Observacoes

| Item | Descricao |
|------|-----------|
| Logout | Funcionalidade nao implementada no frontend |
| Match entre usuarios | Endpoint nao implementado no backend |
| Modo discreto (efeito real) | Necessario segundo usuario para validar se some da busca |
| Chat (match automatico) | Depende da funcionalidade de match |

---

## 5. Arquivos de Teste

Os seguintes arquivos foram criados na pasta `cypress/e2e/`:

- L003-autenticacao.cy.js
- L004-upload-foto.cy.js
- L005-integracao.cy.js
- L006-validacoes-form.cy.js
- L007-busca-match.cy.js (pendente)
- L008-perfil.cy.js
- L009-descoberta.cy.js
- L010-modo-discreto.cy.js
- L012-chat.cy.js
- L013-admin.cy.js

---

## 6. Conclusao

Os testes automatizados cobriram as principais funcionalidades do frontend da plataforma Openest. As pendencias identificadas estao relacionadas a funcionalidades ainda nao implementadas no backend (match e logout) ou que dependem de cenarios especificos (modo discreto com dois usuarios).

O framework Cypress se mostrou adequado para o projeto, permitindo a criacao de testes end-to-end de forma eficiente.

---

**Relatorio elaborado por:** Leandro Soares  
**Data:** 13/05/2026