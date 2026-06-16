# dot-font-label
言語が日本語になっている場合でもドットフォントで表示するラベルのサンプルです。

**2026/06/17**  
**マイクラ統合版 v1.26.30アップデートが来て、これをしなくてもドットフォントになるようになりました！！**

> [!WARNING]
> gridまたはfactory内のラベルの場合動作しないかもしれないです。

- Minecraft v1.21.101

```json
{
  "classic_label": {
    "type": "label",
    "text": "Test",
    "property_bag": {
      "#font_type": "classic"
    },
    "bindings": [
      {
        "binding_type": "view",
        "source_property_name": "#font_type",
        "target_property_name": "#font_type"
      }
    ]
  }
}
```
↑これを`ui/ui_common.json`に入れておくと、便利に使えます！  
使用例

```json
{
  "label@common.classic_label": {
    "text": "てすとだよ"
  }
}
```
