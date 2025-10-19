# **HealthSync: Sistema de Gestão de Consultas Médicas**

### **Integrantes do Grupo**
* **Vitor Shimizu – RM550390** 
* **Fabrizio Maia - RM551869**
* **Victor Asfur - RM551684**
* **André Sóler – RM98827**

Um aplicativo mobile completo e reestruturado para agendamento e gestão de consultas médicas, focado em alta manutenibilidade, legibilidade e uma experiência de usuário consistente com a marca **HealthSync**.

## **I. Identidade Visual e Design System (HealthSync)**

### **Nome e Logotipo**

* **Nome do Aplicativo:** **HealthSync**  
* **Conceito do Logotipo:** Símbolo que combina um traçado de **Eletrocardiograma (ECG)** com um ícone de **Conexão/Sincronização**, representando a união de dados de saúde e tecnologia.

<img width="260" height="278" alt="healthsync" src="https://github.com/user-attachments/assets/3de4eaf7-0d8b-4d86-9056-00a3f4029fe9" />

### **Paleta de Cores e Justificativa (Aplicada em src/styles/theme.ts)**

A paleta foi escolhida para evocar confiança, profissionalismo e modernidade, características essenciais na área da saúde digital.

| Variável (Uso) | Cor HEX | Justificativa |
| :---- | :---- | :---- |
| **Primary** (Ação Principal) | \#003366 (Azul Marinho) | Confiança, estabilidade e profissionalismo (cor clássica da saúde/tecnologia). |
| **Secondary** (Destaque/Interatividade) | \#00C4CC (Turquesa/Ciano) | Limpeza, inovação e cuidado, oferecendo um contraste vibrante com o azul primário. |
| **Success** (Confirmação) | \#28A745 (Verde Esmeralda) | Saúde, positividade e sucesso em operações (confirmação de consultas). |
| **Warning** (Pendente/Alerta) | \#FFC107 (Amarelo Dourado) | Atenção, usado para status de consultas pendentes que exigem ação. |
| **Error** (Negativo/Cancelamento) | \#DC3545 (Vermelho) | Alerta e negatividade (cancelamento, erros de formulário). |
| **Background** | \#F9F9F9 | Fundo claro e limpo para destacar o conteúdo e facilitar a leitura. |

### **Tipografia**

A tipografia foi padronizada no theme.ts para garantir a acessibilidade (alto contraste e tamanhos de fonte adequados):

* **Font Family:** System/Roboto (Fonte nativa para melhor performance e legibilidade).  
* **Title:** 26px, Bold  
* **Subtitle:** 18px, Semibold  
* **Body:** 16px, Regular

## **II. Arquitetura e Organização do Código**

O projeto segue estritamente o padrão de arquitetura em camadas e a modularização completa das telas, promovendo a manutenibilidade e a testabilidade.

### **Estrutura de Pastas Padrão (Modularização)**

Todas as telas foram refatoradas para o padrão modular:  
src/  
├── screens/  
│   ├── \[NomeDaTela\]/     \# Novo padrão de tela  
│   │   ├── index.tsx     \# Lógica do componente (useState, useEffect, Handlers)  
│   │   └── styles.ts     \# Estilos e Styled-Components (CSS-in-JS)  
│   ├── Home/  
│   ├── CreateAppointment/  
│   └── ...  
├── components/           \# Componentes reutilizáveis (Card, Header, Listas)  
├── services/             \# Regras de negócio, manipulação de dados (AsyncStorage/APIs)  
├── types/                \# Definições de TypeScript (Interfaces e Tipos)  
└── styles/  
    └── theme.ts          \# Tema central de cores e tipografia (HealthSync)

## **III. Funcionalidades Implementadas e Polimento (Documento Vivo)**

| Módulo | Funcionalidade Principal | Polimento e Melhorias de UX |
| :---- | :---- | :---- |
| **Geral** | Estrutura de Código | **Refatoração Completa** para separar lógica (index.tsx) de estilos (styles.ts). Uso de **tipagem estrita** em todo o código. |
| **Autenticação** | Login/Registro | **Feedback Visual:** Implementação obrigatória de estados loading (no botão) e error (mensagem clara) para todas as operações. |
| **Agendamento** | CreateAppointmentScreen | **UX Aprimorada:** Substituição do Input de data por um mecanismo de seleção (simulação de Date Picker) e validação de data futura. **Integração de Dados:** Lista de médicos busca dados do serviço, garantindo imagens fixas. |
| **Listas** | HomeScreen / Dashboards | **Coerência Visual:** AppointmentCard e DoctorList atualizados com o tema HealthSync. **Estados Vazios:** Implementação de EmptyText e LoadingText em todas as listas. |
| **Dados** | auth.ts / storage.ts | **Dados Fixos:** Remoção de URLs de imagens aleatórias, substituídas por imagens estáticas por tipo de usuário (Admin, Médico, Paciente), garantindo consistência da UI. |

## **IV. Screenshots do Aplicativo**

Esta seção será preenchida com as capturas de tela do aplicativo após a compilação e execução.

| Tela | Descrição | Imagem |
| :---- | :---- | :---- |
| **Login** | Tela de entrada com o tema HealthSync. |  |
| **Home** | Tela inicial com consultas agendadas e botão de Agendar Nova Consulta. |  |
| **Agendamento** | Tela de agendamento com seletor de médico, horário e data. |  |
| **Dashboard** | Painel do Administrador ou Médico com cards de estatísticas. |  |

## **V. Instruções de Execução Local**

Este projeto utiliza React Native com Expo. Siga os passos abaixo para configurar e rodar a aplicação em seu ambiente.

### **Pré-requisitos**

* Node.js (LTS ou superior)  
* npm (ou yarn)  
* Expo CLI (npm install \-g expo-cli)

### **1\. Instalação das Dependências**

Clone o repositório e instale as dependências.  
\# Clone o repositório (substituir URL pelo seu repositório)  
git clone \[https://github.com/shkmizu/HealthSync]  
cd marcacaoDeConsultasMedicas  
\# Instala as dependências do package.json  
npm install

### **2\. Execução do Projeto**

Para iniciar o servidor de desenvolvimento do Expo e rodar o aplicativo:  
\# Inicia o servidor Expo  
npm start

Após rodar o comando npm start, um QR Code será exibido no seu terminal. Use o aplicativo **Expo Go** no seu celular (Android/iOS) para escanear o código e abrir o projeto.

### **3\. Execução em Emuladores (Opcional)**

Se você tiver o Android Studio (emulador Android) ou Xcode (simulador iOS) configurado:  
\# Para rodar no emulador Android  
npm run android

\# Para rodar no simulador iOS (Apenas macOS)  
npm run ios

### **Credenciais de Teste**

Utilize as seguintes credenciais para testar os diferentes perfis de usuário:

| Perfil | Email | Senha |
| :---- | :---- | :---- |
| **Administrador** | admin@example.com | 123456 |
| **Médico** | joao@example.com | 123456 |
| **Paciente** | (Crie uma nova conta pela tela de Cadastro) | (Qualquer senha) |

