<p align="center">
  <img src="doc/imagens/logo.png" alt="Logo" width="160"/>
  &nbsp;&nbsp;
  <img src="doc/imagens/badge.png" alt="Superbadge Badge" width="120"/>
</p>

# Superbadge: Screen Flow Distribution

Projeto Salesforce DX com os metadados do **Screen Flow Distribution Superbadge** do Trailhead.

<p align="center">
  <img src="doc/imagens/trailhead.png" alt="Trailhead" width="220"/>
</p>

---

## Desafios

### Desafio 1 — Hive App Home Page + Quick Action na Conta

<p align="center">
  <img src="doc/imagens/mascote.png" alt="Mascote" width="180"/>
</p>

- Flow **Provider** adicionado à Página Inicial do Hive App (`Hive_Provider_Home_Page`)
- Quick Action **Create New Provider** criada no objeto Conta e adicionada ao layout

---

### Desafio 2 — Botão no Contato + Barra de Utilitários

<p align="center">
  <img src="doc/imagens/mascote1.png" alt="Mascote 1" width="180"/>
</p>

- Botão customizado **Add New Provider** adicionado ao layout do Contato
  - URL: `/flow/Provider?Contact_Record_Id={!Contact.Id}`
- Flow **Provider** adicionado à Barra de Utilitários do Hive App (altura: 500, largura: 500)

---

### Desafio 3 — Experience Cloud + Configuração do Flow

<p align="center">
  <img src="doc/imagens/challenge.png" alt="Challenge" width="220"/>
</p>

- Flow **Provider** adicionado à Página Inicial do site Hive (Experience Cloud)
- Botão Pausar desabilitado em todas as telas do flow
- Tela **S2 Provider Signup** configurada com preenchimento automático:
  - **Practice Name** → variável `recordId`
  - **Provider Name** → variável `Contact_Record_Id`
- Botão "Finish" renomeado para **"Thank you"**
- Registro Provider criado pela usuária Jane Grey com Tipo de Prática: Solo Practitioner

---

## Deploy

```bash
# Autenticar na org
sf org login web --alias hive-superbadge

# Deploy completo
sf project deploy start --target-org hive-superbadge --source-dir force-app --ignore-warnings
```

## Estrutura do Projeto

```
force-app/main/default/
├── flows/                  # Flow Provider
├── flexipages/             # Home Page e Barra de Utilitários
├── layouts/                # Layouts de Conta e Contato
├── quickActions/           # Create New Provider (Conta)
├── objects/Contact/        # Botão Add New Provider
├── applications/           # Hive App
├── experiences/            # Site Experience Cloud Hive
└── permissionsets/         # Provider Access
```

## Licença

MIT © [Leandro da Silva Stampini](LICENSE)
