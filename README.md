# CMI - Detect Behavior with Sensor Data

Kaggleコンペティション「CMI - Detect Behavior with Sensor Data」の個人分析環境

## 📊 コンペティション概要

センサーデータを使用して行動を検出するコンペティションです。
- **目標**: センサーデータから特定の行動（ジェスチャー）を分類
- **データ**: 時系列センサーデータ + 被験者の人口統計データ
- **評価指標**: 分類精度

## 🎯 BFRB（Body-Focused Repetitive Behavior）行動分類

### **📌 Target（BFRB）Gestures - BFRB行動**

#### **髪を引っ張る系の行動**

- **Above ear - pull hair** （耳の上 - 髪を引っ張る）
  - 耳の上部にある髪を引っ張る行動
  - ストレスや不安時に見られる典型的なBFRB

- **Eyebrow - pull hair** （眉毛 - 髪を引っ張る）
  - 眉毛周辺の髪を引っ張る行動
  - 眉間の緊張を和らげようとする行動

- **Eyelash - pull hair** （まつ毛 - 髪を引っ張る）
  - まつ毛周辺の髪を引っ張る行動
  - 目の周りの緊張を和らげようとする行動

- **Forehead - pull hairline** （額 - 生え際を引っ張る）
  - 額の生え際の髪を引っ張る行動
  - 頭痛や緊張を和らげようとする行動

#### **皮膚を摘む・かく行動**

- **Cheek - pinch skin** （頬 - 皮膚を摘む）
  - 頬の皮膚を指で摘む行動
  - ストレス解消のための自己刺激行動

- **Forehead - scratch** （額 - かく）
  - 額をかく行動
  - かゆみや緊張による行動

- **Neck - pinch skin** （首 - 皮膚を摘む）
  - 首の皮膚を指で摘む行動
  - 首の緊張を和らげようとする行動

- **Neck - scratch** （首 - かく）
  - 首をかく行動
  - かゆみや緊張による行動

### **📌 Non-Target（非BFRB）Gestures - 通常の行動**

#### **書く・描く行動**

- **Write name on leg** （脚に名前を書く）
  - 自分の脚に名前を書く行動
  - 通常の筆記行動

- **Write name in air** （空中に名前を書く）
  - 空中に指で名前を書く行動
  - 練習や表現のための行動

#### **日常的な動作**

- **Wave hello** （こんにちはと手を振る）
  - 挨拶のための手振り行動
  - 社会的なコミュニケーション行動

- **Glasses on/off** （メガネの着脱）
  - メガネをかけたり外したりする行動
  - 日常的な道具操作

- **Text on phone** （電話でテキスト入力）
  - スマートフォンでテキストを入力する行動
  - 現代的なコミュニケーション行動

#### **探索・操作行動**

- **Feel around in tray and pull out an object** （トレイを探って物を取り出す）
  - トレイの中を手で探って物を取り出す行動
  - 探索・操作行動

- **Pull air toward your face** （空気を顔に向かって引っ張る）
  - 手で空気を顔に向かって扇ぐような行動
  - 涼しさを求める行動

#### **身体の一部をかく・摘む（非BFRB）**

- **Scratch knee/leg skin** （膝/脚の皮膚をかく）
  - 膝や脚の皮膚をかく行動
  - 実際のかゆみによる通常の行動

- **Pinch knee/leg skin** （膝/脚の皮膚を摘む）
  - 膝や脚の皮膚を摘む行動
  - 通常の身体接触行動

- **Drink from bottle/cup** （ボトル/カップから飲む）
  - ボトルやカップから飲み物を飲む行動
  - 日常的な摂食行動

### **分類の特徴**

| カテゴリ | 特徴 | 例 |
|---------|------|-----|
| **Target（BFRB）** | 強迫的・反復的・制御困難 | 髪を引っ張る、皮膚を摘む |
| **Non-Target（非BFRB）** | 目的のある通常行動 | 挨拶、筆記、道具操作 |

**BFRBの特徴:**
- ストレスや不安の解消が目的
- 身体に害を与える可能性
- 制御が困難
- 強迫的で繰り返し行われる

**非BFRBの特徴:**
- 社会的に適切
- 身体に害を与えない
- 制御可能
- 目的のある通常の行動

## 🚀 セットアップ

### 1. 環境構築

```bash
# uvを使用
uv sync
```

### 2. データセット

kaggleからダウンロードしてinputに格納