# 🌸 Sistema de Agendamento - Terapeutas

Um site responsivo e intuitivo desenvolvido para que clientes possam **agendar consultas com a terapeuta Emanuella SS** diretamente pelo link disponível em seu perfil do Instagram.

## 💡 Sobre o Projeto

O objetivo deste projeto é oferecer uma experiência de agendamento prática, acolhedora e acessível, refletindo o cuidado e a atenção que o terapeuta dedica aos seus atendimentos.

## ✨ Funcionalidades

- 📅 **Agendamento simples e rápido:** o usuário seleciona o dia e o horário desejados para a consulta.  
- 📲 **Design responsivo:** totalmente adaptável a celulares, tablets e computadores.  
- 🧘‍♀️ **Interface acolhedora:** com paleta de cores suaves e elementos que transmitem calma e confiança.  
- ☁️ **Integração com Google Sheets:** os dados dos agendamentos são enviados com segurança e automaticamente para uma planilha via **requisição POST (Apps Script endpoint)**.  
- 🔗 **Compatível com bio do Instagram:** pode ser acessado facilmente por meio de um link direto no perfil.

## 🛠️ Tecnologias Utilizadas

- **HTML5** — Estrutura do site  
- **CSS3** — Estilo e responsividade  
- **JavaScript (ES6+)** — Validação e envio dos dados  
- **Google Apps Script** — Endpoint para registro dos agendamentos  
- **Vercel** — Hospedagem e deploy automático  

## 🚀 Como Publicar na Vercel

1. Faça login em [https://vercel.com](https://vercel.com).  
2. Crie um novo projeto e conecte o repositório do GitHub.  
3. A Vercel detectará automaticamente os arquivos estáticos (HTML, CSS e JS).  
4. Clique em **Deploy** e aguarde a publicação.  
5. Copie o link gerado e adicione-o na bio do Instagram.

## 🧾 Integração com Google Sheets

1. Crie uma nova planilha no Google Sheets.  
2. Acesse **Extensões → Apps Script**.  
3. Cole o seguinte código no editor (ajuste os nomes de coluna conforme sua planilha):

   ```js
   function doPost(e) {
     var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Agendamentos");
     var data = JSON.parse(e.postData.contents);
     sheet.appendRow([
       new Date(),
       data.nome,
       data.email,
       data.data,
       data.horario,
       data.mensagem
     ]);
     return ContentService.createTextOutput("Agendamento recebido com sucesso.");
   }

4. Clique em Implantar → Nova implantação
5. Escolha o tipo Aplicativo da Web, configure as permissões de acesso a planilha
6. Copie o link do endpoint gerado e cole no arquivo JavaScript do site (onde a requisição fetch() é feita).

---

## 📬 Contato

Para dúvidas sobre o site ou suporte técnico, entre em contato com o desenvolvedor:  
📧 [ronald23.nt@gmail.com](mailto:ronald23.nt@gmail.com)

## 💗 Créditos

Desenvolvido por Ronald SS com dedicação e carinho, em apoio ao trabalho inspirador da terapeuta Emanuella SS.

> “Cuidar de si é o primeiro passo para transformar o mundo ao seu redor.” 🌿
