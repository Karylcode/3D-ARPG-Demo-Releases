# 3D ARPG Demo

第三人稱動作遊戲 Demo 的試玩版，有 Windows 和 Mac 版。這裡只放打包好的遊戲，不放原始碼。

到 [Releases](../../releases/latest) 下載最新版：

| 系統 | 要下載的檔案 |
| --- | --- |
| Windows 10 / 11（64 位元） | `3D-ARPG-Demo-vX.Y.Z-win64.zip` |
| Mac（Intel 與 Apple 晶片都可以，macOS 11 以上） | `3D-ARPG-Demo-vX.Y.Z-mac.zip` |

檔名裡的 `X.Y.Z` 是版本號。`.sha256` 結尾的檔案是校驗碼，不用下載。

---

## Windows

1. 下載 `*-win64.zip`。
2. 在 zip 上按右鍵 → 內容 → 勾選「解除封鎖」→ 確定，再解壓縮。
3. 點 `Update.bat` 開遊戲。

如果出現藍色的「Windows 已保護您的電腦」（SmartScreen），按「其他資訊」→「仍要執行」。遊戲沒有簽章，所以第一次會跳這個。

## Mac

整段步驟都可以直接複製貼上。

1. 下載 `*-mac.zip`，Safari 會放在「下載項目」。
2. 在「下載項目」雙擊 zip 解壓縮，會多出一個資料夾 `3D-ARPG-Demo-vX.Y.Z-mac`。
3. 打開「終端機」（Spotlight 搜尋 `終端機`），整段貼上，按 Return：

   ```bash
   cd ~/Downloads/3D-ARPG-Demo-v*-mac && xattr -cr . && codesign --force --deep -s - 3D-ARPG-Demo.app && echo "完成，可以開遊戲了"
   ```

   這一步做兩件事：清掉下載來的「隔離」標記，並替遊戲做本機簽章。沒簽章的程式在 Apple 晶片（M1、M2、M3…）的 Mac 上打不開。
   「下載項目」資料夾在系統裡的實際名稱是 `~/Downloads`。如果你把遊戲資料夾移到別處，把指令裡的路徑改成那個資料夾就好。
4. 雙擊資料夾裡的 `Update.command` 開遊戲。

只要做一次。之後都雙擊 `Update.command` 開遊戲。

### 還是打不開

- 出現「已損毀」或「無法打開，因為無法驗證開發者」：重貼一次上面第 3 步的指令。
- 還是被擋：開「系統設定 → 隱私權與安全性」，往下找到被擋的 `3D-ARPG-Demo` 或 `Update.command`，按「仍要打開」。
- 較舊的 macOS 也可以在檔案上按右鍵（或 Control + 點一下）→「打開」。
- 雙擊 `Update.command` 沒反應或說沒有權限：在終端機貼 `chmod +x ~/Downloads/3D-ARPG-Demo-v*-mac/Update.command`。

---

## 更新

之後每次都用 `Update.bat`（Windows）或 `Update.command`（Mac）開遊戲：

- 會先查有沒有新版。有就自動下載、驗證、換檔，再開遊戲。
- 已經是最新版，或沒有網路，就直接開遊戲。
- 更新失敗會保留目前的版本，不會把遊戲弄壞。
- 更新時遊戲要先關掉。

想手動更新也可以：下載新版 zip，解壓縮後覆蓋舊資料夾；Mac 手動更新後要再貼一次上面第 3 步的指令。
