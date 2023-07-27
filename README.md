# solidity-assembly
push1(0x1)//将1压入栈中
dup2//复制栈中的第二项
swap1//交换栈顶的两项数据
sstore(0x0,0x1)// 将数值0x01存储在0x0的位置上,这个操作会消耗栈顶两项数据
pop//丢弃栈顶数据
sload(0x0)//读取0x0位置的数据
