# 文言文 Skill Marketplace

教學用的 Claude Code skill marketplace，裡面只有一支 skill：**把白話文章轉成文言文**。

## 安裝

在 Claude Code 裡輸入：

```
/plugin marketplace add leepoweii/wenyan-skill-marketplace
/plugin install wenyan@wenyan-skill-marketplace
```

## 使用

貼上一段文章，然後說：

```
幫我把這段轉成文言文
```

## 檔案結構

```
wenyan-skill-marketplace/
├── .claude-plugin/
│   └── marketplace.json        ← marketplace 目錄：列出有哪些 plugin
└── plugins/
    └── wenyan/
        ├── .claude-plugin/
        │   └── plugin.json     ← plugin 資訊：名稱、版本
        └── skills/
            └── wenyan/
                └── SKILL.md    ← skill 本體：觸發描述＋指令
```

三層關係：**marketplace**（商店）→ **plugin**（商品包）→ **skill**（實際的能力）。

## 自己做一支

1. Fork 這個 repo。
2. 複製 `plugins/wenyan` 改名，改 `plugin.json` 和 `SKILL.md`。
3. 在 `.claude-plugin/marketplace.json` 的 `plugins` 陣列加一筆。
4. 推上 GitHub，用 `/plugin marketplace add <你的帳號>/<repo>` 安裝。

## 授權

MIT
