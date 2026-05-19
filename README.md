<p align="center">
  <img src="doc/imagens/badge.png" alt="Superbadge Badge" width="120"/>
</p>

# Superbadge: Screen Flow Distribution

Projeto Salesforce DX com os metadados do **Screen Flow Distribution Superbadge** do Trailhead.

<p align="center">
  <img src="doc/imagens/trailhead.png" alt="Trailhead" width="200"/>
</p>

## Desafios

### Challenge 1 — Hive App Home Page + Account Quick Action
- Flow **Provider** adicionado à Home Page do Hive App (`Hive_Provider_Home_Page`)
- Quick Action **Create New Provider** criada no objeto Account e adicionada ao layout

### Challenge 2 — Contact Button + Utility Bar
- Botão customizado **Add New Provider** adicionado ao layout do Contact
  - URL: `/flow/Provider?Contact_Record_Id={!Contact.Id}`
- Flow **Provider** adicionado ao Utility Bar do Hive App (altura: 500, largura: 500)

### Challenge 3 — Experience Cloud + Flow Configuration
- Flow **Provider** adicionado à Home Page do site Hive (Experience Cloud)
- Botão Pause desabilitado em todas as telas do flow
- Tela **S2 Provider Signup** configurada com auto-populate:
  - **Practice Name** → variável `recordId`
  - **Provider Name** → variável `Contact_Record_Id`
- Botão "Finish" renomeado para **"Thank you"**
- Registro Provider criado como Jane Grey com Practice Type: Solo Practitioner

## Deploy

```bash
# Autenticar org
sf org login web --alias hive-superbadge

# Deploy completo
sf project deploy start --target-org hive-superbadge --source-dir force-app --ignore-warnings
```

## Estrutura

```
force-app/main/default/
├── flows/                  # Provider flow
├── flexipages/             # Home Page e Utility Bar
├── layouts/                # Account e Contact layouts
├── quickActions/           # Create New Provider (Account)
├── objects/Contact/        # Add New Provider button
├── applications/           # Hive App
├── experiences/            # Experience Cloud Hive site
└── permissionsets/         # Provider Access
```

## Licença

MIT © [Leandro da Silva Stampini](LICENSE)

The `sfdx-project.json` file contains useful configuration information for your project. See [Salesforce DX Project Configuration](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_ws_config.htm) in the _Salesforce DX Developer Guide_ for details about this file.

## Read All About It

- [Salesforce Extensions Documentation](https://developer.salesforce.com/tools/vscode/)
- [Salesforce CLI Setup Guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_intro.htm)
- [Salesforce DX Developer Guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_intro.htm)
- [Salesforce CLI Command Reference](https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/cli_reference.htm)
