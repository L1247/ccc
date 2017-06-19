# 數學

## 線性代數

* [Linear Algebra Review and Reference, Zico Kolter (updated by Chuong Do),September 30, 2015](http://cs229.stanford.edu/section/cs229-linalg.pdf) (讚！)

行列式 (Determinant) |A| 代表其 n 個向量圍起來的《多維梯形》之面積。

## 二次形式

二次形式 (Quadratic Form) xT A x 可分為《正定、正半定、負定、負半定、不定》

1. positive definite : xT A x > 0
2. positive semidefinite : xT A x >=0
3. negative definite : xT A x < 0
4. negative semidefinite : xT A x <=0
5. indefinite : xT A x 非上面四種情況。

正定(負定)矩陣總是 fullrank 的，因此是 invertible (反矩陣存在)

證明：參考文件 3.11 一節。

## 特徵值與向量

A x = λ x

(λI-A) x = 0

|(λI-A)| = 0

tr A = \sum{λi}

|A| = \prod{λi}

rank(A) = non-zero eigenvalues of A

if A is nonsingular then 1/λi is an eigenvalue of A^{-1}

AX = XΛ

If the eigenvectors of A are linearly independent, then the matrix X will be invertible

### Symmetric Matrices A 的 eighevalues

1. 實數 (Real)
2. 正交規範 (Orthonormal)

於是 A 可以寫為 A = UΛUT

UT = inv(U)  // the inverse of an orthogonal matrix is just its transpose

其為正定或負定取決於 eigenvalues 的正負號

如果要最大化 max( xT A x ) , 其實解答就是最大的特徵值 λ1 所對應到的向量 x1。

條件：上式中 ||x|| = 1, 代表 x 是 vector of norm 1

## 矩陣微積分

### 梯度

f (A) → R

A is a m×n matrix

gradient of f is ∇ f(A)

梯度是函數之偏導數的自然延伸。

### Hessian matrix

H(f) = ∇^2_x f(x) -- Hessian matrix 是對稱矩陣

線性函數 f(x) = sum(bi xi) 的梯度就是他的係數 bi 組成的向量

二次函數 f(x) = xTAx 的梯度 ∇ xT Ax = 2Ax (很像 (ax^2)' = 2ax)

∇ b T x = b

∇xTAx = 2Ax (if A symmetric)

∇∇ xTAx = 2A (if A symmetric)

### 最小平方 (Least Squares)

x = (AT A)−1 AT b

### Gradients of the Determinant

∇A log |A| =∇ |A|/|A| = A−1

###  Eigenvalues as Optimization (Lagrangian)

max (xT A x) subject to ||x|| = 1

L(x, λ) = xT A x - λ xT x

∇ L(x, λ) = ∇ (xT Ax − λxTx) = 2ATx − 2λx = 0


### github 數學式

github 不支援 tex 語法，不過有人寫了轉換程式。

https://github.com/leegao/readme2tex