## 最尤推定
パラメトリックな場合に推定量を探す方法
最尤推定法(Maximal likelihood method)

データ生成分布のパラメトリックモデル　$P_{model}(x; \bm\theta)$
与えられたサンプル$\mathit{D} = \left\{x_1, x_2, \cdots, x_N\right\}$
同時確率密度は
$$
L(\bm\theta) = P(x_1, x_2, \cdots, x_N; \bm \theta) =
\prod_{n=1}^{N}P_{model}(x_n; {\bm \theta})
$$
$L(\bm\theta)$を最大にするようなパラメータ値であるためにデータ$\left\{x_1, x_2, \cdots, x_N\right\}$が実現されやすかったと解釈する。すると与えられたデータに対して尤もらしいパラメータの値は尤度を最大化したものということになる。

尤もらしいパラメータの値$\bm\theta_{ML}$は、尤度を最大化するものである。
$$
\bm\theta_{ML} = \argmax_{\bm\theta}L(\bm\theta)
$$
ただし、尤度は確率密度の積なので、1以下の数値を何回もかけ合わせた結果得られる。従って、一般にはとても小さな値になってしまい、消失してしまう。そこで、尤度の対数を取った **対数尤度関数** を最大化する。

$$
\bm\theta_{ML} = \argmax_{\bm\theta} \log{L(\bm\theta)}
$$

機械学習では最小化問題を解くことが多いので、上式にマイナスをかけて`負の対数尤度`を考える。
$$
  \bm\theta_{ML} = \argmin_{\bm\theta}(-\log{L(\bm\theta)})
$$