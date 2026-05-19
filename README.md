# 無人機群飛編劇工具
## 提供圖與文字轉飛機的位置
## 模擬器可提供錄製影片，輸出後可在手機與電腦播放
## Skybrush Server 對接說明
連線方式
畫面底部新增了永久狀態列，顯示連線指示燈和所有已連線無人機：

在 URL 欄輸入 Skybrush Server 位址（預設 http://localhost:5000）
點「連線」— 自動透過 Socket.io WebSocket 連到 Flockwave 協議的 fw 命名空間
連線成功後自動抓取 UAV-LIST，無人機 ID 以標籤顯示，每 3 秒更新狀態

艦隊控制面板（🛸 按鈕）
功能Flockwave 訊息起飛 / 降落 / 返航UAV-TAKEOFF / UAV-LAND / UAV-RTH懸停UAV-HOVER緊急停機（需確認）UAV-HALTLED 燈效SHOW-SETLIGHTS同步格子色 → LED取格子最多色 → SHOW-SETLIGHTS
格子隊型 → GPS 飛行
設定中心緯度/經度、飛行高度、無人機間距後：

「📤 推送當前隊型」：把格子上每個亮點對應到一台無人機，計算 GPS 偏移後發送 UAV-FLY 指令，同時設定對應的 LED 顏色
「📋 推送指定隊型」：可選序列中的任意一幀

注意事項

Skybrush Server 預設只接受同一網段連線，若從外部存取需要設定 CORS 或 VPN。瀏覽器開啟本機檔案時若 Server 是 localhost 則不受跨域限制影響。
