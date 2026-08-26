# 📊 Acompanhamento SESI Esporte

Sistema de acompanhamento de implantação com gerenciamento de tarefas e atas de reunião.

## 🚀 Características

- ✅ **Tarefas**: Criar, editar e acompanhar tarefas com status, responsável e datas
- ✅ **Atas de Reunião**: Registrar alinhamentos, participantes e observações
- ✅ **Dashboard**: Visualizar progresso com gráficos em tempo real
- ✅ **Timeline**: Visualizar cronograma de tarefas
- ✅ **Filtros e Busca**: Encontrar tarefas rapidamente
- ✅ **Exportação**: Exportar dados em CSV e PDF
- ✅ **Autenticação**: Visualização livre + edição com senha
- ✅ **Local Storage**: Dados persistem no navegador
- ✅ **Backup Automático**: Sincronização com Google Drive

## 🔐 Acesso

- **Visualização**: Clique em "Apenas Visualizar" (sem senha)
-
## 💾 Backup com Google Drive

### Configuração Inicial

1. **Autorizar Google Drive**:
   - Clique no botão "Sincronizar com Google Drive"
   - Faça login com sua conta Google
   - Autorize o acesso ao Google Drive

2. **Pasta de Backup**:
   - Uma pasta chamada "Acompanhamento SESI Esporte" será criada automaticamente
   - Os dados serão salvos em formato JSON

### Sincronização Automática

- ✅ Backup automático a cada 5 minutos
- ✅ Download automático ao abrir o site
- ✅ Histórico de backups (últimas 10 versões)

### Recuperar Dados

1. Clique em "Sincronizar com Google Drive"
2. Selecione o backup desejado
3. Os dados serão restaurados automaticamente

## 📱 Responsividade

- ✅ Desktop (1920px+)
- ✅ Tablet (768px - 1024px)
- ✅ Mobile (320px - 767px)

## 🛠️ Tecnologias

- HTML5
- CSS3
- JavaScript (Vanilla)
- Chart.js (Gráficos)
- Google Drive API (Backup)

## 📦 Implantação

### Vercel (Recomendado - Gratuito)

```bash
# 1. Instale o Vercel CLI
npm install -g vercel

# 2. Faça login
vercel login

# 3. Implante o projeto
vercel

# 4. Configure o domínio personalizado (opcional)
vercel domains add seu-dominio.com
```

### GitHub Pages

```bash
# 1. Crie um repositório no GitHub
# 2. Faça push do código
git push origin main

# 3. Ative GitHub Pages nas configurações
# Settings > Pages > Source: main branch
```

### Netlify

```bash
# 1. Instale o Netlify CLI
npm install -g netlify-cli

# 2. Faça login
netlify login

# 3. Implante
netlify deploy --prod
```

## 🔄 Sincronização com Google Drive

### Como Funciona

1. **Autenticação OAuth 2.0**: Acesso seguro ao Google Drive
2. **Armazenamento**: Dados salvos em JSON na pasta do Google Drive
3. **Sincronização**: Automática a cada 5 minutos
4. **Versionamento**: Mantém histórico dos últimos backups

### Estrutura de Backup

```
Google Drive/
├── Acompanhamento SESI Esporte/
│   ├── backup-2026-02-09-09-00-00.json
│   ├── backup-2026-02-09-09-05-00.json
│   └── backup-2026-02-09-09-10-00.json
```

## 📝 Estrutura de Dados

### Tarefa

```json
{
  "id": 1707472800000,
  "description": "Configurar ambiente de produção",
  "responsible": "João Silva",
  "phase": "desenvolvimento",
  "status": "in-progress",
  "date": "2026-02-09",
  "deadline": "2026-02-15",
  "notes": "Aguardando aprovação"
}
```

### Ata de Reunião

```json
{
  "id": 1707472800001,
  "date": "2026-02-09",
  "participants": "João Silva, Maria Santos",
  "achievements": "Discussão sobre cronograma",
  "notes": "Próxima reunião em 15/02"
}
```

## 🐛 Troubleshooting

### Dados não aparecem após reload

- Verifique se o Local Storage está habilitado
- Limpe o cache do navegador
- Tente em modo normal (não privado)

### Sincronização com Google Drive não funciona

- Verifique a conexão com a internet
- Autorize novamente o acesso ao Google Drive
- Verifique se a pasta foi criada no Google Drive

### Exportação em PDF não funciona

- Atualize o navegador
- Tente em outro navegador
- Verifique se o JavaScript está habilitado

## 📞 Suporte

Para reportar problemas ou sugerir melhorias, entre em contato com o administrador do sistema.

## 📄 Licença

Sistema interno - Todos os direitos reservados

---

**Versão**: 1.0.0  
**Última atualização**: 09/02/2026
