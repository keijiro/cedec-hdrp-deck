---

↔ ページ送り

J スライド一覧

P 印刷用画面

---

HDRP

---

High<br/>Definition<br/>Render<br/>Pipeline

<notes>Unity が公式に開発配布する SRP のひとつ
最新の機能を詰め込んだ新しいレンダーパイプライン
もっと分かりやすく有り体に言ってしまえば……</notes>

---

PS4 を<br/>ベースラインにした<br/>新しいレンダラー

<notes>PS4 の AAA タイトルなどでよく使われているレンダリング方式をベースに
PS4 および PS4 以降のハードウェアのスペックに合わせて設計されたレンダラー</notes>

---

<img src="img/Features.png"/>

<notes>ここが便利だな、ここがおいしいな、と思ったポイントをアトランダムに紹介</notes>

---

- サンプルプロジェクト

  https://github.com/keijiro/TestbedHDRP

- プレゼン資料

  https://keijiro.github.io/cedec-hdrp-deck

---

<br/>

---

メリットその１<br/>ライティングが<br/>むちゃくちゃ強力

<notes>ライティングについて、様々な便利な機能が追加されているうえ、同時に高速化もなされているため、負荷を適度に抑えつつも、凝ったライティングを構築することが可能に</notes>

---

FPTL

<notes>その高速化のカギとなるのが FPTL</notes>

---

Fine<br/>Pruned<br/>Tiled<br/>Lighting

<notes>Deferred Shading を高速化する仕組み
いわゆるタイルベースレンダリングの一種
例えばこんなシーンがあるとする</notes>

---

<img src="img/FPTL1.png"/>

---

<img src="img/GBuffer.png"/>

---

<img src="img/FPTL2.png"/>

<notes>Directional Light は例外</notes>

---

<img src="img/FPTL3.png"/>

<notes>20 x 10 = 200 個のスポットライト</notes>

---

<img src="img/FPTL4.png"/>

---

<img src="img/GPUPro7.png"/>

---

半透明<br/>
Clustered Forward Shading

---

<notes>FPTL は主にパフォーマンスに関係
他にもパワーアップのポイントはある</notes>

---

新しいライト形状<br/>矩形ライト<br/>線分ライト

---

<img src="img/LightType.png"/>

<notes>テレビ画面のような面積を持った光源
レフ板やディフューザーを使ったような柔らかなライティング</notes>

---

<img src="img/LTC.png"/>

<notes>Sphere や Disc も追加予定</notes>

---

<img style="width:100%;height:1px" src="img/Blank.png"/>

<img style="width:49%" src="img/LightFx1.gif"/>
<img style="width:49%" src="img/LightFx2.gif"/>

<img style="width:100%;height:1px" src="img/Blank.png"/>

<notes>従来のスタティックなエリアライトと違ってダイナミックな使い方ができるのが面白い</notes>

---

すごく便利<br/>弱点：<br/>明るくなり過ぎがち

<notes>シャドウが使えないので</notes>

---

<img src="img/SSAO.png"/>

<notes>Direct lighting strength</notes>

---

<br/>

---

<img src="img/LightValue.png"/>

<notes>色温度</notes>

---

Volumetric Lighting

(Volumetric Fog)

---

<img src="img/VolumetricLight.png"/>

---

<notes>ライティングについては以上</notes>

---

メリットその２<br/>標準シェーダーがむちゃくちゃ強力

<notes>標準の PBR シェーダーが強化されている</notes>

---

<img src="img/Lit1.png"/>

<notes>ぱっと見では若干パラメーターが増えているかなあ、という程度だが……</notes>

---

<img src="img/Lit2.png"/>

---

<img src="img/Lit3.png"/>

---

<img src="img/Lit4.png"/>

---

<img src="img/Lit5.png"/>

---

<img src="img/Lit6.png"/>

---

Subsurface Scattering<br/>表面下散乱

---

<img src="img/SSS1.png"/>

<notes>人の肌、ゼリー、ミルク、大理石</notes>

---

<img src="img/SSS2.png"/>

<notes>エリアライトとの組み合わせが面白い</notes>

---

Anisotropy<br/>異方性反射

---

<img src="img/Anisotropy1.png"/>

---

<img src="img/Anisotropy2.png"/>

<notes>Tangent</notes>

---

