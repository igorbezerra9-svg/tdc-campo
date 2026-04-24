# TDC Campo · Localizador

Ferramenta de localização de TDCs para equipes de campo — roda direto no navegador do celular via GitHub Pages.

## Como usar

### 1. Configurar o repositório
Edite o arquivo `index.html` e altere as duas linhas no bloco `CONFIG` no topo:
```js
const CONFIG = {
  GITHUB_USER: 'seu_usuario_aqui',
  GITHUB_REPO: 'tdc-campo',
  ...
};
```

### 2. Ativar o GitHub Pages
- Vá em **Settings → Pages**
- Em *Source*, selecione **Deploy from a branch**
- Branch: `main` / pasta: `/ (root)`
- Salve — em alguns minutos o site estará disponível

### 3. Adicionar arquivos de dados
- Faça o download do Excel no sistema (até 60 dias por vez)
- Suba o arquivo `.xlsx` na pasta **`dados/`** deste repositório
- Ao acessar a ferramenta, ela detecta automaticamente os arquivos novos

### Lógica de atualização
- A ferramenta lê **todos os arquivos** da pasta `dados/` automaticamente
- Arquivos já processados ficam em **cache local** (não reprocessa toda vez)
- Se um TDC aparece em mais de um arquivo, fica com os dados **mais recentes**
- Histórico de atendimentos é **acumulado** entre lotes

## Estrutura do repositório
```
tdc-campo/
├── index.html      ← a ferramenta (não precisa mexer)
├── dados/
│   ├── fev_mar_2026.xlsx
│   ├── nov_jan_2026.xlsx
│   └── ...
└── README.md
```

## Nomeação sugerida dos arquivos
Use nomes descritivos para facilitar a identificação:
- `fev_mar_2026.xlsx`
- `abr_mai_2026.xlsx`
- `cosampa_sul_jun_2026.xlsx`
