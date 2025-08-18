# Julia Info JP

ここはJulia言語の情報をまとめた非公式ページです。
PRして情報を追記してください。

# Juliaとは？

Julia は2018年にバージョン1が公開されたオープンソースの科学技術計算言語で、 
Fortranの様に高速でかつPythonの様に生産性の高い言語です。
Julia は様々な分野において活用が始まっています。

[なぜ僕らはJuliaを作ったか](https://www.geidai.ac.jp/~marui/julialang/why_we_created_julia/index.html)

## よくある誤解

1. Q. インタプリタ言語なら遅いのでは?<br>A. Julia はコンパイル言語で、C/C++ のコンパイラClangと同じ技術(LLVM)で実行時コンパイルされます。
2. Q. 初心者には難しい？<br>A. 文法はシンプルで、REPL・Pluto・VS Code 拡張など学習環境も充実しています。最初は Python のように書けますが、高速化のコツ（関数化・グローバル変数を避ける・型安定）を少しずつ覚えると実力を発揮し、C言語レベルの速度も出ます。
3. Q. マイナーな言語ではないの？<br>A. まだ若い言語ですが、科学技術計算・データサイエンス・最適化・HPC で採用が広がっています。パッケージエコシステムも成熟が進み、他言語資産（C/Fortran/Python）とも容易に連携できます。
4. Q. 強い型付けなのか、動的型付けなのか。<br>A. Julia は「動的型付け」かつ「強い型付け」です。変数の型は実行時に決まり、暗黙の危険な型変換は行いません。一方で多重ディスパッチとパラメトリック型により、必要に応じて型注釈や制約を付けて安全かつ高性能に書けます（型安定なコードは JIT により高速化されます）。
5. Q. パッケージが少なくて結局Pythonに戻るのでは？<br>A. 主要分野（数値解析・最適化・機械学習・可視化・データ処理など）は実用パッケージが揃っており、必要なら PyCall/PythonCall や ccall で Python や C/Fortran の資産もそのまま使えます。
6. Q. GPU や HPC が苦手では？<br>A. マルチスレッド・分散計算に加え、CUDA/AMD/Intel/Apple など各GPU向けのエコシステムがあり、単一言語で高水準から低水準カーネルまで記述・最適化できます。既存の C/C++/Fortran カーネルとの連携も容易です。
7. Q. 機械学習/数値計算/大規模並列化/数学が1つの言語でできるというのは信じがたい、(何か)だめなんじゃないの?嘘じゃない?<br>A. Julia は LLVM/JIT と多重ディスパッチにより、高水準のまま低レベル最適化まで一貫して書ける設計です。数値計算（LinearAlgebra/SciML）、機械学習（Flux/Lux）、最適化（JuMP）、大規模並列・HPC（Threads/Distributed/MPI.jl、CUDA/AMDGPU/oneAPI/Metal）を単一言語でカバーできます。足りない所は C/Fortran/Python をオーバーヘッドなしで呼べるので、「1つで全部」は本当です。

## はじめかた

1. **Julia のインストール**

   * ↓ 公式サイトから OS 別インストーラをダウンロード
2. **ターミナルで `julia` を起動**

   ```julia
   julia> 1 + 2
   3
   ```
   
3. **パッケージを試す**

   ```julia
   julia> using Pkg; Pkg.add("Plots")
   julia> using Plots; plot(sin, 0, 2π)
   ```
   
4. **VS Code 拡張機能** *Julia* を入れると REPL・Lint・デバッグが快適。
5. **Pluto.jl** でノートブック環境 → `julia> import Pluto; Pluto.run()`
6. **GoogleColab/Jupyter** でもJulia が使えます。

> 🔗 もっと詳しく: [Julia Documentation → Getting Started](https://docs.julialang.org/en/v1/manual/getting-started/)

# 公式サイト

- [Julia](https://julialang.org/)

# 年間行事(国際)

- [JuliaCon Global](https://juliacon.org/)<br>全世界のJuliaユーザーが集う国際研究会
- [JuliaHEP](https://www.juliahep.org/)<br>高エネルギー物理の全世界のJuliaユーザーの集まり、研究会もある。

# 日本での国内イベント
## アカデミック系

- [Julia in Physics 2021 Online](https://akio-tomiya.github.io/julia_in_physics/)
- [数学と物理におけるJuliaの活用 (2023)](https://akio-tomiya.github.io/julia_imi_workshop2023/)
- [Julia in Physics 2024](https://ohno.github.io/julia_in_physics_2024/)

## エンジニア系
- [JuliaTokyo](https://juliatokyo.connpass.com/)
- [JuliaTokai](https://juliatokai.connpass.com/)

# 団体

- [Julia GitHub Organizations一覧](https://julialang.org/community/organizations/)

# ワーキンググループ
- [ワーキンググループ](https://julialang.org/community/working-groups/), HPC系では月に一回のオンラインミーティングあり。

# スパコンにいれるためのマニュアル(Admin用)

- [Admin: How to provide Julia to users?](https://juliahpc.github.io/sysadmin_julia/)

# 日本語の教科書等

- [1から始める Juliaプログラミング – 2020/3/26 進藤 裕之 (著), 佐藤 建太 (著)](https://www.amazon.co.jp/1%E3%81%8B%E3%82%89%E5%A7%8B%E3%82%81%E3%82%8B-Julia%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0-%E9%80%B2%E8%97%A4-%E8%A3%95%E4%B9%8B/dp/433902905X/)
- [Juliaではじめる数値計算入門 – 2024/5/13 永井 佑紀 (著)](https://www.amazon.co.jp/Julia%E3%81%A7%E3%81%AF%E3%81%98%E3%82%81%E3%82%8B%E6%95%B0%E5%80%A4%E8%A8%88%E7%AE%97%E5%85%A5%E9%96%80-%E6%B0%B8%E4%BA%95-%E4%BD%91%E7%B4%80/dp/4297141280/)
- [Juliaプログラミング大全 (ＫＳ情報科学専門書) 佐藤建太 (著)](https://www.amazon.co.jp/%EF%BC%AA%EF%BD%95%EF%BD%8C%EF%BD%89%EF%BD%81%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E5%A4%A7%E5%85%A8-%EF%BC%AB%EF%BC%B3%E6%83%85%E5%A0%B1%E7%A7%91%E5%AD%A6%E5%B0%82%E9%96%80%E6%9B%B8-%E4%BD%90%E8%97%A4%E5%BB%BA%E5%A4%AA-ebook/dp/B0CBV3S7K8/)
- [実践Julia入門 後藤 俊介 (著) ](https://www.amazon.co.jp/%E5%AE%9F%E8%B7%B5Julia%E5%85%A5%E9%96%80-%E5%BE%8C%E8%97%A4-%E4%BF%8A%E4%BB%8B-ebook/dp/B0BVZ647JD/)
- [1週間で学べる！Julia数値計算プログラミング (ＫＳ情報科学専門書) 永井佑紀 (著) ](https://www.amazon.co.jp/%EF%BC%91%E9%80%B1%E9%96%93%E3%81%A7%E5%AD%A6%E3%81%B9%E3%82%8B%EF%BC%81-%EF%BC%AA%EF%BD%95%EF%BD%8C%EF%BD%89%EF%BD%81%E6%95%B0%E5%80%A4%E8%A8%88%E7%AE%97%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0-%EF%BC%AB%EF%BC%B3%E6%83%85%E5%A0%B1%E7%A7%91%E5%AD%A6%E5%B0%82%E9%96%80%E6%9B%B8-%E6%B0%B8%E4%BA%95%E4%BD%91%E7%B4%80-ebook/dp/B0B56Q8RZ1/)
- [Juliaによる数理最適化 単行本 – 2023/4/12
小林 和博 (著)](https://www.amazon.co.jp/Julia%E3%81%AB%E3%82%88%E3%82%8B%E6%95%B0%E7%90%86%E6%9C%80%E9%81%A9%E5%8C%96-%E5%B0%8F%E6%9E%97-%E5%92%8C%E5%8D%9A/dp/4339029343/)
- [モデルベース深層学習と深層展開 - 2023/06 和田山 正 (著)](https://www.morikita.co.jp/books/mid/085731)
- [Juliaプログラミングクックブック ―言語仕様からデータ分析、機械学習、数値計算まで 単行本（ソフトカバー） – 2019/10/19
Bogumił Kamiński (著), Przemysław Szufel (著), 中田 秀基 (翻訳)](https://www.amazon.co.jp/Julia%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E3%82%AF%E3%83%83%E3%82%AF%E3%83%96%E3%83%83%E3%82%AF-%E2%80%95%E8%A8%80%E8%AA%9E%E4%BB%95%E6%A7%98%E3%81%8B%E3%82%89%E3%83%87%E3%83%BC%E3%82%BF%E5%88%86%E6%9E%90%E3%80%81%E6%A9%9F%E6%A2%B0%E5%AD%A6%E7%BF%92%E3%80%81%E6%95%B0%E5%80%A4%E8%A8%88%E7%AE%97%E3%81%BE%E3%81%A7-Bogumi%C5%82-Kami%C5%84ski/dp/4873118891/)
- [Juliaによる数値計算とシミュレーション 単行本 – 2023/6/20
小高 知宏 (著)](https://www.amazon.co.jp/Julia%E3%81%AB%E3%82%88%E3%82%8B%E6%95%B0%E5%80%A4%E8%A8%88%E7%AE%97%E3%81%A8%E3%82%B7%E3%83%9F%E3%83%A5%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3-%E5%B0%8F%E9%AB%98-%E7%9F%A5%E5%AE%8F/dp/427423049X/)
- [基礎から学ぶJulia ~基本文法からデータサイエンスまで 単行本 – 2021/1/25
石井 一夫 (著)](http://amazon.co.jp/%E5%9F%BA%E7%A4%8E%E3%81%8B%E3%82%89%E5%AD%A6%E3%81%B6Julia-%E5%9F%BA%E6%9C%AC%E6%96%87%E6%B3%95%E3%81%8B%E3%82%89%E3%83%87%E3%83%BC%E3%82%BF%E3%82%B5%E3%82%A4%E3%82%A8%E3%83%B3%E3%82%B9%E3%81%BE%E3%81%A7-%E7%9F%B3%E4%BA%95-%E4%B8%80%E5%A4%AB/dp/488647022X)
- [Juliaで作って学ぶベイズ統計学 2021/11 須山敦志 (著)](https://www.kspub.co.jp/book/detail/5259801.html)
