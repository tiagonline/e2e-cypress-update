# 🧪 Cypress E2E Testing - Projeto Abrangente

Este projeto é um **estudo prático e abrangente de testes end-to-end (E2E)** usando **Cypress** que explora diversos cenários complexos de automação, desde verificação de emails até integração com IA.

## 📋 Descrição do Projeto

O projeto demonstra como implementar testes automatizados avançados que cobrem:

### 🔐 **Autenticação & Email**
- ✅ Preenchimento de formulários de signup
- ✅ Envio de emails de confirmação
- ✅ Captura e validação de códigos de confirmação via email
- ✅ Verificação do fluxo completo de autenticação

### 📊 **Operações CRUD**
- ✅ Create - Criação de registros
- ✅ Read - Leitura e listagem de dados
- ✅ Update - Atualização de informações
- ✅ Delete - Remoção de registros

### 📎 **Upload de Arquivos**
- ✅ Upload de diferentes tipos de arquivo
- ✅ Validação de arquivos enviados
- ✅ Testes de limites e restrições

### 🖼️ **Interação com iFrames**
- ✅ Navegação dentro de iframes
- ✅ Interação com elementos embedados
- ✅ Validação de conteúdo em contextos isolados

### 🤖 **Avaliação com IA (Futuro)**
- 🔄 Integração com APIs de IA externa
- 🔄 Validação automatizada via chave de API
- 🔄 Análise inteligente de resultados

## 🔧 Tecnologias Utilizadas

### **Core Testing**
- **[Cypress](https://cypress.io/)** v15.1.0 - Framework de testes E2E
- **[Cypress Mailosaur](https://www.npmjs.com/package/cypress-mailosaur)** v2.17.0 - Plugin para testes com email
- **[Faker.js](https://fakerjs.dev/)** v6.6.6 - Geração de dados fictícios

### **Relatórios & Qualidade**
- **[Allure](https://docs.qameta.io/allure/)** - Relatórios avançados e interativos
- **[ESLint](https://eslint.org/)** v9.34.0 - Linting e qualidade de código

### **Integrações Futuras**
- **API de IA Externa** - Para validação automatizada inteligente
- **Plugins de Upload** - Para testes de arquivos
- **Cypress iframe** - Para interação com elementos embedados

## 🎯 Funcionalidades Testadas

### 1. **Autenticação e Email** ✅
- Cadastro com confirmação por email via Mailosaur
- Login e logout de usuários
- Recuperação de senha

### 2. **Operações CRUD** 🔄
- **Create**: Criação de novos registros (notas, usuários, etc.)
- **Read**: Listagem e visualização de dados
- **Update**: Edição de informações existentes
- **Delete**: Remoção de registros com confirmação

### 3. **Upload de Arquivos** 🔄
- Upload de imagens, documentos e arquivos diversos
- Validação de tipos de arquivo permitidos
- Testes de limites de tamanho
- Verificação de upload bem-sucedido

### 4. **Interação com iFrames** 🔄
- Navegação dentro de elementos iframe
- Preenchimento de formulários embedados
- Validação de conteúdo em contextos isolados
- Switching entre frames

### 5. **Interceptação de Requisições** ✅
- Monitora chamadas para APIs (`**/notes`, `**/users`, etc.)
- Validação de payloads de requisições
- Simulação de respostas de erro

### 6. **Avaliação com IA** 🔄 *(Implementação Futura)*
- Integração com APIs de IA externa
- Validação automatizada de resultados
- Análise inteligente de comportamentos

## 🚀 Como Executar

### Pré-requisitos
1. Node.js instalado
2. Conta no [Mailosaur](https://mailosaur.com/) (para testes de email)

### Configuração

1. **Clone o repositório:**
```bash
git clone <repository-url>
cd e2e-cypress-update
```

2. **Instale as dependências:**
```bash
npm install
```

3. **Configure as variáveis de ambiente:**
```bash
cp cypress.env.example.json cypress.env.json
```

4. **Edite o arquivo `cypress.env.json` com suas credenciais:**
```json
{
  "USER_PASSWORD": "sua_senha_de_teste",
  "MAILOSAUR_SERVER_ID": "seu_server_id_mailosaur",
  "MAILOSAUR_API_KEY": "sua_api_key_mailosaur",
  "AI_API_KEY": "sua_chave_api_ia",
  "BASE_URL": "https://sua-aplicacao.com"
}
```

### Executando os Testes

#### Modo Interativo (Interface Gráfica):
```bash
npx cypress open
```

#### Modo Headless (Terminal):
```bash
npx cypress run
```

#### Gerar Relatórios Allure:
```bash
# Executar testes e gerar dados para Allure
npx cypress run --reporter allure

# Gerar e abrir relatório Allure
npx allure generate --clean && npx allure open
```

## 📁 Estrutura do Projeto

```
├── cypress/
│   ├── e2e/
│   │   ├── auth/
│   │   │   ├── signup.cy.js          # Teste de cadastro com email
│   │   │   ├── login.cy.js           # Teste de login
│   │   │   └── password-reset.cy.js  # Recuperação de senha
│   │   ├── crud/
│   │   │   ├── notes-crud.cy.js      # Operações CRUD de notas
│   │   │   ├── users-crud.cy.js      # Operações CRUD de usuários
│   │   │   └── categories.cy.js      # CRUD de categorias
│   │   ├── upload/
│   │   │   ├── file-upload.cy.js     # Upload de arquivos
│   │   │   ├── image-upload.cy.js    # Upload de imagens
│   │   │   └── bulk-upload.cy.js     # Upload em lote
│   │   ├── iframe/
│   │   │   ├── embedded-forms.cy.js  # Formulários em iframe
│   │   │   └── widgets.cy.js         # Widgets embedados
│   │   ├── ai-evaluation/
│   │   │   ├── content-analysis.cy.js # Análise com IA
│   │   │   └── smart-validation.cy.js # Validação inteligente
│   │   └── spec.cy.js                # Teste template básico
│   ├── fixtures/
│   │   ├── example.json              # Dados de teste estáticos
│   │   ├── test-files/               # Arquivos para upload
│   │   └── ai-responses/             # Respostas mockadas da IA
│   └── support/
│       ├── commands.js               # Comandos customizados
│       ├── e2e.js                   # Configurações globais
│       └── ai-helpers.js            # Funções auxiliares para IA
├── allure-results/                   # Dados dos relatórios Allure
├── allure-report/                    # Relatórios HTML gerados
├── cypress.config.js                 # Configuração do Cypress
├── cypress.env.example.json          # Template de variáveis de ambiente
├── cypress.env.json                 # Variáveis de ambiente (não versionado)
├── package.json                     # Dependências e scripts
├── eslint.config.mjs                # Configuração do ESLint
└── README.md                        # Este arquivo
```

## 🧪 Detalhes dos Testes

### **Autenticação (signup.cy.js)** ✅
1. **Geração de dados**: Cria email único usando UUID + domínio Mailosaur
2. **Navegação**: Acessa página de cadastro
3. **Preenchimento**: Insere dados no formulário
4. **Submissão**: Clica no botão de cadastro
5. **Aguarda email**: Usa Mailosaur para capturar email de confirmação
6. **Extração de código**: Usa regex para extrair código de 6 dígitos
7. **Confirmação**: Insere código e submete
8. **Validação**: Verifica redirecionamento e elementos da página logada

### **CRUD Operations** 🔄 *(Em Desenvolvimento)*
- **Criação**: Testa formulários de criação com validação
- **Leitura**: Verifica listagens, paginação e filtros
- **Atualização**: Edição inline e formulários de update
- **Exclusão**: Confirmações e soft/hard deletes

### **Upload de Arquivos** 🔄 *(Em Desenvolvimento)*
- Drag & drop de arquivos
- Seleção múltipla
- Progress bars e feedbacks
- Validação de tipos MIME

### **iFrame Testing** 🔄 *(Em Desenvolvimento)*
- Switching entre frames
- Formulários embedados
- Comunicação cross-frame

### **IA Integration** 🔄 *(Planejado)*
- Análise automatizada de conteúdo
- Validação contextual inteligente
- Relatórios enriquecidos com insights de IA

## 🔍 Scripts Disponíveis

- `npm run lint` - Executa verificação de lint nos arquivos
- `npm run lint:fix` - Corrige automaticamente problemas de lint
- `npm run test:open` - Abre Cypress em modo interativo
- `npm run test:run` - Executa testes em modo headless
- `npm run test:chrome` - Executa testes especificamente no Chrome
- `npm run test:firefox` - Executa testes especificamente no Firefox
- `npm run allure:generate` - Gera relatórios Allure
- `npm run allure:open` - Abre relatórios Allure no navegador
- `npm run test:smoke` - Executa apenas testes de smoke
- `npm run test:regression` - Executa suite completa de regressão

## 📚 Aprendizados e Conceitos

Este projeto demonstra conceitos avançados de automação:

### **Fundamentos**
- **Integração com serviços de email** para testes automatizados
- **Geração de dados dinâmicos** com Faker.js
- **Interceptação de requisições HTTP** com Cypress
- **Uso de variáveis de ambiente** para configurações sensíveis

### **Técnicas Avançadas**
- **Operações CRUD completas** com validações robustas
- **Upload de arquivos** com diferentes formatos e tamanhos
- **Manipulação de iFrames** e contextos embedados
- **Extração de dados de emails** com regex
- **Page Object Model** para organização de código

### **Integrações Externas**
- **APIs de terceiros** para validação automatizada
- **Relatórios visuais** com Allure Framework
- **Análise inteligente** com APIs de IA
- **CI/CD pipelines** para execução automatizada

### **Boas Práticas**
- **Organização modular** de testes por funcionalidade
- **Reutilização de código** através de comandos customizados
- **Tratamento de erros** e cenários edge cases
- **Performance testing** e otimização de execução

## 🤝 Contribuindo

Este é um projeto de estudo, mas contribuições são bem-vindas! Sinta-se à vontade para:

- Reportar bugs
- Sugerir melhorias
- Adicionar novos cenários de teste
- Melhorar a documentação

## 📄 Licença

Este projeto está licenciado sob a licença ISC.