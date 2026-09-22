# GameConfig - Excel配置管理与导出工具

参考 BalloonConfig 项目设计的游戏配置管理示例。

## 项目结构

```
GameConfig/
├── Excel/                  # Excel配置文件目录
│   ├── DRGift.xlsx        # 礼物配置
│   ├── DEquip.xlsx        # 装备配置
│   └── SystemConfig.xlsx  # 系统配置
├── excel2json.exe         # 导出工具
├── Output/                # JSON输出目录
└── README.md              # 说明文档
```

## 快速开始

### 导出配置为JSON

双击运行 `Run.bat` 或在命令行执行：

```bash
.\Run.bat
```

默认输出到 `Output/` 目录。

## 配置格式

### Excel文件格式

每个Excel文件代表一类配置，第一行为表头，后续行为数据。

**示例 (DRGift.xlsx):**

| Id | Name | Type | Attack | Value | Desc | Icon |
|----|------|------|--------|-------|------|------|
| 100 | 点赞 | Like | 0 | 15 | 基础点赞礼物 | icon_like |
| 101 | 火箭 | Rocket | 100 | 100 | 高级礼物-火箭 | icon_rocket |

### JSON输出格式

```json
[
  {
    "Id": 100,
    "Name": "点赞",
    "Type": "Like",
    "Attack": 0,
    "Value": 15,
    "Desc": "基础点赞礼物",
    "Icon": "icon_like"
  }
]
```

## 与BalloonConfig对比

| 特性 | BalloonConfig | GameConfig |
|------|---------------|------------|
| 配置格式 | Excel (.xlsx) | Excel (.xlsx) |
| 导出工具 | excel2json.exe | excel2json.exe |
| 输出格式 | JSON | JSON |

## 添加新配置

1. 在 `Excel/` 目录创建新的 .xlsx 文件
2. 第一行为表头字段名
3. 从第二行开始填写数据
4. 运行导出脚本生成JSON

## 注意事项

- Excel文件第一行必须是表头
- 支持多Sheet，每个Sheet单独导出
- 自动识别数字、布尔值等类型
- 空行会被自动跳过
