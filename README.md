  
  
  
# 『データ解析のための統計モデリング入門』 - aviatesk
  
  
[久保拓弥『データ解析のための統計モデリング入門: 一般化線形モデル・階層ベイズモデル・MCMC』][kubopage]を勉強したときの, 自分の理解と実際のコードのノートを, [R-markdown][R-markdown]を用いて(独立して開ける)HTLMファイルに出力してまとめています.

[全てのデータ][data]および[ノート][notes]に含まれるコードの大部分は, [久保さんのwebページ][kubopage]で公開されているものによります.  

  
## TOC
  
  
  
  
  
* [Tasks](#tasks )
* [Author](#author )
* [References](#references )
  
  
  
  
  
  
## Tasks
  
  
- [x] Setups(R, R-markdown, [Atom][atom])
- [x] Chapter 2: 確率分布と統計モデルの最尤推定
- [x] Chapter 3: 一般化線形モデル(GLM) ― ポアソン回帰 ―
- [x] Chapter 4: GLMのモデル選択 ― AICとモデルの予測の良さ ―
- [x] Chapter 5: GLMの尤度比検定と検定の枠組み
- [x] Chapter 6: GLMの応用範囲を広げる ― ロジスティック回帰など ―
- [x] Chapter 7: 一般化線形モデル(GLMM) ― 個体差のモデリング ―
- [ ] Chapter 8: マルコフ連鎖モンテカルロ(MCMC)法とベイズ統計モデル
- [ ] Chapter 9: GLMのベイズモデル化と事後分布の推定
    - [ ] WINBUGS部分を, [Tensorflow probability][tfp] あるいは [PyMC3][pymc3] を使ってを置き換え
- [ ] Chapter 10: 階層ベイズモデル ― GLMMのベイズモデル化 ―
- [ ] Chapter 11: 空間構造のある階層ベイズモデル
  
  
## Author
  
  
- **KADOWAKI, Shuhei** - *Undergraduate@Kyoto Univ.* - [aviatesk][aviatesk]
  
  
## References
  
  
- [久保拓弥, 『データ解析のための統計モデリング入門: 一般化線形モデル・階層ベイズモデル・MCMC』, 2012年, 岩波書店][kubopage]
  
  
  
  
  
  
[aviatesk]: https://github.com/aviatesk
[kubopage]: http://hosho.ees.hokudai.ac.jp/~kubo/ce/IwanamiBook.html
[R-markdown]: https://rmarkdown.rstudio.com/
[data]: ./data/
[figs]: ./figs/
[notes]: ./notes/
[atom]: https://github.com/aviatesk/avi-atom
[tfp]: https://www.tensorflow.org/probability/
[pymc3]: https://docs.pymc.io/
  
