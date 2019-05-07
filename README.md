# 『データ解析のための統計モデリング入門』 - aviatesk

[久保拓弥『データ解析のための統計モデリング入門: 一般化線形モデル・階層ベイズモデル・MCMC』][kubopage]を勉強したときのノートを, [R-markdown]を用いて出力したHTLMファイルとしてまとめています.

[全てのデータ][data]および[ノート][notes]に含まれるコードの大部分は, [久保さんのwebページ][kubopage]で公開されているものによります.


<h2> TOC </h2>

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->
<!-- code_chunk_output -->

* [Tasks](#tasks)
* [Who I am](#who-i-am)
* [References](#references)

<!-- /code_chunk_output -->



## Tasks

- [x] Setups(R, R-markdown, [Atom])
- [x] [Chapter 2](notes/chapter2.Rmd): 確率分布と統計モデルの最尤推定
- [x] [Chapter 3](notes/chapter3.Rmd): 一般化線形モデル(GLM) ― ポアソン回帰 ―
- [x] [Chapter 4](notes/chapter4.Rmd): GLMのモデル選択 ― AICとモデルの予測の良さ ―
- [x] [Chapter 5](notes/chapter5.Rmd): GLMの尤度比検定と検定の枠組み
- [x] [Chapter 6](notes/chapter6.Rmd): GLMの応用範囲を広げる ― ロジスティック回帰など ―
- [x] [Chapter 7](notes/chapter7.Rmd): 一般化線形モデル(GLMM) ― 個体差のモデリング ―
- [ ] Chapter 8: マルコフ連鎖モンテカルロ(MCMC)法とベイズ統計モデル
- [ ] Chapter 9: GLMのベイズモデル化と事後分布の推定
    - [ ] WINBUGS部分を, [Tensorflow probability][tfp] あるいは [PyMC3][pymc3] を使ってを置き換え
- [ ] Chapter 10: 階層ベイズモデル ― GLMMのベイズモデル化 ―
- [ ] Chapter 11: 空間構造のある階層ベイズモデル


## Who I am

- **KADOWAKI, Shuhei** - *Undergraduate@Kyoto Univ.* - [aviatesk][aviatesk]


## References

- [久保拓弥, 『データ解析のための統計モデリング入門: 一般化線形モデル・階層ベイズモデル・MCMC』, 2012年, 岩波書店][kubopage]



<!-- ## links -->

[aviatesk]: https://github.com/aviatesk
[kubopage]: http://hosho.ees.hokudai.ac.jp/~kubo/ce/IwanamiBook.html
[R-markdown]: https://rmarkdown.rstudio.com/
[data]: ./data/
[figs]: ./figs/
[notes]: ./notes/
[atom]: https://github.com/aviatesk/avi-atom
[tfp]: https://www.tensorflow.org/probability/
[pymc3]: https://docs.pymc.io/
