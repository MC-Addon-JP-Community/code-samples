# manifest.json
GameTestアドオンを作るのに必要なmanifestのサンプルです。  

- Minecraft v1.21.51

```json
{
  "format_version": 2,
  "header": {
    "name": "Sample GameTest Pack",
    "description": "sample",
    "version": [ 1, 0, 0 ],
    "uuid": "63670e93-0d7a-4527-ac7e-5568db07ac17",
    "min_engine_version": [ 1, 21, 51 ]
  },
  "modules": [
    {
      "type": "script",
      "description": "sample",
      "version": [ 1, 0, 0 ],
      "uuid": "b18738aa-2854-4ad3-ad88-402ea7c89b69",
      "language": "javascript",
      "entry": "scripts/[ファイル名].js"
    }
  ],
  "dependencies": [
    {
      "module_name": "@minecraft/server",
      "version": "1.17.0-beta"
    },
    {
      "module_name": "@minecraft/server-ui",
      "version": "1.4.0-beta"
    }
  ]
}
```
