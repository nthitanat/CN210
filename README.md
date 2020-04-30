# รายงานวิชา CN210

### สรุปเนื้อหา
CPU MIPS ซึ่งเป็นหน่วยประมวลผลแบบ 32 bits มีชุดคำสั่ง 3 แบบได้แก่ 
R-Format ใช้บวกลบเช่น add และ sub , J-Format ใช้กระโดดไปที่ address และ I-Format ใช้อ่านค่าและเก็บค่าเช่น lw sw beq โดยจะมีการทำงาน 2 แบบคือ Single Cycle, Multicycle และ Pipelining 
    ![](mips.png) 

#### งานครั้งที่ 1
  * [CLIP1(Youtube)](https://www.youtube.com/watch?v=XJNgUDDHLz4&t=5sk)
  
    ![](add.png) 
    
  ++ คำอธิบาย : คลิปนี้เกี่ยวกับคำสั่ง add
               
#### งานครั้งที่ 2 
  * [CLIP2(Youtube)]()
  
    ![]()
    
  ++ คำอธิบาย : คลิปนี้พูดเกี่ยวกับการทำงานของ cpu ในขณะที่รันโปรแกรมภาษาคอมพิวเตอร์
  
#### งานครั้งที่ 3
  * [CLIP3(Youtube)](https://www.youtube.com/watch?v=2ExHtqbKRaQ&t=7s)
  
    ![]()
  
  ++ คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับความแตกต่างของ Single Cycle กับ Multicycle 
  
#### งานครั้งที่ 4
  * [CLIP4(Youtube)](https://www.youtube.com/watch?v=XQ-GosMwBqo&t=2s)
  
    ![]()  
    
  ++ คำอธิบาย : คลิปนี้จะอธิบายเกี่ยวกับการทำงานของคำสั่ง Load Word ในรูปแบบ Multicycle โดยเริ่มต้นจากการ Fetch จะเป็นการส่งค่าให้ register และส่งค่าให้ ALU 
               เพื่อ +4 และทำstepต่อไป จากนั้นก็ทำ Fetch+1 เพื่อเก็บค่า register 2 ตัว และส่งเข้าไปที่ ALUOut จากนั้นทำการ Mem1 เป็นการส่งค่าจาก Register 
               ไปเข้า ALU เพื่อทำคำสั่งแล้วส่งให้ ALUOut หลังจากนั้นก็ส่งเข้า Memory data register
  
#### งานครั้งที่ 5
  * [CLIP5(Youtube)](https://www.youtube.com/watch?v=K4XTfzQJDPQ&t=11s)
 
    ![]()
    
  ++ คำอธิบาย : คลิปนี้อธิบายการทำงานของคำสั่ง Branch On Equal หรือ Beq ใน Multicycle โดยจะเริ่มต้นจากการ Fetch จะเป็นการส่งค่าให้ register และส่งค่า
               ให้ ALU เพื่อ +4 และพร้อมทำขั้นตอนต่อไป เสร็จแล้วก็ถอดรหัสเพื่อเก็บค่าเข้า register 2 ตัว และอ่านค่า offset+pc จากนั้นก็จะส่งไปที่ ALUOut 
               หลังจากนั้นทำการเช็ค register 2 ตัวนี้ว่าเท่ากันมั้ย ถ้าเท่ากันจะส่งให้ ALUOut แต่ถ้าไม่เท่ากันก็ส่งให้ PC แทน
  
#### งานครั้งที่ 6
  * [CLIP6(Youtube)]()
  
    ![]()
  
  ++ คำอธิบาย : คลิปนี้อธิบายเกี่ยวกับการทำงาน State Machine ของ r-format ใน cpu รูปแบบ Multicycle โดยจะส่วนประกอบของการทำงานจะมีั้ง Fetch, 
               Reg/Dec, Exec, Wr โดยการทำงานจะใช้ MemRead, MemWrite, lorD, IRWrite, ALUSrcA, ALUSrcB, ALUOP, PCWrite, PCSource, RegWrite, 
               MemtoReg และ RegDst ในการทำงาน
  
  #### งานครั้งที่ 7
   * [CLIP7(Youtube)](https://www.youtube.com/watch?v=G_C4LKna9z8&t=11s)
   
     ![]() 
  
  ++ คำอธิบาย : คลิปนี้อธิบายเกี่ยวกับ Pipelining ว่ามันคืออะไร รวมถึงข้อดี ปัญหาของ Pipelining การทำงาน ความแตกต่างของการทำงาน โดย Pipelining 
               เป็นหน่วยความจำที่อ่านคำสั่งต่างๆ จนจบคำสั่งคล้าย Register แต่ต่างกันตรงที่ Pipelining เก็บค่าได้มากกว่า Register แต่ทำงานได้ช้ากว่า Register 
               โดย Pipelining จะทำคำสั่งได้มากกว่า 1 คำสั่ง เพราะใช้หลักการว่าเมื่อกระบวนการทำงานทำงานคำสั่งก่อนหน้า แต่มันมีปัญหาคือคำสั่งมีโอกาสทำกระบวนการ                    เดียวกันเกิน 1 คำสั่ง หรือมีโอกาสที่จะผิดพลาดเมื่อคำสั่งหลังต้องการรับค่าจากคำสั่งก่อนหน้า 
