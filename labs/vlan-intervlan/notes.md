# VLAN + Inter-VLAN Routing Lab

## 目的 (Objective)
- 部署ごとにネットワークを分離し、セキュリティと効率を向上させる
- VLAN間通信を可能にするため、Router-on-a-Stick構成を実装する
- CCNA試験範囲の「VLAN」「サブインターフェース」「デフォルトゲートウェイ設定」を理解する

---

## トポロジ (Topology)
- Switch1 に VLAN10 (Sales), VLAN20 (HR), VLAN30 (IT) を作成
- Router0 の G0/0 インターフェースを trunk 接続し、サブインターフェースで各 VLAN をルーティング
- 各 VLAN に PC を配置し、通信確認を行う

*(topology.png をここに添付)*

---

## 設定手順 (Configuration Steps)

### Switch 設定例
```bash
Switch> enable
Switch# configure terminal
Switch(config)# vlan 10
Switch(config-vlan)# name Sales
Switch(config)# vlan 20
Switch(config-vlan)# name HR
Switch(config)# vlan 30
Switch(config-vlan)# name IT
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode trunk
