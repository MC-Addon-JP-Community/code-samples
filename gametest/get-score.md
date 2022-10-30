# get-score
プレイヤーのスコアを取得する関数です。  

- Minecraft v1.19.40  
- @minecraft/server v1.0.0-beta

```js
/**
 * フェイクプレイヤー対応版のスコア取得関数
 * @author akki256
 * @param {import('@minecraft/server').Player|import('@minecraft/server').Entity|string} target
 * @param {string} objective
 * @returns {number|null}
 */
export function getScore(target, objective) {
    try {
        if (typeof target === 'string') return world.scoreboard.getObjective(objective).getScores().find(({ participant }) => participant.displayName === target).score;
        return world.scoreboard.getObjective(objective).getScore(target.scoreboard);
    }
    catch {
        return null;
    }
}
```
