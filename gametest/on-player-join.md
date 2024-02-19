# on-player-join
プレイヤーが参加した時に処理を実行します。こちらのサンプルではテレポートとメッセージを送信させています。

- Minecraft v1.20.60
- @minecraft/server v1.9.0-beta
- @minecraft/server v1.8.0

```js
import { world } from '@minecraft/server';

// PlayerSpawnイベントを登録
world.afterEvents.playerSpawn.subscribe(event => {
  // ワールドに初めてスポーンした時のみ動かす(リスポーン時も動くため)
  if (event.initialSpawn) {
    const player = event.player;

    // 座標(0,0,0)にテレポート
    player.teleport({ x: 0, y: 0, z: 0 });
    // メッセージを送信
    player.sendMessage('ようこそ！');
  }
});
```
