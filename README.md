# DIO-Bradesco-Azure-DB
# Laboratório Prático: Configuração de Azure SQL Database

## 🎯 Descrição do Desafio

Este repositório documenta o processo completo de configuração de uma instância de Banco de Dados SQL na Microsoft Azure, desenvolvido como parte do desafio da DIO. O objetivo principal é criar um material de referência técnico com:

- **Passo a passo** da implementação
- **Anotações** sobre decisões técnicas
- **Melhores práticas** identificadas
- **Soluções** para desafios comuns

## 📦 Entregáveis Técnicos

| Componente | Descrição |
|------------|-----------|
| `setup-azure-sql.md` | Guia técnico de provisionamento |
| `troubleshooting.md` | Registro de erros e soluções |
| `cost-management.md` | Dicas de otimização de custos |
| `/templates` | Scripts ARM/CLI reutilizáveis |

## ⚙️ Fluxo de Trabalho Documentado

1. **Criação do Servidor SQL**
   - Configuração de região e tier
   - Definição de regras de firewall

2. **Configuração do Banco de Dados**
   - Seleção do modelo de compra (DTU/vCore)
   - Ajuste de performance

3. **Gestão de Segurança**
   - Autenticação SQL vs Azure AD
   - Configuração de auditoria

4. **Monitoramento**
   - Alertas de performance
   - Métricas essenciais

## 📚 Recursos Incluídos

```bash
.
├── docs/
│   ├── azure-best-practices.md
│   └── security-checklist.md
├── scripts/
│   ├── deploy-arm-template.json
│   └── automated-backup.ps1
└── architecture-diagram.png

🔍 Dicas de Implementação
-- Exemplo: Consulta para monitorar conexões
SELECT 
    client_ip_address,
    COUNT(*) as connection_count
FROM sys.dm_exec_connections
GROUP BY client_ip_address
ORDER BY connection_count DESC;
