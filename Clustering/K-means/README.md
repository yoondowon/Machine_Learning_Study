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

## feature selection 
https://stats.stackexchange.com/questions/177796/feature-selection-for-clustering-problems | r - Feature selection for clustering problems - Cross Validated
http://www.simafore.com/blog/learning-data-science-feature-selection-for-clustering | Learning Data Science: feature selection for clustering
http://www.simafore.com/blog/bid/61220/How-to-perform-feature-selection-for-predictive-analytics | How to perform feature selection for predictive analytics
https://pdfs.semanticscholar.org/f116/7e2e1fa07cdf432c10beb373e07efd6a5e58.pdf | C:/Users/jiliang/Dropbox/FS_Clutering_BOOK_Chapter/chapter.dvi
https://en.proft.me/2016/06/18/exploring-k-means-clustering-analysis-r/ | Exploring K-Means clustering analysis in R | en.proft.me
https://stats.stackexchange.com/questions/108743/methods-in-r-or-python-to-perform-feature-selection-in-unsupervised-learning | Methods in R or Python to perform feature selection in unsupervised learning - Cross Validated

## categorical data 
https://www.quora.com/How-do-we-apply-k-means-clustering-algorithm-for-mixed-data-numeric-and-categorical | How do we apply k-means clustering algorithm for mixed data-numeric and categorical? - Quora
https://grid.cs.gsu.edu/~wkim/index_files/papers/kprototype.pdf | Microsoft Word - pakdd.doc
http://edu.cs.uni-magdeburg.de/EC/lehre/sommersemester-2013/wissenschaftliches-schreiben-in-der-informatik/publikationen-fuer-studentische-vortraege/kMeansMixedCatNum.pdf | doi:10.1016/j.datak.2007.03.016
https://www.r-bloggers.com/clustering-mixed-data-types-in-r/ | Clustering Mixed Data Types in R | R-bloggers
http://www.cs.ust.hk/~qyang/Teaching/537/Papers/huang98extensions.pdf | huang98extensions.pdf
https://shapeofdata.wordpress.com/2014/03/04/k-modes/ | K-modes | The Shape of Data
https://dabblingwithdata.wordpress.com/2016/10/10/clustering-categorical-data-with-r/ | Clustering categorical data with R – Dabbling with Data
https://m.blog.naver.com/leedk1110/220792605053 | [R] 군집분석/ 클러스터링 -2 : K-Means : 네이버 블로그
https://woosa7.github.io/R-%EA%B5%B0%EC%A7%91%EB%B6%84%EC%84%9D-Clustering/ | 군집분석 Clustering


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


