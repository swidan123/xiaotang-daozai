# 歌词样式扩展（lyrics.style v1）

无脚本资源插件，启用后扩展原生音乐与岛上歌词的卡拉 OK 逐字变色样式。未启用或卸载后恢复原本纯白歌词。只能启用一个歌词样式插件。

维护者负责清单、样式配置、设置项、封面和插件版本，不需要提交脚本。媒体进度读取、KRC/YRC 逐字解析、无损结构化缓存、双向文字映射、互补裁剪染色与浅色皮肤可读性适配均由本体负责，插件不读取播放或本机数据。

## plugin.json

```json
{
  "id": "swidan123.karaoke-lyrics",
  "name": "逐字变色歌词",
  "author": "swidan123",
  "version": "1.0.0",
  "api": 1,
  "runtime": "assets",
  "entry": "lyrics-style.json",
  "cover": "cover.png",
  "owner": "music",
  "capabilities": ["lyrics.style", "settings"],
  "dataVersion": 1,
  "permissions": {},
  "settings": [
    {"key": "enabled", "label": "歌词逐字变色", "type": "switch", "default": "true"},
    {
      "key": "color",
      "label": "已唱颜色",
      "type": "choice",
      "default": "rainbow",
      "choices": [
        {"value": "rainbow", "label": "彩虹流光"},
        {"value": "aurora", "label": "极光渐变"},
        {"value": "sunset", "label": "晚霞渐变"},
        {"value": "sky_blue", "label": "晴空蓝"},
        {"value": "sakura_pink", "label": "樱花粉"},
        {"value": "mint_green", "label": "薄荷绿"},
        {"value": "amber_gold", "label": "琥珀金"},
        {"value": "neon_purple", "label": "电光紫"},
        {"value": "custom", "label": "自定义色号"}
      ]
    },
    {"key": "custom_color", "label": "自定义色号（#RRGGBB）", "type": "text", "default": "#38BDF8"},
    {"key": "expanded", "label": "展开歌词同步变色", "type": "switch", "default": "true"}
  ]
}
```

## lyrics-style.json

```json
{
  "version": 1,
  "karaoke": true,
  "defaultColor": "rainbow",
  "defaultCustomColor": "#38BDF8",
  "expanded": true,
  "enabledSetting": "enabled",
  "colorSetting": "color",
  "customColorSetting": "custom_color",
  "expandedSetting": "expanded"
}
```
