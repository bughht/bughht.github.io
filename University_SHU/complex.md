# Review
+ $Lnz=ln|z|+iargz+2k\pi i (k\in Z)=ln|z|+iArgz$
+ $lnz=ln|z|+iargz\quad -\pi<argz\leq\pi$
    + $arg z=\arctan\cfrac{y}{x}$ 
+ $e^z=e^{z+2k\pi i}\quad (k\in Z)$
    + $e^{Lnz}=e^{lnz}=z$
    + Example: $(1+i)^n=(1-i)^n$
+ $z^\alpha=e^{\alpha(ln|z|+iargz+2k\pi i)}$
+ $\sin z=\cfrac{e^{iz}-e^{-iz}}{2i}\qquad \cos z=\cfrac{e^{iz}+e^{-iz}}{2}$
    + 复数计算展开到$a+bi$
+ $f(z)=zImz$在复平面处处连续
+ 可导的充分条件：
    + $u_x,u_y,v_x,v_y$在$(x,y)$连续，且在$(x,y)$满足C-R方程，则$f(z)$在$z=x+iy$可导，且$f'(z)=u_x+iv_x=v_y+iv_x=u_x-iu_y=v_y-iu_y$
+ 解析函数
    + 所有解析点的合集必为开集，不可能仅在一个点或一条曲线上解析
    + 平面上处处解析的函数
        + $f(z)=e^z,z^n,\sin z,\cos z$
    + 处处不解析的函数
        + $f(z)=Rez,Imz,|z|,\overline{z},z|z|$
    + $\oint_{|z|=1}Rezdz$:参数方程求解
+ 调和函数
    + $u_{xx}+u_{yy}=0$
    + Example $u=x^2-y^2+xy$
        + $u_x=2x+y,\quad u_y=-2y+x$
        + $u_{xx}=2,\qquad u_{xy}=1,\qquad u_{yx}=1,\qquad u_{yy}=-2$
        + $u_xx+u_yy=0$, 调和
+ 复积分
    + 非闭区间
        + 参数方程法
            + $\int_Cf(z)dz=\int_a^bf(z(t))z'(t)dt$
            + Example $\int_CRezdz$, $C=1-i$ to $3+2i$直线段
                + $C:(2t+1)+i(3t-1)$
                + $I=\int_0^1(2t+1)(2+3i)dt$
            + Example $\int_C|z|dz$, C:上半单位圆周线，起点-1
                + $C:z=e^{i\theta}, \theta:\pi\to 0$
                + $|z|=1$
                + $I=\int_\pi^0 1(ie^{i\theta})d\theta=e^{i\theta}\big|_\pi^0=2$
        + 牛顿-莱布尼兹公式
    + 周线积分
        + 参数方程
            + Example $\oint_{|z|=2}(Rez+e^z)dz$
                + $I=\oint_{|z|=2}Rezdz+\oint_{|z|=2}e^zdz=\oint_{|z|=2}Rezdz$
                + $\int_0^{2\pi}2\cos\theta ie^{i\theta}d\theta=\cdots$
        + 推广的柯西积分定理
        + 柯西积分公式
            + $\oint_C\cfrac{f(z)}{(z-z_0)^{n+1}}dz=\cfrac{2\pi i}{n!}f^{(n)}(z_0)$
                + Example $I=\oint_C\cfrac{e^z}{z(z-1)^2}dz, C:x^2+y^2=4x+5$
                    + $C:(x-2)^2+y^2=3^2$
                    + $I=\oint_{C_1}\cfrac{\frac{e^z}{(z-1)^2}}{z}dz+\oint_{C_2}\cfrac{\frac{e^z}{z}}{(z-1)^2}$
        + 留数定理
            + $\oint_Cf(z)dz=2\pi i\sum\limits_{k=1}^n Res[f(z),z_k]$
            + $Res[f(z),z_k]:$ f(z)在$z_k$去心邻域的洛朗展开中$\cfrac{1}{z-z_k}$系数$C_{-1}$
            + 本性奇点
                + $I=\oint_{|z|=1}ze^{-\cfrac{1}{z^2}}dz=2\pi i Res[ze^{-\cfrac{1}{z^2}},0]$
            + 可去奇点
            + 极点
                + 洛朗展开求留数
                + $Res[f(z),z_0]=\cfrac{1}{(m-1)!}\lim\limits_{z\to z_0}\cfrac{d^{m-1}}{dz^{m-1}}[(z-z_0)^mf(z)]$
            + 留数定理应用
        + 泰勒展开
            + $e^z=\sum\limits_{n=0}^\infty\cfrac{z^n}{n!},\quad |z|<\infty$
            + $\sin(z)=\sum\limits_{n=0}^\infty (-1)^n\cfrac{z^{2n+1}}{(2n+1)!}$
            + $\cos(z)=\sum\limits_{n=0}^\infty(-1)^n\cfrac{z^2n}{(2n)!}$
            + $\cfrac{1}{1-z}=\sum\limits_{n=0}^\infty z^n,\quad |z|<1$
            + $\cfrac{1}{1+z}=\sum\limits_{n=0}^\infty (-1)^nz^n,\quad |z|<1$
            + $\cfrac{1}{1-z^2}=\sum\limits_{n=0}^\infty z^{2n},\quad |z|<1$
            + $\cfrac{1}{1+z^2}=\sum\limits_{n=0}^\infty (-1)^n z^{2n},\quad |z|<1$
        + 洛朗展开
            + $e^{\frac{1}{z}}=1+\cfrac{1}{z}+\cfrac{1}{2!}(\cfrac{1}{z})^2+\cdots+\cfrac{1}{n!}(\cfrac{1}{z})^n+\cdots,\qquad 0<|z|<+\infty$
            + $\sin\cfrac{1}{z}=\cfrac{1}{z}-\cfrac{1}{3!}\cfrac{1}{z^3}+\cdots+(-1)^n\cfrac{1}{(2n+1)!}(\cfrac{1}{z})^{2n+1}+\cdots,\qquad 0<|z|<+\infty$
            + $\cos\cfrac{1}{z}1-\cfrac{1}{2!}\cfrac{1}{z^2}+\cdots+(-1)^n\cfrac{1}{(2n)!}(\cfrac{1}{z})^{2n}+\cdots,\qquad 0<|z|<+\infty$
        + 傅里叶变换
            + $F(\omega)=\mathscr{F}[f(t)]=\int_{-\infty}^\infty f(t)e^{-i\omega t}dt,\qquad T\to \infty$
            + $f(t)=\mathscr{F}^{-1}[F(\omega)]=\cfrac{1}{2\pi}\int_{-\infty}^\infty F(\omega)e^{i\omega t}d\omega$
            + $\mathscr{F}[\delta(t)]=1$
            + $\mathscr{F}[e^{i\omega_0 t}]=2\pi\delta(\omega-\omega_0)$
            + $\mathscr{F}[e^{i\omega_0 t}f(t)]=F(\omega-\omega_0)$
            + $\mathscr{F}[f^{(n)}(t)]=(i\omega)^n\mathscr{F}[f]$
            + $\cfrac{d^nF(\omega)}{d\omega^n}=(-i)^n\mathscr{F}[t^nf(t)]$
        + 拉普拉斯变换
            + $F(s)=\mathscr{L}[f(t)]=\int_0^{+\infty}f(t)e^{-st}dt$
            + $\mathscr{L}[1]=\cfrac{1}{s}$
            + $\mathscr{L}[e^{at}]=\cfrac{1}{s-a}$
            + $\mathscr{L}[\sin bt]=\cfrac{b}{s^2+b^2}$
            + $\mathscr{L}[\cos bt]=\cfrac{s}{s^2+b^2}$
            + $\mathscr{L}[t]=\cfrac{1}{s^2}$
            + $\mathscr{L}[t^2]=\cfrac{2!}{s^3}$
            + $\mathscr{L}[t^n]=\cfrac{n!}{s^{n+1}}$
            + $\mathscr{L}[\alpha f+\beta g]=\alpha F(s)+\beta G(s)$
            + $\mathscr{L}[e^{at}f(t)]=F(s-a)$
            + $\mathscr{L}[t^nf(t)]=(-1)^n F^{(n)}(s)$
            + $\mathscr{L}[\int_0^tf(t)dt]=\cfrac{F(s)}{s}$
            + $\mathscr{L}[f^{(n)}(t)]=s^nF(s)-s^{n-1}f(0)-s^{n-2}f'(0)-\cdots-f^{(n-1)}(0)$

# Class 
+ $f'(z_0)=\lim_{\Delta z\to 0}\cfrac{\Delta w}{\Delta z}$
+ $\cfrac{\Delta w}{\Delta z}=f'(z_0)+\eta(\Delta z)\Delta z$
+ $Prove  f(z)=z^2 \text{is derivatable and } (z^2)'=2z$
    $\cfrac{\Delta w}{\Delta z}=\cfrac{(z+\Delta z)^2-z^2}{\Delta z}=\cfrac{2z\Delta z+\Delta z^2}{\Delta z}$
    add lim
    $=2z$

