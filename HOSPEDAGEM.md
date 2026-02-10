# 🌐 Guia de Hospedagem Permanente - Acompanhamento SESI Esporte

## 📋 Índice
1. [Opção 1: Vercel (Recomendado)](#opção-1-vercel-recomendado)
2. [Opção 2: GitHub Pages](#opção-2-github-pages)
3. [Opção 3: Netlify](#opção-3-netlify)
4. [Sincronização com Google Drive](#sincronização-com-google-drive)
5. [Domínio Personalizado](#domínio-personalizado)

---

## Opção 1: Vercel (Recomendado)

**Vantagens:**
- ✅ Hospedagem gratuita e rápida
- ✅ Deploy automático via Git
- ✅ Subdomínio gratuito
- ✅ SSL/HTTPS incluído
- ✅ Suporte a variáveis de ambiente

### Passo 1: Criar Conta no Vercel

1. Acesse [vercel.com](https://vercel.com)
2. Clique em "Sign Up"
3. Escolha "Continue with GitHub" (recomendado)
4. Autorize o Vercel a acessar sua conta GitHub

### Passo 2: Conectar Repositório

1. No dashboard do Vercel, clique em "Add New..."
2. Selecione "Project"
3. Clique em "Import Git Repository"
4. Selecione o repositório `acompanhamento-sesi-esporte`
5. Clique em "Import"

### Passo 3: Configurar Projeto

1. **Project Name**: `acompanhamento-sesi-esporte`
2. **Framework Preset**: Selecione "Other"
3. **Root Directory**: `.` (raiz)
4. **Build Command**: Deixe em branco
5. **Output Directory**: `.` (raiz)
6. Clique em "Deploy"

### Resultado

Seu site estará disponível em:
```
https://acompanhamento-sesi-esporte.vercel.app
```

---

## Opção 2: GitHub Pages

**Vantagens:**
- ✅ Hospedagem gratuita
- ✅ Integrado com GitHub
- ✅ Sem necessidade de configuração
- ✅ Suporte a domínio personalizado

### Passo 1: Criar Repositório no GitHub

1. Acesse [github.com](https://github.com)
2. Clique em "New Repository"
3. Nome: `acompanhamento-sesi-esporte`
4. Descrição: "Sistema de acompanhamento de implantação SESI Esporte"
5. Selecione "Public"
6. Clique em "Create repository"

### Passo 2: Fazer Push do Código

```bash
cd /home/ubuntu/acompanhamento-sistema

# Adicionar remote
git remote add origin https://github.com/seu-usuario/acompanhamento-sesi-esporte.git

# Fazer push
git branch -M main
git push -u origin main
```

### Passo 3: Ativar GitHub Pages

1. Vá para "Settings" do repositório
2. Selecione "Pages" no menu lateral
3. Em "Source", selecione "Deploy from a branch"
4. Selecione "main" como branch
5. Clique em "Save"

### Resultado

Seu site estará disponível em:
```
https://seu-usuario.github.io/acompanhamento-sesi-esporte
```

---

## Opção 3: Netlify

**Vantagens:**
- ✅ Hospedagem gratuita
- ✅ Interface amigável
- ✅ Deploy contínuo
- ✅ Suporte a funções serverless

### Passo 1: Criar Conta no Netlify

1. Acesse [netlify.com](https://netlify.com)
2. Clique em "Sign up"
3. Escolha "Sign up with GitHub"
4. Autorize o Netlify

### Passo 2: Conectar Repositório

1. No dashboard, clique em "Add new site"
2. Selecione "Import an existing project"
3. Escolha "GitHub"
4. Selecione o repositório `acompanhamento-sesi-esporte`
5. Clique em "Deploy site"

### Resultado

Seu site estará disponível em:
```
https://acompanhamento-sesi-esporte.netlify.app
```

---

## Sincronização com Google Drive

### Como Funciona

O site possui funcionalidade nativa de backup:

1. **Botão "💾 Backup"**: Faz download dos dados em JSON
2. **Botão "📥 Restaurar"**: Restaura dados de um arquivo JSON
3. **Sincronização Automática**: A cada 5 minutos (local)

### Usar Google Drive para Backup

#### Opção A: Upload Manual

1. Clique em "💾 Backup" para fazer download
2. Acesse [drive.google.com](https://drive.google.com)
3. Crie uma pasta "Acompanhamento SESI Esporte"
4. Faça upload do arquivo JSON

#### Opção B: Sincronização Automática (Futuro)

Será implementada integração com Google Drive API para:
- ✅ Sincronização automática a cada 5 minutos
- ✅ Histórico de backups
- ✅ Restauração rápida

---

## Domínio Personalizado

### Registrar Domínio

Você pode registrar um domínio em:
- [Namecheap](https://namecheap.com)
- [GoDaddy](https://godaddy.com)
- [Google Domains](https://domains.google)
- [Registro.br](https://registro.br) (para .br)

**Sugestões de domínio:**
- `acompanhamento.sesidesporto.com.br`
- `sistema.sesidesporto.com.br`
- `implantacao.sesidesporto.com.br`

### Configurar Domínio no Vercel

1. No dashboard do Vercel, vá para "Settings"
2. Clique em "Domains"
3. Clique em "Add"
4. Digite seu domínio
5. Siga as instruções para configurar DNS

### Configurar Domínio no GitHub Pages

1. No repositório, vá para "Settings"
2. Clique em "Pages"
3. Em "Custom domain", digite seu domínio
4. Clique em "Save"
5. Configure os registros DNS no seu registrador

---

## 🔐 Segurança

### Proteger Dados Sensíveis

1. **Senha**: Já configurada como `SESIESPORTEAPP`
2. **HTTPS**: Automático em Vercel/GitHub Pages/Netlify
3. **Local Storage**: Dados armazenados apenas no navegador
4. **Backups**: Faça backup regularmente

### Recomendações

- ✅ Mude a senha regularmente
- ✅ Faça backup dos dados semanalmente
- ✅ Use um domínio com HTTPS
- ✅ Restrinja acesso ao repositório (privado)

---

## 📊 Monitoramento

### Verificar Status

**Vercel:**
- Dashboard: https://vercel.com/dashboard
- Analytics: Disponível no plano gratuito

**GitHub Pages:**
- Status: https://www.githubstatus.com

**Netlify:**
- Dashboard: https://app.netlify.com
- Analytics: Disponível no plano gratuito

---

## 🚀 Deploy Automático

### Vercel

Automático ao fazer push para `main`:
```bash
git add .
git commit -m "Atualização do sistema"
git push origin main
```

### GitHub Pages

Automático ao fazer push para `main`:
```bash
git push origin main
```

### Netlify

Automático ao fazer push para `main`:
```bash
git push origin main
```

---

## 🆘 Troubleshooting

### Site não carrega

- Verifique se o arquivo `index.html` está na raiz
- Verifique se o DNS está configurado corretamente
- Limpe o cache do navegador

### Dados desaparecem

- Verifique se o Local Storage está habilitado
- Faça backup regularmente
- Use o botão "📥 Restaurar" para recuperar dados

### Deploy falha

- Verifique se há erros no console
- Verifique se todos os arquivos foram commitados
- Tente fazer deploy novamente

---

## 📞 Suporte

Para mais informações:
- [Documentação Vercel](https://vercel.com/docs)
- [Documentação GitHub Pages](https://docs.github.com/en/pages)
- [Documentação Netlify](https://docs.netlify.com)

---

**Última atualização**: 09/02/2026  
**Versão**: 1.0.0
