# AGENTS.md

This file provides guidance to the AI agent when working with code in this repository.

## 项目概述

Excel 配置导出工具项目，用于将 Excel (.xlsx) 配置文件导出为 JSON 格式。

## 项目结构

- `Excel/` - Excel 配置源文件目录
- `ExcelExpoter/` - 导出工具目录（包含 excel2json.exe）
- `Output/` - JSON 输出目录

## 导出操作

运行导出脚本：

```bash
cd ExcelExpoter
.\Run.bat
```

导出的 JSON 文件会保存到 `Output/` 目录。

## Excel 文件规范

- 第一行必须是表头（字段名）
- 支持多 Sheet，每个 Sheet 单独导出为 JSON 文件
- 文件名格式：`<Excel文件名>_<Sheet名>.json`

## 注意事项

- `Output/*.json` 已在 .gitignore 中忽略
- `*.exe` 已在 .gitignore 中忽略
- Excel 临时文件（`~$*.xlsx`）已忽略