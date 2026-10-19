<!-- ffxiv-tc-port 繁體中文說明開始 -->
# NotificationMasterAPI(台服 fork)

由 NightmareXIV 開發的函式庫，讓其他 Dalamud 插件能透過 IPC 呼叫 `NotificationMaster` 插件，
不需自己處理 Windows API 就能彈出 Windows 通知、播放提示音、閃爍工作列圖示、把遊戲視窗帶到前景，
或送出自訂 HTTP 請求。

## 台服 fork 的目的

跟隨艦隊釘 API13 / net9。上游沒有 README，這份是我方新寫的說明。

## 與上游的差異

- `TargetFramework` 從 `net10.0-windows7.0` 改回 `net9.0-windows7.0`（艦隊釘 API13 / net9）。
- 拿掉每個呼叫前的 `ICallGateSubscriber.HasFunction` 檢查：API13 的介面沒有這個成員；
  NotificationMaster 沒載入的情況原本就由外層攔 `IpcNotReadyError` 處理。

## 誰在用它

- 子模組：目前只有 `NotificationMaster` 插件本身（提供端）以子模組使用這份 fork。
- `AutoRetainer`、`DailyDuty`、`Lifestream`、`Splatoon`、`SubmarineTracker` 透過 NuGet 引用上游發布的
  `NotificationMasterAPI` 套件，不經過這份 fork。

上游原始碼：<https://github.com/NightmareXIV/NotificationMasterAPI>
<!-- ffxiv-tc-port 繁體中文說明結束 -->