+ $f(z)=\overline{z}, Re z, Im z, |z| \text{ continuous on }z$
+ $u(x,y) \text{ is derivatable at }(x,y)\Leftrightarrow \Delta u=A\Delta x+B\Delta y+o(\sqrt{(\Delta x)^2+(\Delta y)^2})$ 
+ $f(z)=u(x,y)+iv(x,y)$
    + $u(x,y),v(x,y) \text{is differentiable at }(x,y)$
    + $u(x,y), v(x,y) \text{ supports } u_x=v_y, u_y=-v_x\textbf{  C-R Euqation}$
+ $\text{if f(z) is derivatable at z, }f'(x)=u_x+iv_x=v_y+iv_x=u_x+iu_y=v_y-iu_y$
+ if $u=u(x,y)$ is partial derivative at $(x,y)$, $u_x$,$u_y$ are continuous at $(x,y)$, and $u(z)$ is differentiable at $(x,y)$.
    + Example 1 $f(z)=|z|^2$.
        1. $f(z)=|z|^2=x^2+y^2$
        2. $u(x,y)=x^2+y^2, v(x,y)=0$
        3. $u_x=2x,u_y=2y,v_x=v_y=0$ 
        4. $u_x=v_y,u_y=-v_x$ (C-R Equation) get $z=0$
        5. $f(z)|_{z=0}=u_x|_{z=0}+iv_x|_{z=0}=2x|_{z=0}=0$
    + Example 2 $f(z)=x^2+2y^2$
        1. $u(x,y)=x^2, v(x,y)-y^2$
        2. $u_x=2x,u_y=0,v_x=0,v_y=2y$
        3. $y=x$
        4. $f'(z)|_{y=x}=2x$
+ analytic function
    + Example $f(z)=\overline{z}$
        1. $f(z)=x-iy$
        2. not analytic
+ $f(z)=\overline{z},Imz,Rez,|z|$ are not analytic
+ ### The relationship between Analytic Function and Harmonic Function 
+ Construct: Given a differentiable function u,(v), if exsist a v,(u) make $u+iv$ analytical
    + **C-R**   
        + $u_x=v_y, u_y=-v_x$
        + $u_{xx}+u_{yy}=v_{yx}-v_{xy}!=0$
    + **C-R**
        + $u_{xx}+u_{yy}=0$
+ Harmonic Function : $u: u_{xx}+u_{yy}=0$ ($u\in C^2(D)$) $u_x$, $u_{xx}$ continuous
    + Example: $u(x,y)=x^3-3xy^2$
        +  $u_{xx}=6x, u_{xy}=-6y, u_{yx}=-6y, u_{yy}=-6x$
        + $u\in C^2(C)$
        + Harmonic
+ $f(z)=u+iv$ analytic $\Leftrightarrow$ u,v harmonic in D and support **C-R** Equation.
+ If $u(x,y)$ and  $v(x,y)$ harmonic in D and satisfying **C-R** equation $u_x=v_y$, $u_y=-v_x$, then v is the convergent harmonic function of u.
+ Partial Integrate Method
    + $u_x=v_y (1)$
    + $\int v_y(x,y)dy=\int u_x(x,y)dy$
    + $\Rightarrow v(x,y)+\psi (x)=\int u_x dy$
    + $v(x,y)=\int u_x dy+\psi (x)$
    + $v_x=-u_y (2)$
    + $(\int u_x(x,y) dy)_x+\phi '(x)=-u_y$
+ Example $u(x,y)=x^3-3xy^2$
    + $u_x=3x^2-3y^2, u_y=-6xy$
    + $v_y=u_x=3x^2-3y^2$
    + $v(x,y)=3x^2y-y^3+\phi (x)$
    + $v_x=-u_y=6xy$
    + $6xy+\phi'(x)=6xy$
    + $\Rightarrow \phi(x)=C$
    + $f(z)=(3x^2y-y^3+C)i+(x^3-3xy^2)$
    + $f(0)=i$
    + $Ci=i$
    + $C=1$
+ Primary Analytic Function
    + $w=e^z=e^{x(cos y+i sin(y))}$
        + $z=|z|=(cos \theta +i\sin\theta)=|z|e^{i\theta}$
        + $(e^z)'=e^z$
        + $|e^z|=e^x>0$
        + $e^{z_1}\cdot e^{z_2}=e^{z_1+z_2}$
        + $e^{z+2k\pi i}=e^z\qquad (k\in Z)$
        + example $e^z=1-\sqrt{3}i$
            + $e^z=e^{i(-\frac{\pi}{3}+ln2)}$ 
    + $e^w=z\Leftrightarrow w=Ln(z)$
        + $z=re^{i\theta}, w=u+iv,e^{u+iv}=re^{i\theta}$
        + $\Rightarrow u=\ln r, v=\theta+2k\pi =Arg z$
        + $w=Ln(z)=\ln |z|+i Arg z(z\not = 0)=\ln|z|+i argz+2k\pi i (k\in Z)$
        + Example $Ln(-1-i)$
            + $Ln(-1-i)=ln(\sqrt{2})+i(-\cfrac{3\pi}{4})+2k\pi i, k\in Z$
        + Example $Ln(-1)$
            + $Ln(-1)=i\pi+2k\pi i, k\in Z$
        + Example $Ln(2)$
            + $Ln(2)=ln2+2k\pi i, k\in Z$+ 
        + $Ln(z_1z_2)=Lnz_1+Lnz_2$
        + $Ln(\cfrac{z_1}{z_2})=Ln z_1-Ln z_2$, ($z_1\not ={0}, z_2\not ={0}$)
        + $Ln z^n\not ={nLnz}, Lnz-Lnz\not ={0}$
        + $2Ln z= ln r^2+i (2\theta +4k\pi), k\in Z$ 
        + *$e^{Lnz}=e^{lnz}=z$
        + Example: solve $lnz=1+\pi i$
            + $z=e^{1+\pi i}$
            + $z=e\cdot(cos \pi + isin \pi)=-e$
    + $\begin{cases}e^{iy}=\cos y+i\sin y\\e^{-iy}=\cos y-i\sin y\\\end{cases}$
        + $sin z=\cfrac{1}{2i}(e^{iz}-e^{-iz})$
        + $cos z=\cfrac{1}{2}(e^{iz}+e^{-iz})$
        + zero point of $sin z$ is $z=k\pi, k\in Z$
        + zero point of $cos z$ is $z=(k+1/2)\pi, k\in Z$
        + Example $sinz=0$
            + $\Rightarrow e^{ir}-e^{-ir}=0$
            + $\Rightarrow e^{2iz}=1$
    + $w=z^\alpha, \alpha \in C$
        + $z^\alpha=e^{\alpha Lnz}=e^{\alpha (ln|z|+iargz+2k\pi i)}$
        + Example $i^i$
            + $i^i=e^{iLni}=e^{i(i(\pi/2+2k\pi ))}=e^{-(\pi /2+2k\pi)}$
+ **Homework 2.9(1)(4), 2.13(1)(2)(4), 2.14**

+ ## Integration of Complex Function
    + Complex Integral
        + $\oint_Cf(z)dz=-\oint_{C^{-}}f(z)dz$
        + If $f(z)=u(x,y)+iv(x,y)$ continuous on smooth curve $C$ from $a$ to $b$ ($u$,$v$ are continuous), $\int_C f(z)dz=\int_C udx-vdy+i(\int_C vdx+udy)$  
            + If $f(z)$ is continuous function and $C$ is a smooth curve, integral $\int_Cf(z)dz$ exist.
            + $\int_Cf(z)dz$ can be simplified into real variable function.
        + Parametric Equation
            + $z(t)=x(t)+iy(t)\qquad t: a\rightarrow b$ 
        + **(Important!)** Parametric Equation method: *$\int_Cf(z)dz=\int_a^bf(z(t))z'(t)dt$
        + Example:
            + Prove: $I_n=\oint_C\cfrac{dz}{(z-z_0)^n}=\begin{cases}2\pi i & n=1\\0& n\in Z^+,\quad n\not ={0}\\\end{cases}$ where $C:|z-z_0|=r\quad(r>0)$
                + $z(\theta)=z_0+re^{i\theta}$
                + $\oint_C\cfrac{1}{(z-z_0)^n}dz=\int_0^{2\pi}ir^{1-n}e^{i(1-n)\theta}d\theta$
                + $=ir^{1-n}\int_0^{2\pi}e^{i(1-n)\theta}d\theta=$ then split it into sin and cos.
        + $|\oint_Cf(z)dz|\leqslant\oint_C|f(z)|ds$
