const readlineSync = require('readline-sync');

// Função para iniciar o bot
function startBot(name, responses) {
  console.log(`Bot ${name} iniciado. Digite 'sair' para encerrar o chat.`);

  let keepChatting = true;
  
  while (keepChatting) {
    const userMessage = readlineSync.question('Você: ');

    if (userMessage.toLowerCase() === 'sair') {
      console.log(`Bot ${name}: Até logo!`);
      keepChatting = false;
    } else {
      let botResponse = responses[userMessage.toLowerCase()] || "Desculpe, não entendi.";
      console.log(`Bot ${name}: ${botResponse}`);
    }
  }
}

// Função para criar e personalizar bots com comandos
function createBot() {
  const botName = readlineSync.question('Digite o nome do seu bot: ');
  const responses = {};

  console.log(`Personalize o seu bot ${botName}:`);
  
  // Definir comandos personalizados
  let customCommands = {};
  while (true) {
    const command = readlineSync.question('Digite um comando que o bot deve reconhecer (ou "fim" para terminar): ');
    
    if (command.toLowerCase() === 'fim') break;

    const commandAction = readlineSync.question(`Qual ação o comando "${command}" deve realizar? (exemplo: "responder com Olá!") `);
    customCommands[command.toLowerCase()] = commandAction;
  }

  // Adicionar os comandos personalizados às respostas
  for (const command in customCommands) {
    responses[command] = customCommands[command];
  }

  // Iniciar o bot com as respostas personalizadas
  startBot(botName, responses);
}

// Função principal para controlar o fluxo
function main() {
  console.log('Bem-vindo ao serviço de bots!');
  const action = readlineSync.question('Você quer criar um bot (c) ou iniciar um bot existente (i)? ');

  if (action.toLowerCase() === 'c') {
    createBot();
  } else if (action.toLowerCase() === 'i') {
    console.log('Função de iniciar um bot ainda não implementada.');
  } else {
    console.log('Comando inválido.');
  }
}

main();
