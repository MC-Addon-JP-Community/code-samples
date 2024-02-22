# on-break-block
ブロックを破壊すると壊したブロックのIDを表示します

- Minecraft v1.20.60  
- @minecraft/server v1.9.0-beta
- @minecraft/server v1.8.0

```js
import { world } from '@minecraft/server';

world.afterEvents.playerBreakBlock.subscribe(event => {
  const player = event.player;
  const permutation = event.brokenBlockPermutation;
  
  player.sendMessage(`${permutation.type.id} を壊しました`);
});
```
