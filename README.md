# 文言文 Skill Marketplace

教學用的 Claude Code skill marketplace，裡面有三支 skill：

| plugin | 做什麼 | 怎麼叫它 |
|---|---|---|
| `wenyan` | 把白話文章改寫成文言文 | 「幫我把這段轉成文言文」 |
| `english` | 把中文文章翻譯成英文 | 「幫我把這段翻成英文」 |
| `line-send-message` | 用 LINE 桌面版以本人身分傳訊息（限 macOS，需開電腦操作權限） | 「LINE 傳給小明說明天見」 |

## 安裝

在 Claude Code 裡先加入市集：

```
/plugin marketplace add leepoweii/wenyan-skill-marketplace
```

再挑要裝的 plugin（可以只裝一支）：

```
/plugin install wenyan@wenyan-skill-marketplace
/plugin install english@wenyan-skill-marketplace
/plugin install line-send-message@wenyan-skill-marketplace
```

之前已經加過市集的人，先更新再安裝新的 plugin：

```
/plugin marketplace update wenyan-skill-marketplace
```

## 檔案結構

```
wenyan-skill-marketplace/
├── .claude-plugin/
│   └── marketplace.json        ← marketplace 目錄：列出有哪些 plugin
└── plugins/
    ├── wenyan/
    │   ├── .claude-plugin/
    │   │   └── plugin.json     ← plugin 資訊：名稱、版本
    │   └── skills/
    │       └── wenyan/
    │           └── SKILL.md    ← skill 本體：觸發描述＋指令
    ├── english/
    │   ├── .claude-plugin/
    │   │   └── plugin.json
    │   └── skills/
    │       └── english/
    │           └── SKILL.md
    └── line-send-message/
        ├── .claude-plugin/
        │   └── plugin.json
        └── skills/
            └── line-send-message/
                └── SKILL.md
```

三層關係：**marketplace**（商店）→ **plugin**（商品包）→ **skill**（實際的能力）。

## 自己做一支

1. Fork 這個 repo。
2. 複製 `plugins/english` 改名，改 `plugin.json` 和 `SKILL.md`。
3. 在 `.claude-plugin/marketplace.json` 的 `plugins` 陣列加一筆。
4. 推上 GitHub，用 `/plugin marketplace add <你的帳號>/<repo>` 安裝。

## 授權

MIT
