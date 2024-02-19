# get-item-amount
インベントリ内の指定したアイテムの個数を取得します

- Minecraft v1.20.60
- @minecraft/server v1.9.0-beta
- @minecraft/server v1.8.0

```js
/**
 * @author tutinoko2048
 * @param { import('@minecraft/server').Player } player
 * @param { string } itemId
 * @returns { number }
 */
export function getItemAmount(player, itemId) {
  let amount = 0;
  const { container } = player.getComponent('minecraft:inventory');
  for (let i = 0; i < container.size; i++) {
    const item = container.getItem(i);
    if (!item) continue;
    if (item.typeId === itemId) amount += item.amount;
  }
  return amount;
}
```
