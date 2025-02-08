# get-item-amount
インベントリ内の指定したアイテムの個数を取得します

- Minecraft v1.21.50
- @minecraft/server v1.17.0-beta
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

## 使用例
```js
world.afterEvents.itemUse.subscribe(event => {
  const itemStack = event.itemStack;
  const player = event.source;

  // 棒を使用した時
  if (itemStack.typeId === 'minecraft:stick') {
    // 棒の個数の数値を変数amountに代入
    const amount = getItemAmount(player, 'minecraft:stick');
    player.sendMessage(`棒の個数: ${amount}`);
  }
});
```