# Desafio DIO: Configurando um Banco de Dados SQL na Microsoft Azure

![Azure SQL Banner](https://user-images.githubusercontent.com/12345678/your-banner-image-url.png) ## 📝 Descrição do Projeto

Este repositório foi criado como parte do desafio de projeto do bootcamp da [DIO](https://www.dio.me/). O objetivo é documentar o passo a passo da criação e configuração de uma instância de Banco de Dados SQL na nuvem da Microsoft Azure, servindo como um material de referência e guia prático.

Aqui você encontrará um resumo dos conceitos abordados, o processo detalhado de provisionamento do recurso e dicas úteis para quem está começando a explorar os serviços de dados do Azure.

---

## 🎯 Objetivos de Aprendizagem

Ao realizar este projeto, os seguintes conceitos foram praticados e assimilados:

- **Provisionamento de Recursos no Azure:** Entender como criar e configurar recursos na plataforma Azure através do portal web.
- **Configuração de Banco de Dados SQL:** Aprender a configurar um servidor lógico e um banco de dados SQL, definindo tier de computação, regras de firewall e credenciais de acesso.
- **Documentação Técnica:** Exercitar a habilidade de documentar um processo técnico de forma clara, estruturada e visual.
- **Uso do Git e GitHub:** Utilizar o GitHub como ferramenta para versionar e compartilhar conhecimento técnico.

---

## 🛠️ Ferramentas Utilizadas

- **[Microsoft Azure](https://portal.azure.com/):** Plataforma de nuvem utilizada para provisionar o banco de dados.
- **[SQL Server Management Studio (SSMS)](https://docs.microsoft.com/pt-br/sql/ssms/download-sql-server-management-studio-ssms):** Ferramenta para conectar e gerenciar o banco de dados.
- **[Git](https://git-scm.com/):** Sistema de controle de versão.
- **[GitHub](https://github.com/):** Plataforma para hospedagem do repositório.
- **[Markdown](https://www.markdownguide.org/):** Linguagem de marcação para formatação do texto.

---

## 🚀 Passo a Passo: Criando o Banco de Dados no Azure

Aqui está o guia detalhado para configurar seu banco de dados SQL.

### 1. Acesso ao Portal Azure

Acesse o [Portal da Microsoft Azure](https://portal.azure.com/) e faça login com sua conta.

* **Dica:** Caso não tenha uma conta, você pode criar uma gratuitamente e aproveitar o crédito inicial para explorar os serviços.

![Captura de tela do Portal Azure](images/01-portal-azure.png)

### 2. Criar um Novo Recurso

No menu do portal, clique em **"Criar um recurso"**. Na barra de busca, pesquise por **"Banco de Dados SQL"** e selecione a opção correspondente.

![Captura de tela da criação de recurso](images/02-criar-recurso.png)

### 3. Selecionar o Plano "Banco de Dados SQL"

Na página do Marketplace, selecione "Banco de Dados SQL" e clique em **"Criar"**.

![Captura de tela da seleção do Azure SQL](images/03-azure-sql.png)

### 4. Configuração da Instância

Nesta etapa, você preencherá as informações essenciais para o seu banco de dados.

- **Assinatura:** Selecione a sua assinatura do Azure.
- **Grupo de Recursos:** Crie um novo grupo de recursos (ex: `rg-desafio-dio`) para organizar os serviços relacionados.
- **Nome do banco de dados:** Escolha um nome único para o seu banco (ex: `db-desafio-dio`).
- **Servidor:** Crie um novo servidor lógico clicando em "Criar novo".
    - **Nome do servidor:** Deve ser globalmente único (ex: `srv-desafio-dio-seu-nome`).
    - **Localização:** Escolha uma região (ex: `Brazil South`).
    - **Autenticação:** Selecione "Usar autenticação SQL" e defina um login de administrador e uma senha segura. Guarde bem essas credenciais!
- **Ambiente e Computação + armazenamento:** Para este desafio, podemos usar um ambiente de desenvolvimento e o nível de computação mais básico para reduzir custos (ex: `Basic` ou `Standard` com poucas DTUs).

![Captura de tela da configuração do Banco de Dados](images/04-configuracao-bd.png)

### 5. Configuração de Rede (Regras de Firewall)

Após a criação do servidor, é crucial configurar o firewall para permitir o acesso.

- Navegue até o recurso do **servidor SQL** que você criou.
- No menu lateral, em "Segurança", clique em **"Rede"**.
- Adicione uma regra de firewall:
    - **Permitir que serviços e recursos do Azure acessem este servidor:** Marque "Sim".
    - **Adicionar seu endereço IP do cliente:** Clique nesta opção para que o Azure adicione automaticamente o IP da sua máquina, permitindo a conexão via SSMS.

![Captura de tela das regras de firewall](images/05-regras-firewall.png)

### 6. Conexão via SQL Server Management Studio (SSMS)

Com o banco de dados provisionado e o firewall configurado, vamos conectar.

1.  Abra o SSMS.
2.  Na tela de conexão, preencha:
    - **Nome do servidor:** O nome completo do seu servidor Azure (ex: `srv-desafio-dio-seu-nome.database.windows.net`). Você pode encontrar essa informação na página de visão geral do seu banco de dados no portal Azure.
    - **Autenticação:** "Autenticação do SQL Server".
    - **Login:** O nome de usuário administrador que você criou.
    - **Senha:** A senha que você definiu.
3.  Clique em **"Conectar"**.

![Captura de tela da conexão via SSMS](images/06-conexao-ssms.png)

Pronto! Você está conectado ao seu banco de dados na nuvem Azure e pode começar a criar tabelas, executar queries e gerenciar seus dados.

---

## 💡 Dicas e Anotações Adicionais

- **Segurança é Fundamental:** Nunca exponha suas senhas ou chaves de acesso no repositório. Utilize o arquivo `.gitignore` para evitar o commit de arquivos sensíveis. As credenciais usadas aqui são para um ambiente de estudo.
- **Controle de Custos:** Lembre-se sempre de parar ou excluir os recursos no Azure após a conclusão dos seus estudos para evitar cobranças inesperadas. O Grupo de Recursos facilita a exclusão de todos os serviços de uma só vez.
- **SQL do Azure vs. Instância Gerenciada:** O serviço "Banco de Dados SQL do Azure" é um banco de dados como serviço (DBaaS), ideal para aplicações modernas na nuvem. Já a "Instância Gerenciada de SQL" oferece maior compatibilidade com o SQL Server on-premises, facilitando a migração de sistemas legados.

---

## 🔗 Recursos Úteis

- **[Documentação Oficial: Criar Banco de Dados SQL do Azure](https://learn.microsoft.com/pt-br/azure/azure-sql/database/single-database-create-quickstart?view=azuresql&tabs=azure-portal)**
- **[GitHub Quick Start](https://github.com/digitalinnovationone/dio-lab-open-source)**
- **[Guia de Markdown do GitHub](https://guides.github.com/features/mastering-markdown/)**

---

Feito com ❤️ por [Seu Nome](https://github.com/seu-usuario).
