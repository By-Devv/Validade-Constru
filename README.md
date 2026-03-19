# Validade Constru 🚧

> Sistema web de Gestão de Validade para Lojas de Materiais de Construção.

## ⚠️ Segurança

Antes de começar, leia [SECURITY.md](SECURITY.md) para diretrizes de segurança.

### Dados Sensíveis
- **NUNCA** comite arquivos `.env`
- **NUNCA** exponha chaves de API no código
- **SEMPRE** use variáveis de ambiente para configurações

---

## Funcionalidades

- **Dashboard**: Visão geral com total de itens vencendo em 30 dias, valor em risco e gráfico por categoria
- **Scanner**: Leitura de código de barras via câmera para entrada de produtos
- **Lista de Estoque**: Filtros por status (Vencidos, Vencendo, No Prazo) e por categoria
- **Gestão de Produtos**: CRUD completo de produtos e lotes
- **Exportação**: Exportar dados para CSV
- **Retiradas**: Sistema de notificações push para gestão de retiradas
- **Orçamentos**: Criação e gerenciamento de orçamentos
- **Missões**: Sistema gamificado de tarefas

## Regras de Negócio

- **Cimento/Argamassa**: Alerta 15 dias antes do vencimento
- **Outros produtos**: Alerta 30 dias antes do vencimento

### Cores por Status
- 🔴 **Vencido**: Produtos com data passada
- 🟡 **Alerta**: < 30 dias (ou < 15 dias para cimento/argamassa)
- 🟢 **OK**: > 60 dias até o vencimento

## Instalação

```bash
# Clone o repositório
git clone https://github.com/SEU_USUARIO/validade-constru.git
cd validade-constru

# Abra diretamente no navegador
# Ou use um servidor local:
npx serve .

# Ou abra com Python:
python -m http.server 8000
```

## Estrutura do Projeto

```
validade-constru/
├── index.html              # App web principal (standalone)
├── index.orcamento.html    # Módulo de orçamentos
├── manifest.json           # PWA manifest
├── package.json           # Configuração do projeto
├── src/                   # Código fonte (se aplicável)
└── README.md
```

## Como Usar

1. Abra `index.html` no navegador
2. Crie uma conta ou faça login
3. Comece a cadastrar seus produtos

## Tecnologias

- **HTML/CSS/JavaScript**: Vanilla JS para máxima performance
- **PWA**: Funciona offline como aplicativo web
- **localStorage**: Armazenamento local de dados

## Scripts Disponíveis

```bash
npm start          # Iniciar servidor local
npm run lint       # Verificar código
```

## Modo Demo

O aplicativo funciona completamente em modo demo, usando dados locais (localStorage). Não é necessário configurar banco de dados.

## Licença

MIT - Consulte [LICENSE](LICENSE) para detalhes.
