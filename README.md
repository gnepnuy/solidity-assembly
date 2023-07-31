solidity-assembly

  push1(0x1)//将1压入栈中
  
  dup2//复制栈中的第二项
  
  swap1//交换栈顶的两项数据
  
  sstore(0x0,0x1)// 将数值0x01存储在0x0的位置上,这个操作会消耗栈顶两项数据
  
  pop//丢弃栈顶数据
  
  sload(0x0)//读取0x0位置的数据

  mstore(32, 0x0)// 把0x0写入32开始的内存位置中,mstore指令写入32个字节到内存中

  keccak256(0,64)//计算0~64内存位置上数据的hash值

计算mapping的存储位置:

  keccak256(bytes32(0x2121)+bytes32(0))//bytes32(0x2121)为mapping的key,bytes32(0)为mapping的插槽位置,slot0

计算数组里第一个元素的存储位置

  keccak256(bytes32(0))//bytes32(0)为数组的插槽位置,slot0
  第二元素为keccak256(bytes32(0))+1

bytes数组使用体会

  bytes.push()//可以在数组末尾添加数据,同时也会增加bytes数组的长度
  bytes[0]//返回的是两个字符,如果index超过了bytes数组的长度会报错
  
    