+ Cauchy Integral Theorm
    + $f(z)$ integral in D is unrelated to path$\Leftrightarrow$ $\oint_lf(z)dz=0$
    + If $F(z)$ is analytic in single connected region $D$, $\oint_Cf(z)dz=0$ for any contour $C$ in $D$.
        + Example1:
            + $f(z)=e^z,z^n,\sin z,\cos z$ analytic on $z$ area, $\oint_Cf(z)dz=0$ where C is a contour in the complex area.
        + Example2: solve $\oint_C\cfrac{1}{z+2}dz, C:|z|=1$
            + singular point: $z=-2$
            + Construct $D$:
               1. $-2\notin D$
               2. $C \subset D$
            + $D: |z|\leq 1.5$
            + $\oint_C\cfrac{1}{z+2}dz=0$
    + Cauchy integral theorm on complex connected region
        + $f(z)$ is analytic in $D$ bounded in $C_1$ and $C_2$ (contours) and continuous on $\overline{D}=D+C_1+C_2$, then $\oint_{C_1}f(z)dz=\oint_{C_2}f(z)dz$
        + $\oint_Cf(z)dz=\sum_{k=1}^{n}\oint_{C_{k}}f(z)dz$
        + Example: solve $\oint_C\cfrac{1}{(z-1)(z+1)}dz$, $C:$ bound 1 and -1
            + $f(z)=\cfrac{1}{(z-1)(z+1)}=\cfrac{1}{2}\big(\cfrac{1}{z-1}-\cfrac{1}{z+1}\big)$
            + Construct $C_1$, $C_2$ around -1 and 1.
            + $\oint_Cf(z)dz=\oint_{C_1}f(z)dz+\oint_{C_1}f(z)dz$
                + $=\oint_{C_1}(\cfrac{1}{z-1}-\cfrac{1}{z+1})+\oint_{C_2}(\cfrac{1}{z-1}-\cfrac{1}{z+1})$
                + $=0-2\pi i+2\pi i+ 0$
                + $=0$
    + $f(z)$ is analytic in $D$, $z_0\in D$, $F(z)$ is analytic in $D$ and $F'(z)=f(z)$
    + $f(z)$ is analytic in single connect region $D$, $\int_{z_0}^{z_1}f(z)dz=F(z_1)-F(z_0), z_0,z_1\in D$ 
+ Calculate Complex Integration
    + $C:$  not close
        + Paramater
        + N-L Formula 
    + $C: $ contour
        + Parameter
        + Cauchy Theory
        + Important Integral: $\oint_C\cfrac{dz}{(z-z_0)^n}=\begin{cases}2\pi i & n=1\\0& n\in Z^+,\quad n\not ={0}\\\end{cases}(C:|z-z_0|=r>0)$
+ Cauchy Integral Formula
    + If $f(z)$ is analytic in $D$ surrounded by contour $C$, continuous on $C$ and $D$, for all $z_0\in D$,
        + $f(z_0)=\cfrac{1}{2\pi i}\oint_C\cfrac{f(z)}{z-z_0}dz$

    + Application:$\oint_C\cfrac{f(z)}{z-z_0}=2\pi if(z_0)$
        + where $g(z)=\cfrac{f(z)}{z-z_0}$, singular point $z_0$
            $g(z)$ has only one sigular point $z_0$
    + Example: $I_1=\oint_C\cfrac{\sin z}{z} dz, C:|z|=2$
        + $g(z)=\cfrac{\sin z}{z}$, singular point $z=0$
        + $I_1=2\pi i sin(0)$
        + $=0$
    + Example2: $I_2=\oint_{|z-i|=1}\cfrac{1}{z^2+i}dz$
        + $g(z)=\cfrac{1}{z^2+i}$, singular point $z_0=\sqrt[n]{|z|}e^{i(\frac{-\pi/2+2k\pi)}{n}}, k \in {0,1}$
        + $z_0=\cfrac{\sqrt{2}}{2}-\cfrac{\sqrt{2}}{2}i$, $z_1=-\cfrac{\sqrt{2}}{2}+\cfrac{\sqrt{2}}{2}i$
        + $z_1$ in C
        + $\oint_C\cfrac{1}{z^2+i}dz=\oint_C\cfrac{\cfrac{1}{z-z_0}}{z-z_1}dz=2\pi i \cfrac{1}{z-z_0}\bigg|_{z=z_1}=\cfrac{2\pi i}{-\sqrt{2}+\sqrt{2}i}=\cfrac{\sqrt{2}}{2}\pi(1-i)$
    + Example3: $I_3=\oint_{|z|=2}\cfrac{e^z}{(z^2+1)(2z-1)}$
+ if $f(z)$ analytic on $D$, $f^{(n)}=\cfrac{n!}{2\pi i}\oint_C\cfrac{f(z)}{(z-z_0)^{n+1}},n\in N$
    + $\oint_C\cfrac{f(z)}{(z-z_0)^{n+1}}=\cfrac{2\pi i }{n!}f^{(n)}(z_0)$
    + Example: $I_1=\oint_{|z-i|=1}\cfrac{\cos z}{(z-i)^3}$
        + $g(z)=\cfrac{\cos z}{(z-i)^3}$, singular point $z=i$
        + $I_1=2\pi i\cfrac{(\cos z)''}{2!}\bigg|_{z=i}=\pi i (-\cos i)=-\pi i \cfrac{e^{-1}+e}{2}$
    + Example2: $I_2=\oint_{|z|=1}\cfrac{\sin z}{z^{2020}}dz$
        + $g(z)=\cfrac{\sin z}{z^{2020}}$, $z_0=0$
        + $I_2=2\pi i\cfrac{(\sin z)^{(2019)}}{2019!}\bigg|_{z=z_0}=2\pi i\cfrac{-\cos 0}{2019!}=-\cfrac{2\pi i}{2019!}$
    + Example3: $I_3=\oint_{|z|=4}\cfrac{e^z}{z^2(z-1)^2}dz$
        + $z_0=0$, $z_1=1$
        + $\oint_{|z|=4}g(z)dz=\oint_{C_1}\cfrac{\frac{e^z}{(z-1)^2}}{z^2}dz+\oint_{C_2}\cfrac{\frac{e^z}{z^2}}{(z-1)^2}=\cfrac{2\pi i }{1!}\cfrac{e^z}{(z-1)^2}\bigg|_{z=0}+\cfrac{2\pi i}{1!}\cfrac{e^z}{z^2}\bigg|_{z=1}=...$
+ infinite series
    + $\sum_{n=1}^{\infty}z_n$
    + $\sum_{n=1}^{\infty}q^n$ convergence on $|q|<1$
    + $z_n=x_n+iy_n$ convergent then $\sum_{n=1}^\infty x_n$ and $\sum_{n=1}^\infty y_n$ convergent.
    + Example $\sum_{n=1}^{\infty}\cfrac{i^n}{n}$   
        + $=i-\cfrac{1}{2}-\cfrac{1}{3}i+\cfrac{1}{4}+\cfrac{1}{5}i$
        + $=(-\cfrac{1}{2}+1/3-1/6+\cdots)+i(1-1/3+1/5-\cdots)$
    + $\sum_{n=1}^{\infty}|z_n|$ convergent, then $\sum_{n=1}^{\infty}z_n$ convergent.
    + power series
        + $\sum_{n=0}^{\infty}C_n(z-z_0)^n$
        + Abel's Theorm
            + if $\sum_{n=1}^{\infty}C_n(z-z_0)$ convergent at $z_1$, it definitely convergent on $K:|z-z_0|<|z_1-z_0|$
