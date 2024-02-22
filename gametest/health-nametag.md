# health-nametag
プレイヤーのネームタグにHPを表示します

- Minecraft v1.20.60  
- @minecraft/server v1.9.0-beta
- @minecraft/server v1.8.0

```js
import { world, Player } from '@minecraft/server';

world.afterEvents.entityHealthChanged.subscribe(event => {
  const entity = event.entity;

  // イベントの発生源がプレイヤー かつ HPの値が変化していたら
  if (entity instanceof Player && event.oldValue !== event.newValue) {
    // 引数にentityを入れ、updateNameTag関数を実行
    updateNameTag(entity);
  }
});

// スポーン時にもネームタグ更新処理を動かす
world.afterEvents.playerSpawn.subscribe(event => {
  updateNameTag(event.player);
});

/**
 * プレイヤーのネームタグを更新する関数
 * @param {Player} player
 */
function updateNameTag(player) {
  // プレイヤーからHealthコンポーネントを取得
  const healthComponent = player.getComponent('minecraft:health');
  // コンポーネントを持っていない時は処理を抜ける
  if (!healthComponent) return;
  // コンポーネントから体力の現在の値と最大値を取り出し、四捨五入して整数にする
  const currentValue = Math.round(healthComponent.currentValue);
  const maxValue = Math.round(healthComponent.effectiveMax);

  // player.nameTagに名前とHPを入れた文字列を代入し、ネームタグを更新する
  player.nameTag = `${player.name}\nHP: ${currentValue}/${maxValue}`;
}
```
