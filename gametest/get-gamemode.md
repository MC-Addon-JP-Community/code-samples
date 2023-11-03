# get-gamemode
プレイヤーのゲームモードを取得する関数です。  

- Minecraft v1.20.40  
- @minecraft/server v1.7.0-beta

```js
import { GameMode } from '@minecraft/server';

/**
 * @author tutinoko2048
 * @param { import('@minecraft/server').Player } target
 * @returns { import('@minecraft/server').GameMode }
 */
export function getGameMode(target) {
  for (const key in GameMode) {
    if (target.matches({ gameMode: GameMode[key] })) return GameMode[key];
  }
}
```
