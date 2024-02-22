# dot-font-label
言語が日本語になっている場合でもドットフォントで表示するラベルのサンプルです。

> [!WARNING]
> factory／grid内のラベルの場合動作しない可能性があります

- Minecraft v1.20.62

```json
{
  "dot_font_label": {
    "type": "panel",
    "text": "Test",
    "font_type": "#font_type",
    "bindings": [
      {
        "binding_type": "view",
        "source_control_name": "font_property_panel",
        "source_property_name": "#font_type",
        "target_property_name": "#font_type"
      }
    ],
    "controls": [
      {
        "font_property_panel": {
          "type": "panel",
          "size": [ 0, 0 ],
          "property_bag": {
            "#font_type": "classic"
          }
        }
      }
    ]
  }
}
```