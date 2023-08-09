const mineflayer = require('mineflayer');

const botUsernames = ['bot1', 'bot2', 'bot3', 'bot4', 'bot5']; 
const joinDelay = 5000; 

function createBot(username) {
  const bot = mineflayer.createBot({
    host: 'localhost', 
    version: '1.12.2',
    port: '51314', 
    username: username 
  });

  bot.once('spawn', () => {
    console.log(`Bot ${username} đã gia nhập server !`);
  });

  bot.on('end', () => {
    console.log(`Bot ${username} mất kết nối!`);
    setTimeout(() => {
      createBot(username); 
    }, joinDelay);
  });
}

botUsernames.forEach((username, index) => {
  setTimeout(() => {
    createBot(username);
  }, index * joinDelay);
});
