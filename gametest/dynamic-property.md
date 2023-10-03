# dynamic-property
DynamicPropertyの使用方法です

- Minecraft v1.20.30  
- @minecraft/server v1.6.0-beta

```js
import { world, DynamicPropertiesDefinition } from '@minecraft/server';

/** プロパティ名 任意の文字列 @type { string } */
const identifier;
/** 最大文字数 Entity: 128KB, World: 1MB @type { number } */
const propertySize;
/** 初期値 オプションのため任意 @type { boolean | number | string | Vector3 | undefined } */
const defaultValue;

world.afterEvents.worldInitialize.subscribe(ev => {
  const property = new DynamicPropertiesDefinition();

  property.defineBoolean(identifier, defaultValue);
  property.defineNumber(identifier, defaultValue);
  property.defineString(identifier, propertySize, defaultValue);
  property.defineVector(identifier, defaultValue);

  ev.propertyRegistry.registerWorldDynamicProperties(property);
  ev.propertyRegistry.registerEntityTypeDynamicProperties(property, entityType);
});

world.getDynamicProperty(identifier);
world.setDynamicProperty(identifier, data);

entity.getDynamicProperty(identifier);
entity.setDynamicProperty(identifier, data);
```