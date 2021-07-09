# AutoScan
based on Hello_AR_Java
1.android.view.ViewRootImpl$CalledFromWrongThreadException: Only the original thread that created a view hierarchy can touch its views. (目前已解，用runOnUiThread)

2.autoScan因為放在on draw frame裡，會隨著frame更新被一直重複call，導致運算量過大、卡頓

-> handleTap中，因為是用HitResult來做斷點，所以他設了一連串判斷式來只抓他hit那時的frame去算，

3.我們的需求是只抓單一一個frame？（若是，則或許可藉由再修改onClick事件的開關來下手）

還是要不斷紀錄每個frame？那麼就須解決運算量過大、卡頓->開多個thread?

4.每一frame的取x y間隔要是多少？現在每100計算一次，還是很卡...

要如何儲存大量計算資料？
