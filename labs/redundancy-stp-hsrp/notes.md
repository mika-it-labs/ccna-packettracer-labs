# 冗長化構成（STP / HSRP）演習

## 🧠 演習の目的
- ネットワークの冗長性を確保するための基本技術を理解する
- STP（Spanning Tree Protocol）によるループ防止構成を体験する
- HSRP（Hot Standby Router Protocol）によるゲートウェイ冗長化を構築する

## 🧩 トポロジ概要
- L2スイッチ2台（冗長構成）
- Router2台（HSRP構成）
- PC1台（クライアント）

※構成図は `topology.png` を参照

## ⚙️ 使用機器
- Switch：Cisco 2960 × 2
- Router：Cisco 2911 × 2
- PC：Generic PC × 1

## 🛠 設定手順（概要）

### 🔹 STP構成（Switch側）
- VLANを作成（例：VLAN10）
- ポートにVLANを割り当て
- STPの動作確認（Root Bridgeの選定）

### 🔹 HSRP構成（Router側）
- 同一セグメントに2台のRouterを配置
- HSRPグループを設定し、仮想IPを作成
- 優先度設定でActive/Standbyを制御

## 📸 トポロジ図
![冗長化トポロジ](./topology.png)

## 📄 設定ファイル
- 詳細なCLI設定は `config.txt` を参照

## ✅ 動作確認
- PCから仮想ゲートウェイへPing  
- RouterのActive/Standby切り替えテスト  
- STPのRoot Bridge変更による経路変化確認

## 📝 学びと気づき
- STPによって物理ループが論理的に遮断される仕組みを理解できた  
- HSRPにより、片方のRouterがダウンしても通信が継続できることを確認  
- 冗長化は「止まらないネットワーク」を作るための重要な技術であると実感

