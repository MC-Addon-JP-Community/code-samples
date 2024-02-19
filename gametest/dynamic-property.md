# dynamic-property
DynamicPropertyの使用方法です

- Minecraft v1.20.60  
- @minecraft/server v1.9.0-beta

```js
import { world } from '@minecraft/server';

/** プロパティ名 任意の文字列 @type { string } */
const identifier;

/** 保存したデータの取得 */
world.getDynamicProperty(identifier);
entity.getDynamicProperty(identifier);
/** データの保存 */
world.setDynamicProperty(identifier, data);
entity.setDynamicProperty(identifier, data);
/** データの削除 */
world.setDynamicProperty(identifier, undefined);
entity.setDynamicProperty(identifier, undefined);
```
