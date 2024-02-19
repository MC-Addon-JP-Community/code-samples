# get-player-by-name
名前からPlayerクラスを取得する関数です。  

- Minecraft v1.20.60  
- @minecraft/server v1.9.0-beta
- @minecraft/server v1.8.0

```js
/**
 * @author tutinoko2048
 * @param { string } targetName
 * @returns { import('@minecraft/server').Player | undefined }
 */
export function getPlayerByName(targetName) {
  return world.getPlayers({ name: targetName })[0];
}
```
