# get-score
プレイヤーのスコアを取得する関数です。  

- Minecraft v1.20.60  
- @minecraft/server v1.9.0-beta

```js
/**
 * フェイクプレイヤー対応版のスコア取得関数
 * @author akki256, kinji2532
 * @param { import('@minecraft/server').Player | import('@minecraft/server').Entity | string } target
 * @param { string } objective
 * @returns { number | null }
 */
export function getScore(target, objective) {
    try {
        return world.scoreboard.getObjective(objective).getScore(target);
    }
    catch {
        return null;
    }
}
```
