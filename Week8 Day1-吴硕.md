## Week8 Day1



### ROM(Read Only Memory)



- PROM programROM，利用的铁丝的熔断导电与否来存储信息，熔断了不导电为0，导电为1，只能写入一次，一般用来写入主板启动自检的代码，价格低廉
- EPROM erasable，利用化学物质来存储数据，可以利用紫外线来消除数据
- E$^2$PROM Electrically 通过电压进行数据消除，只需在四角升高电压就可以消除，比EPROM更加易于消除
- FLASH 闪存，分为NOR和NAND，是目前较为常用的



### RAM(Random Access Memory)



- DRAM dynamic，动态数据，写入数据后经过很长一段时间不去操作数据可能会丢失，有风险
- SDRAM 在cpu和memory之间拉了根线进行时间同步，可由双方进行控制，但一般是CPU控制；利用ROW和COLIMN进行数据寻址
- DDR 也称DDRSDRAM，双倍速率的SDRAM，在一个时钟周期传输两次数据，分别在上升沿和下降沿各传输一次
- SRAM 静态的，存取的速度快但存储密度和容量比DRAM低，只要直流电源一直存在，数据就不会丢失；但只要断电，数据就丢失。



### DRAM



- RAS row address select 用于指示现在要选通行地址，同理还有CAS
- CS chip select 片选信号，使设备能或不能操作，CS为高时，设备未被选中，CS为低时，设备被选中，用来选择要操作的RANK
- CPU仅会在cache miss时访问memory，因此每次对memory的读入都是固定长度的



### Multi-Bank

- 一种用来提高访问效率的方法，在CPU访问memory时，只要不是访问同一个bank，就可以并行进行
- $AMAT_M = T_{addr} + T_{access} + T_{transfer}$







