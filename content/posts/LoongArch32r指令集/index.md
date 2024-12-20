---
title: LoongArch32r指令表
description: 自制版, 将指令格式与指令功能描述放在一起
date: 2024-12-01
lastmod: 2024-12-05T19:10:45+08:00
author: Vincent Ice
cover: cover.jpg
categories:
    - FPGA开发
tags: 
    - 手册
---

[原手册链接](https://www.loongson.cn/uploads/images/2023041918122813624.%E9%BE%99%E8%8A%AF%E6%9E%B6%E6%9E%8432%E4%BD%8D%E7%B2%BE%E7%AE%80%E7%89%88%E5%8F%82%E8%80%83%E6%89%8B%E5%86%8C_r1p03.pdf)
***有错误请及时联系我***

## 基础整数指令定义
### 算术运算类指令
#### ADD.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：**  add.w  rd, rj, rk

**功能描述：**  ADD.W 将通用寄存器 rj 中的数据加上通用寄存器 rk 中的数据，所得结果的[31:0]位写入通用寄存器 rd 中。

**操作定义：**

tmp = GR[rj] + GR[rk]

GR[rd] = tmp[31:0]

#### SUB.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：**  sub.w  rd, rj, rk

**功能描述：**  SUB.W 将通用寄存器 rj 中的数据减去通用寄存器 rk 中的数据，所得结果的[31:0]位写入通用寄存器 rd中。

**操作定义：**

tmp = GR[rj] - GR[rk]

GR[rd] = tmp[31:0]

#### ADDI.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1010</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>


**指令格式：**  addi.w  rd, rj, si12

**功能描述：**  ADDI.W 将通用寄存器 rj 中的数据加上 12 比特立即数 si12 **符号扩展**后的 32 位数据，所得结果写入通用寄存器 rd 中。

**操作定义：**

tmp = GR[rj] + SignExtend(si12, 32)

GR[rd] = tmp[31:0]

#### LUI12I.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">25</td>
<td style="width: 31.25%;  text-align: left;" colspan="5">24</td>
<td style="width: 31.25%;  text-align: right;" colspan="5">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">0001010</td>
<td style="text-align: center;" colspan="10">si20</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：**  lu12i.w  rd, si20

**功能描述：**  LU12I.W 将 20 比特立即数 si20 最低位连接上 12 比特 0 后写入通用寄存器 rd 中。

**操作定义：**

GR[rd] = {si20, 12'b0}

#### SLT

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00100</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>


**指令格式：**  slt  rd, rj, rk

**功能描述：**  SLT 将通用寄存器 rj 中的数据与通用寄存器 rk 中的数据视作**有符号整数**进行大小比较，如果前者小于后者，则将通用寄存器 rd 的值置为 1，否则置为 0。

**操作定义：**

GR[rd] = (signed(GR[rj]) < signed(GR[rk])) ? 1 : 0



#### SLTU

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** sltu  rd, rj, rk

**功能描述：** SLTU 将通用寄存器 rj 中的数据与通用寄存器 rk 中的数据视作**无符号整数**进行大小比较，如果前者小于后者，则将通用寄存器 rd 的值置为 1，否则置为 0 。

**操作定义：**

GR[rd] = (unsigned(GR[rj]) < unsigned(GR[rk])) ? 1 : 0




#### SLTI

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1000</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** slti  rd, rj, si12

**功能描述：** SLTI 将通用寄存器 rj 中的数据与 12 比特立即数 si12 **符号扩展**后所得的数据视作有符号整数进行大小比较，如果前者小于后者，则将通用寄存器 rd 的值置为 1，否则置为 0。

**操作定义：**

tmp = SignExtend(si12, 32)

GR[rd] = (signed(GR[rj]) < signed(tmp)) ? 1 : 0



#### SLTUI

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** sltui  rd, rj, si12

**功能描述：** SLTI 将通用寄存器 rj 中的数据与 12 比特立即数 si12 符号扩展后所得的数据视作无符号整数进行大小比较，如果前者小于后者，则将通用寄存器 rd 的值置为 1，否则置为 0。

**操作定义：**

tmp = SignExtend(si12, 32)

GR[rd] = (unsigned(GR[rj]) < unsigned(tmp)) ? 1 : 0



#### PCADDU12I

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">25</td>
<td style="width: 31.25%;  text-align: left;" colspan="5">24</td>
<td style="width: 31.25%;  text-align: right;" colspan="5">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">0001110</td>
<td style="text-align: center;" colspan="10">si20</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** pcaddu12i  rd, si20

**功能描述：** PCADDU12I 将 20 比特立即数 si20 最低位连接上 12 比特 0 之后**符号扩展**，所得数据加上该指令的 PC，相加结果写入通用寄存器 rd 中。

**操作定义：**

GR[rd] = PC + SignExtend({si20, 12'b0}, 32)



#### MUL.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** mul.w  rd, rj, rk

**功能描述：** MUL.W 将通用寄存器 rj 中的数据与通用寄存器 rk 中的数据进行相乘，乘积结果的[31:0]位数据写入通用寄存器 rd 中。

**操作定义：**

product = signed(GR[rj]) \* signed(GR[rk])

GR[rd] = product[31:0]



#### MULH.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** mulh.w  rd, rj, rk

**功能描述：** MULH.W将通用寄存器rj中的数据与通用寄存器rk中的数据视作**有符号数**进行相乘，乘积结果的[63:32]位数据写入通用寄存器 rd 中。

**操作定义：**

product = signed(GR[rj]) \* signed(GR[rk])

GR[rd] = product[63:32]



#### MULH.WU

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** mulh.wu  rd, rj, rk

**功能描述：** MULH.WU 将通用寄存器 rj 中的数据与通用寄存器 rk 中的数据视作**无符号数**进行相乘，乘积结果的[63:32]位数据符号扩展后写入通用寄存器 rd 中。

**操作定义：**

product = unsigned(GR[rj]) \* unsigned(GR[rk])

GR[rd] = product[63:32]



#### DIV.W，DIV.WU

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">DIV.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">DIV.WU</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>
**指令格式：** 

div.w   rd, rj, rk

div.wu  rd, rj, rk

**功能描述：** DIV.W 和 DIV.WU 将通用寄存器 rj 中的数据除以通用寄存器 rk 中的数据，所得的商写入通用寄存器rd 中。

**操作定义：**

**DIV.W:**

quotient = signed(GR[rj]) / signed(GR[rk])

GR[rd] = quotient[31:0]

**DIV.WU:**

quotient = unsigned(GR[rj]) / unsigned(GR[rk])

GR[rd] = quotient[31:0]



#### MOD.W，MOD.WU

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">MOD.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">MOD.WU</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00011</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>
**指令格式：** 

mod.w   rd, rj, rk

mod.wu  rd, rj, rk

**功能描述：** MOD.W 和 MOD.WU 将通用寄存器 rj 中的数据除以通用寄存器 rk 中的数据，所得的余数写入通用寄存器 rd 中。

**操作定义：**

**MOD.W:**

remainder = signed(GR[rj]) % signed(GR[rk])

GR[rd] = remainder[31:0]

**MOD.WU:**

remainder = unsigned(GR[rj]) % unsigned(GR[rk])

GR[rd] = remainder[31:0]



### 逻辑运算类指令
   #### AND

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>
**指令格式：** and  rd, rj, rk

**功能描述：** AND 将通用寄存器 rj 中的数据与通用寄存器 rk 中的数据进行按位逻辑与运算，结果写入通用寄存器rd 中。

**操作定义：**

GR[rd] = GR[rj] & GR[rk]



#### OR

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** or  rd, rj, rk

**功能描述：** OR 将通用寄存器 rj 中的数据与通用寄存器 rk 中的数据进行按位逻辑或运算，结果写入通用寄存器 rd中。

**操作定义：**

GR[rd] = GR[rj] | GR[rk]



#### NOR

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** nor  rd, rj, rk

**功能描述：** NOR 将通用寄存器 rj 中的数据与通用寄存器 rk 中的数据进行按位逻辑或非运算，结果写入通用寄存器rd 中。

**操作定义：**

GR[rd] = ~(GR[rj] | GR[rk])



#### XOR

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01011</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** xor  rd, rj, rk

**功能描述：** XOR 将通用寄存器 rj 中的数据与通用寄存器 rk 中的数据进行按位逻辑异或运算，结果写入通用寄存器rd 中。

**操作定义：**

GR[rd] = GR[rj] ^ GR[rk]



#### ANDI

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1101</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** andi  rd, rj, rk

**功能描述：** ANDI 将通用寄存器 rj 中的数据与 12 比特立即数**零扩展**之后的数据进行按位逻辑与运算，结果写入通用寄存器 rd 中。

**操作定义：**

GR[rd] = GR[rj] & ZeroExtend(ui12, 32)



#### ORI

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1110</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>


**指令格式：** ori  rd, rj, rk

**功能描述：** ORI 将通用寄存器 rj 中的数据与 12 比特立即数**零扩展**之后的数据进行按位逻辑或运算，结果写入通用寄存器 rd 中。

**操作定义：**

GR[rd] = GR[rj] | ZeroExtend(ui12, 32)



#### XORI

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1111</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** xori  rd, rj, rk

**功能描述：** XORI 将通用寄存器 rj 中的数据与 12 比特立即数**零扩展**之后的数据进行按位逻辑异或运算，结果写入通用寄存器 rd 中。

**操作定义：**

GR[rd] = GR[rj] ^ ZeroExtend(ui12, 32)


### 移位运算类指令
   #### SLL.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** sll.w  rd, rj, rk

**功能描述：** SLL.W 将通用寄存器 rj 中的数据**逻辑左移**，移位结果写入通用寄存器 rd 中。

**操作定义：**

tmp = SLL(GR[rj], GR\[rk][4:0])

GR[rd] = tmp[31:0]



#### SRL.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01111</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** srl.w  rd, rj, rk

**功能描述：** SRL.W 将通用寄存器 rj 中的数据**逻辑右移**，移位结果写入通用寄存器 rd中。

**操作定义：**

tmp = SRL(GR[rj], GR\[rk][4:0])

GR[rd] = tmp[31:0]



#### SRA.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** sra.w  rd, rj, rk

**功能描述：** SRA.W 将通用寄存器 rj 中的数据**算术右移**，移位结果写入通用寄存器 rd 中。

**操作定义：**

tmp = SRA(GR[rj], GR\[rk][4:0])

GR[rd] = tmp[31:0]



#### SLLI.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">ui5</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** slli.w  rd, rj, ui5

**功能描述：** SLLI.W 将通用寄存器 rj 中的数据**逻辑左移**，移位结果写入通用寄存器 rd 中。

**操作定义：**

tmp = SLL(GR[rj], ui5)

GR[rd] = tmp[31:0]



#### SRLI.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">ui5</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** srli.w  rd, rj, ui5

**功能描述：** SRLI.W 将通用寄存器 rj 中的数据**逻辑右移**，移位结果写入通用寄存器 rd 中。

**操作定义：**

tmp = SRL(GR[rj], ui5)

GR[rd] = tmp[31:0]



#### SRAI.W

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">ui5</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** srai.w  rd, rj, ui5

**功能描述：** SRAI.W 将通用寄存器 rj 中的数据**算术右移**，移位结果写入通用寄存器 rd 中。

**操作定义：**

tmp = SRA(GR[rj], ui5)

GR[rd] = tmp[31:0]



### 转移指令
   #### BEQ

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">010110</td>
<td style="text-align: center;" colspan="8">offs16</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** beq  rj, rd, offs16

**功能描述：** BEQ 将通用寄存器 rj 和通用寄存器 rd 的值进行比较，如果两者<u>相等则跳转</u>到目标地址，否则不跳转。

其跳转目标地址计算方式是将指令码中的16比特立即数offs16**逻辑左移**2位后再**符号扩展**，所得的偏移值加上该分支指令的PC。

**操作定义：**

if GR[rj] == GR[rd] :

​	PC = PC + SignExtend({offs16, 2'b0}, 32)



#### BNE

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">010111</td>
<td style="text-align: center;" colspan="8">offs16</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** bne  rj, rd, offs16

**功能描述：** BNE 将通用寄存器 rj 和通用寄存器 rd 的值进行比较，如果两者<u>不等则跳转</u>到目标地址，否则不跳转。

其跳转目标地址计算方式是将指令码中的16比特立即数offs16**逻辑左移**2位后再**符号扩展**，所得的偏移值加上该分支指令的PC。

**操作定义：**

if GR[rj] != GR[rd] :

​	PC = PC + SignExtend({offs16, 2'b0}, 32)



#### BLT

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">011000</td>
<td style="text-align: center;" colspan="8">offs16</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** blt  rj, rd, offs16

**功能描述：** BLT 将通用寄存器 rj 和通用寄存器 rd 的值视作**有符号数**进行比较，如果<u>前者小于后者则跳转</u>到目标地址，否则不跳转。

其跳转目标地址计算方式是将指令码中的16比特立即数offs16**逻辑左移**2位后再符号扩展，所得的偏移值加上该分支指令的PC。

**操作定义：**

if signed(GR[rj]) < signed(GR[rd]) :

​	PC = PC + SignExtend({offs16, 2'b0}, 32)



#### BGE

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">011001</td>
<td style="text-align: center;" colspan="8">offs16</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** bge  rj, rd, offs16

**功能描述：** BGE 将通用寄存器 rj 和通用寄存器 rd 的值视作**有符号数**进行比较，如果<u>前者大于等于后者则跳转</u>到目标地址，否则不跳转。

其跳转目标地址计算方式是将指令码中的16比特立即数offs16**逻辑左移**2位后再符号扩展，所得的偏移值加上该分支指令的PC。

**操作定义：**

if signed(GR[rj]) >= signed(GR[rd]) :

​	PC = PC + SignExtend({offs16, 2'b0}, 32)



#### BLTU

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">011010</td>
<td style="text-align: center;" colspan="8">offs16</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** bltu  rj, rd, offs16

**功能描述：** BLTU 将通用寄存器 rj 和通用寄存器 rd 的值视作**无符号数**进行比较，如果<u>前者小于后者则跳转</u>到目标地址，否则不跳转。

其跳转目标地址计算方式是将指令码中的16比特立即数offs16**逻辑左移**2位后再符号扩展，所得的偏移值加上该分支指令的PC。

**操作定义：**

if unsigned(GR[rj]) < unsigned(GR[rd]) :

​	PC = PC + SignExtend({offs16, 2'b0}, 32)



#### BGEU

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">011011</td>
<td style="text-align: center;" colspan="8">offs16</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** bgeu  rj, rd, offs16

**功能描述：** BGEU 将通用寄存器 rj 和通用寄存器 rd 的值视作**无符号数**进行比较，如果<u>前者大于等于后者则跳转</u>到目标地址，否则不跳转。

其跳转目标地址计算方式是将指令码中的16比特立即数offs16**逻辑左移**2位后再**符号扩展**，所得的偏移值加上该分支指令的PC。

**操作定义：**

if unsigned(GR[rj]) >= unsigned(GR[rd]) :

​	PC = PC + SignExtend({offs16, 2'b0}, 32)




#### B

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">010100</td>
<td style="text-align: center;" colspan="8">offs16</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** b  offs26

**功能描述：** B <u>无条件跳转</u>到目标地址处。

其跳转目标地址是将指令码中的 26 比特立即数 offs26 **逻辑左移** 2 位后再**符号扩展**，所得的偏移值加上该分支指令的 PC。

**操作定义：**

PC = PC + SignExtend({offs26, 2'b0}, 32)



#### BL

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">010101</td>
<td style="text-align: center;" colspan="8">offs16</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** bl  offs26

**功能描述：** BL <u>无条件跳转</u>到目标地址处，同时将该指令的 PC 值加 4 的结果写入到 1 号通用寄存器 r1 中。

其跳转目标地址是将指令码中的 26 比特立即数 offs26 **逻辑左移** 2 位后再符号扩展，所得的偏移值加上该分支指令的 PC。

**操作定义：**

GR[1] = PC + 4

PC = PC + SignExtend({offs26, 2'b0}, 32)



#### JIRL

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">010011</td>
<td style="text-align: center;" colspan="8">offs16</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** jirl  rj, rd, offs16

**功能描述：** JIRL <u>无条件跳转</u>到目标地址处，同时将该指令的 PC 值加 4 的结果写入到通用寄存器 rd 中。

该指令的跳转目标地址是将指令码中的 16 比特立即数 offs16 **逻辑左移** 2 位后再符号扩展，所得的偏移值加上通用寄存器 rj中的值。

**操作定义：**

GR[rd] = PC + 4

PC = GR[rj] + SignExtend({offs16, 2'b0}, 32)



注：上述指令如果在写汇编时采用直接填入偏移值的方式，则汇编表示中的立即数应

填入以字节为单位的偏移值，即指令码中offs<<2。

### 普通访存指令
   #### LD.B，LD.H，LD.W

<table>
<tbody>
<tr>
<td></td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">LD.B</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">LD.H</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0001</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">LD.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0010</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** 

ld.b  rd, rj, si12

ld.h  rd, rj, si12

ld.w  rd, rj, si12

**功能描述：** LD.{B/H}从内存取回一个字节/半字的数据**符号扩展**后写入通用寄存器 rd，LD.W 从内存取回一个字的数据写入通用寄存器 rd。

其访存地址计算方式是将通用寄存器rj中的值与**符号扩展**后的12比特立即数si12相加求和。

**操作定义：**

**LD.B:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

byte = MemoryLoad(paddr, BYTE)

GR[rd] = SignExtend(byte, 32)

**LD.H:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

halfword = MemoryLoad(paddr, HALFWORD)

GR[rd] = SignExtend(halfword, 32)

**LD.W:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

word = MemoryLoad(paddr, WORD)

GR[rd] = word

**例外：**如果访存地址非自然对齐[^1]，则触发地址非对齐例外（ALE）。

#### LD.BU，LD.HU

<table>
<tbody>
<tr>
<td></td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">LD.BU</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1000</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">LD.HU</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** 

ld.bu  rd, rj, si12

ld.hu  rd, rj, si12

**功能描述：** LD.{BU/HU}从内存取回一个字节/半字的数据**零扩展**后写入通用寄存器 rd。

其访存地址计算方式是将通用寄存器rj中的值与**符号扩展**后的12比特立即数si12相加求和。

**操作定义：**

**LD.BU:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

byte = MemoryLoad(paddr, BYTE)

GR[rd] = ZeroExtend(byte, 32)

**LD.HU:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

halfword = MemoryLoad(paddr, HALFWORD)

GR[rd] = ZeroExtend(halfword, 32)

**例外：**如果访存地址非自然对齐[^1]，则触发地址非对齐例外（ALE）。

#### ST.B，ST.H，ST.W

<table>
<tbody>
<tr>
<td></td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">ST.B</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">ST.H</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0101</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">ST.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0110</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** 

st.b  rd, rj, si12

st.h  rd, rj, si12

st.w  rd, rj, si12

**功能描述：** ST.{B/H/W}将通用寄存器 rd 中的[7:0]/[15:0]/[31:0]位数据写入到内存中。

其访存地址计算方式是将通用寄存器rj中的值与**符号扩展**后的12比特立即数si12相加求和。

**操作定义：**

**ST.B:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

MemoryStore(GR[rd][7:0], paddr, BYTE)

**ST.H:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

MemoryStore(GR[rd][15:0], paddr, HALFWORD)

**ST.W:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

MemoryStore(GR[rd][31:0], paddr, WORD)

**例外：**如果访存地址非自然对齐[^1]，则触发地址非对齐例外（ALE）。

#### PRELD

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">hint</td>
</tr>
</tbody>
</table>

**指令格式：** preld   hint, rj, si12

**功能描述：** PRELD 从内存中预取一个 Cache 行的数据进入 Cache 中。其访存地址的计算方式是将通用寄存器 rj 中的值与**符号扩展**后的 12 比特立即数 si12 相加求和。该访存地址落在待预取的 Cache 行内。

PRELD 指令中的 hint 提示处理器预取的类型以及取回的数据填入哪一级 Cache。hint 从 0~31 有 32 个可选值。目前 hint=0 定义为 load 预取至一级数据 Cache，hint=8 定义为 store 预取至一级数据 Cache。其余hint 值的含义暂未定义，处理器执行时视同 NOP 指令处理。

如果 PRELD 指令的访存地址的 Cache 属性不是 cached，那么该指令不能产生访存动作，视同 NOP 指令处理。



[^1]:  所谓自然对齐是指，访问半字对象时地址是2字节边界对齐，访问字对象时地址是4字节边界对齐，访问双字对象时地址是8字节边界对齐，访问128 位向量对象时地址是16字节边界对齐，访问256位向量对象时地址是32字节边界对齐。

### 原子访存指令
   #### LL.W, SC.W

<table>
<tbody>
<tr>
<td></td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">24</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">23</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">LL.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">00</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si14</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">SC.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">01</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si14</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：**

ll.w   rd, rj, si14

sc.w  rd, rj, si14

**功能描述：** LL.W 和 SC.W 这一对指令用于实现原子的“读-修改-写”访存操作序列。LL.W 指令从内存指定地址取回一个字的数据符号扩展后写入通用寄存器 rd，与之配对的 SC.W 指令操作同样宽度的数据且访问相同的内存地址。访存操作序列原子性的维护机制是，LL.W 执行时记录下访问地址并置上一个标记（LLbit 置为1），SC.W 指令执行时会查看 LLbit，仅当 LLbit 为 1 时才真正产生写动作，否则不写。当软件需要一定成功完成一个原子的“读-修改-写”访存操作序列时，需要构建一个循环来反复执行 LL-SC 指令对直至 SC 成功完成。为了构建这个循环，SC.{W/D}指令会将其执行成功与否的标志（也可以简单理解为 SC 指令执行时所看到的 LLbit 值）写入到通用寄存器 rd 中返回。

在配对的 LL-SC 执行期间，下列事件会让 LLbit 清 0：

❖ 执行了 ERTN 指令且执行时 CSR.LLBCTL 中的 KLO 位不等于 1；

❖ 其它处理器核或 Cache Coherent I/O master 对该 LLbit 对应的地址所在的 Cache 行执行完成了一个store 操作。

如果 LL-SC 指令对访问地址的存储访问属性不是 Cached，那么执行结果不确定。

需要注意的是，上述指令在计算内存地址时，需要将指令码中的 si14 左移 2 位后再与基址相加，即

vaddr = GR[rj] + SignExtend({si14, 2'b0}, 32)



### 栅障指令
   #### DBAR

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 23.4375%; text-align: left;" colspan="3">14</td>
<td style="width: 23.4375%; text-align: right;" colspan="3">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">001110</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">11</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00100</td>
<td style="text-align: center;" colspan="6">hint</td>
</tr>
</tbody>
</table>

**指令格式：** dbar  hint

**功能描述：** DBAR 指令用于完成 load/store 访存操作之间的栅障功能。其携带的立即数 hint 用于指示该栅障的同步对象和同步程度。

hint 值为 0 是默认必须实现的，其指示一个完全功能的同步栅障。只有等到之前所有 load/store 访存操作彻底执行完毕后，“DBAR 0”指令才能开始执行；且只有“DBAR 0”执行完成执行后，其后所有 load/store访存操作才能开始执行。

如果没有专门的功能实现，其它所有 hint 值都必须按照 hint=0 执行。



#### IBAR

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 23.4375%; text-align: left;" colspan="3">14</td>
<td style="width: 23.4375%; text-align: right;" colspan="3">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">001110</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">11</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00101</td>
<td style="text-align: center;" colspan="6">hint</td>
</tr>
</tbody>
</table>

**指令格式：** ibar  hint

**功能描述：** IBAR 指令使用完成单个处理器核内部 store 操作与取指操作之间的同步。其携带的立即数 hint 用于指示该栅障的同步对象和同步程度。

hint 值为 0 是默认必须实现的。它能够确保“IBAR 0”指令之后的取指一定能够观察到“IBAR 0”指令之前所有 store操作的执行效果。



### 其它杂项指令
   #### SYSCALL

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 23.4375%; text-align: left;" colspan="3">14</td>
<td style="width: 23.4375%; text-align: right;" colspan="3">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10110</td>
<td style="text-align: center;" colspan="6">code</td>
</tr>
</tbody>
</table>

**指令格式：** syscall  code

**功能描述：** 执行 SYSCALL 指令将立即无条件的触发系统调用例外。

指令码中 code 域携带的信息可供例外处理例程作为所传递的参数使用。

**例外：**执行SYSCALL指令将确定地立刻触发系统调用例外（SYS）。

#### BREAK

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 23.4375%; text-align: left;" colspan="3">14</td>
<td style="width: 23.4375%; text-align: right;" colspan="3">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10100</td>
<td style="text-align: center;" colspan="6">code</td>
</tr>
</tbody>
</table>

**指令格式：** break  code

**功能描述：** 执行 BREAK 指令将立即无条件的触发系统调用例外。

指令码中 code 域携带的信息可供例外处理例程作为所传递的参数使用。

**例外：**执行BREAK指令将确定地立刻触发断点例外（BRK）。

#### RDCNTV{L/H}.W, RDCNTID

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">RDCNTID</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
</tr>
<tr>
<td style="test-align: center;">RDCNTVL.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">RDCNTVH.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** 

rdcntvl.w  	rd

rdcntvh.w 	rd

rdcntid   	rj

**功能描述：** 龙芯架构 32 位精简版定义了一个恒定频率计时器，其主体是一个 64 位的计数器，称为 Stable Counter。Stable Counter 在复位后置为 0，随后每个计数时钟周期自增 1，当计数至全 1 时自动绕回至 0 继续自增。同时每个计时器都有一个软件可配置的全局唯一编号，称为 Counter ID。

RDCNTV{L/H}.W 指令用于读取恒定频率计时器信息，其中 RDCNTVL.W 读取 Counter 的[31:0]位写入通用寄存器 rd 中，RDCNTVH.W 读取 Counter 的[63:32]位。RDCNTID Counter ID 号信息写入通用寄存器 rj中。

> 龙芯架构 32 位精简版中的 `RDCNTVL.W rd`、`RDCNTVH.W rd` 和 `RDCNTID rj` 指令实际上分别对应 32位龙芯架构中的`RDTIMEL.W rd, zero`、`RDTIMEH.W rd, zero`和`RDTIMEL.W zero, rj`这三种 RDTIME{L/H}.W指令的特殊使用。

**操作定义：**

**RDCNTVL.W:**

GR[rd] = Counter [31:0]

**RDCNTVH.W:**

GR[rd] = Counter [63:32]

**RDCNTID:**

GR[rj] = Counter ID




## 基础浮点数指令

### 浮点运算类指令

#### FADD.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FADD.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FADD.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fadd.s		fd, fj, fk

fadd.d		fd, fj, fk

**功能描述：** FADD.{S/D}指令将浮点寄存器 fj 中的单精度/双精度浮点数加上浮点寄存器 fk 中的单精度/双精度浮点数，得到的单精度/双精度浮点数结果写入到浮点寄存器 fd 中。浮点加法运算遵循 IEEE 754-2008 标准中addition(x,y)操作的规范。

**操作定义：**

**FADD.S:**

FR\[fd][31:0] = FP32\_addition(FR\[fj][31:0], FR\[fk][31:0])

**FADD.D:**

FR[fd] = FP64\_addition(FR[fj], FR[fk])

#### FSUB.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FSUB.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FSUB.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fsub.s		fd, fj, fk

fsub.d		fd, fj, fk

**功能描述：** FSUB.{S/D}指令将浮点寄存器 fj 中的单精度/双精度浮点数减去浮点寄存器 fk 中的单精度/双精度浮点数，得到的单精度/双精度浮点数结果写入到浮点寄存器 fd 中。浮点减法运算遵循 IEEE 754-2008 标准中subtraction(x,y)操作的规范。

**操作定义：**

**FSUB.S:**

FR\[fd][31:0] = FP32\_subtraction(FR\[fj][31:0], FR\[fk][31:0])

**FSUB.D:**

FR[fd] = FP64\_subtraction(FR[fj], FR[fk])

#### FMUL.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FMUL.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FMUL.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fmul.s		fd, fj, fk

fmul.d		fd, fj, fk

**功能描述：** FMUL.{S/D}指令将浮点寄存器 fj 中的单精度/双精度浮点数乘以浮点寄存器 fk 中的单精度/双精度浮点数，得到的单精度/双精度浮点数结果写入到浮点寄存器 fd 中。浮点乘法运算遵循 IEEE 754-2008 标准中multiplication(x,y)操作的规范。

**操作定义：**

**FMUL.S:**

FR\[fd][31:0] = FP32\_multiplication(FR\[fj][31:0], FR\[fk][31:0])

**FMUL.D:**

FR[fd] = FP64\_multiplication(FR[fj], FR[fk])

#### FDIV.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FDIV.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FDIV.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fdiv.s		fd, fj, fk

fdiv.d		fd, fj, fk

**功能描述：** FDIV.{S/D}指令将浮点寄存器 fj 中的单精度/双精度浮点数除以浮点寄存器 fk 中的单精度/双精度浮点数，得到的单精度/双精度浮点数结果写入到浮点寄存器 fd 中。浮点除法运算遵循 IEEE 754-2008 标准中division(x,y)操作的规范。

**操作定义：**

**FDIV.S:**

FR\[fd][31:0] = FP32\_division(FR\[fj][31:0], FR\[fk][31:0])

**FDIV.D:**

FR[fd] = FP64\_division(FR[fj], FR[fk])

#### FMADD.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FMADD.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fa</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FMADD.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fa</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fmadd.s		fd, fj, fk

fmadd.d		fd, fj, fk

**功能描述：** FMADD.{S/D}指令将浮点寄存器 fj 中的单精度/双精度浮点数与浮点寄存器 fk 中的单精度/双精度浮点数相乘，得到的结果加上浮点寄存器 fa 中的单精度/双精度浮点数，得到的单精度/双精度浮点数结果写入到浮点寄存器 fd 中。

**操作定义：**

**FMADD.S:**

FR\[fd][31:0] = FP32\_fusedMultiplyAdd(FR\[fj][31:0], FR\[fk][31:0], FR\[fa][31:0])

**FMADD.D:**

FR[fd] = FP64\_fusedMultiplyAdd(FR[fj], FR[fk], FR[fa])

#### FMSUB.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FMSUB.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fa</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FMSUB.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fa</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fmsub.s		fd, fj, fk

fmsub.d		fd, fj, fk

**功能描述：** FMSUB.{S/D}指令将浮点寄存器 fj 中的单精度/双精度浮点数与浮点寄存器 fk 中的单精度/双精度浮点数相乘，得到的结果减去浮点寄存器 fa 中的单精度/双精度浮点数，得到的单精度/双精度浮点数结果写入到浮点寄存器 fd 中。

**操作定义：**

**FMSUB.S:**

FR\[fd][31:0] = FP32\_fusedMultiplyAdd(FR\[fj][31:0], FR\[fk][31:0], -FR\[fa][31:0])

**FMSUB.D:**

FR[fd] = FP64\_fusedMultiplyAdd(FR[fj], FR[fk], -FR[fa])

#### FNMADD.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FNMADD.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0010</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fa</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FNMADD.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0010</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fa</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fnmadd.s		fd, fj, fk

fnmadd.d		fd, fj, fk

**功能描述：** FNMADD.{S/D}指令将浮点寄存器 fj 中的单精度/双精度浮点数与浮点寄存器 fk 中的单精度/双精度浮点数相乘，得到的结果加上浮点寄存器 fa 中的单精度/双精度浮点数，得到的单精度/双精度浮点数结果取负后写入到浮点寄存器 fd 中。

**操作定义：**

**FNMADD.S:**

FR\[fd][31:0] = -FP32\_fusedMultiplyAdd(FR\[fj][31:0], FR\[fk][31:0], FR\[fa][31:0])

**FNMADD.D:**

FR[fd] = -FP64\_fusedMultiplyAdd(FR[fj], FR[fk], FR[fa])

#### FNMSUB.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FNMSUB.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0011</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fa</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FNMSUB.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0011</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">10</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fa</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fnmsub.s		fd, fj, fk

fnmsub.d		fd, fj, fk

**功能描述：** FNMSUB.{S/D}指令将浮点寄存器 fj 中的单精度/双精度浮点数与浮点寄存器 fk 中的单精度/双精度浮点数相乘，得到的结果减去浮点寄存器 fa 中的单精度/双精度浮点数，得到的单精度/双精度浮点数结果取负后写入到浮点寄存器 fd 中。

**操作定义：**

**FNMSUB.S:**

FR\[fd][31:0] = -FP32\_fusedMultiplyAdd(FR\[fj][31:0], FR\[fk][31:0], -FR\[fa][31:0])

**FNMSUB.D:**

FR[fd] = -FP64\_fusedMultiplyAdd(FR[fj], FR[fk], -FR[fa])

#### FMAX.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FMAX.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FMAX.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fmax.s		fd, fj, fk

fmax.d		fd, fj, fk

**功能描述：** FMAX.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数与浮点寄存器 fk 中的单精度/双精度浮点数中的较大者写入到浮点寄存器 fd 中。这两条指令的运算遵循 IEEE 754-2008 标准中 maxNum(x,y)操作的规范。

**操作定义：**

**FMAX.S:**

FR\[fd][31:0] = FP32\_maxNum(FR\[fj][31:0], FR\[fk][31:0])

**FMAX.D:**

FR[fd] = FP64\_maxNum(FR[fj], FR[fk])

#### FMIN.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FMIN.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FMIN.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fmin.s		fd, fj, fk

fmin.d		fd, fj, fk

**功能描述：** FMIN.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数与浮点寄存器 fk 中的单精度/双精度浮点数中的较小者写入到浮点寄存器 fd 中。这两条指令的运算遵循 IEEE 754-2008 标准中 minNum(x,y)操作的规范。

**操作定义：**

**FMIN.S:**

FR\[fd][31:0] = FP32\_minNum(FR\[fj][31:0], FR\[fk][31:0])

**FMIN.D:**

FR[fd] = FP64\_minNum(FR[fj], FR[fk])

#### FMAXA.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FMAXA.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FMAXA.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fmaxa.s		fd, fj, fk

fmaxa.d		fd, fj, fk

**功能描述：** FMAXA.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数与浮点寄存器 fk 中的单精度/双精度浮点数中绝对值较大者写入到浮点寄存器 fd 中。这两条指令的运算遵循 IEEE 754-2008 标准中 maxNumMag(x,y)操作的规范。

**操作定义：**

**FMAXA.S:**

FR\[fd][31:0] = FP32\_maxNumMag(FR\[fj][31:0], FR\[fk][31:0])

**FMAXA.D:**

FR[fd] = FP64\_maxNumMag(FR[fj], FR[fk])

#### FMINA.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FMINA.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FMINA.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fmina.s		fd, fj, fk

fmina.d		fd, fj, fk

**功能描述：** FMINA.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数与浮点寄存器 fk 中的单精度/双精度浮点数中绝对值较小者写入到浮点寄存器fd中。这两条指令的运算遵循IEEE 754-2008标准中minNumMag(x,y)操作的规范。

**操作定义：**

**FMINA.S:**

FR\[fd][31:0] = FP32\_minNumMag(FR\[fj][31:0], FR\[fk][31:0])

**FMINA.D:**

FR[fd] = FP64\_minNumMag(FR[fj], FR[fk])

#### FABS.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FABS.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FABS.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fabs.s		fd, fj

fabs.d		fd, fj

**功能描述：** FABS.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数，取其绝对值（也即将符号位置为 0，其它部分不变），写入到浮点寄存器 fd 中。这两条指令的运算遵循 IEEE 754-2008 标准中 abs(x)操作的规范。

**操作定义：**

**FABS.S:**

FR\[fd][31:0] = FP32\_abs(FR\[fj][31:0])

**FABS.D:**

FR[fd] = FP64\_abs(FR[fj])

#### FNEG.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FNEG.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FNEG.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fneg.s		fd, fj

fneg.d		fd, fj

**功能描述：** FNEG.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数，取其相反数（也即将符号位取反，其它部分不变），写入到浮点寄存器 fd 中。这两条指令的运算遵循 IEEE 754-2008 标准中 negate(x)操作的规范。

**操作定义：**

**FNEG.S:**

FR\[fd][31:0] = FP32\_negate(FR\[fj][31:0])

**FNEG.D:**

FR[fd] = FP64\_negate(FR[fj])

#### FSQRT.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FSQRT.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FSQRT.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fsqrt.s		fd, fj

fsqrt.d		fd, fj

**功能描述：** FSQRT.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数，将其开方后得到的单精度/双精度浮点数写入到浮点寄存器 fd 中。浮点开方运算遵循 IEEE 754-2008 标准中 squareRoot(x)操作的规范。

**操作定义：**

**FSQRT.S:**

FR\[fd][31:0] = FP32\_squareRoot(FR\[fj][31:0])

**FSQRT.D:**

FR[fd] = FP64\_squareRoot(FR[fj])

#### FRECIP.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FRECIP.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FRECIP.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

frecip.s	fd, fj

frecip.d	fd, fj

**功能描述：** FRECIP.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数，用 1.0 除以这个浮点数后将得到的单精度/双精度浮点数写入到浮点寄存器 fd 中。相当于 IEEE 754-2008 标准中 division(1.0,x)操作。

**操作定义：**

**FRECIP.S:**

FR\[fd][31:0] = FP32\_division(1.0, FR\[fj][31:0])

**FRECIP.D:**

FR[fd] = FP64\_division(1.0, FR[fj])

#### FRSQRT.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FRSQRT.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FRSQRT.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

frsqrt.s		fd, fj

frsqrt.d	fd, fj

**功能描述：** FRSQRT.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数，将其开方后得到的单精度/双精度浮点数再用 1.0除，得到的单精度/双精度浮点数写入到浮点寄存器 fd 中。浮点开方求倒运算遵循 IEEE 754-2008标准中 rSqrt(x)操作的规范。

**操作定义：**

**FRSQRT.S:**

FR\[fd][31:0] = FP32\_division(1.0, FP\_squareRoot(FR\[fj][31:0]))

**FRSQRT.D:**

FR[fd] = FP64\_division(1.0, FP\_squareRoot(FR[fj]))

#### FCOPYSIGN.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FCOPYSIGN.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FCOPYSIGN.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fcopysign.s  	fd, fj, fk

fcopysign.d  	fd, fj, fk

**功能描述：** FCOPYSIGN.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数，将它的符号位改为浮点寄存器 fk中的单精度/双精度浮点数的符号位，得到的新的单精度/双精度浮点数写入到浮点寄存器 fd 中。浮点复制符号运算遵循 IEEE 754-2008 标准中 copySign(x, y)操作的规范。

**操作定义：**

**FCOPYSIGN.S:**

FR\[fd][31:0] = FP32\_copySign(FR\[fj][31:0], FR\[fk][31:0])

**FCOPYSIGN.D:**

FR[fd] = FP64\_copySign(FR[fj], FR[fk])

#### FCLASS.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FCLASS.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FCLASS.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fclass.s  	fd, fj 

fclass.d 	fd, fj

**功能描述：** 本指令对浮点寄存器 fj 中的浮点数进行类别的判断，所得的判断结果一共由 10 比特信息组成，每比特的含义如下表所示:

<table>
    <tr>
        <th colspan="1">Bit0</th>
        <th colspan="1">Bit1</th>
        <th colspan="1">Bit2</th>
        <th colspan="1">Bit3</th>
        <th colspan="1">Bit4</th>
        <th colspan="1">Bit5</th>
        <th colspan="1">Bit6</th>
        <th colspan="1">Bit7</th>
        <th colspan="1">Bit8</th>
        <th colspan="1">Bit9</th>
    </tr>
	<tr>
        <td style="text-align: center;" colspan="1" rowspan="2">SNaN</td>
        <td style="text-align: center;" colspan="1" rowspan="2">QNaN</td>
        <td style="text-align: center;" colspan="4">negative value</td>
        <td style="text-align: center;" colspan="4">positive value</td>
    </tr>
	<tr>
        <td colspan="1">∞</td>
        <td colspan="1">normal</td>
        <td colspan="1">subnormal</td>
        <td colspan="1">0</td><td colspan="1">∞</td>
        <td colspan="1">normal</td>
        <td colspan="1">subnormal</td>
        <td colspan="1">0</td>
    </tr>
</table>


当被判断的数据符合某个比特对应的条件时，结果信息向量的对应比特就会被置为 1。该指令对应IEEE 754-2008 标准中的 class(x)函数。

**操作定义：**

**FCLASS.S:**

FR\[fd][31:0] = FP32\_class(FR\[fj][31:0])

**FCLASS.D:**

FR[fd] = FP64\_class(FR[fj])

### 浮点比较指令
   #### FCMP.cond.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FCMP.cond.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000011</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">cond</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">cd</td>
</tr>
<tr>
<td style="test-align: center;">FCMP.cond.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000011</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0000</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">cond</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">cd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fcmp.cond.s  cc, fj, fk 

fcmp.cond.d  cc, fj, f

**功能描述：** 这是一条浮点比较指令，将比较的结果存入指定的状态码（cc）。这条指令的 cond 有 22 种，这些比较条件以及判断的标准在下表中列出来:

<table><tr><th colspan="1"><b>助记符</b></th><th colspan="1"><b>cond</b></th><th colspan="1"><b>含义</b></th><th colspan="1"><b>True Condition</b></th><th colspan="1"><b>QNaN是否 报例外</b></th><th colspan="1"><b>对应 IEEE 754-2008 函数</b></th></tr>
<tr><td colspan="1" valign="bottom">CAF</td><td colspan="1" valign="bottom">Ox0</td><td colspan="1">否</td><td colspan="1" valign="bottom">无</td><td colspan="1" rowspan="11" align="center" valign="middle">否</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="1" valign="bottom">CUN</td><td colspan="1" valign="bottom">0x8</td><td colspan="1" valign="bottom">无法比较</td><td colspan="1" valign="bottom">UN</td><td colspan="1" valign="bottom">compareQuietUnordered</td></tr>
<tr><td colspan="1" valign="bottom">CEQ</td><td colspan="1" valign="bottom">0x4</td><td colspan="1" valign="bottom">相等</td><td colspan="1" valign="bottom">EQ</td><td colspan="1" valign="bottom">compareQuietEqual</td></tr>
<tr><td colspan="1" valign="bottom">CUEQ</td><td colspan="1" valign="bottom">OxC</td><td colspan="1" valign="bottom">相等或无法比较</td><td colspan="1" valign="bottom">UN EQ</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="1" valign="bottom">CLT</td><td colspan="1" valign="bottom">0x2</td><td colspan="1" valign="bottom">小于</td><td colspan="1" valign="bottom">LT</td><td colspan="1" valign="bottom">compareQuietLess</td></tr>
<tr><td colspan="1" valign="bottom">CULT</td><td colspan="1" valign="bottom">OxA</td><td colspan="1" valign="bottom">小于或无法比较</td><td colspan="1" valign="bottom">UN LT</td><td colspan="1" valign="bottom">compareQuietLessUnordered</td></tr>
<tr><td colspan="1" valign="bottom">CLE</td><td colspan="1" valign="bottom">0x6</td><td colspan="1" valign="bottom">小于等于</td><td colspan="1" valign="bottom">LT EQ</td><td colspan="1" valign="bottom">compareQuietLessEqual</td></tr>
<tr><td colspan="1" valign="bottom">CULE</td><td colspan="1" valign="bottom">OxE</td><td colspan="1" valign="bottom">小于等于或无法比较</td><td colspan="1" valign="bottom">UN LT EQ</td><td colspan="1" valign="bottom">compareQuietNotGreater</td></tr>
<tr><td colspan="1" valign="bottom">CNE</td><td colspan="1" valign="bottom">0x10</td><td colspan="1" valign="bottom">不等</td><td colspan="1" valign="bottom">GT LT</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="1" valign="bottom">COR</td><td colspan="1" valign="bottom">0x14</td><td colspan="1" valign="bottom">有序</td><td colspan="1" valign="bottom">GT LT EQ</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="1" valign="bottom">CUNE</td><td colspan="1" valign="bottom">0x18</td><td colspan="1" valign="bottom">无法比较或不等</td><td colspan="1" valign="bottom">UN GT LT</td><td colspan="1" valign="bottom">compareQuietNotEqual</td></tr>
<tr><td colspan="1" valign="bottom">SAF</td><td colspan="1" valign="bottom">0x1</td><td colspan="1" valign="bottom">否</td><td colspan="1" valign="bottom">无</td><td colspan="1" rowspan="11" align="center" valign="middle">是</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="1" valign="bottom">SUN</td><td colspan="1" valign="bottom">0x9</td><td colspan="1" valign="bottom">不是大于小于或等于</td><td colspan="1" valign="bottom">UN</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="1" valign="bottom">SEQ</td><td colspan="1" valign="bottom">0x5</td><td colspan="1" valign="bottom">相等</td><td colspan="1" valign="bottom">EQ</td><td colspan="1" valign="bottom">compareSignalingEqual</td></tr>
<tr><td colspan="1" valign="bottom">SUEQ</td><td colspan="1" valign="bottom">OxD</td><td colspan="1" valign="bottom">不是大于或小于</td><td colspan="1" valign="bottom">UN EQ</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="1" valign="bottom">SLT</td><td colspan="1" valign="bottom">0x3</td><td colspan="1" valign="bottom">小于</td><td colspan="1" valign="bottom">LT</td><td colspan="1" valign="bottom">compareSignalingLess</td></tr>
<tr><td colspan="1" valign="bottom">SULT</td><td colspan="1" valign="bottom">OxB</td><td colspan="1" valign="bottom">不是大于或等于</td><td colspan="1" valign="bottom">UN LT</td><td colspan="1" valign="bottom">compareSignalingLessUnordered</td></tr>
<tr><td colspan="1" valign="bottom">SLE</td><td colspan="1" valign="bottom">0x7</td><td colspan="1" valign="bottom">小于等于</td><td colspan="1" valign="bottom">LT EQ</td><td colspan="1" valign="bottom">compareSignalingLessEqual</td></tr>
<tr><td colspan="1" valign="bottom">SULE</td><td colspan="1" valign="bottom">OxF</td><td colspan="1" valign="bottom">不是大于</td><td colspan="1" valign="bottom">UN LT EQ</td><td colspan="1" valign="bottom">compareSignalingNotGreater</td></tr>
<tr><td colspan="1" valign="bottom">SNE</td><td colspan="1" valign="bottom">0x11</td><td colspan="1" valign="bottom">不等</td><td colspan="1" valign="bottom">GT LT</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="1" valign="bottom">SOR</td><td colspan="1" valign="bottom">0x15</td><td colspan="1" valign="bottom">有序</td><td colspan="1" valign="bottom">GT LT EQ</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="1" valign="bottom">SUNE</td><td colspan="1" valign="bottom">0x19</td><td colspan="1" valign="bottom">无法比较或不等</td><td colspan="1" valign="bottom">UN GT LT</td><td colspan="1" valign="bottom"></td></tr>
<tr><td colspan="6">注：UN表示无法比较、EQ表示相等、LT表示小于。当有两个操作数中有至少一个NaN时，这两个数就无法比较。</td></tr>
</table>


### 浮点转换指令
   #### FCVT.S.D

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** fcvt.s.d 	fd, fj

**功能描述：** FCVT.S.D 指令选择浮点寄存器 fj 中的双精度浮点数转换为单精度浮点数，得到的单精度浮点数写入到浮点寄存器 fd 中。

**操作定义：**

FR\[fd][31:0] = FP32\_convertFormat(FR[fj], FP64)

#### FCVT.D.S

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** fcvt.d.s 	fd, fj

**功能描述：** FCVT.D.S 指令选择浮点寄存器 fj 中的单精度浮点数转换为双精度浮点数，得到的双精度浮点数写入到浮点寄存器 fd 中。

**操作定义：**

FR[fd] = FP64\_convertFormat(FR\[fj][31:0], FP32)

#### FFINT.{S/D}.W

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FFINT.S.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00100</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FFINT.D.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">11010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

ffint.s.w	fd, fj

ffint.d.w	fd, fj

**功能描述：** FFINT.{S/D}.W 指令选择浮点寄存器 fj 中的整数型定点数转换为单精度/双精度浮点数，得到的单精度/双精度浮点数写入到浮点寄存器 fd 中。此浮点格式转换运算遵循 IEEE 754-2008 标准中 convertFromInt(x)操作的规范。

**操作定义：**

**FFINT.S.W:**

FR\[fd][31:0] = FP32\_convertFromInt(FR\[fj][31:0], SINT32)

**FFINT.D.W:**

FR[fd] = FP64\_convertFromInt(FR\[fj][31:0], SINT32)

#### FTINT.W.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FFINT.W.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FFINT.W.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

ftint.w.s	fd, fj

ftint.w.d	fd, fj

**功能描述：** FTINT.W.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数转换为整数型定点数，得到的整数型定点数写入到浮点寄存器 fd 中。根据 FCSR 中不同的状态，此浮点格式转换运算遵循的 IEEE 754-2008 标准中的操作见下表:

|**舍入模式**|**IEEE754-2008标准中的操作**|
| :-: | :-: |
|向最近的偶数舍入|convertTolntegerExactTiesToEven(x)|
|向零方向舍入|convertTolntegerExactTowardZero(x)|
|向正无穷方向舍入|convertTolntegerExacrTowardPositive(x)|
|向负无穷方向舍入|convertTolntegerExactTowardNegative(x)|

**操作定义：**

**FTINT.W.S:**

FR\[fd][31:0] = FP32convertToSint32(FR\[fj][31:0], FCSR.RM)

**FTINT.W.D:**

FR[fd] = FP64convertToSint32(FR[fj], FCSR.RM)

#### FTINT{RM/RP/RZ/RNE}.W.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FTINTRM.W.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10100</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FTINTRM.W.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10100</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
    <tr>
<td style="test-align: center;">FTINTRP.W.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10100</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FTINTRP.W.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10100</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
    <tr>
<td style="test-align: center;">FTINTRZ.W.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FTINTRZ.W.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
    <tr>
<td style="test-align: center;">FTINTRNE.W.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FTINTRNE.W.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

ftintrm.w.s 	fd, fj 	ftintrp.w.s 	fd, fj

ftintrm.w.d	fd, fj 	ftintrp.w.d	fd, fj

ftintrz.w.s 	fd, fj 	ftintrne.w.s 	fd, fj

ftintrz.w.d 	fd, fj 	ftintrne.w.d 	fd, fj

**功能描述：** FTINTRM.W.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数转换为整数型定点数，得到的整数型定点数写入到浮点寄存器 fd 中，采用“向负无穷方向舍入”的方式。

FTINTRP.W.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数转换为整数型定点数，得到的整数型定点数写入到浮点寄存器fd 中，采用“向正无穷方向舍入”的方式。

FTINTRZ.W.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数转换为整数型定点数，得到的整数型定点数写入到浮点寄存器 fd 中，采用“向零方向舍入”的方式。

FTINTRNE.W.{S/D}指令选择浮点寄存器 fj 中的单精度/双精度浮点数转换为整数型定点数，得到的整数型定点数写入到浮点寄存器 fd 中，采用“向最近的偶数舍入”的方式。

**操作定义：**

**FTINTRM.W.S:**

FR\[fd][31:0] = FP32convertToSint32(FR\[fj][31:0], 3)

**FTINTRM.W.D:**

FR[fd] = FP64convertToSint32(FR[fj], 3)

**FTINTRP.W.S:**

FR\[fd][31:0] = FP32convertToSint32(FR\[fj][31:0], 2)

**FTINTRP.W.D:**

FR[fd] = FP64convertToSint32(FR[fj], 2)

**FTINTRZ.W.S:**

FR\[fd][31:0] = FP32convertToSint32(FR\[fj][31:0], 1)

**FTINTRZ.W.D:**

FR[fd] = FP64convertToSint32(FR[fj], 1)

**FTINTRNE.W.S:**

FR\[fd][31:0] = FP32convertToSint32(FR\[fj][31:0], 0)

**FTINTRNE.W.D:**

FR[fd] = FP64convertToSint32(FR[fj], 0)
### 浮点搬运指令
   #### FMOV.{S/D}

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FMOV.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FMOV.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fmov.s 	fd, fj 

fmov.d 	fd, fj

**功能描述：** FMOV.{S/D}将浮点寄存器 fj 的值按单精度/双精度浮点数格式写入到浮点寄

存器 fd 中，如果 fj 的值不是单精度/双精度浮点数格式，则结果不确定。

**操作定义：**

**FMOV.S：**

FR\[fd][31:0] = FR\[fj][31:0]

**FMOV.d：**

FR[fd] = FR[fj]

**例外：**上述指令操作是非算术的，不会引发 IEEE 754 例外，也不修改浮点控制状态寄存器的 Cause 和 Flags域。

#### FSEL

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000011</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">ca</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** fsel 	fd, fj, fk, ca

**功能描述：** FSEL 指令进行条件赋值操作。FSEL 执行时，如果条件标志寄存器 ca 的值等于 0 则将浮点寄存器 fj 的值写入到浮点寄存器 fd 中，否则将浮点寄存器 fk 的值写入到浮点寄存器 fd 中。

**操作定义：**

FR[fd] = CFR[ca] ? FR[fk] : FR[fj]

#### MOVGR2FR.W, MOVGR2FRH.W

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">MOVGR2FR.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">MOVGR2FRH.W</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

movgr2fr.w 	fd, rj

movgr2frh.w 	fd, rj

**功能描述：** MOVGR2FR.W 将通用寄存器 rj 值写入浮点寄存器 fd 的低 32 位中。若浮

点寄存器位宽为 64 位，则 fd的高 32 位值不确定。

MOVGR2FRH.W 将通用寄存器 rj 值写入浮点寄存器 fd 的高 32 位中，浮点寄存器 fd 的低 32 位值不变。

**操作定义：**

**MOVGR2FR.W：**

FR\[fd][31:0] = GR[rj]

**MOVGR2FRH.W：**

FR\[fd][63:32] = GR[rj]

FR\[fd][31: 0] = FR\[fd][31:0]

#### MOVFR2GR.S, MOVFRH2GR.S

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">MOVFR2GR.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">MOVFRH2GR.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** 

movfr2gr.s 	rd, fj

movfrh2gr.s 	rd, fj

**功能描述：** MOVFR2GR/MOVFRH2GR.S 将浮点寄存器 fj 的低 32 位/高 32 位值写入

通用寄存器 rd。

**操作定义：**

**MOVFR2GR.S：**

GR[rd] = FR\[fj][31:0]

**MOVFRH2GR.S：**

GR[rd] = FR\[fj][63:32]

#### MOVGR2FCSR, MOVFCSR2GR

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">MOVGR2FCSR</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fcsr</td>
</tr>
<tr>
<td style="test-align: center;">MOVFCSR2GR</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fcsr</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** 

movgr2fcsr 	fcsr, rj

movfcsr2gr 	rd, fcsr

**功能描述：** MOVGR2FCSR 根据通用寄存器 rj 值修改 fcsr 指示的浮点控制状态寄存器对应的软件可写域的值。如果MOVGR2FCSR 指令修改 FCSR0 使得其 Cause 域的位和对应的 Enables 的位同时为 1，或者修改 FCSR1 的Enables 域、FCSR2 的 Cause 域，使得 Cause 的位和对应 Enables 位同时为 1，MOVGR2FCSR 指令自身不会触发浮点例外。

MOVFCSR2GR 将 fcsr 指示的浮点控制状态寄存器的 32 位值写入通用寄存器 rd。

**操作定义：**

**MOVGR2FCSR：**

FCSR[fcsr] = GR[rj]

**MOVFCSR2GR：**

GR[rd] = FCSR[fcsr]

**注：**如果上述指令中的 fcsr 指示的浮点控制状态寄存器不存在，则结果不确定。

#### MOVFR2CF, MOVCF2FR

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">MOVFR2CF</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">cd</td>
</tr>
<tr>
<td style="test-align: center;">MOVCF2FR</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">cj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

movfr2cf 	cd, fj

movcf2fr 	fd, cj

**功能描述：** 

MOVFR2CF 将浮点寄存器 fj 的最低一比特的值写入条件标志寄存器 cd。

MOVCF2FR 将条件标志寄存器 cj 的值写入浮点寄存器 fd 的最低一比特，fd 余下的位补 0。

**操作定义：**

**MOVFR2CF：**

CFR[cd] = FR\[fj][0]

**MOVCF2FR：**

FR\[fd][0] = ZeroExtend(CFR[cj], 64)

#### MOVGR2CF, MOVCF2GR

<table>
<tbody>
<tr>
<td style="test-align: center;"> </td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">MOVGR2CF</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">cd</td>
</tr>
<tr>
<td style="test-align: center;">MOVCF2GR</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000000</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">0100</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">01</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10111</td>
<td style="text-align: center; width: 15.625%;" colspan="2">cj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** 

movgr2cf 	cd, rj

movcf2gr 	rd, cj

**功能描述：** 

MOVGR2CF 将通用寄存器 rj 的最低一比特的值写入条件标志寄存器 cd。

MOVCF2GR 将条件标志寄存器 cj 的值写入通用寄存器 rd 的最低一比特，rd 余下的位补 0。

**操作定义：**

**MOVGR2CF：**

CFR[cd] = GR\[rj][0]

**MOVCF2GR：**

GR\[rd][0] = ZeroExtend(CFR[cj], 32)

### 浮点分支指令
   #### BCEQZ

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 3.125%; text-align: left;">9</td>
<td style="width: 3.125%; text-align: right;">8</td>
<td style="width: 4.6875%; text-align: left;">7</td>
<td style="width: 4.6875%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">010010</td>
<td style="text-align: center;" colspan="8">offs21[15:0]</td>
<td style="text-align: center;" colspan="2">00</td>
<td style="text-align: center;" colspan="2">cj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">offs21[20:16]</td>
</tr>
</tbody>
</table>

**指令格式：** bceqz 	cj, offs21

**功能描述：** BCEQZ 对条件标志寄存器 cj 的值进行判断，如果<u>等于 0 则跳转</u>到目标地址，否则不跳转。

跳转目标地址是将指令码中的 21 比特立即数 offs21 **逻辑左移** 2 位后再**符号扩展**，所得的偏移值加上该分支指令的 PC。

**操作定义：**

if CFR[cj]==0 :

PC = PC + SignExtend({offs21, 2'b0}, 32)

#### BCNEZ

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 25%;     text-align: left;" colspan="4">25</td>
<td style="width: 25%;     text-align: right;" colspan="4">10</td>
<td style="width: 3.125%; text-align: left;">9</td>
<td style="width: 3.125%; text-align: right;">8</td>
<td style="width: 4.6875%; text-align: left;">7</td>
<td style="width: 4.6875%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">010010</td>
<td style="text-align: center;" colspan="8">offs21[15:0]</td>
<td style="text-align: center;" colspan="2">01</td>
<td style="text-align: center;" colspan="2">cj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">offs21[20:16]</td>
</tr>
</tbody>
</table>

**指令格式：** bcnez 	cj, offs21

**功能描述：** BCNEZ 对条件标志寄存器 cj 的值进行判断，如果<u>不等于 0 则跳转</u>到目标地址，否则不跳转。

跳转目标地址是将指令码中的 21 比特立即数 offs21 **逻辑左移** 2 位后再符号扩展，所得的偏移值加上该分支指令的 PC。

**操作定义：**

if CFR[cj]!=0 :

PC = PC + SignExtend({offs21, 2'b0}, 32)

注：上述指令如果在写汇编时采用直接填入偏移值的方式，则汇编表示中的立即数应

填入以字节为单位的偏移值，即指令码中offs<<2。

### 浮点普通访存指令
   #### FLD.{S/D}, FST.{S/D}

<table>
<tbody>
<tr>
<td></td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">FLD.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1100</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FLD.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1101</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FLT.S</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1110</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
<tr>
<td style="test-align: center;">FLT.D</td>
<td style="text-align: center; width: 18.75%; " colspan="2">001010</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1111</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">fd</td>
</tr>
</tbody>
</table>

**指令格式：** 

fld.s 	fd, rj, si12

fld.d 	fd, rj, si12

fst.s 	fd, rj, si12

fst.d	fd, rj, si12

**功能描述：** FLD.S 从内存取回一个字的数据写入浮点寄存器 fd 的低 32 位。若浮点寄存器位宽为 64 位，则 fd 的高32 位值不确定。FLD.D 从内存取回一个双字的数据写入浮点寄存器 fd。

FST.S 将浮点寄存器 fd 中低 32 位字数据写入到内存中。FST.D 将浮点寄存器 fd 中双字数据写入到内存中。

其访存地址计算方式是将通用寄存器 rj 中的值与符号扩展后的 12 比特立即数 si12 相加求和。

**操作定义：**

**FLD.S:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

word = MemoryLoad(paddr, WORD)

FR\[fd][31:0] = word

**FLD.D:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

doubleword = MemoryLoad(paddr, DOUBLEWORD) 

FR[fd] = doubleword

**FST.S:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

MemoryStore(FR\[fd][31:0], paddr, WORD)

**FST.D:**

vaddr = GR[rj] + SignExtend(si12, 32)

AddressComplianceCheck(vaddr)

paddr = AddressTranslation(vaddr)

MemoryStore(FR\[fd][63:0], paddr, DOUBLEWORD)

**例外：**如果访存地址非自然对齐[^1]，则触发地址非对齐例外（ALE）。

## 特权指令
   
### CSR 访问指令

#### CSRRD, CSRWR, CSRXCHG

<table>
<tbody>
<tr>
<td></td>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">24</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">23</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="test-align: center;">CSRRD</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">00</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">csr</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">CSRWR</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">00</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">csr</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00001</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
<tr>
<td style="test-align: center;">CSRXCHG</td>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">00</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">csr</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj!=0,1</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：**

csrrd 		rd, csr\_num

csrwr 		rd, csr\_num

csrxchg 	rd, rj, csr\_num

**功能描述：** 

CSRRD、CSRWR 和 CSRXCHG 指令用于软件访问 CSR。

CSRRD 指令将指定 CSR 的值写入到通用寄存器 rd 中。

CSRWR 指令将通用寄存器 rd 中的旧值写入到指定 CSR 中，同时将指定 CSR 的旧值更新到通用寄存器 rd 中。

CSRXCHG 指令根据通用寄存器 rj 中存放的写掩码信息，将通用寄存器 rd 中的旧值写入到指定 CSR 中对应写掩码为 1 的那些比特，该 CSR 中的其余比特保持不变，同时将该 CSR 的旧值更新到通用寄存器 rd 中。

所有 CSR 寄存器采用独立的寻址空间。上述指令中 CSR 的寻址值来自于指令中的 14 比特立即数csr\_num。CSR 的寻址单位是一个 CSR 寄存器，即 0 号 CSR 的 csr\_num 是 0，1 号 CSR 的 csr\_num 是 1，以此类推。

在龙芯架构 32 位精简版中，所有 CSR 寄存器的位宽都是 32 位。

当 CSR 访问指令访问一个架构中未定义或硬件未实现的 CSR 时，读动作返回全 0 值，写动作不修改处理器的任何软件可见状态。需要提请注意的是，CSRWR 和 CSRXCHG 指令不仅包含更新 CSR 的写动作，也包含读取 CSR 旧值的读动作。

### Cache 维护指令
   #### CACOP

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 18.75%;  text-align: left;" colspan="3">21</td>
<td style="width: 18.75%;  text-align: right;" colspan="3">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1000</td>
<td style="text-align: center; width: 6.25%;  " colspan="6">si12</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rd</td>
</tr>
</tbody>
</table>

**指令格式：** cacop 	code, rj, si12

**功能描述：** 

CACOP 指令主要用于 Cache 的初始化以及 Cache 一致性维护。

通用寄存器 rj 的值加上符号扩展后的 12 位立即数 si12，将得到 CACOP 指令所用的虚拟地址 VA，其将用于指示被操作 Cache 行的位置。

CACOP 指令访问哪个 Cache 以及进行何种 Cache 操作由指令中 5 比特的 code 决定。code[2:0]指示操作的 Cache 对象，code[4:3]指示操作类型。

code[2:0]=0 表示操作一级私有指令 Cache，code[2:0]=1 表示操作一级私有数据 Cache，code[2:0]=2 表示操作二级共享混合 Cache。

code[4:3]=0 表示用于 Cache 初始化（Store Tag），将指定 Cache 行的 tag 置为全 0。假设被访问的 Cache有（1<<Way）路，每一路有（1<<Index）个 Cache 行，每个 Cache 行大小为（1<<Offset）个字节，那么采用地址直接索引方式意味着，操作该 Cache 的第 VA[Way-1:0]路的第 VA[Index+Offset-1:Offset]个 Cache 行。

code[4:3]=1 表示采用地址直接索引方式维护 Cache 一致性（Index Invalidate / Invalidate and Writeback）。地址直接索引方式的定义请见上一段的描述。维护一致性的操作是对指定的 Cache 进行无效并写回的操作。如果被操作的是指令 Cache，那么仅需要进行无效操作，并不需要将 Cache 行中的数据写回。写回的数据进入到哪一级存储中由具体实现的 Cache 层次及各级间的包含或互斥关系决定。对于数据 Cache 或混合 Cache，由具体实现决定是否仅在 Cache 行数据为脏时才将其写回。

code[4:3]=2 表示采用查询索引方式维护 Cache 一致性（Hit Invalidate / Invalidate and Writeback）。这里维护 Cache 一致性的操作与上面一段所述一致。所谓查询索引方式，是将 CACOP 指令的 VA 视作一个普通 load指令去访问待操作的 Cache，如果命中则对命中的 Cache 行进行操作，否则不做任何操作。由于这个查询过程可能涉及虚实地址转换，所以这种情况下 CACOP 指令可能触发 TLB 相关的例外。不过，由于 CACOP指令操作的对象是 Cache 行，所以这种情况下并不需要考虑地址对齐与否。

code[4:3]=3 属于实现自定义的 Cache 操作，架构规范中不予明确的功能定义。

### TLB 维护指令
   #### TLBSRCH

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01010</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
</tr>
</tbody>
</table>

**指令格式：** tlbsrch

**功能描述：** 

使用 CSR.ASID 和 CSR.TLBEHI 的信息去查询 TLB。如果有命中项，那么将命中项的索引值写入到CSR.TLBIDX 的 Index 域，同时将 CSR.TLBIDX 的 NE 位置为 0；如果没有命中项，那么将 CSR.TLBIDX 的NE 位置为 1。

TLB 中各项的索引值计算规则是，从 0 开始依次递增编号，从第 0 行至最后一行。

#### TLBRD

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01011</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
</tr>
</tbody>
</table>

**指令格式：** tlbrd

**功能描述：** 

将 CSR.TLBIDX 的 Index 域的值作为索引值去读取 TLB 中的指定项。如果指定位置处是一个有效 TLB项，那么将该 TLB 项的页表信息写入到 CSR.TLBEHI、CSR.TLBELO0、CSR.TLBELO1 和 CSR.TLBIDX.PS中，且将 CSR.TLBIDX 的 NE 位置为 0；如果指定位置处是一个无效 TLB 项，需将 CSR.TLBIDX 的 NE 位置为 1，且将 CSR.ASID.ASID、CSR.TLBEHI、CSR.TLBELO0、CSR.TLBELO1 和 CSR.TLBIDX.PS 全置为0。

需要注意的是，有效/无效 TLB 项和 TLB 中的页表项有效/无效是两个概念。如果访问所用的 index 值超过了 TLB 的范围，则处理器的行为不确定

#### TLBWR

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01100</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
</tr>
</tbody>
</table>

**指令格式：** tlbwr

**功能描述：** 

TLBWR 指令将 TLB 相关 CSR 中所存放的页表项信息写入到 TLB 的指定项。被填入的页表项信息来自于 CSR.TLBEHI、CSR.TLBELO0、CSR.TLBELO1 和 CSR.TLBIDX.PS。若此时 CSR.ESTAT.Ecode=0x3F，即处于 TLB 重填例外处理过程中，那么 TLB 中总是填入一个有效项（即 TLB 项的 E 位为 1）。否则的话，就需要看 CSR.TLBIDX.NE 位的值。此时如果 CSR.TLBIDX.NE=1，那么 TLB 中会被填入一个无效 TLB 项；仅当 CSR.TLBIDX.NE=0 时，TLB 中才会被填入一个有效 TLB 项。

执行 TLBWR 时，页表项写入 TLB 的位置是由 CSR.TLBIDX 的 Index 域的值指定的。具体的对应规则请参看 TLBSRCH 指令中关于 TLB中各项索引值的计算规则。

#### TLBFILL

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01101</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
</tr>
</tbody>
</table>

**指令格式：** tlbfill

**功能描述：** 

TLBFILL 指令将 TLB 相关 CSR 中所存放的页表项信息填入到 TLB 中。被填入的页表项信息来自于CSR.TLBEHI、CSR.TLBELO0、CSR.TLBELO1 和 CSR.TLBIDX.PS。若此时 CSR.ESTAT.Ecode=0x3F，即处于 TLB 重填例外处理过程中，那么 TLB 中总是填入一个有效项（即 TLB 项的 E 位为 1）。否则的话，就需要看 CSR.TLBIDX.NE 位的值。此时如果 CSR.TLBIDX.NE=1，那么 TLB 中会被填入一个无效 TLB 项；仅当 CSR.TLBIDX.NE=0 时，TLB 中才会被填入一个有效 TLB 项。

执行 TLBFILL 时，页表项被填入到 TLB 的哪一项，是由硬件随机选择的。

#### INVTLB

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10011</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rk</td>
<td style="text-align: center; width: 15.625%;" colspan="2">rj</td>
<td style="text-align: center; width: 15.625%;" colspan="2">op</td>
</tr>
</tbody>
</table>

**指令格式：** invtlb op, rj, rk

**功能描述：** 

INVTLB 指令用于无效 TLB 中的内容，以维持 TLB 与内存之间页表数据的一致性。

指令的三个源操作数中，op 是 5 比特立即数，用于指示操作类型。

通用寄存器 rj 的[9:0]位存放无效操作所需的 ASID 信息（称为“寄存器指定 ASID”），其余比特必须填0。当 op 所指示的操作不需要 ASID 时，应将通用寄存器 rj 设置为 r0。

通用寄存器 rk 中用于存放无效操作所需的虚拟地址信息（称为“寄存器指定 VA”）。当 op 所指示的操作不需要虚拟地址信息时，应将通用寄存器 rk 设置为 r0。

各 op 对应的操作如下表所示，未在表中出现的 op 将触发保留指令例外。

|**op**|**操作**|
| :-: | :-- |
|0x0|清除所有页表项|
|0x1|清除所有页表项，此时操作效果与 op=0 完全一致|
|0x2|清除所有 G=1 的页表项|
|0x3|清除所有 G=0 的页表项|
|0x4|清除所有 G=0，且 ASID 等于寄存器指定 ASID 的页表项|
|0x5|清除 G=0，且 ASID 等于寄存器指定 ASID，且 VA 等于寄存器指定 VA 的页表项|
|0x6|清除所有 G=1 或 ASID 等于寄存器指定 ASID，且 VA 等于寄存器指定 VA 的页表项|

### 其它杂项指令
   #### ERTN

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 7.8125%; text-align: left;">14</td>
<td style="width: 7.8125%; text-align: right;">10</td>
<td style="width: 7.8125%; text-align: left;">9</td>
<td style="width: 7.8125%; text-align: right;">5</td>
<td style="width: 7.8125%; text-align: left;">4</td>
<td style="width: 7.8125%; text-align: right;">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">01110</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
<td style="text-align: center; width: 15.625%;" colspan="2">00000</td>
</tr>
</tbody>
</table>

**指令格式：** ertn

**功能描述：** 

ERTN 指令用于从例外处理返回。

将例外对应的 PPLV、PIE 等信息更新至 CSR.CRMD 中，同时跳转到例外所对应的 ERA处开始取指。

例外对应的 PPLV、PIE 信息来自于 CSR.PRMD，例外对应的 ERA 来自于 CSR.ERA。

执行 ERTN 指令时，如果 CSR.LLBCTL 中的 KLO 位不等于 1，则将 LLbit 置 0，否则 LLbit 不修改。

#### IDLE

<table>
<tbody>
<tr>
<td style="width: 9.375%;  text-align: left;">31</td>
<td style="width: 9.375%;  text-align: right;">26</td>
<td style="width: 6.25%;   text-align: left;">25</td>
<td style="width: 6.25%;   text-align: right;">22</td>
<td style="width: 3.125%;  text-align: left;">21</td>
<td style="width: 3.125%;  text-align: right;">20</td>
<td style="width: 7.8125%; text-align: left;">19</td>
<td style="width: 7.8125%; text-align: right;">15</td>
<td style="width: 23.4375%; text-align: left;" colspan="3">14</td>
<td style="width: 23.4375%; text-align: right;" colspan="3">0</td>
</tr>
<tr>
<td style="text-align: center; width: 18.75%; " colspan="2">000001</td>
<td style="text-align: center; width: 12.5%;  " colspan="2">1001</td>
<td style="text-align: center; width: 6.25%;  " colspan="2">00</td>
<td style="text-align: center; width: 15.625%;" colspan="2">10001</td>
<td style="text-align: center; width: 15.625%;" colspan="6">level</td>
</tr>
</tbody>
</table>

**指令格式：** idle 	level

**功能描述：** 

IDLE 指令执行完毕后，处理器核将停止取指进入等待状态，直至其被中断唤醒或被复位。从停止状态

被中断唤醒后，处理器核执行的第一条指令是 IDLE 之后的那一条指令。




