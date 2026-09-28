\# 🕊️ OrnithoLinker (羽ばたき機構 設計支援シミュレータ)



An interactive, browser-based 2D kinematic CAD simulator for designing and analyzing \*\*ornithopter 4-bar flap mechanisms (crank-rocker linkages)\*\*.



単一の `index.html` のみで動作し、サーバーやビルドツール不要で使用可能です。



\[!\[License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

\[!\[GitHub Pages](https://img.shields.io/badge/Demo-GitHub%20Pages-brightgreen)](https://ys-lavic.github.io/OrnithoLinker/)

\---



\## 📸 Overview / 概要



!\[Screenshot](assets/screenshot1\_jp.png)

!\[Screenshot](assets/screenshot1\_en.png)



\---



\## ✨ Features / 主な機能



\### 1. Kinematics \& Mechanics (機構学・幾何学エンジン)



\- \*\*Grashof Condition \& Closed-Loop Solver (Grashof条件 \& 閉ループ方程式解析)\*\*:

機構ロックや干渉が発生しないかをリアルタイムに判定。

\- \*\*Symmetric Wing Angle Definition (左右対称な角度定義)\*\*:

&#x20;   - 水平姿勢を \*\*$0^\\circ$\*\*

&#x20;   - \*\*右翼\*\*: 反時計回り（上反角）が正（$+$）／時計回り（下反角）が負（$-$）

&#x20;   - \*\*左翼\*\*: 時計回り（上反角）が正（$+$）／反時計回り（下反角）が負（$-$）

&#x20;   - 左右ともに「跳ね上げでプラス、打ち下ろしでマイナス」の直感的な数値を表示。



\### 2. Dual-Crank \& Motor Dynamics (デュアルクランク・動力学)



\- \*\*Crank Separation Distance ($D\_{\\text{crank}}$ / 軸間距離)\*\*:

シングルクランクの場合は 0mm に設定。

\- デュアルクランクの場合はクランク間の距離を設定。

\- \*\*Motor Rotation Direction (CW / CCW / 回転方向)\*\*:

モーターの回転方向（時計回り / 反時計回り）を切り替え、上昇・下降時の特性の変化を検証。

\- \*\*Coupling Mode (連動方式)\*\*:

&#x20;   - \*\*Counter-rotating (対向逆回転)\*\*: 

&#x20;   デュアルギアの場合は通常こちら。

&#x20;   ギア連動によるカウンタートルク相殺構成。

&#x20;   - \*\*Co-rotating (同方向回転)\*\*: 

&#x20;   シングルギアの場合はこちら。

&#x20;   ベルトやプーリー連動による同調回転。

\- \*\*Phase Offset ($\\Delta\\Phi$ / クランク位相差)\*\*:

シングルクランクの場合の左右翼の位相調整が可能。デュアルギアの場合は通常 180°に指定。

同位相（$0^\\circ$）、直交位相（$90^\\circ$）、逆位相交互羽ばたき（$180^\\circ$）などを自在に設定可能。



\### 3. Analysis \& Visual Feedback (解析・モニター機能)



\- \*\*Quick-Return \& Time Ratio (上昇/下降時間比)\*\*:

アップストロークとダウンストロークの、所要時間比および角度比をリアルタイム表示。

\- \*\*Max Up / Max Down / Stroke Angle (最大上方角・下方角・全振幅)\*\*

\- \*\*Centered Zero Displacement Graph (縦軸中心 0° の角度変位波形グラフ)\*\*:

下部に2周期分（$0^\\circ \\sim 720^\\circ$）の左右翼端変位を常時プロット。

位相合わせに使用できる。

\- \*\*Manual Crank Angle Seek Slider (手動クランク角シークバー)\*\*:

停止中および動作中に $0^\\circ \\sim 360^\\circ$ のクランク角を直接スライダーで指定でき、上死点や下死点の静止姿勢を精密検証。



\### 4. Usability \& Export (操作性・データ管理)



\- \*\*Bilingual Support (日英言語切り替え)\*\*: 

ヘッダーのボタンから `JA` / `EN` をワンクリック切り替え。

\- \*\*Horn Plate Toggle (剛体プレート表示切替)\*\*: 

スパー付根の剛体補強板（三角プレート）の表示/非表示を選択可能。

\- \*\*Aeroelastic Membrane (柔軟翼膜アニメーション)\*\*: 

主翼の各速度に応じた空気抵抗によるたわみ（移送遅れ）を再現。

\- \*\*Data Persistence (保存・共有)\*\*:

&#x20;   - \*\*Slots (LocalStorage)\*\*: ブラウザ内に名前付きで設計パターンを保存・呼出。

&#x20;   - \*\*JSON Import / Export\*\*: 設定ファイルを外部保存・読み込み。

&#x20;   - \*\*PNG Snapshot\*\*: CAD画面を高解像度画像としてダウンロード。



\---



\## 🎯 Presets / プリセット一覧



実機設計の用途に合わせた3つの標準プリセットを内蔵しています：



| プリセット名 (EN / JA) | 特徴と用途 |

| --- | --- |

| \*\*Rubber-Powered / ゴム動力機\*\* | 単一クランクの軽飛行機など。

左右の位相補正あり。 |

| \*\*Single-Crank RC / シングルクランク\*\* | シングルギアのRCなど。

左右の位相補正あり。 |

| \*\*Dual-Crank Gear / デュアルクランク\*\* | デュアルギアのRCなど。

左右ギアの対向逆回転でカウンタートルクを相殺できる構成。 |



\---



\## 🚀 Quick Start / 使い方



\### ウェブアプリ



https://ys-lavic.github.io/OrnithoLinker/ 



\### Local Run (ローカルで実行)



ビルドやインストールは一切不要です：

本リポジトリをZIPダウンロードし、index.htmlをブラウザで開いてください。

&#x20;   



