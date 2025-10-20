# Exercício Dev Redesign 🤖

## Sobre o Projeto 📋
Sistema de automação para extração e processamento de dados de oportunidades de vendas, desenvolvido utilizando UiPath.

## Funcionalidades Principais ⚡
- 📊 Extração de dados de oportunidades de vendas
- 📝 Preenchimento automático de formulários
- 📧 Envio automático de emails com resultados
- 🔄 Integração com UiPath Orchestrator

## Como Usar 🚀
1. Configure as credenciais do Orchestrator
2. Execute o processo `ExtractionSalesOpportunities`
3. Os dados serão extraídos e enviados para a fila
4. Execute o processo `ProcessFormsData`
5. Acompanhe o status pelo email de notificação

## Pré-requisitos 📌
- UiPath Studio 25.10.0+
- Acesso ao UiPath Orchestrator
- Conta Gmail configurada
- Edge Browser

## Estrutura do Projeto 🏗️
```
├── ExtractionSalesOpportunities/    # Extração de dados
└── ProcessFormsData/                # Processamento de formulários
```

## Documentação Técnica 📚
Para informações técnicas detalhadas sobre a implementação, configurações e manutenção, consulte nossa [Documentação Técnica](technical_doc.md).

## Suporte 💬
Para suporte, entre em contato via email: leticia.ssilva.rj@gmail.com

## Licença 📄
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.