# W14D1笔记 —— Review

## Pipeline

### Hazard
* Structure hazard (cache)
* Data hazard 
  —— ture: RAW (forwarding, compiler)
  —— pseudo: WAW, WAR (renaming)
* Control hazard (predict, stall)

### 乱序

* 问题: 精准中断，跳转
* 解决: ROB保证提交顺序
* Tomasulo: Issue -> execute -> commit

### 解决control hazard
* 分支预测
* delay slot: 将后续一定会执行的指令放进delay slot来填充br产生的stall
* super block: 将分支合并，增大块，便于delay slot填充
```
      A                   ___________
     | |                 |   |   |   |
    B   C         ->    ABD ABF ACG ACH
   | | | |    
   D F G H
```
* 循环展开: 减少跳转

### Cache & Memory

 $AMAT_{cache} = T_{hit} +\eta_{miss-rate}*T_{penalty}$
 
  $AMAT_{mem} = T_{addr} +T_{access}+T_{trans}$
