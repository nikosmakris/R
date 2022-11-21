library(factoextra)
library(NbClust)
iris
# exclude "Species"- two ways
iris_data<-iris[1:4]
iris_data2<-iris[,-c(5)]
# exclude and scale
iris_data3<-scale(iris[,-c(5)])
# Suggested Elbows 
res.nb<-NbClust(iris_data3,min.nc=2,max.nc=8,method="complete")
# kmeans
K_cl2<-kmeans(iris_data3,3)

# resulting console
*** : The Hubert index is a graphical method of determining the number of clusters.
                In the plot of Hubert index, we seek a significant knee that corresponds to a 
                significant increase of the value of the measure i.e the significant peak in Hubert
                index second differences plot. 
 
*** : The D index is a graphical method of determining the number of clusters. 
                In the plot of D index, we seek a significant knee (the significant peak in Dindex
                second differences plot) that corresponds to a significant increase of the value of
                the measure. 
 
******************************************************************* 
* Among all indices:                                                
* 2 proposed 2 as the best number of clusters 
* 19 proposed 3 as the best number of clusters 
* 2 proposed 8 as the best number of clusters 

                   ***** Conclusion *****                            
 
* According to the majority rule, the best number of clusters is  3 
 
 
******************************************************************* 

# Kmeans resulting

Cluster means:
  Sepal.Length Sepal.Width Petal.Length Petal.Width
1  -0.05005221 -0.88042696    0.3465767   0.2805873
2  -1.01119138  0.85041372   -1.3006301  -1.2507035
3   1.13217737  0.08812645    0.9928284   1.0141287

Clustering vector:
  [1] 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
 [51] 3 3 3 1 1 1 3 1 1 1 1 1 1 1 1 3 1 1 1 1 3 1 1 1 1 3 3 3 1 1 1 1 1 1 1 3 3 1 1 1 1 1 1 1 1 1 1 1 1 1
[101] 3 1 3 3 3 3 1 3 3 3 3 3 3 1 1 3 3 3 3 1 3 1 3 1 3 3 1 3 3 3 3 3 3 1 1 3 3 3 1 3 3 3 1 3 3 3 1 3 3 1

Within cluster sum of squares by cluster:
[1] 44.08754 47.35062 47.45019
 (between_SS / total_SS =  76.7 %)

Available components:

[1] "cluster"      "centers"      "totss"        "withinss"     "tot.withinss" "betweenss"   
[7] "size"         "iter"         "ifault"      
