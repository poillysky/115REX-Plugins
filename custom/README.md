# 自定义插件

把声明式插件包放到本目录下，例如：

```
custom/my-source/
  manifest.json
  metadata_source.json
```

`manifest.json` 里的 `origin` 字段会被 App 导入时强制改成 `custom`，不能冒充官方。

导入基址示例：

```
https://raw.githubusercontent.com/poillysky/115REX-Plugins/main/custom/my-source
```
