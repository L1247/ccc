# Optimization (最佳化, 優化)

凸集可分定理: ....

凸函數全域最佳化定理: ....

## Convex optimization problems

http://cs229.stanford.edu/section/cs229-cvxopt.pdf

## Convex Sets (凸集)

Definition 2.1 A set C is convex if, for any x, y ∈ C and θ ∈ R with 0 ≤ θ ≤ 1,
θx + (1 − θ)y ∈ C.

範例

1. Rn
2. Rn+
3. Norm balls : ex Euclidean norm balls
4. Affine space (仿射空間) : 仿射空間，又稱線性流形，是數學中的幾何結構，這種結構是歐式空間的仿射特性的推廣。在仿射空間中，點與點之間做差可以得到向量，點與向量做加法將得到另一個點，但是點與點之間不可以做加法。
5. Polyhedra : 多面體
6. Intersections of convex sets: 凸集的交集
7. Positive semidefinite matrices : 正半定矩陣

https://en.wikipedia.org/wiki/Affine_space

## Convex Functions (凸函數)

D(f) : Domain Space of f

凸函數 : f(θx + (1 − θ)y) ≤ θf(x) + (1 − θ)f(y)

嚴格凸函數 (Strictly convex function) 是將上式等號去掉。

凹函數 (Concave Function) :  f is concave if −f is convex

一階逼近： First-order approximation : f(x) + ∇xf(x)T (y − x)

Then f is convex if and only if D(f) is a convex set and for all x, y ∈ D(f),

  f(y) ≥ f(x) + ∇xf(x)T (y − x).

二階逼近： Second Order Condition for Convexity

Then f is convex if and only if D(f) is a convex set and its Hessian is positive semidefinite:

i.e., for any x ∈ D(f), ∇2xf(x) ≥ 0

In one dimension, this is equivalent to the condition that
the second derivative f''(x) always be non-negative

## 3.3 Jensen’s Inequality (傑森不等式)

凸函數定義： f(θx + (1 − θ)y) ≤ θf(x) + (1 − θ)f(y) for 0 ≤ θ ≤ 1.

推廣

傑森不等式: f(E[x]) ≤ E[f(x)]

## 3.4 Sublevel Sets (子層集合)

α-sublevel set : {x ∈ D(f) : f(x) ≤ α}

定理：α-sublevel set 也是個凸集。

## 3.5 凸函數範例 Examples

1. Exponential : f(x) = e^{ax}
2. Negative logarithm : f(x) = − log x
3. Affine functions : f(x) = bT x + c f
4. Quadratic functions : f(x) = (1/2)xTAx + bT x + c
5. Norms: a norm on V is a function p: V → R with the following properties:For all a ∈ F and all u, v ∈ V
    * p(av) = | a | p(v) (being absolutely homogeneous or absolutely scalable).
    * p(u + v) ≤ p(u) + p(v) (being subadditive or satisfying the triangle inequality).
    * p(v) ≥ 0 (being positive or more precisely non-negative).
    * If p(v) = 0 then v=0 is the zero vector (being definite or being point-separating).
6. Nonnegative weighted sums of convex functions : f(x) = sum(wi fi(x))

## 4 凸優化問題 Convex Optimization Problems

問題： minimize f(x) subject to x ∈ C

其中 f 為凸函數且 C 為凸集。

optimal value : p⋆ = min{f(x) : gi(x) ≤ 0, i = 1, . . . , m, hi(x) = 0, i = 1, . . . , p}

locally optimal : 鄰居都比他差。

global optimal : 全部裡面最好的。

## 4.1 Global Optimality in Convex Problems

定理：凸函數優化問題中的區域最佳解必然是全域最佳解。

For a convex optimization problem all locally optimal points are globally optimal.

## 4.2 Special Cases of Convex Problems

1. Linear Programming :
    * minimize cT x + d
    * subject to Gx <= h, Ax = b
2. Quadratic Programming:
    * minimize (1/2)xT P x + cT x + d
    * subject to Gx <= h, Ax = b
3. Quadratically Constrained Quadratic Programming :
    * minimize (1/2)xT P x + cT x + d
    * subject to (1/2)xTQix + rTi x + si ≤ 0, Ax = b
4. Semidefinite Programming
    * minimize tr(CX)
    * subject to tr(AiX) = bi, X>=0

## 4.3 凸集優化的方法 Examples

範例 1 : Support Vector Machines (SVM) :

minimize (1/2) ||w|| + C sum(ξi)
subject to yi (wT xi + b) >= 1-ξi, ξi ≥ 0

範例 2 : Constrained least squares

minimize (1/2) ||Ax − b||
subject to l <= x <= u

## 更多關於 optimization 的知識

在 cs231 捲積神經網路與影像辨識當中還有

http://cs231n.github.io/optimization-1/












