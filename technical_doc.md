# Documentação Técnica 🔧

## Arquitetura do Sistema 🏗️

### ExtractionSalesOpportunities 📊
- **Main.xaml**: Orquestrador principal do processo de extração
- **WebsiteDataExtraction.xaml**: Extração de dados do site usando UI Automation
- **SendToOrchestrator.xaml**: Envio dos dados para fila do Orchestrator

### ProcessFormsData 📝
- **Main.xaml**: Controlador principal do processo de formulários
- **GetFromOrchestrator.xaml**: Recuperação de dados da fila
- **FillForms.xaml**: Automação de preenchimento de formulários
- **SendEmail.xaml**: Notificação por email do processo

## Fluxo de Dados 🔄

1. **Extração** 📥
   - Acessa website via Edge Browser
   - Extrai dados usando UiPath UI Automation
   - Estrutura dados em DataTable
   - Envia para fila "OpportunitiesData"

2. **Processamento** ⚙️
   - Recupera itens da fila
   - Processa cada item individualmente
   - Preenche formulário Google Forms
   - Atualiza status na fila
   - Envia email de notificação

## Dependências 📦

```json
{
  "UiPath.Excel.Activities": "[3.2.1]",
  "UiPath.GSuite.Activities": "[3.4.10]",
  "UiPath.Mail.Activities": "[2.4.10]",
  "UiPath.System.Activities": "[25.10.0]",
  "UiPath.Testing.Activities": "[25.10.0]",
  "UiPath.UIAutomation.Activities": "[25.10.16]"
}
```

## Configurações Técnicas ⚙️

### Orchestrator
- **Fila**: OpportunitiesData
- **Assets**: Credenciais Gmail
- **Folder**: leticia.ssilva.rj@gmail.com's workspace

### Email
- **Serviço**: Gmail via GSuite Activities
- **Template**: HTML com link para repositório
- **Tratamento de Erros**: Try-Catch com logs

## Tratamento de Erros 🛡️

1. **Níveis de Log**:
   - Info: Progresso normal
   - Error: Falhas no processo

2. **Estratégias**:
   - Try-Catch em operações críticas
   - Logs detalhados de erros
   - Notificação por email em falhas

## Performance 📈

- Processamento item a item
- Retry automático em falhas de rede
- Timeout configurado para operações

## Segurança 🔒

- Credenciais armazenadas no Orchestrator
- Senhas nunca expostas no código
- Logs excluem dados sensíveis

## Manutenção 🔧

### Pontos de Atenção
- Atualizar seletores UI em caso de mudanças no site
- Verificar versões de dependências
- Monitorar logs de erro no Orchestrator

### Melhorias Futuras
- Implementar relatórios detalhados
- Adicionar dashboards de monitoramento
- Expandir validações de dados