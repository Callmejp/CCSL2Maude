## TestCase For ccsl.maude

### Case 1:
   
`Order`: search [,30] < (’c1, ’c2, ’c3) ; (’c1 < ’c2) (’c2 < ’c3) ’c3 != ’c1$1; [’c1,nil,0],[’c2,nil,0],[’c3,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints; X:ConfList ; 30 > .

`Expected Result`: ![Case1](Images/CCSL_1.JPG)

---

## TestCase For verify.maude

### Case 1:
   
`Order`: search [,35] < (['c1, (1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0)], ['c2, (0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1)], ['c3, (0, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0)]) ; ('c1 < 'c2) ('c2 < 'c3) ('c3 != 'c1 $ 1) ; 1 > =>* < CS:ClockSet ; CON:Constraints ; 21 > .

`Expected Result`: ![Case1](Images/VERIFY_1.JPG)