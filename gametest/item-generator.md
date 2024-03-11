# item-generator
10秒に1回、特定の座標にアイテムをスポーンさせます  

- Minecraft v1.20.60
- @minecraft/server v1.9.0-beta
- @minecraft/server v1.8.0

```js
import { world, system, ItemStack } from '@minecraft/server';

// ディメンション(overworld)を取得
const overworld = world.getDimension('overworld');

// runIntervalを使って定期実行する
system.runInterval(() => {

  // エメラルド1個のItemStackを作成
  const item = new ItemStack('minecraft:emerald', 1);

  // 座標(0,0,0)に作成したアイテムをスポーン
  overworld.spawnItem(item, { x: 0, y: 0, z: 0 });

}, 200); // 10秒=200tick
```
