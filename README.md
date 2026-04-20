# 🛡️ RailsGuardian

**RailsGuardian** é um agente de IA especializado em desenvolvimento seguro de aplicações Ruby on Rails. Ele combina implementação de código com revisão automática de segurança, garantindo que suas features sejam desenvolvidas seguindo as melhores práticas de segurança.

## 🎯 O que o RailsGuardian faz?

O RailsGuardian atua em duas frentes:

1. **Implementação de Código**: Cria, modifica e refatora código Ruby on Rails conforme solicitado
2. **Revisão de Segurança Automática**: Analisa todos os arquivos alterados em busca de vulnerabilidades

### Fluxo de Trabalho

```
Solicitação → Implementação → Revisão de Segurança → Correções Automáticas → Relatório
```

## 🚀 Como Usar

### Sintaxe Básica

Para usar o RailsGuardian, mencione o agente com `@RailsGuardian` seguido da sua solicitação:

```
@RailsGuardian [sua solicitação]
```

### Exemplos Práticos

#### 1. Criar uma nova funcionalidade
```
@RailsGuardian crie um CRUD completo para gerenciar artigos
```

#### 2. Adicionar autenticação
```
@RailsGuardian adicione autenticação ao controller de posts
```

#### 3. Implementar autorização
```
@RailsGuardian implemente autorização para que usuários só vejam seus próprios pedidos
```

#### 4. Criar rotas
```
@RailsGuardian crie rotas RESTful para o recurso de comentários
```

#### 5. Gerar migração
```
@RailsGuardian crie uma migration para adicionar campo email_verified aos users
```

#### 6. Corrigir bugs
```
@RailsGuardian corrija o bug no método de busca que permite SQL injection
```

#### 7. Apenas revisar segurança (sem implementar)
```
@RailsGuardian faça uma auditoria de segurança no UserController
```

## 🔒 Verificações de Segurança

O RailsGuardian verifica automaticamente:

### Autenticação
- ✅ Rotas públicas expondo dados privados
- ✅ Falta de `authenticate_user!`
- ✅ Bypass de sessão
- ✅ Fluxos inseguros de "lembrar-me"

### Autorização
- ✅ IDOR (Insecure Direct Object Reference)
- ✅ Escalação de privilégios
- ✅ Falta de verificações de política
- ✅ Usuários acessando registros que não possuem

### Validação de Entrada
- ✅ SQL Injection
- ✅ Command Injection
- ✅ Queries dinâmicas inseguras
- ✅ Strong Parameters fracos
- ✅ Mass Assignment
- ✅ Manipulação insegura de arquivos

### Segurança Rails
- ✅ CSRF desabilitado
- ✅ XSS (Cross-Site Scripting)
- ✅ Uso inseguro de `raw`
- ✅ Uso inseguro de `html_safe`
- ✅ `render html:` sem sanitização
- ✅ Redirects inseguros
- ✅ Uploads inseguros

### Exposição de Dados
- ✅ Logs com tokens/senhas
- ✅ Vazamento de dados pessoais (emails, CPF, etc.)
- ✅ Dados de debug em produção
- ✅ Stack traces expostos

### Dependências
- ✅ Gems vulneráveis
- ✅ Pacotes sensíveis à segurança desatualizados

### Performance e Boas Práticas
- ✅ Queries N+1 quando óbvias
- ✅ Falta de limites de paginação
- ✅ Queries sem limites
- ✅ Endpoints caros sem autorização

## 📋 Formato do Relatório

Após cada execução, o RailsGuardian fornece um relatório estruturado:

```
IMPLEMENTAÇÃO CONCLUÍDA:
- Lista das funcionalidades implementadas

ARQUIVOS ALTERADOS:
- Lista dos arquivos criados ou modificados

REVISÃO DE SEGURANÇA:
- Análise realizada

RISCOS ENCONTRADOS:
- Vulnerabilidades identificadas

CORREÇÕES APLICADAS:
- Problemas corrigidos automaticamente

RECOMENDAÇÕES MANUAIS:
- Ações que requerem atenção humana
```

## 📁 Arquivos Monitorados

O RailsGuardian verifica automaticamente estes arquivos quando relevante:

- `config/routes.rb`
- `app/controllers/*`
- `app/models/*`
- `app/views/*`
- `app/helpers/*`
- `app/services/*`
- `db/migrate/*`
- `config/initializers/*`
- `Gemfile`
- `Gemfile.lock`

## 💡 Dicas de Uso

### ✅ Boas Práticas

1. **Seja específico**: Quanto mais detalhes, melhor o resultado
   ```
   ❌ @RailsGuardian crie um controller
   ✅ @RailsGuardian crie um controller de Posts com ações index, show, create, update e destroy
   ```

2. **Use para refatoração segura**:
   ```
   @RailsGuardian refatore o método de busca para prevenir SQL injection
   ```

3. **Combine implementação e auditoria**:
   ```
   @RailsGuardian adicione upload de imagens e garanta que está seguro
   ```

### 🎯 Quando Usar

- ✅ Criar novas features
- ✅ Modificar código existente
- ✅ Refatorar código
- ✅ Corrigir bugs de segurança
- ✅ Auditar código
- ✅ Implementar autenticação/autorização
- ✅ Criar migrações
- ✅ Adicionar validações

## ⚙️ Comandos de Validação

O RailsGuardian pode executar comandos para validar a implementação:

- `bundle exec brakeman` - Scanner de segurança estático
- `bundle exec rubocop` - Linter de código
- `bundle exec rspec` - Testes
- `bundle exec rails test` - Testes
- `bundle exec rails routes` - Verificar rotas

**Nota**: O agente nunca executa comandos destrutivos.

## 🔧 Configuração

O RailsGuardian está pronto para uso sem configuração adicional. Ele detecta automaticamente:

- Estrutura da aplicação Rails
- Gems instaladas
- Configurações de segurança
- Padrões do projeto

## 🤝 Contribuindo

Este é um agente de IA que evolui com o uso. Se encontrar casos que deveriam ser verificados:

1. Relate o cenário
2. Sugira a verificação
3. Compartilhe exemplos
