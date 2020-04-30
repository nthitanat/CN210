#สรุปเนื้อหา
MIPS Instruction format

ทุกคำสั่งของ MIPS จะถูกเข้ารหัสโดย binary และจะมีขนาด 32 bits

มีอยู่ 3 ประเภท


image

R-Format ใช้ในการคำนวณทางตรรกศาสตร์

ALU => alu $rd,$rs,$rt
jr => jr $rs
I-Format ใช้ย้ายข้อมูลเปลี่ยนข้อมูล

ALUi => alui $rt,$rs,value
Data Tranfers => lw $rt,offset($rs) * sw $rt,offset($rs)
Branch => beq $rs,$rt,offset
J-Format ย้ายไปทำงานที่อื่น

Jump => j address
Jump&Link => jal address
การบ้านครั้งที่ 1
