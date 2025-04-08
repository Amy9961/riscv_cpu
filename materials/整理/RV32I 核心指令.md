 # RV32I 核心指令

### **1. 整数运算指令**
• **ADD**：加法（`Rd = Rs1 + Rs2`）。
• **SUB**：减法（`Rd = Rs1 - Rs2`）。
• **ADDI**：立即数加法（`Rd = Rs1 + imm`）。
• **SLT**：有符号比较，小于时置 1（`Rd = (Rs1 < Rs2) ? 1 : 0`）。
• **SLTU**：无符号比较，小于时置 1（`Rd = (Rs1 < Rs2) ? 1 : 0`）。
• **SLTI**：立即数有符号比较（`Rd = (Rs1 < imm) ? 1 : 0`）。
• **SLTIU**：立即数无符号比较（`Rd = (Rs1 < imm) ? 1 : 0`）。
• **XOR**：按位异或（`Rd = Rs1 ^ Rs2`）。
• **OR**：按位或（`Rd = Rs1 | Rs2`）。
• **AND**：按位与（`Rd = Rs1 & Rs2`）。
• **XORI**：立即数按位异或（`Rd = Rs1 ^ imm`）。
• **ORI**：立即数按位或（`Rd = Rs1 | imm`）。
• **ANDI**：立即数按位与（`Rd = Rs1 & imm`）。

---

### **2. 移位指令**
• **SLL**：逻辑左移（`Rd = Rs1 << Rs2[4:0]`）。
• **SRL**：逻辑右移（`Rd = Rs1 >> Rs2[4:0]`）。
• **SRA**：算术右移（`Rd = Rs1 >>> Rs2[4:0]`）。
• **SLLI**：立即数逻辑左移（`Rd = Rs1 << imm`）。
• **SRLI**：立即数逻辑右移（`Rd = Rs1 >> imm`）。
• **SRAI**：立即数算术右移（`Rd = Rs1 >>> imm`）。

---

### **3. 加载/存储指令**
• **LW**：从内存加载一个字（`Rd = Mem[Rs1 + offset]`）。
• **SW**：存储一个字到内存（`Mem[Rs1 + offset] = Rs2`）。
• **LH**：从内存加载半字（`Rd = SignExtend(Mem[Rs1 + offset])`）。
• **LHU**：从内存加载无符号半字（`Rd = ZeroExtend(Mem[Rs1 + offset])`）。
• **LB**：从内存加载字节（`Rd = SignExtend(Mem[Rs1 + offset])`）。
• **LBU**：从内存加载无符号字节（`Rd = ZeroExtend(Mem[Rs1 + offset])`）。
• **SH**：存储半字到内存（`Mem[Rs1 + offset] = Rs2[15:0]`）。
• **SB**：存储字节到内存（`Mem[Rs1 + offset] = Rs2[7:0]`）。

---

### **4. 分支指令**
• **BEQ**：相等时跳转（`if (Rs1 == Rs2) PC += offset`）。
• **BNE**：不相等时跳转（`if (Rs1 != Rs2) PC += offset`）。
• **BLT**：有符号小于时跳转（`if (Rs1 < Rs2) PC += offset`）。
• **BGE**：有符号大于等于时跳转（`if (Rs1 >= Rs2) PC += offset`）。
• **BLTU**：无符号小于时跳转（`if (Rs1 < Rs2) PC += offset`）。
• **BGEU**：无符号大于等于时跳转（`if (Rs1 >= Rs2) PC += offset`）。

---

### **5. 跳转指令**
• **JAL**：跳转并链接（`Rd = PC + 4; PC += offset`），用于函数调用。
• **JALR**：跳转并链接寄存器（`Rd = PC + 4; PC = Rs1 + offset`），用于函数返回或间接跳转。

---

### **6. 其他指令**
• **LUI**：加载高位立即数（`Rd = imm << 12`），用于构建 32 位常数。
• **AUIPC**：将立即数与 PC 相加（`Rd = PC + (imm << 12)`），用于构建 PC 相对地址。
• **FENCE**：内存屏障，用于保证内存操作的顺序。
• **ECALL**：环境调用，用于触发系统调用或异常。
• **EBREAK**：断点指令，用于调试。

