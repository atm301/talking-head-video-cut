# 口播影片剪片工作流

把一段「有人對著鏡頭講話」的長錄影，剪成一批帶字幕、資訊動畫、片頭圖卡、BGM 的
短影音與長片（直式 9:16 ＋ 橫式 16:9）。

**課程講座、商品開箱、產品介紹、自錄口播、客戶見證都適用。**

👉 **[開啟安裝導引](https://atm301.github.io/talking-head-video-cut/)** — 回答三個問題，
就給你該下載的檔案、該貼的指令，跟該對 AI 說的第一句話。

## 這是什麼

一套在你自己電腦上執行的剪片流程：Python ＋ ffmpeg，Windows 與 macOS 皆可跑。
錄影檔不會上傳到任何地方。

搭配 AI 使用（Claude Code、Claude 桌面版 Cowork、Codex CLI 皆可），
AI 負責選段、寫字幕、寫設定檔與除錯，引擎負責去靜音、算圖與驗收。

## 包了什麼

| 檔案 | 內容 |
|---|---|
| `SKILL.md` | 規則總表。符合 [Agent Skills](https://agentskills.io) 開放標準，Claude 與 Codex 通用 |
| `references/手冊.md` | 完整手冊：環境判別、九步驟、剪輯參數、設定檔規格、內容安全、踩坑紀錄、安裝路徑 |
| `AGENTS.md` | 給 Codex 的簡短指示（放專案根目錄） |
| `操作流程說明.md` | 給人看的操作手冊 |
| `scripts/` | 引擎本體：去靜音與時間軸重映射、動畫元件庫、算圖前健檢、排隊執行、成品驗收 |
| `scripts/paths.py` | **唯一要改的檔案** |

## 兩種模式

| | 模式一 雙畫面錄影 | 模式二 單機位自錄 |
|---|---|---|
| 來源 | 課程、講座、會議側錄 | 商品開箱、產品介紹、口播、見證 |
| 要量畫面幾何 | 要 | 不用 |
| 版面 | `A` / `B` / `C` | `F` / `P` |

兩種模式共用同一套引擎與同一套剪輯參數，切換只要改 `paths.py` 三行。

## 需要的環境

- Python 3.10+
- ffmpeg（**必須含 libass**，否則字幕燒不上去）
- `pip install faster-whisper opencc-python-reimplemented pillow numpy`
- 一套有 Bold 與 Heavy 兩個字重的中文字型

## 授權

[MIT License](LICENSE) — 可自用、修改、再散布，商業使用也可以。
唯一的條件是保留著作權聲明。

## 關於

[圭話行銷 ATMarketing](https://atmarketing.tw/)｜何佳勳（小圭）
[粉絲專頁](https://www.facebook.com/ATMarketing.tw/) ‧ [線上課程](https://atmarketing.kaik.io/@skyman)
