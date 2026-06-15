# Simulated Annealing
## 輸入參數

Bit, Run, Iteration, Rate, and ProblemType(0: onemax ; 1: deception)

## 程式流程

#### <ins>初始化</ins>
**Init()**: 依照Bit數建立初始佇列current_sol(value = 0 / 1)，並依照輸入的ProblemType去Evaluate其佇列分數
初始參數： T = 100 ; alpha = 0.99

#### <ins>主程式</ins>
1. 生成下一個佇列(next_sol)，每個element生成一個0~1的隨機數，若該值小於輸入的Rate值則0/1互換，並計算其分數
2. 如果next_sol分數大於current_sol則更新current_sol
3. 若next_sol分數小於current_sol，我們不像Hill Climbing一樣直接捨棄
4. 先隨機生成隨機數P
5. 由於要計算最大化問題，所以接受機率Accpt = e^(f(new)-f(current)/T)
6. 如果P<Accept，則接受較差的解;反之則捨棄next_sol 
7. 溫度降低 T = T * alpha
  
          
