---

HDRP

---

High<br/>Definition<br/>Render<br/>Pipeline

<notes>Unity が公式に開発配布する SRP のひとつ
最新の機能を詰め込んだ新しいレンダーパイプライン
もっと分かりやすく有り体に言ってしまえば……</notes>

---

PS4 を<br/>ベースラインにした<br/>新しいレンダラー

<notes>PS4 の AAA タイトルなどでよく使われているレンダリング方式をベースに</notes>

---

<img src="img/Features.png"/>

<notes>ここが便利だな、ここがおいしいな、と思ったポイントをアトランダムに紹介</notes>

---

<a href="https://github.com/keijiro/TestbedHDRP">github.com/keijiro/TestbedHDRP</a>

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

<notes>Deferred Shading ではこれをまず GBuffer にレンダリングする</notes>

---

<img src="img/GBuffer.png"/>

<notes>これを細かなタイルに分割して</notes>

---

<img src="img/FPTL2.png"/>

<notes>２段階に分けて厳密に絞り込むので fine pruned
GBuffer へのアクセスが最小限で済むのでメモリ帯域に優しい</notes>

<notes>難しい理屈はあるが……簡単に言えば……
タイルデバッグモードで表示されるこの数値を低くすれば軽くなる
Directional Light は例外</notes>

---

<img src="img/FPTL3.png"/>

<notes>極端な例
20 x 10 = 200 個のスポットライト</notes>

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

<notes>スタティックなエリアライトと違って動きのある表現にも使えるのが面白い</notes>

---

すごく便利<br/>弱点：<br/>明るくなり過ぎがち

<notes>シャドウが使えないので</notes>

---

<img src="img/SSAO.png"/>

<notes>PPS の Volume と組み合わせるといいかも</notes>

---

<br/>

---

<img src="img/LightValue.png"/>

<notes>色温度での色の設定も可能</notes>

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

---

<img src="img/SSS2.png"/>

---

<img src="img/SSS3.png"/>

---

Thickness map<br/>xNormal<br/>Knald<br/>Substance Painter

---

<img src="img/SSS4.png"/>

<notes>マテリアルとは別に Diffusion Profile というのを用意する
１パイプラインにつき１６個まで定義できる</notes>

---

Anisotropy<br/>異方性反射

---

<img src="img/Anisotropy1.png"/>

---

<img src="img/Anisotropy2.png"/>

---

<img src="img/Anisotropy3.png"/>

---

Iridescence<br/>虹色反射

---

<img src="img/Iridescence.png"/>

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

<notes>Pixel displacement
Tesselation displacement</notes>

---

<img src="img/Displacement3.png"/>

---

<img src="img/Displacement4.png"/>

<notes>Pixel displacement は凹み方向のみ
平面への適用のみ正しく処理できる</notes>

---

Layered Material<br/>
レイヤー機能

---

<img src="img/Layered2.png"/>

---

<img src="img/Layered3.png"/>

---

<img src="img/Layered1.png"/>

<notes>マスクにはテクスチャと頂点カラーが使える
レイヤーとデカールを使いこなすのがディテール感を出すコツ</notes>

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

<notes>中の実装についてもカスタマイズが許容されるものになっている
というのも……</notes>

---

今までのUnity<br/>謎マクロ<br/>謎プラグマが暗躍

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

---

関数、structを使った<br/>C言語風の実装<br/>汎用的な<br/>シェーダーライブラリ<br/>

---

<img style="width:100%;height:1px" src="img/Blank.png"/>

<img style="width:49%" src="img/CustomShader1.gif"/>
<img style="width:49%" src="img/CustomShader2.gif"/>

<img style="width:49%" src="img/CustomShader3.gif"/>
<img style="width:49%" src="img/CustomShader4.gif"/>

<img style="width:100%;height:1px" src="img/Blank.png"/>

---

カスタムシェーダー<br/><a href="https://github.com/Unity-Technologies/ScriptableRenderPipeline/blob/master/com.unity.render-pipelines.high-definition/HDRP/Material/Lit/Lit.shader">Lit.shader</a> をコピペして改造

---

頂点いじるなら <a href="https://github.com/Unity-Technologies/ScriptableRenderPipeline/blob/master/com.unity.render-pipelines.high-definition/HDRP/ShaderPass/VertMesh.hlsl">VertMesh.hlsl</a> の辺りを改造

---

GBuffer いじるなら <a href="https://github.com/Unity-Technologies/ScriptableRenderPipeline/blob/master/com.unity.render-pipelines.high-definition/HDRP/ShaderPass/ShaderPassGBuffer.hlsl">ShaderPassGBuffer.hlsl</a> の辺りを改造

---

#define と<br/>#include の塊

---

ホワイトボックス<br/>なので諦める<br/>ポイントは少ない

---

<br/>

---

HDRP<br/>導入検討の<br/>ポイント

<notes>導入すべきか、せざるべきか
判断ポイント</notes>

---

で、もう<br/>完成してるの？<br/>使っていいの？

---

- 未実装部分が少なくない
- 後方互換性が確立されていない

---

- 長期プロジェクトへの導入は慎重に
- ワンオフ的に使うならアリです

<notes>後方互換性がしっかりしていないのけど、未実装部分があるので、長期間使っていくのはつらい
とは言え、いきなりクラッシュするような不安定さは無いので、短期間の用途で使うなら</notes>

---

謝辞

- Statue models scanned by Geoffrey Marchal (CC-BY)
  https://sketchfab.com/geoffreymarchal
- Photogrammetric textures created by StruffelProductions (CC0)
  https://cc0textures.com