+ Taylor Series
    + Taylor Expansion Theorem: If $f(z)$ analytic in $D$, for all $z_0\in D$, if $K:|z-z_0|<R$ in $D$, $f(z)$ could be expand into $f(z)=\sum_{n=0}^{\infty}C_n(z-z_0)^n$, where 
        + $C_n=\cfrac{1}{2\pi i}\oint_{C_\rho}\cfrac{f(\xi)}{(\xi-z_0)^{n+1}}d\xi=\cfrac{f^{(n)}(z_0)}{n!}$: Taylor Coefficient
        + $z_0$: Expand Center
        + $C_\rho:|\xi-z_0|=\rho$, $0<\rho<R$
        + *Trick:* $\cfrac{1}{\xi-z}=\cfrac{1}{(\xi-z_0)-(z-z_0)}=\cfrac{1}{\xi-z_0}\cfrac{1}{1-\cfrac{z-z_0}{\xi-z_0}}=\cfrac{1}{\xi-z_0}\sum_{n=0}^{\infty}t^n=\sum_{n=0}^{\infty}\cfrac{(z-z_0)^n}{(\xi-z_0)^{(n+1)}}$
        + Example 1: $f(z)=\cfrac{1}{1+z}$, $z_0=0$
            + Singular Point: $z=-1$, $D:z\not ={-1}$
            + $K: |z-z_0|=|z|<1$
            + $\cdots$
    + Taylor Expansion Method
        1. Solve Taylor Coefficient Directly: $C_n=\cfrac{f^{(n)}(z_0)}{n!}$
            + $e^z=\sum_{n=0}^{\infty}\cfrac{z^n}{n!}, |z|<\infty$
            + $\sin(z)=\sum_{n=0}(-1)^n\cfrac{z^{2n+1}}{(2n+1)!}$
            + $\cos(z)=\sum_{n=0}(-1)^n\cfrac{z^{2n}}{(2n)!}$
        2. Solve with known expansion like $\cfrac{1}{1-z}=\sum_{n=0}^\infty z^n, |z|<1$
            + $\cfrac{1}{1-z^2}$, $z_0=0$
                + $R=1$, $|z|<1$
                + $\cfrac{1}{1-z^2}=\sum_{n=0}^\infty z^2n$
                + $\cfrac{1}{1+z^2}=\sum_{n=0}^\infty (-1)^n z^{2n}$
                + $\cfrac{1}{1+z}=\sum_{n=0}^\infty (-1)^n z^n$
            + $\cfrac{z-1}{z+1}$, $z_0=1$
                + $R=2, |z-1|<2$
                + $=1-\cfrac{2}{1+z}=1-\cfrac{1}{2+(z-1)}=1-\cfrac{1}{2}\cfrac{1}{1+\cfrac{z-1}{2}}=1-\cfrac{1}{2}\sum_{n=0}^\infty (-1)^n(\cfrac{z-1}{2})^{2n}$
            + $\cfrac{z}{z^2+3z+2}$, $z_0=2$
                + $R=3$, $|z-2|<3$
                + $=\cfrac{z}{(z+1)(z+2)}=\cfrac{a}{z+1}+\cfrac{b}{z+2}$
                + $a(z+2)+b(z+1)=z$
                + $a=-1$, $b=2$
                + $=-\cfrac{1}{z+1}+\cfrac{2}{z+2}=\cdots$
                    + $\cfrac{2}{z+2}=\cfrac{2}{(z-2)+4}=\cfrac{1}{2}\cfrac{1}{1+\frac{z-2}{4}}=\cfrac{1}{2}\sum_{n=0}^\infty(-1)^n(\cfrac{z-2}{4})^n$
            + $f(z)=\cfrac{z}{z^2-2z+5}$, $z_0=1$
                + singular point: $z^2-2z+5=0$, $1\pm 2$ 
                + $R=2$
                + $f(z)=\cfrac{(z-1)+1}{(z-1)^2+4}=((z-1)+1)\cfrac{1}{(z-1)^2+4}$
                + $=\cfrac{(z-1)+1}{4}\sum_{n=0}^\infty (-1)^n(\cfrac{z-1}{2})^{2n}$
                + $=\cfrac{z-1}{4}\sum_{n=0}^\infty (-1)^n(\cfrac{z-1}{2})^{2n}+\cfrac{1}{4}\sum_{n=0}^\infty (-1)^n(\cfrac{z-1}{2})^{2n}$
        3. Derivative within contour $\cfrac{1}{(z-a)^2}=-(\cfrac{1}{z-a})'$
            + Example: $f(z)=\cfrac{1}{(z+2)^2}$, $z_0=-1$
                + $R=1$, $|z+1|<1$
                + $\cfrac{1}{(z+1)^2}=(-\cfrac{f1}{z+2})'$
                + $-\cfrac{1}{z+2}=-\cfrac{1}{(z+1)+1}=-\sum_{n=0}^\infty (-1)^{n+1}(z+1)^n$
                + $\Rightarrow \cfrac{1}{(z+2)^2}=\sum_{n=1}^\infty (-1)^{n-1}n(z+1)^{n-1}$
            + Example2: $f(z)=\cfrac{1}{(z^2+1)^2}$, $z_0=0$
                + $|z|<1$
                + $\cfrac{1}{(z^2+1)^2}=(-\cfrac{1}{z^2+1})'\cfrac{1}{2z}$
                + $(\sum_{n=0}^\infty (-1)^n z^2n)'\cfrac{1}{2z}$
                + $=\sum_{n=1}^\infty (-1)^{n+1}z^{2n-1}(2n)\cfrac{1}{2z}$
                + $=\sum_{n=1}^\infty (-1)^{n+1}(2n)z^{2n-2}$
            + Example3: $f(z)=\cfrac{z^2}{(z+1)^2}$, $z_0=1$
                + $|z-1|<2$
                + $f(z)=\cfrac{(z+1)^2-2(z+1)+1}{(z+1)^2}=1-\cfrac{}{z+1}+\cfrac{1}{(z+1)^2}$
                + $\cdots$
