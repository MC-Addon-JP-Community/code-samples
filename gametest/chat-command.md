# chat-command
チャットを使ってカスタムコマンド風の機能を実装します。  
`!lobby`とチャットに入力した場合は0,0,0にテレポートされます。  
`!test`と入力した場合はsayコマンドとgiveコマンドがそれぞれ実行されます。

- Minecraft v1.21.50
- @minecraft/server v1.17.0-beta

```js
import { world } from '@minecraft/server';

world.afterEvents.chatSend.subscribe(event => {
  const message = event.message;
  const player = event.sender;

  const [command, ...args] = message.split(' ');

  if (command === '!lobby') {
    player.teleport({ x: 0, y: 0, z: 0 });
  }

  if (command === '!test') {
    player.runCommand('say Hello, World!');
    player.runCommand('give @s stick');
  }
})
```
