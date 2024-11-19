#

## 4.7.6 里特切割方法 (Ritter’sches Schnittverfahren)

**里特切割方法**是一种用于**计算桁架结构中特定杆件力**的分析方法，通常在需要计算个别杆件内力而不是整个结构的所有内力时使用。该方法通过对桁架的特定位置进行切割，然后利用平衡方程求解内部力，具有简化计算的效果。

一句话概括就是：里特切割方法主要应用于**仅需确定单个杆件力**的场合。

### 步骤

1. 定义坐标系
2. 确定支座反作用力
3. 通过目标杆件切割桁架，将其分解为两个子桁架
4. 将杆件力作为拉力标注
5. 针对一个子系统列出并求解平衡条件

### 边界条件

- 最多只能切割3根杆件
- 被切割的杆件不能都在同一个点相交

### 里特切割方法的应用条件

- 适用于简单桁架的分析，尤其是当只需要计算少数杆件的内力时。
- 避免了整个结构的力分析，因此在只需计算部分杆件力的情况下更加高效。

### 优点

- **简化计算**：只需分析桁架的一部分，减少了计算的复杂性。
- **快速求解**：通过切割和使用平衡方程可以快速得到目标杆件的内力。

### 示例

- 桁架：$\( a = 1.0 \, \text{m}, F = 100 \, \text{N} \)$
- 目标：仅需确定三个高亮杆件的力

![4.7.6-b3](./subjects/Statik/modul-012/imgs/4.7.6-b3.png)
![4.7.6-b3-L1](./subjects/Statik/modul-012/imgs/4.7.6-b3-L1.png)
![4.7.6-b3-L2](./subjects/Statik/modul-012/imgs/4.7.6-b3-L2.png)
![4.7.6-b3-1](./subjects/Statik/modul-012/imgs/4.7.6-b3-1.png)

### Beispielfachwerke

![4.7.6-1](./subjects/Statik/modul-012/imgs/4.7.6-1.jpg)
![4.7.6-2](./subjects/Statik/modul-012/imgs/4.7.6-2.jpg)

---

## 5 内力和弯矩

对于机械系统，支座反作用力和多段系统的铰接力可通过分析得到。而结构设计和构件计算则需要内力和弯矩的信息。

### 重点

- 内力和弯矩也称为“切应力”
- 它们表示一个物体的受力情况，是计算和设计的重要依据
- 使用切割原理可以显现这些切应力

![5.0-1](./subjects/Statik/modul-012/imgs/5.0-1.png)

---

## 5.1 切面和切应力

### 切面上产生的力

![5.1-1](./subjects/Statik/modul-012/imgs/5.1-1.png)

- **杆件**：法向力 $\( F_N \)$
- **平面梁**：
  - **法向力** $\( F_N \)$
  - **剪力** $\( F_Q \)$
  - **弯矩** $\( M_b \)$

![5.1-2](./subjects/Statik/modul-012/imgs/5.1-2.png)

### 梁的约定

- **切割垂直于梁轴进行**
- 坐标轴定义：
  - **x-轴**：沿梁轴方向
  - **y-轴**：垂直于图形平面
  - **z-轴**：向下
- **虚线用于标注梁上z方向的正方向**
- **所有力的作用线位于荷载平面（x-z平面）**
- **正切面**：切应力指向坐标轴的正方向
- **负切面**：切应力指向坐标轴的负方向（由于作用力-反作用力公理）
- **切应力始终成对出现**，即在两个切面上遵循“作用=反作用”原理。

在梁的切割位置上，我们考虑三个主要切应力类型：

1. **法向力 $\( F_N \)$**：沿梁轴方向的力，通常影响拉伸或压缩状态。
2. **剪力 $\( F_Q \)$**：垂直于梁轴的力，影响剪切变形。
3. **弯矩 $\( M_b \)$**：引起梁的弯曲变形。

---

## 5.2 在某位置确定切应力

对于部件的强度设计，通常关注的是**最大应力的位置**，而非整个梁长度上的应力分布。如果最大应力的位置确定，就可以在该位置切割梁，并通过分析该部分的平衡条件计算切应力。

### 示例 5.2

梁长度 $\( l = 1 \, \text{m} \)$，支撑点为 $\( A \)$ 和 $\( B \)$，受集中力 $\( F = 100 \, \text{N} \)$ 作用，作用角度 $\( \alpha = 30^\circ \)$，力施加点 $\( C \)$ 离支撑点 $\( A \)$ 的距离 $\( a = 0.3 \, \text{m} \)$。

![5.2-1](./subjects/Statik/modul-012/imgs/5.2-1.png)

1. **定性确定切应力的最大值**（基于经验和分析）
2. **计算支座反力**
3. **在最大弯矩处切割**
4. **建立子系统的平衡方程并求解**

#### 1) 定性切应力分布

- **法向力**
  - 在 $\( A \)$ 和 $\( C \)$ 之间保持常数 $\( F \cdot \cos \alpha \)$
  - 在 $\( C \)$ 和 $\( B \)$ 之间为 0

- **剪力**
  - 在 $\( C \)$ 处发生突变，之后保持恒定

- **弯矩**
  - 在 $\( A \)$ 和 $\( B \)$ 处为 0，从 $\( A \)$ 到 $\( C \)$ 线性增加，从 $\( C \)$ 到 $\( B \)$ 线性减少，**最大值在 $\( C \)$**

![5.2-2](./subjects/Statik/modul-012/imgs/5.2-2.png)

#### 2) 计算支座反力

通过受力分析计算支座反力 $\( F_{Ax} \)$、$\( F_{Az} \)$、$\( F_{Bz} \)$ 的值。

![5.2-3](./subjects/Statik/modul-012/imgs/5.2-3.png)
![5.2-3-1](./subjects/Statik/modul-012/imgs/5.2-3-1.png)

#### 3) 切割在最大弯矩处

选择正、负切面，并对切割后的两部分施加力 $\( F \)$。

- 正切面：$\( x \)$-轴指向切面外
- 负切面：$\( x \)$-轴指向切面内

![5.2-4](./subjects/Statik/modul-012/imgs/5.2-4.png)

#### 4) 子系统的平衡方程

1. **在 x 方向的力平衡：确定法向力 $\( F_N \)$**
   - 正切面：$\( \Sigma F_{ix} + F_N = 0 \)$
   - 负切面：$\( F_N = F \cdot \cos \alpha \)$

2. **在 z 方向的力平衡：确定剪力 $\( F_Q \)$**
   - 正切面：$\( \Sigma F_{iz} + F_Q = 0 \)$
   - 负切面：$\( F_Q = F \cdot \sin \alpha - F_{Bz} \)$

3. **关于切点的力矩平衡：确定弯矩 $\( M_b \)$**
   - 正切面：$\( \Sigma M_i + M_b = 0 \)$
   - 负切面：$\( M_b = F_{Bz} \cdot (l - a) - M_b \)$

#### 5) 结论

正切面与负切面给出的结果相同
因此，**只需建立并分析一个子系统**即可。