# item-enchantment
エンチャントを付けたアイテムを与えるサンプルです  
`!enchant`とチャットに入力すると、送信者に耐久力エンチャントのついた木の剣を与えます。

- Minecraft v1.21.50
- @minecraft/server v1.17.0-beta

```js
// ItemStack, EnchantmentTypesのインポートし忘れに注意
import { world, ItemStack, EnchantmentTypes } from '@minecraft/server';

world.afterEvents.chatSend.subscribe(event => {
  const { message, sender } = event;

  if (message === '!enchant') {
    // ここからが本番
    const woodenSword = new ItemStack('minecraft:wooden_sword', 1);

    // ItemEnchantableコンポーネントを取得
    const enchantable = woodenSword.getComponent('minecraft:enchantable');

    // 耐久力エンチャントを付ける
    enchantable.addEnchantment({
      type: EnchantmentTypes.get('minecraft:unbreaking'),
      level: 3
    });

    // 送信者に木の剣を与える
    // Inventoryコンポーネントを取得して、
    const container = sender.getComponent('minecraft:inventory').container;
    // addItemで空いているスロットにアイテムを追加
    container.addItem(woodenSword);
  }
})
```
