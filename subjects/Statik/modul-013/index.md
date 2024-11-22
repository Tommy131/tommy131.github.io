#

## 5.3 线性分布载荷（Linienlasten）

线性分布载荷是指沿一定方向连续分布的力，例如：

- 梁和绳索的自身重力分布
- 作用在绳索上的风力
- 管道或烟囱的分布载荷

这些载荷可以用一个等效的集中力 $F_R$ 替代，集中力作用在等效点 $x_S$ 处，其效果与分布载荷相同。

![5.3-1](./subjects/Statik/modul-013/imgs/5.3-1.png)

### 理论推导：通过力矩平衡确定 $F_R$

对于分布载荷 $q(x)$，每个小段 $dx$ 上的力可以表示为：
$$ dF = q(x) dx $$

集中力 $F_R$ 的位置 $x_S$ 和大小通过以下方法计算：

1. **力矩平衡方程**
    $$ F_R \cdot x_S = \int x \cdot q(x) dx $$

2. **集中力大小**
    $$ F_R = \int q(x) dx $$

3. **集中力作用点（形心位置）**
    $$ x_S = \frac{\int x \cdot q(x) dx}{\int q(x) dx} $$

### 详细解释

1. **分布载荷 $q(x)$**
   - $q(x)$ 是单位长度上的载荷强度（例如，牛顿每米，$\text{N/m}$）。
   - 分布载荷的形状可以是恒定的、线性变化的，或更复杂的函数形式。

2. **等效集中力 $F_R$**
   - 等效集中力是将整个分布载荷的效果等效为一个单一力，其大小为分布载荷在梁上整体的积分：
     $$ F_R = \int q(x) dx $$
   - 物理意义：等效集中力 $F_R$ 是分布载荷的总作用力。

3. **等效作用点 $x_S$**
   - 等效作用点是使集中力 $F_R$ 对某参考点的力矩与原分布载荷对该点的力矩相同的位置：
     $$ x_S = \frac{\int x \cdot q(x) dx}{\int q(x) dx} $$
   - 物理意义：这个位置是分布载荷的形心，也被称为质心位置。

4. **平衡条件**
   - 力的平衡条件用于确定 $F_R$ 的大小。
   - 力矩的平衡条件用于确定集中力的作用点 $x_S$。

---

### 示例应用

- **均匀分布载荷** $q(x) = q_0$：
  - 等效集中力：$F_R = q_0 \cdot l$
  - 等效作用点：$x_S = \frac{l}{2}$（均匀分布时，集中力作用在形心位置）

- **线性变化载荷** $q(x) = kx$：
  - 等效集中力：$F_R = \int_0^l kx dx = \frac{1}{2}kl^2$
  - 等效作用点：$x_S = \frac{\int_0^l x \cdot kx dx}{\int_0^l kx dx} = \frac{2l}{3}$

**总结**: 线性分布载荷的等效集中力 $F_R$ 和其作用点 $x_S$ 是通过积分方法计算的，用于简化分布载荷的力学分析。这一方法在梁和结构分析中广泛应用。

---

### 例子 1：恒定分布载荷（Konstante Streckenlast）

![5.3-b1](./subjects/Statik/modul-013/imgs/5.3-b1.png)

- 恒定分布载荷 $q_0$ 沿梁的长度 $l$ 分布。
- 等效集中力 $F_R$ 和作用点 $x_S$ 的计算如下：

1. **等效集中力 $F_R$**：
   恒定载荷的等效集中力是矩形面积：
   $$
   F_R = \int_0^l q(x) dx = \int_0^l q_0 dx = q_0 \cdot l
   $$

2. **等效作用点 $x_S$**：
   恒定载荷的等效作用点是矩形的形心，位于中点 $\frac{l}{2}$ 处：
   $$
   x_S = \frac{\int_0^l x \cdot q(x) dx}{\int_0^l q(x) dx} = \frac{\int_0^l x \cdot q_0 dx}{q_0 \cdot l}
   $$
   $$
   x_S = \frac{q_0 \cdot \frac{l^2}{2}}{q_0 \cdot l} = \frac{l}{2}
   $$

