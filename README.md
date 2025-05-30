# Automação Travian com Interface Web

Este projeto automatiza o processo de iniciar todas as listas de farms no jogo Travian (ts100.x10.america.travian.com) usando Node.js e Playwright, com uma interface web para controle e configuração.

## Funcionalidades

* Faz login na sua conta Travian
* Navega até a página do Rally Point (Farm List)
* Clica no botão "Iniciar todas as listas de farms"
* Roda automaticamente em intervalos aleatórios entre 4 e 6 minutos
* Interface web para controle com botões Start/Stop
* Configuração de credenciais diretamente pela interface web
* Executa 100% na nuvem (não precisa do seu computador ligado)

## Pré-requisitos

* Conta no [Travian](https://ts100.x10.america.travian.com)
* Conta no [Render.com](https://render.com/) (plano gratuito)

## Deploy no Render.com (Passo a Passo)

1. **Criar uma conta no Render.com**
   - Acesse [render.com](https://render.com/)
   - Crie uma conta gratuita (pode usar GitHub, Google ou email)

2. **Criar um novo Web Service**
   - Após fazer login, clique em "New +" no canto superior direito
   - Selecione "Web Service"

3. **Configurar o deploy**
   - Escolha "Deploy from public Git repository"
   - Cole este URL: `https://github.com/travian-automation/travian-farm-bot-local`
   - Clique em "Continue"

4. **Configurar o serviço**
   - Nome: `travian-automation` (ou outro nome de sua preferência)
   - Runtime: `Node`
   - Build Command: `npm install`
   - Start Command: `npm start`
   - Plano: `Free`

5. **Criar o Web Service**
   - Clique em "Create Web Service"
   - Aguarde o deploy (pode levar alguns minutos)

6. **Acessar a interface web**
   - Após o deploy, o Render fornecerá uma URL (algo como `https://travian-automation.onrender.com`)
   - Acesse essa URL para abrir a interface de controle
   - Configure suas credenciais do Travian na interface
   - Use os botões para iniciar e parar a automação

## Como usar a interface web

1. **Configurar credenciais**
   - Preencha seu nome de usuário e senha do Travian nos campos correspondentes
   - Clique em "Salvar Credenciais"
   - As credenciais são salvas no servidor e não precisam ser inseridas novamente

2. **Controlar a automação**
   - Clique em "Iniciar Automação" para começar o loop
   - A automação executará imediatamente e depois a cada 4-6 minutos
   - Clique em "Parar Automação" quando quiser interromper o processo
   - O painel de status mostra se está rodando ou parado
   - A contagem regressiva mostra quando será a próxima execução

3. **Monitorar atividades**
   - O registro de atividades mostra o que está acontecendo
   - Clique em "Atualizar Status" para verificar o estado atual

## Notas importantes

* A automação roda 100% na nuvem, seu computador não precisa ficar ligado
* O plano gratuito do Render.com pode "adormecer" após períodos de inatividade
* Se isso acontecer, basta acessar a URL novamente para "acordar" o serviço
* As credenciais são armazenadas apenas no servidor Render e não são compartilhadas

## Estrutura do projeto

* `server.js` - Servidor Express e rotas da API
* `automation.js` - Lógica de automação usando Playwright
* `views/index.html` - Interface web para controle
* `credentials.json` - Arquivo onde as credenciais são salvas (criado automaticamente)

## Solução de problemas

* **A página não carrega**: O serviço pode estar "adormecido". Acesse a URL e aguarde alguns segundos.
* **Erro de login**: Verifique se as credenciais estão corretas na interface web.
* **Botão não encontrado**: O Travian pode ter mudado a interface. Entre em contato para atualização.
