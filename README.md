# 3D_Reconstruction
本專案實現了從 RGB-D 輸入進行 3D 點雲重建，使用的是 7-Scenes 資料集
核心模型設計主要參考《Enhanced Camera Relocalization Through Optimized Accelerated Coordinate Encoding Network and Pose Solver》架構作修改

📁 資料集準備
本專案使用的是 7-Scenes 資料集。在執行訓練或測試程式碼之前，請完成以下準備步驟：

建議在 Colab 中掛載Google 雲端檔案(省去download時間)
具體需要掛載有四個folder(7SCENE, training/validate GT point cloud, testing GT point cloud, bonus GT point cloud)，分別對應地址如下:

7SCENE: https://drive.google.com/drive/folders/1qbQWc51AJ-Z7Jq48QdjMJuuMUASCYEt6
training/validate:https://drive.google.com/drive/folders/1tkJhWLj9WNGnnCWaPximkMBtI8ndw4vk
testing, bonus 可直接用其父目錄:https://drive.google.com/drive/folders/1-x9HSpBliRU2CVHGqZ8YWn6OT3dqEkVJ

1.做法為先新增捷徑至自己的drive
![image](https://github.com/user-attachments/assets/8f177dd3-9dbc-40c3-be69-2a33118550c4)

2.執行程式中drive.mount('/content/drive')

3.確認左側files內有成功掛載並且四個目錄所在位置與程式內四個路徑一致
![image](https://github.com/user-attachments/assets/fe9d0222-3175-4689-b49b-4073ffc72b44)

例如：'./drive/MyDrive/.../7SCENES','./drive/MyDrive/.../ground_truth_data/test'

🔧 相依套件與環境設定
本專案使用以下工具與套件：

torch: 2.5.1+cu124
torchvision: 0.20.1+cu124
opencv: 4.11.0
numpy: 1.26.4
matplotlib: 3.10.0
open3d: 0.19.0
PIL (Pillow): 11.1.0
Google Colab

(執行初始設定區塊，將會自動安裝所需的套件)


🚀 執行流程
當環境與資料集準備就緒後，請依下列步驟依序執行：

掛載 Google Drive 並設置資料集路徑

安裝相依套件（Colab 筆記本前幾個 cell

define dataset & related methods

訓練模型

執行testing

執行bonus

📦 輸出結果
在完成測試與 bonus 部分後，最終結果將會儲存於：

./content/test
./content/bonus

執行save out 即可下載分別的zip檔至本機。

📝 備註
評估指標包括：Chamfer Distance(loss)、準確度（Accuracy）、完整度（Completeness）
