---

HDRP

---

HDRP<br/>とは

---

High<br/>Definition<br/>Render<br/>Pipeline

<notes>最新の機能を詰め込んだ新しいレンダーパイプライン
もっと分かりやすく有り体に言ってしまえば……</notes>

---

PS4 を<br/>ベースラインにした<br/>新しいレンダラー

<notes>PS4 の AAA タイトルなどでよく使われているレンダリング方式をベースに</notes>

---

<img src="img/Features.png"/>

<notes>ここが便利だな、ここがおいしいな、と思ったポイントをアトランダムに紹介</notes>

---

メリットその１<br/>ライティングが<br/>むちゃくちゃ強力

<notes>そのうえ高速化もなされているため、パフォーマンスに影響を与えることなく凝ったライティング演出を構築することが可能に</notes>

---

FPTL

---

Fine<br/>Pruned<br/>Tiled<br/>Lighting

---

<img src="img/GBuffer.png"/>

---

<img src="img/FPTL1.png"/>

---

<img src="img/FPTL2.png"/>

---

<img src="img/FPTL3.png"/>

---

<img src="img/FPTL4.png"/>

---

<img src="img/GPUPro7.png"/>

---

新しいライト形状<br/>
矩形ライト<br/>
線分ライト

---

<img src="img/LightType.png"/>

---

<img src="img/LTC.png"/>

---

すごく便利<br/>弱点：<br/>明るくなり過ぎがち

---

<img src="img/SSAO.png"/>

---

<img src="img/LightValue.png"/>

---

<img src="img/VolumetricLight.png"/>

---

半透明<br/>
Clustered Forward Shading

---

<br/>

---

メリットその２<br/>標準シェーダーがむちゃくちゃ強力

---

<img src="img/Lit1.png"/>

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

---

Displacement Mapping

---

<img src="img/Displacement1.png"/>

---

<img src="img/Displacement2.png"/>

---

<img src="img/Displacement3.png"/>

---

Layered Material<br/>
レイヤー機能

---

<img src="img/Layered1.png"/>

---

<img src="img/Layered2.png"/>

---

<img src="img/Layered3.png"/>

---

メリットその３<br/>カスタマイズに<br/>フレンドリー

---

<img src="img/Versioning1.png"/>

---

<img src="img/Versioning2.png"/>

---

<img src="img/Versioning3.png"/>

---

<img src="img/Versioning4.png"/>

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

関数、structを使った<br/>C言語風の実装<br/>充実した<br/>シェーダーライブラリ<br/>

---

<img style="width:49%" src="img/CustomShader1.gif"/>
<img style="width:49%" src="img/CustomShader2.gif"/>

<img style="width:49%" src="img/CustomShader3.gif"/>
<img style="width:49%" src="img/CustomShader4.gif"/>

---

<a href="https://github.com/Unity-Technologies/ScriptableRenderPipeline/blob/master/com.unity.render-pipelines.high-definition/HDRP/Material/Lit/Lit.shader">Lit.shader</a> をコピペして改造<br/>
<a href="https://github.com/Unity-Technologies/ScriptableRenderPipeline/blob/master/com.unity.render-pipelines.high-definition/HDRP/ShaderPass/VertMesh.hlsl">VertMesh.hlsl</a> や<br/>
<a href="https://github.com/Unity-Technologies/ScriptableRenderPipeline/blob/master/com.unity.render-pipelines.high-definition/HDRP/ShaderPass/ShaderPassGBuffer.hlsl">ShaderPassGBuffer.hlsl</a><br/>
なども改造ポイント

---

#define と<br/>#include の塊

---

ホワイトボックスなので<br/>諦めるポイントは少ない

---

HDRP<br/>導入検討の<br/>ポイント

---

で、もう<br/>完成してるの？<br/>使っていいの？

---

- 未実装部分が少なくない
- 後方互換性が確立されていない