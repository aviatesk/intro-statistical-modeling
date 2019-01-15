---
html:
    embed_local_images: true
    toc: true
export_on_save:
    html: true
---


Just scratch to play with PCA, t-SNE and k-Means, using handwritten digits data




# load

import handwritten digits data from [`sklearn.datasets.load_digits`](https://scikit-learn.org/stable/datasets/index.html)


```python
from sklearn.datasets import load_digits
 
X, y = load_digits(return_X_y=True)
fig, axes = plt.subplots(nrows=2, ncols=5, figsize=(12, 5), tight_layout=False)
for i in range(2):
    for j in range(5):
        cnt = i * 5 + j
        axes[i, j].imshow(X[cnt].reshape(8, 8), cmap=plt.cm.gray_r)
        axes[i, j].set_title(y[cnt])
        axes[i, j].axis('off')
plt.show()
 
print('X: {}'.format(X.shape))
print('y: {}'.format(y.shape))
```

```
X: (1797, 64)
y: (1797,)
```

![](figures/scratch_figure2_1.png)



# visualize in 2D

Visualize the data reducing its dimension into 2D, using PCA and t-SNE

## PCA


```python
%%time
from sklearn.decomposition import PCA
 
pca = PCA(n_components=2)
X_pca = pca.fit_transform(X)
 
plt.figure(figsize=(8, 8))
plt.scatter(X_pca[:, 0], X_pca[:, 1], s=10)
plt.xticks(())
plt.yticks(())
plt.show()
```


Wall time: 2.84 s
![](figures/scratch_figure3_1.png)


Umm, there does not seem to be clear clusters for 10 digits...


## t-SNE


```python
%%time
from sklearn.manifold import TSNE
 
tsne = TSNE(n_components=2)
X_tsne = tsne.fit_transform(X)
 
plt.figure(figsize=(8, 8))
plt.scatter(X_tsne[:, 0], X_tsne[:, 1], s=10)
plt.xticks(())
plt.yticks(())
plt.show()
```


Wall time: 1min 12s
![](figures/scratch_figure4_1.png)


Awesome ! Now we can see 10 or more clear clusters and it's very nice for this dataset.

# clustering

Let's cluster the decomposed data(`X_tsne`) into 10 classes using k-Means.


```python
%%time
from sklearn.cluster import KMeans
 
kmeans = KMeans(n_clusters=10)
kmeans.fit(X_tsne)
 
h = .02
x_min, x_max = X_tsne[:, 0].min() - 1, X_tsne[:, 0].max() + 1
y_min, y_max = X_tsne[:, 1].min() - 1, X_tsne[:, 1].max() + 1
xx, yy = np.meshgrid(np.arange(x_min, x_max, h), np.arange(y_min, y_max, h))
X_tmp = np.hstack([xx.reshape(-1)[:, np.newaxis], yy.reshape(-1)[:, np.newaxis]])
Z = kmeans.predict(X_tmp)
Z = Z.reshape(xx.shape)
centeroids = kmeans.cluster_centers_
 
plt.figure(1, figsize=(8, 8))
plt.clf()
plt.imshow(Z, interpolation='nearest', extent=(xx.min(), xx.max(), yy.min(), yy.max()), cmap=plt.cm.Paired, aspect='auto', origin='lower')
plt.scatter(X_tsne[:, 0], X_tsne[:, 1], color='black', s=10)
plt.scatter(centeroids[:, 0], centeroids[:, 1], marker='x', s=100, linewidth=3, color='white', zorder=10)
plt.xlim(x_min, x_max)
plt.ylim(y_min, y_max)
plt.xticks(())
plt.yticks(())
plt.show()
```


Wall time: 23.6 s
![](figures/scratch_figure5_1.png)


k-Means separates a given data into **convex** clusters. Thus in 2D, we can draw the border of each convex region like above.

The plots below shows some points were not correctly clustered.
Note that the legend can only be applied for the 'true-labeled' plot (on right) but not for the 'clustered' plot (on left), because of **"label switching problem"**, e.g. labeling in clustering has no meaning in general.


```python
ints = range(10)
y_tsne = kmeans.fit_predict(X_tsne)
 
fig, axes = plt.subplots(nrows=1, ncols=2, figsize=(16, 8), tight_layout=False)
 
ps = []
for i in ints:
	X_tmp = X_tsne[y_tsne == i]
	ps.append(axes[0].scatter(X_tmp[:, 0], X_tmp[:, 1], s=10))
axes[0].set_title('clustered')
axes[0].set_xticks(())
axes[0].set_yticks(())
 
ps = []
for i in ints:
	X_tmp = X_tsne[y == i]
	ps.append(axes[1].scatter(X_tmp[:, 0], X_tmp[:, 1], s=10))
axes[1].set_title('true-labeled')
axes[1].set_xticks(())
axes[1].set_yticks(())
axes[1].legend(ps, ints, loc='lower left', ncol=2, fontsize=8)
plt.show()
```

![](figures/scratch_figure6_1.png)



# Appendix

(refer to the original .pmd file for the code generating the plot)

## PCA results


![](figures/scratch_figure7_1.png)


## PCA vs. t-SNE


![](figures/scratch_figure8_1.png)
![](figures/scratch_figure8_2.png)