<img src="img/Anisotropy3.png"/>

<notes>Binormal</notes>

---

Iridescence<br/>虹色反射

---

<img src="img/Iridescence.png"/>

<notes>シャボン玉、虫の羽</notes>

---

Bent Normal Mapping

---

<img src="img/BentNormal1.png"/>

---

<img src="img/BentNormal2.png"/>

<notes>Specular Occlusion</notes>

---

Displacement Mapping

---

<img src="img/Displacement1.png"/>

---

<img src="img/Displacement2.png"/>

<notes>Pixel displacement (parallax occlusion mapping)
Vertex/Tesselation displacement</notes>

---

<img src="img/Displacement3.png"/>

<notes>Pixel displacement は凹み方向のみ
平面への適用のみ正しく処理できる</notes>

---

<notes>このようにマテリアルの基本的な表現力が向上しているが
それを組み合わせて更に複雑にするための機能が用意されている</notes>

---

Layered Material<br/>
レイヤー機能

---

<img src="img/Layered2.png"/>

---

<img src="img/Layered1.png"/>

<notes>マスクにはテクスチャと頂点カラーが使える</note>

---

<img src="img/Layered3.png"/>

<notes>レイヤーとデカールを使いこなすのがディテール感を出すコツ</notes>

---

<br/>

---

メリットその３<br/>カスタマイズに<br/>フレンドリー

<notes>カスタマイズされることを想定した設計になっている
まず何といっても違うのは……</notes>

---

ソースコードが<br/><a href="https://github.com/Unity-Technologies/ScriptableRenderPipeline">GitHub</a> 上に<br/>公開されている

---

パッケージとして<br/>独立した<br/>バージョニング

---

<img src="img/Versioning1.png"/>

---

<img src="img/Versioning2.png"/>

---

<img src="img/Versioning3.png"/>

---

<img src="img/Versioning4.png"/>

---

シェーダーの<br/>ホワイト<br/>ボックス化

---

今までのUnity<br/>謎マクロ<br/>謎プラグマが暗躍

<notes>謎なブラックボックス部分が多くてカスタマイズしにくいという側面があった</notes>

---

<pre>#pragma surface surf Standard vertex:vert addshadow

void vert(inout appdata_full v, out Input data)
{
  UNITY_INITIALIZE_OUTPUT(Input, data);
  ...
}

void surf(Input IN, inout SurfaceOutputStandard o)
{
  ...
}</pre>

<notes>シェーダーコンパイラが見えない所で生成するものが多く、読み解くにも限界が</notes>

---

普通のC言語風の実装<br/>ソースから解読可能<br/>改造も可能

<notes>シェーダーライブラリも汎用性の高いものになっている</notes>

---

まずはここから <a href="https://github.com/Unity-Technologies/ScriptableRenderPipeline/blob/master/com.unity.render-pipelines.high-definition/HDRP/Material/Lit/Lit.shader">HDRP/Material/Lit/Lit.shader</a>

---

#define<br/>#ifdef<br/>#include<br/>の塊

---

ホワイトボックス<br/>なので諦める<br/>ポイントは少ない

---

<img style="width:100%;height:1px" src="img/Blank.png"/>

<img style="width:49%" src="img/CustomShader1.gif"/>
<img style="width:49%" src="img/CustomShader2.gif"/>

<img style="width:49%" src="img/CustomShader3.gif"/>
<img style="width:49%" src="img/CustomShader4.gif"/>

<img style="width:100%;height:1px" src="img/Blank.png"/>

---

<br/>

---

HDRP<br/>導入検討の<br/>ポイント

---

で、もう<br/>完成してるの？<br/>使っていいの？

<notes>残念ながら、まだプレビュー
Unity 2019 のどこかでプレビューを外したい</notes>

---

- 未実装部分がある
- 後方互換性が不確実

---

- 長期プロジェクトへの導入は慎重に
- ワンオフものならアリかも

<notes>後方互換性がしっかりしていないので、長期間付き合っていくのはつらい
とは言え、いきなりクラッシュするような不安定さは無いので、短期間の用途で使うなら</notes>

---

謝辞

- Statue models scanned by Geoffrey Marchal (CC-BY)

  https://sketchfab.com/geoffreymarchal

- Photogrammetric textures created by StruffelProductions (CC0)

  https://cc0textures.com
