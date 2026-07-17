# 🚀 CVFlow AI — CRM Inteligente de Currículos

![Status](https://img.shields.io/badge/status-Prot%C3%B3tipo%20Funcional-success)
![n8n](https://img.shields.io/badge/n8n-Automation-orange)
![OpenAI](https://img.shields.io/badge/OpenAI-IA-green)
![Google%20Workspace](https://img.shields.io/badge/Google-Workspace-blue)

## 📌 Sobre o Projeto

O **CVFlow AI** é um protótipo desenvolvido para automatizar o processo de recebimento, leitura, organização e cadastro de currículos enviados por e-mail.

A solução utiliza **Inteligência Artificial** para interpretar currículos em PDF, extrair informações relevantes e alimentar automaticamente um CRM desenvolvido no Google Sheets, reduzindo tarefas repetitivas e evitando cadastros duplicados.

Este projeto foi desenvolvido como parte da minha jornada de transição para a área de Tecnologia, com foco em **Automação de Processos, IA aplicada e Low-Code**.

---

# 🎯 Objetivo

Automatizar o fluxo inicial de recrutamento, eliminando atividades manuais como:

- Receber currículos por e-mail;
- Baixar arquivos manualmente;
- Organizar documentos;
- Cadastrar candidatos;
- Evitar cadastros duplicados;
- Responder automaticamente ao candidato.

---

# ⚙️ Tecnologias Utilizadas

- n8n
- OpenAI
- Gmail
- Google Drive
- Google Sheets
- JavaScript

---

# 🏗 Arquitetura da Solução

```text
Gmail
    │
    ▼
Buscar e-mails não lidos
    │
    ▼
Selecionar 1 e-mail
    │
    ▼
Baixar currículo em PDF
    │
    ▼
Extrair texto do PDF
    │
    ▼
OpenAI
    │
    ▼
Estruturar dados do candidato
    │
    ▼
Pesquisar candidato no CRM
    │
    ▼
      Já existe?
      │        │
     Sim      Não
      │        │
      ▼        ▼
 Aviso      Upload Google Drive
Duplicado        │
                 ▼
          Cadastro no CRM
                 │
                 ▼
      Confirmação automática
                 │
                 ▼
      Marcar e-mail como lido
```

---

# 🔄 Fluxo da Automação

## 1️⃣ Recebimento

O sistema monitora automaticamente a caixa de entrada e identifica e-mails não lidos contendo currículos em PDF.

---

## 2️⃣ Processamento

O currículo é:

- baixado;
- convertido em texto;
- enviado para a IA;
- estruturado automaticamente.

São extraídos dados como:

- Nome;
- E-mail;
- Telefone;
- Cidade;
- Formação;
- Experiência;
- Cargo desejado;
- Área principal;
- Habilidades técnicas;
- Habilidades comportamentais.

---

## 3️⃣ Validação

O sistema pesquisa automaticamente no CRM utilizando o **e-mail encontrado dentro do currículo**, evitando duplicidade.

**Importante**

A validação NÃO utiliza o e-mail do remetente.

Isso permite que terceiros enviem currículos de outras pessoas.

---

## 4️⃣ Novo candidato

Quando o candidato ainda não existe na base:

- salva o currículo no Google Drive;
- cadastra automaticamente no CRM;
- envia confirmação por e-mail;
- marca o e-mail como lido.

---

## 5️⃣ Candidato já cadastrado

Quando o candidato já existe:

- não salva novamente o currículo;
- não cria novo cadastro;
- envia aviso de duplicidade;
- marca o e-mail como lido.

---

# 📋 Estrutura do CRM

O CRM registra automaticamente informações como:

- Nome;
- E-mail;
- Telefone;
- Cidade;
- LinkedIn;
- Cargo desejado;
- Área principal;
- Senioridade;
- Formação;
- Experiência;
- Habilidades técnicas;
- Habilidades comportamentais;
- Link do currículo;
- ID do arquivo no Google Drive;
- Data de cadastro.

---

# 📌 Regras de Negócio

## ✔ Novo candidato

- Upload do currículo para o Google Drive;
- Cadastro automático no CRM;
- Envio de confirmação;
- Marcação do e-mail como lido.

---

## ✔ Currículo duplicado

- Não realiza novo cadastro;
- Não salva novamente o PDF;
- Envia aviso ao candidato;
- Marca o e-mail como lido.

---

# 💡 Funcionalidades

- ✅ Busca automática de e-mails
- ✅ Processamento de um currículo por execução
- ✅ Extração de texto do PDF
- ✅ Interpretação utilizando IA
- ✅ Estruturação automática das informações
- ✅ Cadastro automático no CRM
- ✅ Upload do currículo no Google Drive
- ✅ Verificação automática de duplicidade
- ✅ Resposta automática ao candidato
- ✅ Marcação automática do e-mail como lido

---

# 📷 Demonstração

## Fluxo no n8n

> *(Adicionar print do workflow)*

---

## CRM

> *(Adicionar print da planilha)*

---

## E-mail de confirmação

> *(Adicionar print do e-mail)*

---

## E-mail de duplicidade

> *(Adicionar print do e-mail)*

---

# 🚀 Melhorias Futuras

- Conversão automática de arquivos Word para PDF;
- Processamento de múltiplos currículos no mesmo e-mail;
- Busca de currículos também na pasta Spam;
- Atualização automática de currículos já cadastrados;
- Score de compatibilidade entre currículo e vaga;
- Dashboard de indicadores;
- Banco de talentos com pesquisa inteligente.

---

# 📚 Aprendizados

Durante o desenvolvimento deste projeto foram aplicados conhecimentos em:

- Automação de Processos;
- Integração entre APIs;
- Inteligência Artificial aplicada;
- Manipulação de JSON;
- Tratamento de exceções;
- CRM;
- Google Workspace;
- Regras de negócio;
- Low-Code.

---

# 📂 Estrutura do Projeto

```text
CVFlow-AI
│
├── README.md
│
├── workflow/
│   └── CVFlow_AI.json
│
├── imagens/
│   ├── fluxo.png
│   ├── crm.png
│   ├── email-confirmacao.png
│   └── email-duplicado.png
│
└── prompts/
    └── information-extractor.md
```

---

# 📈 Status

**Versão:** 1.0

✅ Protótipo funcional

Atualmente o projeto está em fase de testes, validando cenários reais de recebimento e processamento automático de currículos.

---

# 👨‍💻 Autor

**Gabriel Cardozo**

Em transição para a área de Tecnologia com foco em:

- Automação de Processos
- Inteligência Artificial
- Low-Code
- RPA
- CRM
- Integrações
- Análise de Sistemas

---

## ⭐ Se este projeto foi interessante para você, deixe uma estrela no repositório.