![b1](./subjects/Statik/modul-013/imgs/b1.png)

---

### 例子 2：线性变化分布载荷（Linear steigende Streckenlast）

![5.3-b2](./subjects/Statik/modul-013/imgs/5.3-b2.png)

- 载荷从 0 变化到 $q_0$，形成一个三角形分布。
- 等效集中力 $F_R$ 和作用点 $x_S$ 的计算如下：

1. **分布载荷方程 $q(x)$**：
   三角形分布的方程为：
   $$
   q(x) = \frac{q_0}{l} \cdot x
   $$

2. **等效集中力 $F_R$**：
   三角形载荷的等效集中力是面积：
   $$
   F_R = \int_0^l q(x) dx = \int_0^l \frac{q_0}{l} \cdot x dx = \frac{q_0}{l} \cdot \frac{x^2}{2} \Big|_0^l
   $$
   $$
   F_R = \frac{q_0}{l} \cdot \frac{l^2}{2} = \frac{q_0 \cdot l}{2}
   $$

3. **等效作用点 $x_S$**：
   三角形载荷的等效作用点是三角形的形心，位于底边的 $\frac{2}{3}l$ 处：
   $$
   x_S = \frac{\int_0^l x \cdot q(x) dx}{\int_0^l q(x) dx}
   $$
   $$
   x_S = \frac{\int_0^l x \cdot \frac{q_0}{l} \cdot x dx}{\frac{q_0 \cdot l}{2}} = \frac{\frac{q_0}{l} \cdot \frac{x^3}{3} \Big|_0^l}{\frac{q_0 \cdot l}{2}}
   $$
   $$
   x_S = \frac{\frac{q_0}{l} \cdot \frac{l^3}{3}}{\frac{q_0 \cdot l}{2}} = \frac{2l}{3}
   $$

![b2-1](./subjects/Statik/modul-013/imgs/b2-1.png)

![b2-2](./subjects/Statik/modul-013/imgs/b2-2.png)

---

### 结论

- 对于恒定分布载荷，等效集中力作用在中点 $x_S = \frac{l}{2}$。
- 对于线性变化分布载荷（如三角形分布），等效集中力作用在 $x_S = \frac{2l}{3}$，靠近重的部分（形心位置）。
- 等效集中力 $F_R$ 始终等于分布载荷的总面积。

---

## 5.4 切应力分布的计算 (Ermittlung der Schnittgrößenverläufe)

在大多数情况下，由于梁的受力和几何形状，很难直观地确定切应力的最大值所在的位置。因此，**需要通过分析整个梁的长度来确定切应力的分布**。

为了计算切应力的分布，梁会在任意位置 $x$ 处进行切割，并通过分析正切面和负切面两个子系统的平衡条件来求解。

![5.4-1](./subjects/Statik/modul-013/imgs/5.4-1.png)

### 计算步骤

1. **定义坐标系**
   - $x$-轴沿梁的长度方向。
   - $z$-轴向下。
   - 沿梁的正 $z$-方向绘制虚线以标识正方向。

2. **根据平衡条件计算支座反力**

    ![5.4-2](./subjects/Statik/modul-013/imgs/5.4-2.png)

   - 在梁两端的支座处求解支座反力（例如 $F_{Ax}, F_{Az}, F_{Bz}$），平衡方程为：
     $$
     \sum F_x = 0, \quad \sum F_z = 0, \quad \sum M_{i[A]} = 0
     $$
   - 计算结果：支座反力 $F_{Ax}, F_{Az}, F_{Bz}$。

3. **切割梁并分析切应力**

    ![5.4-3](./subjects/Statik/modul-013/imgs/5.4-3.png)

    - 在任意位置 $x$ 处对梁进行切割。
    - 分析切割后两个子系统（正切面和负切面）的力平衡和力矩平衡，求解该位置的切应力（法向力 $F_N$、剪力 $F_Q$、弯矩 $M$）。
    - 分布载荷 $q(x)$ 施加在梁的右侧，集中力 $F$ 和力矩 $M$ 作用于中间位置。
    - 切割后，正切面和负切面分别暴露出内部的切应力，这些切应力与外力和支座反力共同满足平衡条件。

    a. **平衡条件**：
    - 力的平衡：
        $
        \sum F_x = 0, \quad \sum F_z = 0
        $
    - 力矩平衡：
        $
        \sum M = 0
        $

    b. **切应力计算**：
    - 法向力 $F_N$
    - 剪力 $F_Q$
    - 弯矩 $M$

    c. **在位置 $x$ 处切割梁并标注切应力**:
    - **法向力 $F_N(x)$**
    - **剪力 $F_Q(x)$**
    - **弯矩 $M_B(x)$**

4. **对任一切割后的子系统（正切面或负切面）建立平衡条件**:

    | 切应力   | 正切面平衡条件                        | 负切面平衡条件                        |
    |----------|---------------------------------------|---------------------------------------|
    | **法向力 $F_N$** | $\Sigma F_{ix} + F_N(x) = 0$       | $\Sigma F_{ix} - F_N(x) = 0$       |
    | **剪力 $F_Q$**   | $\Sigma F_{iz} + F_Q(x) = 0$       | $\Sigma F_{iz} - F_Q(x) = 0$       |
    | **弯矩 $M_B$**   | $\Sigma M_{i[\approx]} + M_B(x) = 0$ | $\Sigma M_{i[\approx]} - M_B(x) = 0$ |

    - **正切面**：切应力指向坐标轴正方向。
    - **负切面**：切应力指向坐标轴负方向。
    - 通过这些平衡条件，可以求解任意位置 $x$ 的切应力。

    ![5.4-4](./subjects/Statik/modul-013/imgs/5.4-4.png)

5. **切应力的图示**:
    通过计算和分析，可以绘制法向力 $F_N(x)$、剪力 $F_Q(x)$、弯矩 $M_B(x)$ 在梁长度上的分布曲线。
   - **法向力 $F_N$**：通常在分布载荷作用下为线性分布。
   - **剪力 $F_Q$**：常表现为分段线性变化，在集中载荷处可能有突变。
   - **弯矩 $M_B$**：通常为二次曲线分布，最大弯矩通常出现在剪力为零的位置。

    ![5.4-5](./subjects/Statik/modul-013/imgs/5.4-5.png)

---

### 注意事项

1. $F_N(x), F_Q(x), M_B(x)$ 是 $x$ 的函数，其具体分布依赖于外部载荷和支座条件。
2. **不连续点**（如集中力或分布载荷的边界）需要逐段分析。
3. 切应力的分布是结构分析的重要部分，直接影响梁的设计与安全性评估。

**总结**: 通过在任意位置 $x$ 切割梁并分析平衡条件，可以确定切应力（法向力、剪力和弯矩）在梁长度上的分布。这种方法适用于复杂受力的梁，特别是分布载荷或多种外力作用下的梁结构分析。

---

## 5.4.1 单区间问题

### 描述

在单区间问题中，梁的几何形状和受力沿整个区间保持不变。这种情况简化了对切应力分布的分析，因为整个梁可以用一个数学函数描述切应力分布。

### 可能的几何变化

- **折点（Knick）**：梁在某处发生折线变化。
- **弧线起始（Beginn eines Bogens）**：梁形状开始呈现曲线。

### 可能的载荷变化

- **力的作用点改变（Kraftangriffspunkt）**
- **弯矩的作用点改变（Momentangriffspunkt）**
- **分布载荷的开始或结束（Beginn oder Ende einer Streckenlast）**
- **支座位置改变（Lagerstelle）**

### 特点

对于单区间问题，不论切割位置如何，切割后的图示始终一致。这表明整个梁可以用一个数学函数统一描述切应力分布（法向力、剪力、弯矩）。

### 示例

**固定端梁，长度 $l = 1m$，集中力 $F = 100N$**

![5.4.1-1](./subjects/Statik/modul-013/imgs/5.4.1-1.png)

#### 1) 定义坐标系

- **x-轴**：沿梁的长度方向。
- **z-轴**：垂直向下。

#### 2) 分析支座反力

通过释放支座并应用平衡条件，计算支座反力和支座弯矩。

- 支座反力：
  - 垂直方向力 $F_{Az}$
  - 水平方向力 $F_{Ax}$（通常为 0）
- 支座弯矩：
  - 固定端的弯矩 $M_A$

![5.4.1-2](./subjects/Statik/modul-013/imgs/5.4.1-2.png)

![b3-1](./subjects/Statik/modul-013/imgs/b3-1.png)

### 3) 在位置 $x$ 处切割梁并标注切应力

![5.4.1-3](./subjects/Statik/modul-013/imgs/5.4.1-3.png)

#### 切应力

- **法向力 $F_N$**：沿 $x$-轴方向，表示轴向作用的力。
- **剪力 $F_Q$**：沿 $z$-轴方向，表示垂直作用的剪切力。
- **弯矩 $M_B$**：在切口处产生的弯曲作用。

### 4) 对切割的子系统建立平衡条件

对于任意切割位置 $x$ 的正切面，列出平衡条件：

1. **法向力平衡**：
   $$ \Sigma F_{ix} + F_N = 0 \quad \Rightarrow \quad F_N = F_{Ax} = 0 $$

2. **剪力平衡**：
   $$ \Sigma F_{iz} + F_Q = 0 \quad \Rightarrow \quad F_Q = F_{Az} = 100 \text{N} $$

3. **弯矩平衡**：
   $$ \Sigma M_{i[\approx]} + M_B = 0 $$
   $$ \Rightarrow \quad M_B(x) = M_A + F_{Az} \cdot x = -100 \text{Nm} + 100 \text{N} \cdot x $$

4. **弯矩计算**
    - 弯矩 $M_B(x)$ 是 $x$ 的线性函数：
    $
    M_B(x) = -100 \text{Nm} + 100 \text{N} \cdot x
    $
    - 在 $x = 0$ 时：
    $
    M_B(0) = -100 \text{Nm}
    $
    - 在 $x = l$ 时：
    $
    M_B(l) = 0 \text{Nm}
    $

### 5. 切应力的图示

#### 分布图

![5.4.1-4](./subjects/Statik/modul-013/imgs/5.4.1-4.png)

1. **法向力 $F_N$**：
   - 恒为零，因为梁无轴向作用力。

2. **剪力 $F_Q$**：
   - 恒为 $+100 \text{N}$，与集中力 $F$ 的作用一致。

3. **弯矩 $M_B$**：
   - 起始点 $M_B(0) = -100 \text{Nm}$，
   - 终点 $M_B(l) = 0 \text{Nm}$，
   - 分布为线性增加。

![b3-2](./subjects/Statik/modul-013/imgs/b3-2.png)

#### 图示说明

- 法向力的分布为零。
- 剪力的分布为常值 $+100 \text{N}$。
- 弯矩分布从 $-100 \text{Nm}$ 线性变化到 $0 \text{Nm}$。

**总结**: 对于固定端梁：

1. **法向力 $F_N$** 为零。
2. **剪力 $F_Q$** 在梁上保持恒定。
3. **弯矩 $M_B$** 呈线性分布，从固定端的最大值逐渐减小到零。

这种分析方式适用于所有单区间问题，能够快速得到切应力分布的数学表达和图示结果。