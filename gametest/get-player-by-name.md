# get-player-by-name
名前からPlayerクラスを取得する関数です。  

- Minecraft v1.20.40  
- @minecraft/server v1.6.0

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
