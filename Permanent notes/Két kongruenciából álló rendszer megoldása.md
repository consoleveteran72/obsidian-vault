Date: 2026-10-13
Tags: 

Tekintsük a következő két kongruenciából álló rendszert:

$$\begin{aligned} x &\equiv c_1 \pmod{m_1} \\ x &\equiv c_2 \pmod{m_2} \end{aligned}$$

#### 1. Megoldhatóság feltétele:

$$\text{Inko}(m_1, m_2) \mid (c_1 - c_2)$$

Magyarázat:** Az első egyenletből $x = c_1 + k \cdot m_1$. Ezt behelyettesítve a másodikba:
  
   $$c_1 + k \cdot m_1 \equiv c_2 \pmod{m_2} \iff k \cdot m_1 \equiv c_2 - c_1 \pmod{m_2}$$
 $$
 k\cdot m_{1} = y\cdot m_{2} + c_{2}-c_{1} \\
 k \cdot m_{1} - y \cdot m_{2} = c_{2} -c_{1}
 $$
 
Ez egy lineáris kongruencia $k$-ra, aminek akkor és csak akkor van megoldása a [[Kongruencia megoldhatóság feltétel]] alapján, ha $\text{Inko}(m_1, m_2) \mid (c_1 - c_2)$.


Related concepts:
[[Index - Diszkrét matematika]]


Source:
