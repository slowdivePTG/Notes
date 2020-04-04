# 奇解

## 一阶隐方程

一阶常微分方程不一定能显式地表达出来，本节讨论的是一阶隐方程
$$
F\left(x,y,\frac{\text dy}{\text dx}\right)=0
$$

1. 平凡的情况——可解出 $y'$，转化为以前的形式

   **例**
   $$
   y'^2+yy'-x^2-xy=0\Rightarrow(y'-x)(y'+x+y)=0
   $$
   则 $y'=x$ 或 $y'+x+y=0$，从而有
   $$
   y=\frac12x^2+C\text{ or } y=-x+1+Ce^{-x}
   $$

2. $y=f(x,y')$

   令 $p=y'$，原式两侧对 $x$ 求导，得到
   $$
   p=f_x(x,p)+f_p(x,p)\frac{\text dp}{\text dx}\Rightarrow p'=\frac{p-f_x(x,p)}{f_p(x,p)}=F(x,p)
   $$

   - 若上式有通解 $p=\phi(x,C)$，则 $y=f(x,\phi(x,C))$ 为原方程的通解

   - 若上式有通解 $x=\phi(p,C)$，则可能会给出一个参数方程
     $$
     \left\{
     \begin{array}{l}
     x=\psi(p,C)\\
     y=f(\psi(p,C),p)
     \end{array}
     \right.
     $$
     $p$ 为参数，$C$ 为常数

   - 若通解为 $\phi(x,p,C)=0$，则原方程的通解
     $$
     \left\{
     \begin{array}{l}
     \phi(x,p,C)=0\\
     y=f(x,p)
     \end{array}
     \right.
     $$

   **例**
   $$
   y'^3+2xy'-y=0\Rightarrow y=y'^3+2xy'
   $$
   设 $p=y'$，则 $y=p^3+2xp$，求导得
   $$
   p=3p^2p'+2xp'+2p\Rightarrow p\text dx+(3p^2+2x)\text dp=0
   $$

   $$
   \Rightarrow 2p^2\text dx+(3p^2+2x)\text dp^2=\text d(2p^2x)+\frac32\text d p^4=0
   $$

   $$
   \Rightarrow \frac34p^4+xp^2=C
   $$

   $$
   \Rightarrow 
   \left\{
   \begin{array}{l}
   x=\frac{1}{p^2}\left(C-\frac34p^4\right)\\
   y=p^3+2xp=-\frac12p^3+\frac{2C}{p}
   \end{array}
   \right.
   $$

   同时在求恰当方程时方程两边曾经同乘过 $2p$，而事实上 $p\equiv0$ 也是方程的解，即 $y\equiv0$ 也是一个解

   事实上在 $C>0$ 时想使 $y=0$ 需要 $p=(2C)^{1/4}$，此时
   $$
   x=-\frac12\sqrt{\frac{C}{2}}
   $$
   从而过 $x$ 轴负半轴上的任意一点有两条解曲线，唯一性遭到了破坏！

   **例**：(克莱罗方程)
   $$
   y=xp+f(p)\Rightarrow p=p+xp'+\frac{\text df(p)}{\text dp}p'\Rightarrow \left(x+\frac{\text df(p)}{\text dp}\right)\frac{\text dp}{\text dx}=0
   $$
   有两种情况会满足这个方程
   $$
   \frac{\text dp}{\text dx}=0\text{ or }x+\frac{\text df(p)}{\text dp}=0
   $$

   - 第一种情况
     $$
     \Rightarrow p=C\Rightarrow y=Cx+f(C)
     $$
     为一族直线

   - 第二种情况
     $$
     \left\{
     \begin{array}{l}
     x=-f'(p)\\
     y=xp+f(p)=-pf'(p)+f(p)
     \end{array}
     \right.
     $$
     是一个特解

     - 若 $f''(p)\neq0$，则这个特解不会是直线，事实上由 $x=-f'(p)$ 可得反函数 $p=u(x)$，$y=xu(x)+f(u(x))$，但是 $u(x)$ 不是常值函数

   - 通解是特解的切线族

     设 $(x_0,y_0)$ 是特解上一点，则 $p_0=u(x_0),\ y_0=x_0p_0+f(p_0)$，通解中 $C=p_0$ 对应的直线 $y=Cx+f(C)$ 过 $(x_0,y_0)$ 且为特解的切线

   **例**
   $$
   y=xy'-\frac14y'^2
   $$
   令 $y'=p$，有
   $$
   p=p+xp'-\frac12pp'\Rightarrow p'\left(x-\frac12p\right)=0
   $$
   从而 $p=C\Rightarrow y=Cx-C^2/4$ 和 $y=x^2$ 是原方程的两个解 (事实上已经丢掉了很多解)，前者是后者的切线

   实际上，过 $y=x^2$ 上任意一点 $(x_0,y_0)$ 都有无穷多个解，因为对于任意一个 $x_1>x_0$，在其右侧无论是抛物线还是过 $(x_1,y_1)$ 的切线，都是方程的解

   **例**
   $$
   xp^2-2yp+9x=0\Rightarrow y=\frac{9x}{2p}+\frac{xp}{2}\quad(p\neq0)
   $$
   当然如果 $p\equiv0$，必有 $x=0$，此时 $p$ 没有定义

   求导
   $$
   p=\frac{9}{2p}-\frac{9x}{2p^2}p'+\frac{p}2+\frac{x}{2}p'\Rightarrow \left(\frac{9}{p^2}-1\right)(p-xp')=0
   $$

   $$
   \Rightarrow p=\pm 3\text{ or } p=Cx
   $$

   前者代入原方程
   $$
   y=\pm\frac32x\pm\frac{3}{2}x=\pm 3x
   $$
   后者代入原方程
   $$
   y=\frac{9}{2C}+\frac{C}{2}x^2
   $$
   特解是通解的切线，与上个例子相同，过 $y=\pm3x$ (除了原点) 上的任意一点都有无穷多条解曲线

3. $x=f(y,p)$

   令 $p=y'$，原式两侧对 $y$ 求导，得到
   $$
   \frac1p=f_y(y,p)+f_p(y,p)\frac{\text dp}{\text dy}\Rightarrow \frac{\text dp}{\text dy}=\frac{p^{-1}-f_y(y,p)}{f_p(y,p)}
   $$
   与上一种情形完全类似

4. $F(x,y')=0$

   令 $p=y'$，设 $F(x,p)=0$ 有参数形式 $x=\phi(t),\ p=\psi(t)$，则
   $$
   \text dy=p\text dx=\psi(t)\phi'(t)\text dt\Rightarrow y=\int \psi(t)\phi'(t)\text dt+C
   $$
   **例**
   $$
   x^3+p^3-3xp=0
   $$
   令 $p=tx$，则
   $$
   x^2(x+xt^3-3t)=0\Rightarrow x=\frac{3t}{1+t^3},\ p=\frac{3t^2}{1+t^3}
   $$

   $$
   y=\int \frac{3(1+t^3)-9t^3}{(1+t^3)^2}\frac{3t^2}{1+t^3}\text dt=3\int\frac{1-2t^3}{(1+t^3)^3}\text dt^3=\frac32\frac{4t^3+1}{(1+t^3)^2}
   $$

5. $F(y,y')=0$

   令 $p=y'$，设 $F(y,p)=0$ 有参数形式 $y=\phi(t),\ p=\psi(t)$，则
   $$
   \text dy=\phi'(t)\text dt=\psi(t)\text dx\Rightarrow x=\int \frac{\phi'(t)}{\psi(t)}\text dt+C
   $$
   若 $F(y,0)\equiv 0$ 有一个根为 $y=k$，则 $y\equiv k$ 是解

   **例**
   $$
   y^2(1-y')=(2-y')^2
   $$
   令 $2-y'=yt$，有
   $$
   y^2(yt-1-t^2)=0\Rightarrow y=\frac1t+t,\ p=1-t^2
   $$

   $$
   \Rightarrow x=\int \frac{1-t^{-2}}{1-t^2}\text dt+C=\frac{1}{t}+C
   $$

   当 $y'=0$ 时， $y=\equiv\pm2$ 也是解

6. 一般形式 $F(x,y,y')=0$，设其有一个双参数表示
   $$
   \left\{
   \begin{array}{l}
   x=x(u,v)\\
   y=y(u,v)\\
   y'=p=p(u,v)
   \end{array}
   \right.
   $$

   $$
   \text dy=p\text dx\Rightarrow y_u\text du+y_v\text dv=p(u,v)(x_u\text du+x_v\text dv)
   $$

   $$
   (y_u-p(u,v)x_u)\text du+(y_v-p(u,v)x_v)\text dv=0
   $$

   若它可以解出 $v=v(u,C)$，则
   $$
   \left\{
   \begin{array}{l}
   x=x(u,v(u,C))\\
   y=y(u,v(u,C))\\
   \end{array}
   \right.
   $$
   当然成功概率并不高