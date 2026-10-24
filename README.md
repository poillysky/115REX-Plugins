# 115REX-Plugins

[115REX](https://github.com/poillysky/115REX) 的插件仓库：官方内置包在此发版更新，自定义插件也放这里供导入 / 更新。

## 目录

```
official/<plugin-id>/     # 官方插件（App assets 同步一份；远程以此为准做 OTA）
  manifest.json
  metadata_source.json    # 按能力可选
custom/<plugin-id>/       # 自定义 / 社区插件（导入时 origin 强制为 custom）
catalog.json              # 官方目录索引（含 update 基址）
```

## App 如何用

- **官方**：App 启动时挂载内置包；「检查更新」请求  
  `https://raw.githubusercontent.com/poillysky/115REX-Plugins/main/official/<id>/`
- **自定义**：在插件设置里粘贴包基址，例如  
  `https://raw.githubusercontent.com/poillysky/115REX-Plugins/main/custom/<id>`  
  「检查更新」会按导入时的基址重新拉取。

每个包目录必须能直接访问到 `manifest.json`（可选 `metadata_source.json`）。

## 发版约定

1. 改 `official/<id>/` 后 **抬高 `manifest.version`**（语义化版本）。
2. 推送到 `main`。
3. App 端点「检查更新」即可拉到新包；内置 assets 可在下次 App 发版时再同步。
