# kill-death-counter
プレイヤーによるキル数とデス数をスコアに記録します

- Minecraft v1.20.60  
- @minecraft/server v1.9.0-beta
- @minecraft/server v1.8.0

> [!NOTE]
> 使用するスコアボードのオブジェクト(kills, deaths)は事前に作成しておいてください

```js
import { world, Player } from '@minecraft/server';

// EntityDieイベントを登録
world.afterEvents.entityDie.subscribe(event => {
  // 死んだエンティティをdeadEntity変数に代入
  const deadEntity = event.deadEntity;
  // キルしたエンティティをdamagingEntity変数に代入
  const damagingEntity = event.damageSource.damagingEntity;

  // 死んだエンティティがプレイヤー かつ キルしたエンティティがプレイヤー なら
  if (deadEntity instanceof Player && damagingEntity instanceof Player) {

    // スコアボードのkillsオブジェクトを取得し、変数に代入
    const kills = world.scoreboard.getObjective('kills');
    // スコアボードのdeathsオブジェクトを取得し、変数に代入
    const deaths = world.scoreboard.getObjective('deaths');
	
    // 各スコアボードに1を足す
    kills.addScore(damagingEntity, 1);
    deaths.addScore(deadEntity, 1);
  }
});
```
