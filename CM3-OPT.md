# CM3 OPTIMISATION 

-----

## Exemple : Méthode de Newton
___________________

$$f(x) = \frac{1}{2}x_1^2 + \frac{1}{4}x_2^4 - \frac{1}{2}x_2^2$$     
<u>__Gradient:__</u>

$$\nabla f(x)= \begin{pmatrix}  
x_1\\
x_2^3 - x_2
\end{pmatrix}
$$

<u>__Matrice Hessienne:__</u>

$$
\nabla^2 f(x)= \begin{pmatrix}
1&0\\
0& 3x_2^2-1
\end{pmatrix}
$$

$$(\nabla^2 f(x))^{-1}= \frac{1}{3x_2^2-1}\begin{pmatrix}
3x_2^2-1&0\\
0 & 1
\end{pmatrix}
$$
<u>1er cas</u>:
$$X_0 = \begin{pmatrix}
1\\ 
0 
\end{pmatrix}
\rightarrow
X_1 = \begin{pmatrix}
1\\ 
0 
\end{pmatrix} +
\begin{pmatrix}
-1&0\\
0&1
\end{pmatrix}
\begin{pmatrix}
1\\
0
\end{pmatrix}
$$

$$X_1 = \begin{pmatrix}
0\\ 
0 
\end{pmatrix}
\rightarrow
X_2 = \begin{pmatrix}
0\\ 
0 
\end{pmatrix} +
\begin{pmatrix}
-1&0\\
0&1
\end{pmatrix}
\begin{pmatrix}
0\\
0
\end{pmatrix}
$$

Conclusion : c'est un point selle  

<u>2ème cas</u>:

$$X_0 = \begin{pmatrix}
1\\ 
1 
\end{pmatrix}
\rightarrow
X_1 = \begin{pmatrix}
1\\ 
1 
\end{pmatrix} -\frac{1}{2}
\begin{pmatrix}
2&0\\
0&1
\end{pmatrix}
\begin{pmatrix}
1\\
0
\end{pmatrix}
$$

$$X_1 = \begin{pmatrix}
0\\ 
1 
\end{pmatrix}
\rightarrow
X_2 = \begin{pmatrix}
0\\ 
1
\end{pmatrix} -\frac{1}{2}
\begin{pmatrix}
2&0\\
0&1
\end{pmatrix}
\begin{pmatrix}
0\\
0
\end{pmatrix}
$$

Conclusion : on obitent un minimum local.

-------------------
## Exemple : Critère des moindres carrés
-----------

 $$ min
 f(x) = \frac{1}{2} [(x_i-a)^2 + (y_i - b)^2 - R^2]
 $$

$$ 
r_i^2 = R^2 - (x_i^2 + a -2x_ia) - (y_i^2+b^2-2y_ib)
$$
 
$$ 
min f(x) = \frac{1}{2}(r_1^2 + r_2^2 +...+ r_m^2)
$$

$$
r_i = \begin{bmatrix}
2x_i &2y_i& 1\\
\end{bmatrix}
\begin{bmatrix}
a\\
b\\
c
\end{bmatrix} - 
\begin{bmatrix}
x_i^2 + y_i^2\\
\end{bmatrix} = ax_i + b_i
$$

Finalement on obtient :
$$
\begin{bmatrix}
2x_1 & 2y_1 & 1\\
\\
2x_m & 2y_m & 1
\end{bmatrix}
$$
$$\begin{bmatrix}
a\\
b\\
R^2-a^2-b^2
\end{bmatrix} -
\begin{bmatrix}
x_1^2+y_1^2\\
\\
x_m^2+y_m^2
\end{bmatrix}
$$
$$

-------------------
## Exemple : Gauss-Newton
-----------

$$f(x,y) = \frac{1}{2}[(x^2 - y)^2 + (1 -x)^2]$$ 
      
<u>__Gradient:__</u>

$$
\nabla f(x)= \begin{pmatrix}
2x^3 -2xy +x -1\\
y - x^2
\end{pmatrix}
$$

<u>__Matrice Hessienne:__</u>
$$\nabla^2 f(x)= \begin{pmatrix}
6x^2 -2y +1& -2x\\
-2x&  1
\end{pmatrix}

\nabla r_1 = \begin{pmatrix}
2x\\
-1
\end{pmatrix}; \hspace{0.1cm}
\nabla r_2 = \begin{pmatrix}
-1\\
0
\end{pmatrix}\newline

\nabla^2 r_1 = \begin{pmatrix}
2 & 0\\
0 & 0
\end{pmatrix}; \hspace{0.1cm}
\nabla^2 r_2 = \begin{pmatrix}
0 & 0\\
0 & 0
\end{pmatrix}
$$

<u>__Matrice Jacobienne:__</u>

$$
J(x) = \begin{pmatrix}
2x & -1\\
-1 & 0
\end{pmatrix}
$$
d'où :
$$
\nabla f(x) = \begin{pmatrix}
2x & -1\\
-1 & 0
\end{pmatrix}
\begin{pmatrix}
x^2-y\\
1-x
\end{pmatrix} = \begin{pmatrix}
2x^3 -2xy +x -1\\
y -x^2
\end{pmatrix}
$$ 

On approxime la matrice hessienne :
$$
\nabla^2 f(x) = J.J^T = \begin{pmatrix}
4x^2 + 1 & -2x\\
-2x & 1
\end{pmatrix}
$$




