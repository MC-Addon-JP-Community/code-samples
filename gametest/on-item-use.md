# on-item-use
アイテムを使用した時に処理を実行します  
こちらのサンプルでは棒を使用した人をテレポートさせています。  

- Minecraft v1.20.60
- @minecraft/server v1.9.0-beta
- @minecraft/server v1.8.0

```
import { world } from '@minecraft/server';

world.afterEvents.itemUse.subscribe(event => {
  const itemStack = event.itemStack;
  const source = event.source;

  // 棒を使用した時
  if (itemStack.typeId === 'minecraft:stick') {
    // 座標(0,0,0)にテレポート
    source.teleport({ x: 0, y: 0, z: 0 });
  }
});
```
