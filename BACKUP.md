# 💾 Guia de Backup e Sincronização

## 📋 Índice
1. [Backup Local](#backup-local)
2. [Backup em Google Drive](#backup-em-google-drive)
3. [Restauração de Dados](#restauração-de-dados)
4. [Sincronização Automática](#sincronização-automática)

---

## Backup Local

### Como Fazer Backup

1. **Acesse o site**: https://acompanhamento-sesi-esporte.vercel.app
2. **Clique em "💾 Backup"** no canto superior direito
3. **Arquivo será baixado** com o nome: `backup-acompanhamento-YYYY-MM-DD-HH-MM-SS.json`

### Estrutura do Arquivo de Backup

```json
{
  "timestamp": "2026-02-09T09:00:00.000Z",
  "tasks": [
    {
      "id": 1707472800000,
      "description": "Configurar ambiente",
      "responsible": "João Silva",
      "phase": "desenvolvimento",
      "status": "in-progress",
      "date": "2026-02-09",
      "deadline": "2026-02-15",
      "notes": "Aguardando aprovação"
    }
  ],
  "minutes": [
    {
      "id": 1707472800001,
      "date": "2026-02-09",
      "participants": "João Silva, Maria Santos",
      "achievements": "Discussão sobre cronograma",
      "notes": "Próxima reunião em 15/02"
    }
  ],
  "version": "1.0.0"
}
```

### Onde Armazenar

**Recomendações:**
- 📁 Google Drive
- 📁 Dropbox
- 📁 OneDrive
- 💻 Pasta local no computador
- 🔐 Servidor de backup corporativo

---

## Backup em Google Drive

### Passo 1: Criar Pasta no Google Drive

1. Acesse [drive.google.com](https://drive.google.com)
2. Clique em "Novo" > "Pasta"
3. Nome: `Acompanhamento SESI Esporte`
4. Clique em "Criar"

### Passo 2: Fazer Backup Manual

1. **No site**, clique em "💾 Backup"
2. **Arquivo será baixado** no seu computador
3. **Abra Google Drive** e entre na pasta criada
4. **Faça upload** do arquivo JSON

### Passo 3: Organizar Backups

Crie subpastas por mês:
```
Acompanhamento SESI Esporte/
├── 2026-02/
│   ├── backup-2026-02-09-09-00-00.json
│   ├── backup-2026-02-09-14-30-00.json
│   └── backup-2026-02-10-10-15-00.json
├── 2026-03/
│   └── ...
```

### Passo 4: Configurar Sincronização (Futuro)

Será implementada sincronização automática com Google Drive:

```javascript
// Exemplo de integração futura
const googleDriveSync = {
  enabled: true,
  interval: 5 * 60 * 1000, // 5 minutos
  folderId: "FOLDER_ID_DO_GOOGLE_DRIVE"
};
```

---

## Restauração de Dados

### Restaurar de um Backup

1. **Acesse o site**: https://acompanhamento-sesi-esporte.vercel.app
2. **Faça login** com a senha: `SESIESPORTEAPP`
3. **Clique em "📥 Restaurar"** no canto superior direito
4. **Selecione o arquivo** `backup-acompanhamento-*.json`
5. **Clique em "Abrir"**
6. **Confirmação**: "Backup restaurado com sucesso!"
7. **Página será recarregada** com os dados restaurados

### Restaurar Manualmente

Se o botão não funcionar:

1. **Abra o arquivo** `backup-acompanhamento-*.json` em um editor de texto
2. **Copie o conteúdo JSON**
3. **Abra o console** do navegador (F12)
4. **Execute o comando**:

```javascript
// Restaurar tarefas
const backup = JSON.parse(`{COLE_O_JSON_AQUI}`);
localStorage.setItem('tasks', JSON.stringify(backup.tasks));
localStorage.setItem('minutes', JSON.stringify(backup.minutes));
location.reload();
```

---

## Sincronização Automática

### Como Funciona

O site cria backups locais automaticamente:

- ✅ **Intervalo**: A cada 5 minutos
- ✅ **Armazenamento**: Local Storage do navegador
- ✅ **Limite**: Últimos 10 backups
- ✅ **Acesso**: Via console do navegador

### Visualizar Backups Locais

1. **Abra o console** do navegador (F12)
2. **Execute o comando**:

```javascript
// Ver todos os backups
const backups = JSON.parse(localStorage.getItem('backups')) || [];
console.table(backups);

// Ver último backup
const lastBackup = backups[backups.length - 1];
console.log(lastBackup);

// Restaurar backup específico
const backup = backups[0]; // Primeiro backup
localStorage.setItem('tasks', JSON.stringify(backup.tasks));
localStorage.setItem('minutes', JSON.stringify(backup.minutes));
location.reload();
```

### Limpar Backups Locais

```javascript
// Limpar todos os backups locais
localStorage.removeItem('backups');
console.log('Backups locais removidos');
```

---

## 🔄 Estratégia de Backup Recomendada

### Backup Diário

```
Segunda a Sexta:
- 09:00 - Backup automático (local)
- 17:00 - Download manual para Google Drive
```

### Backup Semanal

```
Toda sexta-feira:
- 17:00 - Backup completo em Google Drive
- Verificar integridade dos dados
```

### Backup Mensal

```
Primeiro dia do mês:
- Fazer backup completo
- Arquivar em pasta separada
- Manter por 12 meses
```

---

## ⚠️ Recuperação em Caso de Emergência

### Cenário 1: Dados Perdidos

1. **Verifique os backups locais** (console)
2. **Restaure do Google Drive** (botão 📥)
3. **Se não houver backup**: Contate o administrador

### Cenário 2: Arquivo Corrompido

1. **Tente restaurar backup anterior**
2. **Se não funcionar**: Verifique o JSON em um validador
3. **Corrija manualmente** se necessário

### Cenário 3: Sincronização Falha

1. **Faça backup manual** (botão 💾)
2. **Verifique a conexão com internet**
3. **Tente novamente após alguns minutos**

---

## 📊 Checklist de Backup

- [ ] Backup diário realizado
- [ ] Arquivo salvo em Google Drive
- [ ] Arquivo verificado (pode ser restaurado)
- [ ] Senha atualizada regularmente
- [ ] Acesso ao Google Drive funcionando
- [ ] Espaço em disco disponível
- [ ] Backup mensal arquivado

---

## 🛠️ Ferramentas Úteis

### Validar JSON

```javascript
// No console do navegador
const backup = JSON.parse(localStorage.getItem('backups')[0]);
console.log('Backup válido:', backup);
```

### Comparar Backups

```javascript
// Comparar dois backups
const backup1 = JSON.parse(localStorage.getItem('backups')[0]);
const backup2 = JSON.parse(localStorage.getItem('backups')[1]);

console.log('Tarefas em backup1:', backup1.tasks.length);
console.log('Tarefas em backup2:', backup2.tasks.length);
```

### Exportar para CSV

```javascript
// Exportar tarefas para CSV
const tasks = JSON.parse(localStorage.getItem('tasks')) || [];
const csv = [
  ['ID', 'Descrição', 'Responsável', 'Status', 'Data', 'Prazo'],
  ...tasks.map(t => [t.id, t.description, t.responsible, t.status, t.date, t.deadline])
].map(row => row.join(',')).join('\n');

const blob = new Blob([csv], { type: 'text/csv' });
const url = URL.createObjectURL(blob);
const a = document.createElement('a');
a.href = url;
a.download = 'tarefas.csv';
a.click();
```

---

## 📞 Suporte

Para problemas com backup:
1. Verifique este guia
2. Consulte o README.md
3. Contate o administrador do sistema

---

**Última atualização**: 09/02/2026  
**Versão**: 1.0.0
