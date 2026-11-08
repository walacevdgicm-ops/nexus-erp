# 🏢 Nexus ERP — Sistema de Gestão Empresarial em Python

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?logo=sqlite&logoColor=white)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-informational)
![Status](https://img.shields.io/badge/status-em%20evolução-success)

ERP desktop completo para pequenas e médias empresas, que reúne **financeiro, faturamento, estoque, RH, controladoria e conciliação bancária** em uma única aplicação, com **controle de acesso por perfil (RBAC)** e **trilha de auditoria**.

Nasceu da minha experiência prática na área financeira (contas a pagar e receber, conciliação, notas fiscais) e foi pensado para resolver as dores reais do dia a dia de um escritório.

---

## ✨ Funcionalidades

| Módulo | O que faz |
|---|---|
| 🔐 **Login + RBAC** | Perfis Admin, Financeiro, Faturamento, Estoque e RH, cada um vendo só os módulos permitidos |
| 🔒 **Segurança** | Senhas com hash **PBKDF2-SHA256 + salt** (nunca em texto puro) e migração automática de senhas antigas |
| 👥 **Entidades** | Cadastro de clientes e fornecedores com **busca automática por CNPJ** em API pública |
| 💸 **Financeiro** | Contas a pagar e a receber, parcelamento, status e vencimentos |
| 🧾 **Faturamento** | Simulador de emissão de NF-e com chave de acesso de 44 dígitos |
| 📦 **Estoque** | Entrada e saída de produtos com saldo atualizado em tempo real |
| 👔 **RH (HCM)** | Cadastro de colaboradores e folha |
| 📊 **Controladoria** | **DRE estruturada**, orçamento por centro de custo e limite de gastos |
| 🏦 **Conciliação** | Importação de extrato **OFX** e simulação de sincronização Open Finance |
| 🕵️ **Auditoria** | Log de todas as ações (usuário, IP, tabela, descrição) |
| 📈 **Dashboard** | Gráficos executivos com Matplotlib e exportação de relatório |

## 🧱 Arquitetura

```
nexus_erp.py
├── BackendAPI            → camada de dados (SQLite), criação do schema, auditoria
└── AppControleFinanceiro → camada de interface (Tkinter), regras de negócio e RBAC
```

A separação entre **backend** e **interface** permite trocar o SQLite por um servidor (MySQL/PostgreSQL) ou expor a camada de dados como API no futuro.

## 🚀 Como executar

```bash
git clone https://github.com/walacevdgicm-ops/nexus-erp.git
cd nexus-erp
pip install -r requirements.txt
python nexus_erp.py
```

O banco `sistema_gestao_enterprise.db` é criado automaticamente na primeira execução.

### Usuários de demonstração

| Perfil | E-mail | Senha |
|---|---|---|
| Admin | admin@nexusdemo.com.br | admin123 |
| Financeiro | financeiro@nexusdemo.com.br | fin123 |
| Estoque | estoque@nexusdemo.com.br | est123 |
| RH | rh@nexusdemo.com.br | rh123 |

> São credenciais fictícias, apenas para testar a matriz de permissões. A empresa e o CNPJ usados no sistema também são fictícios.

## 🛣️ Próximos passos

- [ ] Integração real com a SEFAZ (NF-e homologação)
- [ ] Banco de dados em servidor (MySQL/PostgreSQL)
- [ ] Testes automatizados da camada `BackendAPI`
- [ ] Empacotamento em `.exe` com PyInstaller

## 📜 Versões anteriores

Este projeto é a evolução de versões que também estão no meu GitHub:
[Nexus ERP v1](https://github.com/walacevdgicm-ops/nexus-erp-v1) · [FinPanel](https://github.com/walacevdgicm-ops/finpanel) · [FinPanel SQLite](https://github.com/walacevdgicm-ops/finpanel-sqlite)

## 👨‍💻 Autor

**Walace Soares Vidigal Junior**: desenvolvedor de sistemas com experiência na área financeira e administrativa.
[GitHub](https://github.com/walacevdgicm-ops)

---
Licença [MIT](LICENSE)
