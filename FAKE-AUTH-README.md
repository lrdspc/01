# Sistema de Autenticação Fake - Modo Desenvolvimento

## 📋 Visão Geral

Para facilitar o desenvolvimento, foi implementado um sistema de login fake que permite acesso rápido ao sistema sem necessidade de configurar autenticação real.

## 🔑 Credenciais Fake

Durante o desenvolvimento, você pode usar as seguintes credenciais:

- **E-mail:** `admin@brasilit.com`
- **Senha:** `123456`

## 🛠️ Como Usar

### 1. Login Automático
Na página de login (`/login`), em modo de desenvolvimento, você verá uma seção azul com as credenciais fake e um botão "Preencher Credenciais Fake" que automaticamente preenche os campos.

### 2. Login Manual
Digite manualmente:
- E-mail: `admin@brasilit.com`
- Senha: `123456`

### 3. Funcionamento
- O sistema detecta automaticamente se são credenciais fake
- Cria uma sessão local simulada sem chamar o Supabase
- O usuário fake tem as seguintes propriedades:
  - ID: `fake-user-id`
  - Nome: `Admin Brasilit`
  - Role: `admin`

## 🔧 Arquivos Modificados

### `src/lib/fake-auth.ts`
- Constantes das credenciais fake
- Funções de verificação de modo de desenvolvimento
- Configurações centralizadas

### `src/lib/auth.context.tsx`
- Modificado para suportar login fake
- Logout fake
- Verificação de modo de desenvolvimento

### `src/pages/auth/Login.tsx`
- Interface atualizada com seção de credenciais fake
- Botão de preenchimento automático
- Só exibe em modo de desenvolvimento

## 🚀 Modo de Produção

Em produção, o sistema de login fake é automaticamente desabilitado:
- A seção de credenciais fake não aparece
- Apenas login real com Supabase funciona
- Segurança mantida

## 🎯 Benefícios

1. **Desenvolvimento Rápido:** Acesso instantâneo sem configurar contas
2. **Testes Facilitados:** Credenciais consistentes para todos os desenvolvedores
3. **Segurança:** Automaticamente desabilitado em produção
4. **Flexibilidade:** Fácil de modificar as credenciais fake

## ⚠️ Importante

- Este sistema é **APENAS para desenvolvimento**
- Em produção, use sempre autenticação real
- As credenciais fake são visíveis no código (não há problema em desenvolvimento)
- O sistema detecta automaticamente o ambiente
