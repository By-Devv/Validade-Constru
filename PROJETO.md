# Validade Constru - MVP
Gestão de Validade para Lojas de Materiais de Construção

## Estrutura de Pastas

```
validade-constru/
├── index.html              # App web principal (standalone)
├── index.orcamento.html    # Módulo de orçamentos
├── manifest.json           # PWA manifest
├── package.json           # Configuração do projeto
├── README.md
├── TUTORIAL.md
├── PROJETO.md
├── SECURITY.md
├── LICENSE
└── .gitignore
```

## Regras de Negócio

### Cálculo de Criticidade
- **Cimento/Argamassa**: Alerta 15 dias antes do vencimento (risco de empedramento)
- **Outros produtos**: Alerta 30 dias antes do vencimento

### Cores por Status
- 🔴 **Vencido**: Produtos com data passada
- 🟡 **Alerta**: < 30 dias (ou < 15 dias para cimento/argamassa)
- 🟢 **OK**: > 60 dias até o vencimento

## Armazenamento de Dados

O aplicativo utiliza **localStorage** para armazenamento de dados locais.

### Estrutura de Dados

#### Produtos
```javascript
{
  id: string,
  nome: string,
  ean_code: string | null,
  categoria: string,
  marca: string | null,
  quantidade: number,
  preco_compra: number,
  preco_venda: number,
  min_estoque_alerta: number,
  created_at: string
}
```

#### Lotes
```javascript
{
  id: string,
  produto_id: string,
  data_fabricacao: string | null,
  data_validade: string,
  quantidade: number,
  created_at: string
}
```

#### Retiradas
```javascript
{
  id: number,
  cliente: string,
  telefone: string,
  observacoes: string,
  produtos: RetiradaProduto[],
  data: string,
  status: 'pendente' | 'concluida'
}
```

## Funcionalidades

1. **Dashboard** - Visão geral com estatísticas
2. **Scanner** - Leitura de código de barras
3. **Lista de Estoque** - Gerenciamento de produtos e lotes
4. **Exportação** - Exportar dados para CSV
5. **Retiradas** - Sistema de retirada de produtos
6. **Notificações Push** - Alertas de retiradas
7. **Orçamentos** - Criação de orçamentos
8. **Missões** - Sistema gamificado de tarefas

## Tecnologias

- HTML5 / CSS3 / JavaScript (Vanilla)
- PWA (Progressive Web App)
- localStorage para persistência
- Web Notifications API para push
- Barcode Detection API para scanner

## Como Funciona

1. Abra `index.html` no navegador
2. Crie uma conta de usuário
3. Cadastre seus produtos
4. Escaneie códigos de barras
5. Gerencie retiradas de clientes
6. Exporte relatórios

## Suporte a PWA

O app funciona como PWA:
- Instalável no desktop e mobile
- Funciona offline
- Notificações push
- Acesso à câmera para scanner