+ Laurent Series
    + Laurent Expansion
        + Definition: $C_0+C_1(z-z_0)+C_2(z-z_0)^2+\cdots$(1) and $\cfrac{C_{-1}}{z-z_0}+\cfrac{C_{-2}}{(z-z_0)^2}+\cdots$(2), (1)+(2) called Laurent Series.
            + **Expression:** $\sum\limits_{n=-\infty}^\infty C_n(z-z_0)^n$
        + Convergence Region: 
            + Let $\xi=\cfrac{1}{z-z_0}$, then $(2)=c_{-1}\xi+c_-2\xi^2+\cdots$
            + $|\xi|<\cfrac{1}{r}(0\leq r\le \infty)$ convergent
            + $\Rightarrow$ (2) convergent in $|z-z_0| \ge r(0 \leq r\le \infty$
            + When $r<R$, $r \le |z-z_0| \le R$
                + Especially when $r=0$, $0<|z-z_0|<R$
    + $f(z)=\sum\limits_{n=-\infty}^{+\infty}C_n(z-z_0)^n$ could be derivative by steps within $H$
    + $f(z)$ could be integrate along $C$ within $H$
    + Laurent Expansion Theorem
        + $C_n\cfrac{1}{2\pi i}\oint_C\cfrac{f(\xi)}{(\xi-z_0)^{n+1}}d\xi$
            + $C_n\not ={\cfrac{f^{(n)}(z_0)}{n!}}$
        + Example1: $f(z)=\cfrac{z}{z^2+z-2}$, $z_0=-2$
            + singular point: $z=-2,1$
            + $\rho_0=0$,$\rho_1=3$
            + $0< |z+2|< 3$
            + $\cdots$
            
    + Laurent Expansion Method
        + Expand through exsisted Taylor Expansion $\cfrac{1}{1-z}=\sum\limits_{n=0}^\infty z^n,|z|<1$
            + $z_0$ is an analyic point on $f(z)$
            + Example $f(z)=\cfrac{z}{z^2+z-2}$, $z_0=-1$
                + $f(z)=\sum_{n=-\infty}^\infty C_n(z+1)^n$
                + $f(z)=\cfrac{z}{(z+2)(z-1)}=\cfrac{a}{z+2}+\cfrac{b}{z-1}=\cfrac{1}{3}(\cfrac{2}{z+2}+\cfrac{1}{z-1})$
                    + (1) $\cfrac{2}{z+2}=\cfrac{2}{(z+1)+1}=\sum_{n=0}^\infty(-1)^n(z+1)^n$
                    + (1) $\cfrac{1}{z-1}=\cfrac{1}{(z+1)-2}=\cfrac{1}{2}\sum_{n=0}^\infty(\cfrac{z+1}{2})^n$
                    + (2) $\cfrac{2}{z+2}=\cfrac{2}{(z+1)+1}=\cfrac{2}{z+1}\sum_{n=0}^\infty(-1)^n(\cfrac{1}{z+1})^n$
                    + (2) $\cfrac{1}{z-1}=\cfrac{1}{(z+1)-2}=\cfrac{1}{2}\sum_{n=0}^\infty(\cfrac{z+1}{2})^n$
            + Example: $f(z)=\sin \cfrac{1}{z}$, $z_0=0$
                + $0<|z|<+\infty$, $f(z)=\sum C_n z^n$
                + $\sin \frac{1}{z}=\sin t(t=1/z)=\sum_{n=0}^\infty (-1)^n\cfrac{z^{2n+1}}{(2n+1)!}$, $0<|t|<\infty$
                + $\cdots$
        + Integrate/Derivate by steps within domain region
            + Example $f(z)=\cfrac{1}{(z+2)^2}$
                + $f(z)=-(\cfrac{1}{z+2})'$, $z_0=-1$
                + $\cfrac{1}{z+2}=\cfrac{1}{1+(z+1)}=\cfrac{1}{z+1}\cfrac{1}{1+\frac{1}{z+1}}=\cfrac{1}{z+1}\sum_{n=0}^\infty(-1)^n(\cfrac{1}{z+1})^n=\sum_{n=0}^\infty(-1)^{n++1}(\cfrac{1}{z+1})^{n+1}$
                + $(-\cfrac{1}{z+2})'=\sum (-1)^{n+1}(\cfrac{1}{z+1})^n(-\cfrac{1}{(z+1)^2})$
        + Integrate
            + $\oint_Cf(z)dz=\oint_{C_1}f(z)dz+\oint_{C_2}f(z)dz$
            + $\oint_{C_1}f(z)dz ==\oint_{C}\sum_{C_n}(z-z_0)^n$
                + $f(z)=\sum_{n=0}^\infty C_n(z-z_0)^n+\sum_{n=-\infty}^{-1}c_n(z-z_0)^n$
                    + **Analytic Part** + **Main Part**
            + $=\sum_{n=-\infty}^\infty \oint_{C_1}C_n(z-z_1)^ndz$
            + $=\sum_{n=0}^\infty\oint_{C_1}C_n(z-z_0)^n+\sum_{n=-\infty}^{-1}\oint_{C_1}C_n(z-z_0)^ndz$
            + $=\sum_{n=-\infty}^{-1}\oint_{C_1}C_n(z-z_0)^ndz$
            + $=\sum_{n=1}^\infty C_{-n}\oint_{C_1}\cfrac{1}{(z-z_0)^n}$
            + $=C_{-1}2\pi i$
+ Residue: $\text{Res}[f(z),z_0]=C_{-1}$
    + Residue Theroem: $\oint_Cf(z)dz=2\pi i\sum_{k=1}^n\text{Res}[f(z),z_k]$
    + Isolated Singularity
        + Classification of Isolated Singularity    
            + Removable Singularity 
                + Main part of $f(z)$ equals to 0, $f(z)=C_0+C_1(z-z_0)+\cdots$, $0<|z-z_0|<R$
                + Append definition $f(z_0)=\lim\limits_{z\to z_0}f(z)=C_0$ then $f(z)$ analytic on $z_0$.
                + Example 1:  Prove that $z=0$ is the removable singularity of $f(z)=\cfrac{\sin z}{z}$
                    + Singularity: $z_0=0$, $0<|z|<+\infty$
                    + $f(z)=\cfrac{1}{z}\sum_{n=0}^\infty(-1)^n\cfrac{z^{2n+1}}{(2n+1)!}$
                    + $\cdots$
                + Th: $z_0$ is the removable singularity of $f(z)$ $\Leftrightarrow$ $\lim\limits_{z\to z_0}f(z)=C_0 (\not ={\infty})$
                + **L'Hospital Rule**: $\lim\limits_{z\to z_0}\cfrac{f(z)}{g(z)}=\lim\limits_{z\to z_0}\cfrac{f'(z)}{g'(z)}$
                + $f(z)=\cfrac{\sin z}{z}$, $z_0=0$
                + $f(z)=\cfrac{e^z-1}{z}$, $z_0=0$
                + $f(z)=\cfrac{1}{e^z-1}-\cfrac{1}{z}$, $z_0=0$ is removable singularity
            + Pole Singularity 
                + $f(z)=\cfrac{C_{-m}}{(z-z_0)^m}+\cdots+ \cfrac{C_{-1}}{z-z_0}+C_0+C_1(z-z_0)+\cdots$ and $C_m\not ={0}$, then $z_0$ is the m-order pole singularity of $f(z)$ 
                + Example: prove that $z=0$ is the 2018-order polar singularity of $f(z)=\cfrac{e^z-1}{z^{2019}}$
                    + $z_0=0$
                    + $f(z)=\cfrac{1}{z^{2019}}(-1+ 1+\cfrac{z^2}{2!}+\cfrac{z^3}{3!}+\cdots$
                    + $\cdots$
                + methods 
                    + $z=z_0\Leftrightarrow \lim_{z\to z_0}f(z)=\infty$, $\cfrac{1}{0}=\infty, \cfrac{1}{\infty}=0, a\cdot \infty=\infty$
                        + Example: $f(z)=\cfrac{e^z-1}{z^{2019}}$
                            + $\lim\limits_{z\to 0}\cfrac{e^z-1}{z^2019}=\lim\limits\cfrac{e^z}{2019z^{2018}}=\infty$
                    + $z_0$ is the pole singularity of $f(z)\Leftrightarrow f(z)$ can be expressed as $f(z)=\cfrac{\phi(z)}{(z-z_0)^m}$ and $\phi(z)$ analytic in $z_0$ and $\phi(z_0)\not ={0}$
                        + Requirements
                            + Polynomial denominator 
                            + **Important:** $\frac{1}{0}$
                        + Example: $f(z)=\cfrac{1}{z^2(z-1)}$, $z_0=0$
                            + $f(z)=\cfrac{\frac{1}{z-1}}{z^2}$
                            + 2-order
                    + $z_0$ is m-order pole singularity of $f(z)\Leftrightarrow z_0$ is m-order 0-point of $g(z)=\cfrac{1}{f(z)}$
                        + Example: $f(z)=\cfrac{1}{e^z-1}$, $z_0=2k\pi i$
                            + $g(z)=e^z-1$
                            + $g^{(1)}(z)=e^z$
                            + $g^{(1)}(2k\pi i)=0$
                            + 1-order
                        + Example 2: $f(z)=\cfrac{z-1}{z(e^z-1)}$
                            + $z_0=0$ or $2k\pi i$
                            + $z_0=0$
                                + $g(z)=\cfrac{z(e^z-1)}{z-1}=\cfrac{1}{z-1}h(z)$
                                + $h(z)=z(e^z-1)$
                                + $g'(z)=(\cfrac{1}{z-1})'h(z)+(\cfrac{1}{z-1})h'(z)$
                                + $g'(0)=(\cfrac{1}{0-1})h'(0)=0$
                                + $g''(0)=(\cfrac{1}{z-1})''h(z)+(\cfrac{1}{z-1})'h'(z)+\cfrac{1}{z-1}h''(z)\Leftrightarrow g''(0)=0\Leftrightarrow h''(0)=0$
                        + $\sin z=\cfrac{e^{iz}-e^{-iz}}{2i}$
                + $f(z)=g(z)h(z)$ where $g(z)$ is removable singularity and $f(z)$ is m-order pole singuarity, then $f(z)$ is m-order pole singularity
                    + $f(z)=\cfrac{\sin z}{z(e^z-1)}=\cfrac{\sin z}{z}\cdot \cfrac{1}{e^z-1}$
            + Essential Singularity 
                + $f(z)=\cdots + \cfrac{C_{-m}}{(z-z_0)^m}+ \cdots$
                + $z=0$, $f(z)=e^{\frac{1}{z}}$, $\sin\cfrac{1}{z}$, $\cos \cfrac{1}{z}$
    + Residue of removable singularity: $Res[f(z),z_0]=C_{-1}=0$
        + $Res[\cfrac{z}{e^z-1}]=0$, $\oint_{|z|=10}\cfrac{z}{e^z-1}dz=2\pi i*$
    + Residue of essential singularity: solve with Laurent Expansion
        + Example: $f(z)=\cos\cfrac{1}{z}$
            + $f(z)=1-\cfrac{1}{2!}(1/2)^2$
            + 0
        + Example: $f(z)=\cfrac{z^3}{1+z}e^{\cfrac{1}{z}}$
            + $z=0$
                + $f(z)=(z^3(1-z+z^2-z^3\cdots))(1+\cfrac{1}{z}+\cfrac{1}{2!z}+\cdots)$
                + $=(\cfrac{1}{4!}-\cfrac{1}{5!}+\cfrac{1}{6!}-\cdots)\cfrac{1}{z}+ \cdots$
                + $=(e^{-z}-\cfrac{1}{2!}+\cfrac{1}{3!})(1/z)+\cdots$
    + Residue of m-order pole singularity
        + solve with Laurent Expansion: $C_{-1}$
            + Example: $Res[\cfrac{e^z-1}{z^{2019}},0]$
                + $=\cfrac{1}{z^{2019}}(z+\cfrac{1}{2!}z^2+\cdots+\cfrac{1}{n!}z^n+\cdots)$
                + $C_{-1}=\cfrac{1}{2018!}$
            + $I=\oint_{|z|=1}\cfrac{e^z-1}{z^{2019}}dz=2\pi i*\cfrac{1}{2018!}$
        + if $z_0$ is m-order pole singularity of $f(z)$, $Res[f(z),z_0]=\cfrac{1}{(m-1)!}\lim\limits_{z\to z_0}\cfrac{d^{m-1}}{dz^{m-1}}[(z-z_0)^mf(z)]$
            + Especially when $m=1$, $Res[f(z),z_0]=\lim\limits_{z\to z_0}[(z-z_0)f(z)]$
            + Example1 $Res[\cfrac{e^z}{(z-1)^2(2z+1)}]$
                + $z_0=1$: 2-order pole singularity
                    + $Res[\cfrac{e^z}{(z-1)^2(2z+1)},1]=\cfrac{1}{1!}(\cfrac{e^z}{2z+1})'=\cfrac{e}{9}$
                + $z_0=-\cfrac{1}{2}$: 1-order 
                    + $Res[\cfrac{e^z}{(z-1)^2(2z+1)},-\cfrac{1}{2}]=\lim\limits_{z\to-1/2}\cfrac{e^z}{(z-1)^2}$
            + Example $Res[\cfrac{z-1}{z(e^z-1)},0]$
                + 2-order
                + $=\lim_{z\to 0}({\cfrac{(z-1)z}{e^z-1}})'$
                + $=\lim_{z\to 0}{\cfrac{(2z-1)(e^z-1)-z(z-1)e^z}{(e^z-1)^2}}$
                + $=\cfrac{3}{2}$
            + Example $Res[\tan\pi z,k+\cfrac{1}{2}], I_3=\oint_{|z|=2}\tan \pi zdz$
                + $z_k=k+\cfrac{1}{2}$: 1-order;
                + $=\lim_{z\to z_k}(z-z_k)\cfrac{\sin \pi z}{\cos\pi z}$
                + $\cdots$
            + Example $f(z)=\cfrac{1}{x^4+1}$
                + $z_k=e^{\cfrac{(2k+1)\pi i}{4}}$
                + 1-order
                + $Res[f(z),z_k]=\lim_{z\to z_k}f(z)(z-z_k)=\cfrac{1}{4z_k^3}=\cfrac{z_k}{4\cdot (-1)}$
        + Process
            1. find all singularity
            2. check type
            3. get residue based on singularity type
            4. use residue theroem
    + Application of Residue theorem
        + $\int_0^{2\pi} R(\cos\theta,\sin\theta)d\theta$
            + $\int_0^{2\pi} R(\cos\theta,\sin\theta)d\theta=\oint_Cf(z)dz$
            + let $z=e^{i\theta}$
            + $\int_0^{2\pi}R(\cos\theta,\sin\theta)d\theta=\oint_{|z|=1}f(z)dz$
                + $d\theta=\cfrac{1}{iz}dz$
                + $\cos\theta=\cfrac{e^{i\theta}+e^{-i\theta}}{2}=\cfrac{z^2+1}{2z}$
                + $\sin\theta=\cfrac{e^{i\theta-e^{-i\theta}}}{2i}=\cfrac{z^2-1}{2iz}$
            + $I=\oint_{|z|=1}R(\cfrac{z^2+1}{2z},\cfrac{z^2-1}{2iz})\cfrac{1}{2z}dz$
            + Example: $I=\int_0^{2\pi}\cfrac{d\theta}{5-3\cos\theta}$
                + $z=e^{i\theta}$
                + $\cos\theta=\cfrac{z^2+1}{2z}$
                + $d\theta=\cfrac{1}{iz}dz$
                + $I=\oint_{|z|=1}\cfrac{1}{5-3(\cfrac{z^2+1}{2z})}\cfrac{1}{iz}dz$
                + $=-\cfrac{2}{i}\oint_{|z|=1}\cfrac{dz}{(3z-1)(z-3)}=-\cfrac{1}{8}$
        + $\int_{-\infty}^\infty\cfrac{P(x)}{Q(x)}dx=\lim\limits_{R\to\infty}\int_{-R}^R\cfrac{P(x)}{Q(x)}dx$
            + where $P(x)=C_0x^m+C_1x^{m-1}+\cdots+C_m$ and $Q(x)=b_0x^n+b_1x^{n-1}+\cdots+b_n$
                + $\partial Q(x)-\partial P(x)\ge 2$
                + $Q(x)\ne 0$
            + then $\int_{-\infty}^\infty\cfrac{P(x)}{Q(x)}dx=2\pi i\sum_{i=1}^n Res[f(z),z_k]$, where $f(z)=\cfrac{P(z)}{Q(z)}$ and $z_k$ is the singularity on above part of $f(z)$
            + Example: $I=\int_{-\infty}^\infty\cfrac{1}{1+x^4}dx$
                + $f(z)=\cfrac{1}{1+z^4}$     
                + $z_k=e^{\cfrac{\pi+2k\pi}{4}}$, $k=0,1$
                + $I=2\pi i(Res(f(z),0)+Res(f(z),1))$
            + Example2: $I_2=\int_0^\infty\cfrac{1}{1+x^4}dx$
                + $=\cfrac{\int_{-\infty}^\infty\cfrac{1}{1+x^4}dx}{2}$
        + $\int_{-\infty}^\infty\cfrac{P(x)}{Q(x)}e^{iax}dx$ $(a>0)$
            + $\partial Q(x)>\partial P(x)$
            + $Q(x)\ne 0$
            + $\int_{-\infty}^\infty\cfrac{P(x)}{Q(x)}e^{iax}dx=2\pi i\sum_{i=1}^n Res[\cfrac{P(x)}{Q(z)}e^{iaz},z_k]$
                + $z_K$ is the singularity on $\cfrac{P(z)}{Q(z)}e^{iaz}$ on above part of $f(z)$
            + $A=2\pi i\sum_{i=1}^nRes[\cfrac{P(z)}{Q(z)}e^{iaz},z_k]$
            + $\int_{-\infty}^\infty \cfrac{P(x)}{Q(x)}\cos axdx=\Re A$
            + $\int_{-\infty}^\infty \cfrac{P(x)}{Q(x)}\sin axdx=\Im A$
+ Fourier Transform
    + Dirichlet Requiremnt:
        + Continuous or has limited one-order discontinuity.
        + ?
    + $f_T(t)=\cfrac{a_0}{2}\sum_{n=1}\infty a_n \cos n\omega_0 t+b_n\sin n \omega_0 t$
        + $a_n=\cfrac{2}{T}\int_{-T/2}^{T/2}f_T(t)\cos n\omega_0 tdt$
        + $b_n=\cfrac{2}{T}\int_{-T/2}^{T/2}f_T(t)\sin n\omega_0 tdt$
        + $\omega_0:$  Baseband
    + using Euler Equation
        + $f_T(t)=\sum_{n=-\infty}^{\infty}c_ne^{in\omega_0 t}$
        + $c_0=\cfrac{a_0}{2}$
        + $c_n=\cfrac{1}{T}\int_{-T/2}^{T/2}f_T(t)e^{-in\omega_0 t}dt$
        + $f_T(t)=\sum_{n=-\infty}^\infty(\cfrac{1}{T}\int_{-T/2}^{T/2}f_T(t)e^{-in\omega_0 t}dt)e^{in\omega_0 t}$
        + $c_n=\cfrac{1}{T}\int_{-T/2}^{T/2}f_T(t)e^{-i\omega_nt}dt$
        + $f(t)=\lim\limits_{T\to\infty}f_T(t)=\lim\limits_{T\to\infty}\cfrac{1}{T}\sum_{n=-\infty}^\infty(\int_{-T/2}^{T/2}f_T(t)e^{-in\omega_0 t}dt)e^{i\omega_n t}$
        + $\Delta\omega=\omega_n-\omega_{n-1}=2\pi/T$
        + $\Delta\omega\to 0\Leftrightarrow T\to +\infty$
        + $f(t)=\lim\limits_{\Delta \omega\to 0}\cfrac{1}{2\pi}\sum_{n=-\infty}^\infty F_T(\omega_n)e^{i\omega_n t}\Delta\omega$
        + $f(t)=\cfrac{1}{2\pi}\int_{-\infty}^\infty[\int_{-\infty}^\infty f(t)e^{-i\omega t}dt]e^{i\omega t}d\omega$
        + $F(\omega)$: Fourier Transform of $f(t)$: $F_T(\omega)=\int_{-\infty}^{\infty}f(t)e^{-i\omega t}dt$, $T\to +\infty$
        + Fourier Integration of $f(t)$: $f(t)=\cfrac{1}{2\pi}\int_{-\infty}^{+\infty}F(\omega)e^{i\omega t}d\omega$
    + Fourier Integration Exisit theorem
    + LIST:
        + $\int_{-\infty}^{\infty}|f(t)|dt<+\infty$
        + $f(t)$ support Dirichlet requirement within bounded region
        + Fourier Transform of $f(t)$: $F(\omega)=\mathscr{F}[f(t)]=\int_{-\infty}^{+\infty}f(t)e^{-i\omega t}dt$
        + Inverse Fourier Transform of $F(\omega)$: $\mathscr{F}^{-1}[F(\omega)]=\cfrac{1}{2\pi}\int_{-\infty}^{+\infty}F(\omega)e^{i\omega t}d\omega$
    + $\delta$ Function (Dirac Function)
        + $$\rho(x)=\lim\limits_{L\to 0}\rho_L(x)=\begin{cases}
            0 & x\ne x_0\\
            \infty & x=x_0\\ \end{cases}$$
        + $\int_{-\infty}^{\infty}\delta(t)dt=1$
        + $\int_{-\infty}^{\infty}\delta(t-t_0)f(t)dt=f(t_0)$

    + Fourier Transformation of $\delta$ function
        + $\mathscr{F}[\delta(t)]=\int_{-\infty}^\infty\delta(t)e^{-i\omega t}dt=e^{-i\omega t}\big|_{t=0}=1$
        + $\delta(t)=\cfrac{1}{2\pi}\int_{-\infty}^\infty 1e^{i\omega t}d\omega\Rightarrow \int_{-\infty}^\infty e^{i\omega t}d\omega=2\pi \delta(t)\Rightarrow \int_{-\infty}^\infty e^{i\omega t}dt=2\pi \delta(\omega)$
        + Example $\mathscr{F}[1]$
            + $\int_{-\infty}^\infty e^{-i\omega t}dt=\int_{-\infty}^\infty e^{it(-\omega)}dt=2\pi \delta(-\omega)=2\pi\delta(\omega)$
        + Example $f(t)=e^{i\omega_0 t}$
            + $\mathscr{F}[e^{i\omega_0 t}]=\int_{-\infty}^\infty e^{it(\omega_0-\omega)}dt=2\pi\delta(\omega-\omega_0)$
        + Example $f(t)=\cos\omega_0 t$
            + $\mathscr{F}[f(t)]=\int_{-\infty}^\infty \cos\omega_0 te^{-i\omega t}=\int_{-\infty}^{\infty}=\cfrac{e^{i\omega_0t}-e^{-i\omega_0t}}{2}e^{-i\omega t}=\pi[\delta(\omega-\omega_0)+\delta(\omega+\omega_0)]$
    + Characteristics
        + Linear
            + $\mathscr{F}[\alpha f+\beta g]=\alpha\mathscr{F}[f]+\beta\mathscr{F}[g]$
        + Translate
            + $\mathscr{F}[f(t-t_0)]=e^{-i\omega t_0}\mathscr{F}[f]$
            + $\mathscr{F}[e^{i\omega_0t}f(t)]=F(\omega-\omega_0)$
            + Example $\mathscr{F}[\delta(t-2)]$
                + $=e^{i\omega 2}$
            + Example $\mathscr{F}[\cos\omega_0(t-1)]=e^{i\omega}\pi(\delta(\omega-\omega_0)+\delta(\omega+\omega_0))$
            + Example $\mathscr{F}[f(t)\cos\omega_0t]=\mathscr{F}[f(t)\cfrac{e^{i\omega_0t}+e^{-i\omega_0t}}{2}]=\cfrac{1}{2}F(\omega-\omega_0)+\cfrac{1}{2}F(\omega+\omega_))$
        + Similarity
            + assume that $a\not ={0}$, $\mathscr{F}[f(at)]=\cfrac{1}{|a|}F(\cfrac{\omega}{a})$
        + differential
            + If $\lim\limits_{|t|\to\infty}f(t)=0$,then
            + $\mathscr{F}[f'(t)]=i\omega\mathscr{F}[f]$
            + $\cfrac{dF(\omega)}{d\omega}=\mathscr{F}[-itf(t)]$
            + Generally
                + $\mathscr{F}[f^{(n)}(t)]=(i\omega)^n\mathscr{F}[f]$
                + $\cfrac{d^nF(\omega)}{d\omega^n}=(-i)^n\mathscr{F}[t^nf(t)]$
            + Example $\mathscr{F}[(2t-1)f(t)]$
                + $=2\mathscr{F}[tf]-F(\omega)=$
        + integral
            + $\mathscr{F}[g(t)]=\cfrac{1}{i\omega}\mathscr{F}[f(t)]$
        + Convolution
            + $\mathscr{f_1*f_2}=\mathscr{f_1(t)}+\mathscr{f_2(t)}$
            + TODO
+ Preparation For Laplace Transform
    + $\cfrac{Q(s)}{R(s)}$
        + $==\cfrac{c_1}{s-a}+\cfrac{c_2}{(s-a)^2}+\cdots+\cfrac{c_k}{(s-a)^k}$
        + $==\cfrac{M_1s+N_1}{(s-\alpha)^2+\beta^2}+\cfrac{M_2s+N_2}{[(s-\alpha)]^2-\beta^2}$
        + $\cdots$
    + Example $\cfrac{5s-1}{(s+1)(s-2)}$
        + $=\cfrac{a}{s+1}+\cfrac{b}{s-2}$
        + $a=2$
        + $b=3$
        + $=\cfrac{2}{s+1}+\cfrac{3}{s-2}$
    + Example $\cfrac{s+3}{(s+1)(s+2)^2}$
        + $=\cfrac{a}{s+1}+\cfrac{b}{s+2}+\cfrac{c}{(s+2)^2}$
        + $\cdots$
    + Example $\cfrac{1}{[(s+1)^2+1](s+2)}$
        + $=\cfrac{a}{s+2}+\cfrac{bs+c}{(s+1)^2+1}+\cfrac{ds+e}{[(s+1)^2+1]^2}$
    + Example $\cfrac{s^2}{(s^2+1)^2}$
        + $=\cfrac{as+b}{(s^2+1)}+\cfrac{cs+d}{(s^2+1)^2}$
+ Laplace Transformation
    + Definition of Laplace Transformation
        + assume that $f(t)$ is a real function defined on $[0,\infty)$ and support Dirichlet Requirements, for $s=\beta+i\omega$, the Laplace Transformation of $f(t)$ is $F(s)=\int_0^{+\infty}f(t)e^{-st}dt$ which convergent.
        + $$f_1(t)=\begin{cases}
            f(t)e^{-st}&t>=0\\
            0&t<0\\        \end{cases}$$
        + $\mathscr{F}[f_1(t)]=\int_{-\infty}^{+\infty}f_1(t)e^{-i\omega t}dt=\int_0^{+\infty}f(t)e^{-\beta t}e^{-i\omega t}dt=\int_0^{+\infty}f(t)e^{-(\beta+i\omega)t}dt==$
        + **$\mathscr{L}[f(t)]=\int_0^{+\infty}f(t)e^{-st}dt$**
        + $f(t)$ is the reverse Laplace Tranformation of $F(s)$, signed $f(t)=\mathscr{L}^{-1}[F(s)]$
        + $\mathscr{L}[f(t)]=\mathscr{F}[f_1(t)]=\mathscr{F}[f(t)e^{-\beta t}u(t)]$
    + Examples:
        + $\mathscr{L}[1]=\int_0^\infty e^{-st}dt=-\cfrac{1}{s}e^{-st}\bigg|_0^{+\infty}=-\cfrac{1}{s}e^{-\beta t}e^{-i\omega t}\bigg|_0^\infty=\cfrac{1}{s}$
            + $\mathscr{L}^{-1}[\cfrac{1}{s}]=1$
        + $\mathscr{L}[e^{\alpha t}]=\int_0^\infty e^{\alpha t-st}dt=\cfrac{1}{\alpha-s}e^{(\alpha-s)t}\bigg|_0^\infty=\cfrac{1}{s-a}$
            + $\mathscr{L}^{-1}[\cfrac{1}{S-\alpha}]=e^{\alpha t}$
        + $\mathscr{L}[\cos bt]=\mathscr{L}[\cfrac{e^{ibt}+e^{-ibt}}{2}]=\cfrac{1}{2}(\cfrac{1}{s-bi}+\cfrac{1}{s+bi})=\cfrac{s}{s^2+b^2}$
            + $\mathscr{L}^{-1}[\cfrac{s}{s^2+b^2}]=\cos bt$
            + * solve $\int_0^\infty e^{-3t}\cos tdt$
                + $\mathscr{L}[\cos t]\bigg|_{s=3}=\int_0^\infty \cos te^{-st}dt=\cfrac{s}{s^2+1}\bigg|_{s=3}$
        + $\mathscr{L}[\sin bt]=\mathscr{L}[\cfrac{e^{ibt}-e^{-ibt}}{2i}]=-\cfrac{i}{2}(\cfrac{1}{s-bi}-\cfrac{1}{s+bi})=\cfrac{b}{s^2+b^2}$
            + $\mathscr{L}^{-1}[\cfrac{b}{s^2+b^2}]=\sin bt$
        + $\mathscr{L}[t]=\int_0^\infty te^{-st}dt=\cfrac{1}{s^2}$
            + $\mathscr{L}^{-1}[\cfrac{1}{s^2}]=t$
        + $\mathscr{L}[t^2]=\cfrac{2!}{s^{3}}$
            + $\mathscr{L}^{-1}[\cfrac{2!}{s^3}]=t^2$
        + $\mathscr{L}[t^m]=\cfrac{m!}{s^{m+1}}$
            + $\mathscr{L}^{-1}\cfrac{m!}{s^{m+1}}=t^m$
    + Solve $\mathscr{L}^{-1}[\cfrac{Q(s)}{R(s)}]$
        + Mini-
            + $\cfrac{c_1}{s-a}$
            + $\cfrac{c_2}{(s-a)^2}$
            + $\cfrac{M_1s+N_1}{(s-\alpha)^2+\beta^2}$
            + $\cfrac{M_2s+N_2}{(s-\alpha)^2+\beta^2}$
        + 2 characteristics
            + Linear
                + $\mathscr{L}[\alpha f+\beta g]=\alpha F(s)+\beta G(s),\alpha,\beta\in C$
                    + $\mathscr{L}^{-1}[\alpha F(s)+\beta G(s)]=\alpha\mathscr{L}^{-1}[F(s)]+\beta\mathscr{L}^{-1}[G(s)]$
                + Example 1: 
                    + $\mathscr{L}^{-1}[\cfrac{s}{(s^2+1)(s^2+9)}]=\cfrac{1}{8}\mathscr{L}^{-1}[(\cfrac{s}{s^2+1}-\cfrac{s}{s^2+9})]=\cfrac{1}{8}(\cos t-\cos 3t)$
                + Example 2:
                    + $\mathscr{L}^{-1}[\cfrac{1}{(s^2+1)(s^2+9)}]=\cfrac{1}{8}\mathscr{L}^{-1}[(\cfrac{1}{s^2+1}-\cfrac{3}{s^2+9})]=\cfrac{1}{8}(\sin t-\sin 3t)$
            + Translate
                + $\mathscr{L}[e^\alpha tf(t)]=F(s-\alpha)$
                + $\mathscr{L}^{-1}[F(s-\alpha)]=e^{\alpha t}f(t)$
                + Example 1:
                    + $\mathscr{L}^{-1}[\cfrac{1}{s^2+4s+8}]=\mathscr{L}^{-1}[\cfrac{1}{(s+2)^2+4}]=(\alpha=-2)=e^{-2t}\mathscr{L}^{-1}[\cfrac{1}{s^2+4}]=e^{-2t}\sin 2t$
                + Example 2:
                    + $\mathscr{L}^{-1}[\cfrac{c_1}{(s-a)^2}]=c_1e^{at}\mathscr{L}^{-1}[\cfrac{1}{s^2}]=c_1te^{at}$
                + $\mathscr{L}^{-1}[\cfrac{1}{(s-\alpha)^2+\beta^2}]=e^{\alpha t}\mathscr{L}^{-1}[\cfrac{1}{s^2+\beta^2}]=\cfrac{1}{\beta}e^{\alpha t}\sin\beta t$
                + $\mathscr{L}^{-1}[\cfrac{s}{(s-\alpha)^2+\beta^2}]=\mathscr{L}^{-1}[\cfrac{s-\alpha}{(s-\alpha)^2+\beta^2}]+\alpha\mathscr{L}^{-1}[\cfrac{1}{(s-\alpha)^2+\beta^2}]=\cdots$
                + $\mathscr{L}^{-1}[\cfrac{s}{[(s-\alpha)^2+\beta^2]^2}]=\mathscr{L}^{-1}[\cfrac{s-\alpha}{[(s-\alpha)^2+\beta^2]^2}]+\alpha\mathscr{L}^{-1}[\cfrac{1}{[(s-\alpha)^2+\beta^2]^2}]=???$ unknown
            + Derivative
                + Assume that $\mathscr{L}[f(t)]=F(s)$, then $F'(s)=-\mathscr{L}[tf(t)]$
                + $\Rightarrow\mathscr{L}^{-1}[F'(s)]=-tf(t)$
                + Generally, $F^{(n)}(s)=(-1)^n\mathscr{L}[t^n f(t)]$
                + $\Rightarrow\mathscr{L}^{-1}[F^{(n)}(s)]=(-1)^nt^nf(t)$
                + Example $\mathscr{L}^{-1}[\cfrac{s}{(s^2+1)^2}]$
                    + $=\mathscr{L}^{-1}[(-\cfrac{1}{2}\cfrac{1}{s^2+1})']=-t\mathscr{L}^{-1}[-\cfrac{1}{2}\cfrac{1}{s^2+1}]=\cfrac{t}{2}\sin t$
                + Example $\mathscr{L}^{-1}[\cfrac{s}{(s^2+\beta^2)^2}]=\mathscr{L}^{-1}[(\cfrac{1}{2}\cfrac{1}{s^2+\beta^2})']=\cfrac{t}{2\beta}\sin\beta t$
                + Example $\mathscr{L}[t\sin\omega t]$
                    + $=-(\mathscr{L}[\sin\omega t])'=-(\cfrac{\omega}{s^2+\omega^2})'=\cfrac{2s\omega}{(s^2+\omega^2)^2}$
                + Example $\mathscr{L}[e^{-3t}t\sin\omega t]$
                    + $=F(s+3)$
                    + $F(s)=\cfrac{2s\omega}{(s^2+\omega^2)^2}$
                    + $=F(s+s)=\cfrac{2(s+3)\omega}{((s+3)^2+\omega^2)^2}$
            + Differential
                + Assume that $\mathscr{L}[f(t)]=F(s)$, then $\mathscr{L}[f'(t)]=sF(s)-f(0)$
                + $\mathscr{L}[f^{(n)}(t)]=s^nF(s)-s^{n-1}f(0)-s^{n-2}f'(0)-\cdots-f^{(n-1)}(0)$
                + Especially when $f(0)=f'(0)=f^{(n-1)}(0)=0$, $\mathscr{L}[f^{(n)}(t)]=s^nF(s)$
                + **Example Important** $\begin{cases} y''+3y'+2y=2e^{-t}\cos t\\
                y(0)=y'(0)=0\\\end{cases}$
                    + $Y(s)=\mathscr{L}[y(t)]$
                    + then $\mathscr{L}[y'(t)]=sY(s)$
                    + $\mathscr{L}[y''(t)]=s^2Ys$
                    + $\mathscr{L}[2e^{-t}\cos t]=2\cfrac{s+1}{(s+1)^2+1}$
                    + $(s^2+3s+2)Y(s)=\cfrac{s+1}{(s+1)^2+1}$
                    + $Y(s)=\cfrac{1}{((s+1)^2+1)(s+2)}$
                    + $\Rightarrow y(t)=\mathscr{L}^{-1}[Y(s)]=\mathscr{L}^{-1}[\cfrac{1}{s+2}-\cfrac{s}{(s+1)^2+1}]=e^{-2t}+e^{-t}(\cos t-\sin t)$
                + Example $\begin{cases}y''(t)-y(t)=4\sin t+5\cos 2t\\y(0)=-1, y'(0)=-2\\\end{cases}$
                    + $Y(s)=\mathscr{L}[y(t)]$, $\mathscr{L}[y''(t)]=s^2Y(s)+2$
                    + $-sy(0)-y'(0)=S^2Y(s)+s+2$
                    + $\mathscr{L}[4\sin t+ 5\cos 2t]=\cfrac{4}{s^2+1}+\cfrac{5s}{s^2+4}$
                    + $(s^2-1)Y(s)+s+2=\cfrac{4}{s^2+1}+\cfrac{5s}{s^2+4}$
                    + $Y(s)=\cfrac{4}{(s^2+1)(s^2-1)}+\cfrac{5s}{(s^2+4)(s^2-1)}-\cfrac{s+2}{s^2-1}=-\cfrac{2}{s^2+1}-\cfrac{s}{s^2+4}$
                    + $y(t)=\mathscr{L}^{-1}[Y(s)]=-2\sin t-\cos 2t$
            + Integral
                + Assume that $\mathscr{L}[f(t)]=F(s)$, then $\mathscr{L}[\int_0^t f(t)dt]=\cfrac{F(s)}{s}$
                + $\Rightarrow \mathscr{L}^{-1}[\cfrac{F(s)}{s}]=\int_0^tf(t)dt$, where $f(t)=\mathscr{L}^{-1}[F(s)]$
                + $\mathscr{L}^{-1}[F'(s)]=-tf(t)$
                + Example $\mathscr{L}^{-1}[\cfrac{1}{(s^2+\beta^2)^2}]$
                    + $=\mathscr{L}^{-1}[\cfrac{s}{(s^2+\beta^2)^2\cfrac{1}{s}}]=\int_0^tf(t)dt$
                    + $f(t)=\mathscr{L}^{-1}[\cfrac{1}{(s^2+\beta^2)^2}]=\cfrac{1}{2\beta}t\sin \beta t$
                    + $I=\int_0^t\cfrac{1}{2\beta}t\sin\beta\tau d\tau=\cfrac{1}{2\beta}(-\cfrac{1}{\beta})[\tau\cos\beta\tau\big|_0^t-\int_0^t\cos\beta\tau d\tau]=-\cfrac{1}{2\beta^2}[t\cos\beta t-\cfrac{1}{\beta}\sin\beta t]$
                + Example $I_1=\mathscr{L}[\int_0^t e^{-3t}t\sin 2t dt]$
                    + $f(t)=e^{-3t} t\sin 2t$
                    + $g(t)=t\sin 2t$
                    + $I_1=\mathscr{L}[f(t)]=\mathscr{L}[e^{-3t}t\sin 2t]=G(s+3)$
                    + $h(t)=\sin 2t$
                    + $G(s)=\mathscr{L}[g(t)]=-H'(s)$
                    + $H(s)=\mathscr{L}[\sin 2t]=\cfrac{2}{s^2+4}$
                    + $G(s)=\cfrac{4s}{s^2+4}$
                    + $F(s)=\cfrac{4s+3}{(s+3)^2+4}$
                    + $I_1=\cfrac{F(s)}{s}$
                + Example $I_2=\mathscr{L}[e^{-3t}\int_0^t t\sin 2t dt]$
                    + $I_2=\mathscr{L}[e^{-3t}f(t)]=F(s+3)$
                    + $F(s)=\mathscr{L}[f(t)]=\mathscr{L}[\int_0^tg(t)dt]=\cfrac{G(s)}{s}$
                    + $G(s)=\mathscr{L}[\sin 2t]=\cfrac{4s}{s^2+4}$
                + Example $I_3=\mathscr{L}[t\int_0^t e^{-3t}\sin 2t dt]$ 
                    + $F(s)=\mathscr{L}[g(t)]=\cfrac{G(s)}{s}$
                    + $G(s)=\mathscr{L}[e^{-3t}\sin 2t]=\cfrac{2}{(s+3)^2+4}$
                + Example $\int_0^\infty\cfrac{1-\cos t}{t}e^{-t}dt=\mathscr{L}[\cfrac{1-\cos t}{t}]\big|_{s=1}$
        + Examples:
            + $\mathscr{L}^{-1}\cfrac{s}{(s^2+1)(s^2+0)}$