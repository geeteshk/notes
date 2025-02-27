...menustart

 - [Week2 数理逻辑： 命题逻辑 及 形式系统](#92addd098ba33932426d801ce050c08e)
     - [13 重言式](#1cf2129c7c1194339ed019de4a39ecab)
         - [命题公式分类](#4f39e3ca02c935e20b8b63bc55da839c)
         - [重言式的例子和证明](#16e3c02584fe33b286af1332db249bf4)
     - [14 逻辑等价式和逻辑蕴涵式](#6133459f591484c515d74380526d0b37)
         - [逻辑等价式(logical equivalent)](#ddf9a6bc893ec966413f3a6c79a55439)
         - [一些重要的逻辑等价式（A,B,C是任意公式）](#73c6827ea01576267649339677e041db)
         - [逻辑蕴涵式(logical implication)](#bbb23c4238cecbdbafda8cb84bff5275)
         - [一些重要的逻辑蕴涵式（A,B,C是任意公式）](#ef62c2ee0760084d530f77017d0abe9c)
         - [逻辑结果](#4aaa3e72dc72f72325ad05b0ad1fe68f)
         - [逻辑等价式和逻辑蕴涵式的几个重要性质](#14bc3a7d56e4daf452c47fe43536c196)
     - [15 代入原理和替换原理](#56c7424fc0fc52f07c10119464c5b017)
         - [重言式的代入原理(rule of substitution)](#99d0502630685e6c2061c9a3213becfb)
         - [命题公式的替换原理(rule of replacement)](#e0e12fa1c285516de5ccb7088b6bd19a)
         - [代入原理RS与替换原理RR的区别](#c0db4f97ce3587162e0894a02ac745d3)
     - [16 证明逻辑等价式和逻辑蕴涵式](#6011365b0be8ebf41c9ec8424a7ac6a0)
         - [Example : 讨论赋值法证明逻辑等价式：(A∨B)→C╞╡(A→C)∧(B→C)](#7e1c75481dcf092f6d461dfeae1d31a4)
         - [推演法证明逻辑等价式：(A∨B)→C╞╡(A→C)∧(B→C)](#6dba98e3a74769e7cc6b60d022b2f3b1)
         - [推演法证明逻辑蕴涵式：A∧B╞¬A→(C→B)](#e039e860c693f0993f7cf7bec929ed68)
     - [17 范式及基本术语](#e70e9141edb1edb8c6d0a9df975a85fd)
         - [概念及基本术语](#91d3fbc59a5a6d4923b6247d9bc3f9a7)
             - [析取范式(disjunctive normal form)](#c8f5e7ae4a260f7308e6cc7e328b60c5)
             - [合取范式(conjunctive normal form)](#a67f5c2667ba300d9ebe7a684e5578b8)
     - [18 求范式的一般步骤](#62daf70f1488509a484ffe81a07d998a)
         - [范式用于重言式和矛盾式的识别](#180464532ab724ad5bc5d3bf7ed40023)
         - [求析取范式或合取范式的一般步骤](#ddb1f8942817927c8a96097b61f9b4e6)
         - [范式的唯一性问题](#99a2001daad46da16ada190616cb340c)
     - [19 主范式](#4ad2e462d732bba7ab0b1d9c703eea7c)
         - [主范式的定义](#533fba237096b5570290cec9cd4be913)
         - [主范式的存在及唯一性？](#14b7452137673cd9b399d581de3c088d)
         - [命题公式A(p1, p2, …pn)的等值分类](#04394df12572419ad65a8946bc098a7f)
         - [主合取范式：具有和主析取范式对称的性质](#ae1d46e8334ce6c90deca67ec55c7a31)
     - [20-联结词集完备性](#d58084f9d55f53fe8ecf655f5390e015)
     - [21-形式系统和证明、演绎](#a722e16a5ab466add63d9e95baff6f6c)
     - [22-命题演算形式系统PC ( Proposition Calculus )](#30fb41d7af930c05d8fd6bbd4c6b41d0)

...menuend


<h2 id="92addd098ba33932426d801ce050c08e"></h2>

-----
-----

# Week2 数理逻辑： 命题逻辑 及 形式系统

<h2 id="1cf2129c7c1194339ed019de4a39ecab"></h2>

-----

## 13 重言式

<h2 id="4f39e3ca02c935e20b8b63bc55da839c"></h2>

-----

### 命题公式分类

 - 命题公式的数量是无穷的，但是 可以从真值的 角度进行分类
 - **重言式**：（永真式）tautology
    - 命题变元的所有赋值都是命题公式的成真赋值
 - **矛盾式**（永假式、不可满足式） contradiction
    - 命题变元的所有赋值都是命题公式的成假赋值
 - **可满足式** (contingency)
    - 命题公式至少有一个成真赋值

--- 

 - 需要分清的概念
    - 永真式**都是**可满足式
    - 矛盾式**都不是**可满足式
    - 非永真式**并不都是**永假式
    - 如果A是永真式，则¬A就是永假式，
        - 反之亦然

<h2 id="16e3c02584fe33b286af1332db249bf4"></h2>

-----

### 重言式的例子和证明

 - 对于**任何公式A**
 - A∨¬A 是重言式（排中律）
    - A → A 也是重言式 
 - A∧¬A 是矛盾式（矛盾律）
 - 采用命题公式的**真值表证明**重言式
    - 证明 (p∨q)∧¬p→q 是重言式
    - ![](../imgs/DM_example_proof_tautology.png)

---

<h2 id="6133459f591484c515d74380526d0b37"></h2>

-----

## 14 逻辑等价式和逻辑蕴涵式

<h2 id="ddf9a6bc893ec966413f3a6c79a55439"></h2>

-----

### 逻辑等价式(logical equivalent)

 - 当命题公式**A↔B** 是**重言式**时，则称A 逻辑等价于B，记作**A╞╡B** ，称作**逻辑等价式**
    - 也可以理解为公式A和公式B **等值**
 - 逻辑等价体现了两个公式之间的一种 **关系**：在任何赋值状况下它们都等值
    - 任何赋值，如果使得 A 成真，那么B 也必然真； 如果使得A 为假，那么B也必然假。
 - eg. 如果A,B 都是永真式, 那么A,B 逻辑等价

<h2 id="73c6827ea01576267649339677e041db"></h2>

-----

### 一些重要的逻辑等价式（A,B,C是任意公式）

 1. ¬¬A╞╡A（双重否定律）
 2. A∨A╞╡A，A∧A╞╡A（幂等律）
    - v, ∧ 无论作用于自身多少次，都等价于 自身
 3. A∨B╞╡B∨A， A∧B╞╡B∧A（交换律）
 4. (A∨B)∨C╞╡A∨(B∨C)，(A∧B)∧C╞╡A∧(B∧C)（结合律）
 5. A∧(B∨C)╞╡(A∧B)∨(A∧C)，A∨(B∧C)╞╡(A∨B)∧(A∨C)（分配律）
 6. ¬(A∨B)╞╡¬A∧¬B， ¬(A∧B)╞╡¬A∨¬B（德摩根律）
 7. A∨(A∧B)╞╡A， A∧(A∨B)╞╡A（吸收律）
    - v, ∧ 各作用一次到A， 结果和B没有关系
 8. A→B╞╡¬A∨B（蕴涵等值式）
 9. A↔B╞╡(A→B)∧(B→A)（等价等值式）
 10. A∨t╞╡t，A∧f╞╡f（零律）
    - A 被吸收
 11. A∨f╞╡A，A∧t╞╡A（同一律）
 12. A∨¬A╞╡t， A∧¬A╞╡f（排中律和矛盾律）
 13. ¬t╞╡f，¬f╞╡t
 14. A∧B→C╞╡A→(B→C) ╞╡B→(A→C)
    - A∧B→C╞╡ ¬(A∧B)∨C ╞╡ (¬A∨¬B)vC ╞╡ ¬A∨(¬BvC) ╞╡ A→(¬BvC) ╞╡ A→(B→C) 
 15. A→B╞╡¬B→¬A（假言易位）
    - 逆否命题
 16. (A→B)∧(A→¬B)╞╡¬A（归谬论）
    - A本身 是有问题的，自相矛盾，因为它推出了B ，又推出了¬B , 那么A肯定是不成立的, 所以等价于 ¬A
 17. A↔B╞╡(A∧B)∨(¬A∧¬B)（等价等值式2）
    - 等值， A和B 同时成立，或 同时不成立


<h2 id="bbb23c4238cecbdbafda8cb84bff5275"></h2>

-----

### 逻辑蕴涵式(logical implication)

 - 当命题公式A→B是**重言式**时，则称A逻辑蕴涵B，记作**A╞B** ，称作逻辑蕴涵式 
    - 也可以理解为公式A的所有成真赋值都是公式B的成真赋值
 - 每个逻辑等价式可以看作两个逻辑蕴涵式， 也就是说A╞╡B 也有 A╞B,B╞A
    - A和B等值，所以A→B和B→A都是重言式
 - 逻辑蕴涵体现了两个公式AB之间的另一种 **关系**: 在任何赋值状况下只要A真，B都真
 - eg. 如果A,B都为 矛盾式， 那么 A逻辑蕴涵 B 
    - 逻辑蕴涵式只关心 A成立的情况，A不成立的情况，肯定逻辑蕴涵

<h2 id="ef62c2ee0760084d530f77017d0abe9c"></h2>

-----

### 一些重要的逻辑蕴涵式（A,B,C是任意公式）

 1. A ╞ A∨B
    - 只要A 为真，A∨ 任何东西都为真
 2. A∧B ╞ A , A∧B ╞ B
 3. A∧(A→B) ╞ B (分离规则)
    - A 成立，同时 A→B 也成立, 则B成立
 4. (A→B)∧¬B ╞ ¬A
    - A推出B, 但是 B不成立, 则A不成立 
 5. ¬A∧(A∨B) ╞ B
    - 如果A∨B 成立，同时A不成立，则 B成立
 6. (A→B)∧(B→C)╞ A→C   (蕴涵可传递性) 
 7. (A→B)∧(C→D)╞ (A∧C)→(B∧D)
    - 把前件归在一起，把后件归在一起
 8. (A↔B)∧(B↔C) ╞ A↔C


<h2 id="4aaa3e72dc72f72325ad05b0ad1fe68f"></h2>

-----

### 逻辑结果

 - 逻辑蕴涵经常会被推广为 **Γ╞ B** 的形式  ( Γ gamma)
    - 其中Γ是一系列公式，表示B是Γ的 **逻辑结果**
    - 即：使Γ中**每一个公式**成真的赋值，都是公式B的成真赋值 
    - 即Γ中的 **所有公式的合取** 逻辑蕴涵B
 - 当Γ中仅包含一个公式A时，就是A╞B ；
 - 如果Γ中不包含任何公式，记做╞B，表示 “B永真”
    
<h2 id="14bc3a7d56e4daf452c47fe43536c196"></h2>

-----

### 逻辑等价式和逻辑蕴涵式的几个重要性质

 - 命题公式关系的自反、对称、传递等性质
 - A╞╡B 当且仅当 ╞ A↔B  (逻辑等价的定义)
 - A╞B 当且仅当 ╞A→B  (定义)
 - 若A╞╡B，则B╞╡A   (对称性)
 - 若A╞╡B， B╞╡C，则A╞╡C  (传递性)
 - 若A╞B，则¬B╞¬A   (类似 假言易位)
 - 若A╞B， B╞C，则A╞C
 - 若A╞B，A╞╡A’，B╞╡B’，则A’╞B’  (可替换性)

---

<h2 id="56c7424fc0fc52f07c10119464c5b017"></h2>

-----

## 15 代入原理和替换原理

<h2 id="99d0502630685e6c2061c9a3213becfb"></h2>

-----

### 重言式的代入原理(rule of substitution)

 - 将**重言式A**中的某个**命题变元**p的**所有出现**都代换为**命题公式B**，
 - 得到的命题公式记作A(B/p)，A(B/p) 也是**重言式**。
 - 因为重言式A的真值与p的取值状况 无关，恒为t，
 - 所以将p全部代换后的公式A(B/p)的 真值也恒为t
 - 注意：
    - 仅**代换部分出现**本原理不成立
    - 如果B中包含了p或者A中的其它变元, 本原理依然成立

<h2 id="e0e12fa1c285516de5ccb7088b6bd19a"></h2>

-----

### 命题公式的替换原理(rule of replacement)

 - 将**命题公式A**中的**子公式C**的部分出现替换为和C逻辑等价的 **公式D** （C╞╡D ），
 - 得到的命题公式记作B，则 **A╞╡B** 。
 - 因为C和D（在任何赋值下）等值， 所以用D替换C不会改变A的真值
 - 注意：
    - 不要求全部出现都替换

<h2 id="c0db4f97ce3587162e0894a02ac745d3"></h2>

-----

### 代入原理RS与替换原理RR的区别

 · | 代入原理RS | 替换原理RR 
 --- | --- | --- 
 使用对象 | 任意永真式 |  任意命题公式
 代换对象 | 任意命题变元 | 任意子公式
 代换物 | 任意命题公式 | 任意与代换对象等价的命题公式
 代换方式 | 代换同一命题变元的所有出现 | 代换子公式的某些出现
 代换结果 | 仍为永真式 |  与原公式等价 

--- 

<h2 id="6011365b0be8ebf41c9ec8424a7ac6a0"></h2>

-----

## 16 证明逻辑等价式和逻辑蕴涵式

 - **真值表法**：要证明A╞╡B，A╞B，只要：
    - 分别列出A↔B和A→B的真值表，最后一列全为真即可。
    - 公式一复杂，真值表会非常庞大
 - **对赋值进行讨论**：要证明A╞B，只要证明：
    - A的任意一个成真赋值都是B的成真赋值，或者
    - B的任意一个成假赋值都是A的成假赋值。
        - 并不是说对每一个赋值进行讨论，对赋值的各种状况进行一个分类，并每一类进行导论。
        - 如果每一类都符合我们的要求的话， 那么也就完成了证明
    - -> 如果证明了A╞B和B╞A，那么就证明了A╞╡B。
 - **推演法**：利用已知的重言式、逻辑等价式和逻辑蕴涵式，采用**代入原理**和**替换原理**进行推演。

<h2 id="7e1c75481dcf092f6d461dfeae1d31a4"></h2>

-----

### Example : 讨论赋值法证明逻辑等价式：(A∨B)→C╞╡(A→C)∧(B→C)

 - 先证明(A∨B)→C╞(A→C)∧(B→C) 
 - 假设α是(A∨B)→C任意一个**成真赋值**，这样会有两种情况：
    - α(A∨B)=f：于是α(A)=α(B)=f，就有α(A→C)=α(B→C)=t 〉 或者，
    - α(A∨B)=t，α(C)=t：于是α(A→C)=α(B→C)=t
 - 上述两种情况都得到α((A→C)∧(B→C))=t，得证。
 - 讨论赋值法证明逻辑等价式：(A∨B)→C╞╡(A→C)∧(B→C)
    - 我们发现反过来的证明是比较困难的, 所以我们 也反过来进行假设
    - 反过来，假设α是(A∨B)→C任意一个**成假赋值**，这样只有一种情况：
        - α(A∨B)=t，α(C)=f 
    - 当α(A)=t，α(C)=f时，α(A→C)=f；
    - 当α(B)=t，α(C)=f时，α(B→C)=f，
    - 不管如何，都有α((A→C)∧(B→C))=f 
    - 得证

---

<h2 id="6dba98e3a74769e7cc6b60d022b2f3b1"></h2>

-----

### 推演法证明逻辑等价式：(A∨B)→C╞╡(A→C)∧(B→C)

 - (A∨B)→C
 - ╞╡¬(A∨B)∨C（蕴涵等值式，代入原理）
 - ╞╡(¬A∧¬B)∨C（德摩根律，替换原理）
 - ╞╡(¬A∨C)∧(¬B∨C)（分配律，代入）
 - ╞╡(A→C)∧(¬B∨C)（蕴涵等值式，替换）
 - ╞╡(A→C)∧(B→C)（蕴涵等值式，替换）


<h2 id="e039e860c693f0993f7cf7bec929ed68"></h2>

-----

### 推演法证明逻辑蕴涵式：A∧B╞¬A→(C→B)  

 - A∧B
 - ╞B（I2：A∧B╞A）
 - ╞¬C∨B（I1：A╞A∨B，代入）
 - ╞C→B（蕴涵等值式，代入）
 - ╞A∨(C→B)（I1：A╞A∨B，代入）
 - ╞¬A→(C→B)（蕴涵等值式，代入）
 

---

<h2 id="e70e9141edb1edb8c6d0a9df975a85fd"></h2>

-----

## 17 范式及基本术语

<h2 id="91d3fbc59a5a6d4923b6247d9bc3f9a7"></h2>

-----

### 概念及基本术语

 - 每个命题公式都会存在**很多**与之逻辑等价的公式
 - **范式**：在命题公式的多个逻辑等价的 形式中，较为符合“标准”或“规范” 的一种形式
 - **文字**(literals)：命题常元、变元和它们的否定
    - 前者称**正**文字，后者称**负**文字，
    - 如：p, ¬q, t
 - **析取子句**(disjunctive clauses)：文字或者若干文字的析取， 
    - 如：p, p∨q, ¬p∨q
 - **合取子句**(conjunctive clauses)：文字或者若干文字的合取， 
    - 如：p, p∧q, ¬p∧q
 - **互补文字对**(complemental pairs of literals)：指一对正文字和 负文字，
    - 如：p和¬p

<h2 id="c8f5e7ae4a260f7308e6cc7e328b60c5"></h2>

-----

#### 析取范式(disjunctive normal form)

 - 公式A’称作公式A的**析取范式**，如果：
    1. A’╞╡A
    2. A’为合取子句或者若干合取子句 的析取
 - eg.
    - p→q的析取范式为¬p∨q（合取子句¬p 和q的析取）
    - ((p→q)∧¬p)∨¬q的析取范式为 ¬p∨(q∧¬ p)∨¬q
 
<h2 id="a67f5c2667ba300d9ebe7a684e5578b8"></h2>

-----

#### 合取范式(conjunctive normal form)

 - 公式A’称作公式A的**合取范式**，如果：
    1. A’╞╡A
    2. A’为析取子句或者若干析取子句 的合取
 - eg.
    - p→q的合取范式为¬p∨q（析取子句 ¬p∨q）
        - 和 析取范式 相同的形式
    - ((p→q)∧¬p)∨¬q的合取范式为 (¬p∨t)∧(¬p∨¬q)或¬p∨¬q

<h2 id="62daf70f1488509a484ffe81a07d998a"></h2>

-----

## 18 求范式的一般步骤

 - 利用**逻辑等价式**和**代入原理**、**替换原理**，可 以求出任一一个公式的析取范式和合取范式
 - eg. 求¬p→¬(p→q)的析取范式及合取范式
    - ¬p→¬(p→q)
    - ╞╡¬p→¬(¬p∨q) 
    - ╞╡p∨¬(¬p∨q)
    - ╞╡p∨(p∧¬q)（析取范式）
    - ╞╡(p∨p)∧(p∨¬q) 
    - ╞╡p∧(p∨¬q)（合取范式）
    - ╞╡p

<h2 id="180464532ab724ad5bc5d3bf7ed40023"></h2>

-----

### 范式用于重言式和矛盾式的识别

 - 重言式识别
 - 合取范式中每个析取子句都包含了至 少一个互补文字对：
    - (p∨¬p∨q)∧(p∨q∨¬q)
    - 如果一个命题公式，它的某一个合取范式的形式里面，有每一个的析取自居 都包含了至少一个 互补文字对的话，那么这个命题公式就是 重言式。
 - 矛盾式识别
 - 析取范式中每个合取子句都包含了至 少一个互补文字对：
    - (p∧¬p∧q)∨(p∧q∧¬q)

<h2 id="ddb1f8942817927c8a96097b61f9b4e6"></h2>

-----

### 求析取范式或合取范式的一般步骤

 - **消去公式中的联结词→和↔**
    - p→q化为¬p∨q（蕴涵等值式）
    - p↔q化为(¬p∨q)∧(p∨¬q)或者(p∧q)∨(¬p∧¬q)（等价等值式）
 - 利用德摩根律 **将否定联结词¬向内深入**，最后只作用于文字，再将 ¬¬p化为p 
 - **利用分配律**，最后得到需要的析取或者合取范式

<h2 id="99a2001daad46da16ada190616cb340c"></h2>

-----

### 范式的唯一性问题

 - 一个公式的析取范式或合取范式都 **不是唯一**的
    - p, p∨(p∧¬q), (p∧q)∨(p∧¬q)都是¬p→¬(p→q)的析取范式
    - p, p∧(p∨¬q), (p∨q)∧(p∨¬q)都是¬p→¬(p→q)的合取范式
 - 公式的析取范式有可能同时又是合取范式
    - ¬p∨q既是p→q的析取范式又是合取范式
 - 能否找到“最为规范”的范式？
    - 具备**唯一性**的范式

<h2 id="4ad2e462d732bba7ab0b1d9c703eea7c"></h2>

-----

## 19 主范式

 - 具有 唯一性的 范式的形式。
  
<h2 id="533fba237096b5570290cec9cd4be913"></h2>

-----

### 主范式的定义

 - 主析取范式(major disjunctive form)
    - 公式A'称作公式A(p1, p2, …pn)的主析取范式，如果：
        - A'是A的析取范式
        - A'中每一个合取子句里p1, p2, …pn均恰出现一次
            - 每一个合取子句 都要包含所有的命题变元，而且 只出现一次
 - 主合取范式(major conjunctive form)
    - 公式A'称作公式A(p1, p2, …pn)的主合取范式，如果：
        - A'是A的合取范式
        - A'中每一个析取子句里p1, p2, …pn均恰出现一次

<h2 id="14b7452137673cd9b399d581de3c088d"></h2>

-----

### 主范式的存在及唯一性？

 - 主析取范式存在唯一性证明：约定
    - 首先，合取子句中的文字按照其包含的变元下标从**小到大排列** 
    - 对于包含所有变元p1, p2, …pn的并排列好文字顺序的合取子句，我们称为**极小项**(min term)，记作**mᵢ**
        - 其中i是一个整数，i对应的n位二进制表示描述了对应下标的变元在合取子句中 的否定状态 
        - 例p1∧p2∧p3记作m₇（7=111）；p1∧¬p2∧¬p3记作m₄（4=100）
    - **主析取范式是极小项按照其下标从小到大排列的析取**
        - 顺序不影响证明
 - 主析取范式存在唯一性证明：极小项赋值引理
    - 极小项只有唯一的**成真**赋值，
    - 且成真赋值中每个变元的取值等于**极小项下标**的二进制形式中变元下标所 对应的二进制位的值： 
        - p1∧p2∧p3（m7）的唯一成真赋值 是p1=1, p2=1, p3 =1, 
        - p1∧¬p2∧¬p3（m4）的唯一成真 赋值是p1=1, p2=0, p3 =0
 - 主析取范式存在唯一性证明：主析取范式的成真赋值
    - 极小项和主析取范式的关系
        - 主析取范式包含的极小项的**成真赋值** 也是主析取范式的**成真赋值**
        - 主析取范式的任一一个成真赋值是其 **包含**的某个极小项的成真赋值 
        - 主析取范式**不包含**的极小项的成真赋值是主析取范式的**成假赋值**

--- 

 - 主析取范式存在唯一定理：存在性证明
    - **任何命题公式A(p1, p2, …pn)的主析取范式都是存在的，并且是唯一的**.
    - 假设A'是公式A(p1, p2, …pn)的析取范式
    - 如果A'中某个合取子句Ai既不包含pj，也不包含¬pj，那么我们将Ai展成如下 形式：
        - Ai╞╡Ai∧1╞╡Ai∧(pj∨¬pj)╞╡(Ai∧pj) ∨(Ai∧¬pj)
        - 这样就有 pj 了
    - 将合取子句中重复出现的命题变元，矛盾式消去，将重复出现的合取子句消去
        - p∧p╞╡p； p∧¬p╞╡0； Ai∨Ai╞╡ Ai
    - 最后将所有的合取子句**整理变元顺序**，成为**极小项**，并得到**主析取范式A'**

 - 主析取范式存在唯一定理：唯一性证明
    - 反证法：假设公式A(p1, p2, …pn)存在两个不同的主析取范式B和C
    - 由于A╞╡B且A╞╡C，所以B╞╡C
    - 因为B和C是两个不同的主析取范式，那么一定存在某个极小项**mᵢ**只出现在B或 者只出现在C中，不妨设**mᵢ**只出现在B中，不出现在C中，这样：
        - **mᵢ**的成真赋值是B的**成真**赋值，却是C的**成假**赋值
    - **与B╞╡C矛盾**
    - 所以B和C必然相同，也就是说公式A(p1, p2, …pn)的主析取范式是**唯一**的
    - 存在性证明还给出了主析取范式的构造步骤。

<h2 id="04394df12572419ad65a8946bc098a7f"></h2>

-----

### 命题公式A(p1, p2, …pn)的等值分类

 - 具有相同主析取范式的公式都是**等值**的，属于同一个等值类，否则 属于不同的等值类
 - 虽然公式的数量无限多，但**等值类的数量**是**有限**的：
    - 极小项的数量为 N=2ⁿ ；
    - 由极小项组合成的主析取范式的数量为2ᴺ；
        - C(N,0) + C(N,1) + C(N,2) + ... + C(N,N) = 2ᴺ 
    - 等值类的数量等于主析取范式的数量
 - 虽然包含n个变元的 命题公式数量是 无穷的，但主析取范式的数量确是有限的

<h2 id="ae1d46e8334ce6c90deca67ec55c7a31"></h2>

-----

### 主合取范式：具有和主析取范式对称的性质

 - **极大项**和**成假赋值**
 - 主合取范式的**存在性**和**唯一性**
 - 主合取范式的**构造步骤**
 - 命题公式A(p1, p2, …pn)的**等值分类**

---

<h2 id="d58084f9d55f53fe8ecf655f5390e015"></h2>

-----

## 20-联结词集完备性
 - TODO 

 - 为什么 ∧ , ∨ , ￢ 三个连接词就足以代表所有的命题公式了呢？

 - 如果任意一个真值函数都可以用仅包含某个联结词集中的联结词的 命题公式表示，则称这个联结词集为功能完备集
    - 目前使用的{¬,∧,∨,→,↔}是功能完备集
        - →,↔ 是冗余联结词
    - {¬,∧,∨}是功能完备集
    - {¬,→}是功能完备集
 - 如果一个功能完备集中不含冗余联结 词，则称这个功能完备集为极小的。
    - {¬,→}， {¬,∧}， {¬,∨}都是极小功 能完备集 
 - 仅包含单个联结词的功能完备集
    - 定义联结词↓（Peirce记号）
        - p↓q╞╡¬(p∨q)
    - {↓}是功能完备集

<h2 id="a722e16a5ab466add63d9e95baff6f6c"></h2>

-----

## 21-形式系统和证明、演绎

<h2 id="30fb41d7af930c05d8fd6bbd4c6b41d0"></h2>

-----

## 22-命题演算形式系统PC ( Proposition Calculus )







 
