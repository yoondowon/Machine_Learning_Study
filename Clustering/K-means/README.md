# K-means Clustering
dd

For more information on the blog: http://nife0719.blog.me/221033414774 

## Description
※ Download file in here: https://drive.google.com/open?id=0B9eALrnw2M_iRDZUcWNFRVZXYnc

![Kmeans1]

[Kmeans1]: Kmeans_1.png

![Kmeans2]

[Kmeans2]: Kmeans_2.png


![Kmeans3]

[Kmeans3]: Kmeans_3.png


![Kmeans4]

[Kmeans4]: Kmeans_4.png


![Kmeans5]

[Kmeans5]: Kmeans_5.png


![Kmeans6]

[Kmeans6]: Kmeans_6.png


![Kmeans7]

[Kmeans7]: Kmeans_7.png


## Basic
기본 분석내용
※ kemans clustering example: https://www.r-bloggers.com/k-means-clustering-in-r/

```{r setup, include=FALSE}
kmeans(x, centers, iter.max = 10, nstart = 1,
       algorithm = c("Hartigan-Wong", "Lloyd", "Forgy", "MacQueen"), trace=FALSE)
## S3 method for class 'kmeans'
fitted(object, method = c("centers", "classes"), ...)
```
**x**: numeric matrix of data, or an object that can be coerced to such a matrix 

**centers**: either the number of clusters, say k, or a set of initial (distinct) cluster centres. 

**iter.max**: the maximum number of iterations allowed.

**nstart**: if centers is a number, how many random sets should be chosen?

**algorithm**: character: may be abbreviated. Note that "Lloyd" and "Forgy" are alternative names for one algorithm.

**object**: an R object of class "kmeans", typically the result ob of ob <- kmeans(..).

**method**: character: may be abbreviated. "centers" causes fitted to return cluster centers (one for each input point) and "classes" causes fitted to return a vector of class assignments.

**trace**: logical or integer number, currently only used in the default method ("Hartigan-Wong"): if positive (or true), tracing information on the progress of the algorithm is produced. Higher values may produce more tracing information.


library: https://stat.ethz.ch/R-manual/R-devel/library/stats/html/kmeans.html


## Initialization methods
※ kemans Initialization methods: https://www.slideshare.net/djempol/kmeans-initialization-15041920

### Random Partition

### Forgy

### MacQueen

### Kaufman

### Hartigan-Wong
이건 

### 직접 지정
```
## Your centers
C1 <- c(1, 2)
C2 <- c(4, -5)

## Simulate some data with groups around these centers
library(MASS)
set.seed(0)
dat <- rbind(mvrnorm(100, mu=C1, Sigma = matrix(c(2,3,3,10), 2)),
             mvrnorm(100, mu=C2, Sigma = matrix(c(10,3,3,2), 2)))

clusts <- kmeans(dat, rbind(C1, C2))  # get clusters with your center starting points

## Look at them
plot(dat, col=clusts$cluster)
```

## 클러스터 계산법

SSE


## how to find optimal k number
### elbow
※ elbow method: https://www.r-bloggers.com/finding-optimal-number-of-clusters/

#### elbow code로 파악할 수 있는 것 만들어 보고 싶음

### Silhouette
※ Silhouette method: https://stackoverflow.com/questions/15376075/cluster-analysis-in-r-determine-the-optimal-number-of-clusters


## cluster validation
site: http://www.sthda.com/english/articles/29-cluster-validation-essentials/97-cluster-validation-statistics-must-know-methods/#internal-clustering-validation-measures

### Internal evaluation 

#### 굉장히 다양 (Davies-Bouldin index, Dunn index, Silhouette ...)
※ nbclust library: https://cran.r-project.org/web/packages/NbClust/NbClust.pdf

※

#### 각각의 index 정의 및 이해

### External evaluation
이미 결과의 정답을 알고 있는 경우

#### Rand measure

#### F-measure

#### Jaccard index

## cluster visualization
### plot
### ggplot
#### ggplot으로 좀 더 이쁘게 그리는 것 만들어 보고 싶음


