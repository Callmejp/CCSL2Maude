## TestCase For ccsl.maude

### Case 1(Precedence and Delay):
   
`Order`: search [,30] < (’c1, ’c2, ’c3) ; (’c1 < ’c2) (’c2 < ’c3) ’c3 != ’c1 $ 1 ; [’c1,nil,0],[’c2,nil,0],[’c3,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints ; X:Conf ; 30 > .

`Expected Result`: ![Case1](Images/CCSL_1.JPG)

### Case 2(Periodicity):

`Order`: search [1, 10] < ('c1, 'c2) ; ('c1 != 'c2 ~ 3) ; ['c1,nil,0],['c2,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints ; X:Conf ; 6 > .

`Expected Result`: ![Case2](Images/CCSL_Periodicity.JPG)


### Case 3(Intersection):

`Order`: search [2, 10] < ('c1, 'c2, 'c3) ; ('c1 != 'c2 * 'c3) ; ['c1,nil,0],['c2,nil,0],['c3,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints ; X:Conf ; 6 > .

`Expected Result`: ![Case3](Images/CCSL_Intersection.JPG)

### Case 4(Union):

`Order`: search [2, 10] < ('c1, 'c2, 'c3) ; ('c1 != 'c2 + 'c3) ; ['c1,nil,0],['c2,nil,0],['c3,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints ; X:Conf ; 6 > .

`Expected Result`: ![Case4](Images/CCSL_Union.JPG)

### Case 5(Infimum):

`Order`: search [2, 10] < ('c1, 'c2, 'c3) ; ('c1 != 'c2 /\ 'c3) ; ['c1,nil,0],['c2,nil,0],['c3,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints ; X:Conf ; 6 > .

`Expected Result`: ![Case5](Images/CCSL_Infimum.JPG)

### Case 6(Supremum):

`Order`: search [2, 10] < ('c1, 'c2, 'c3) ; ('c1 != 'c2 \/ 'c3) ; ['c1,nil,0],['c2,nil,0],['c3,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints ; X:Conf ; 6 > .

`Expected Result`: ![Case6](Images/CCSL_Supremum.JPG)

### Case 7(Subclock):

`Order`: search [2, 10] < ('c1, 'c2) ; ('c1 << 'c2) ; ['c1,nil,0],['c2,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints ; X:Conf ; 6 > .

`Expected Result`: ![Case7](Images/CCSL_Subclock.JPG)

### Case 8(Exclusion):

`Order`: search [2, 10] < ('c1, 'c2) ; ('c1 # 'c2) ; ['c1,nil,0],['c2,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints ; X:Conf ; 6 > .

`Expected Result`: ![Case8](Images/CCSL_Exclusion.JPG)

### Case 9(Causality):

`Order`: search [2, 10] < ('c1, 'c2) ; ('c1 <= 'c2) ; ['c1,nil,0],['c2,nil,0] ; 0 > =>* < CS:ClockSet ; CTS:Constraints ; X:Conf ; 6 > .

`Expected Result`: ![Case9](Images/CCSL_Causality.JPG)
---

## TestCase For verify.maude

### Case 1(Precedence and Delay):
   
`Order`: search [,35] < (['c1, (1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0)], ['c2, (0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1)], ['c3, (0, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0)]) ; ('c1 < 'c2) ('c2 < 'c3) ('c3 != 'c1 $ 1) ; 1 > =>* < CS:ClockSet ; CON:Constraints ; 21 > .

`Expected Result`: ![Case1](Images/VERIFY_1.JPG)

### Case 2(Periodicity):

`Order`: search [,10] < (['c1, (1, 0, 1, 1, 1)], ['c2, (0, 0, 1, 0, 1)]) ; ('c2 != 'c1 ~ 2) ; 1 > =>* < CS:ClockSet ; CON:Constraints ; 6 > .

`Expected Result`: `1 Solution`

### Case 3(Intersection and Union):

`Order`: search [,10] < (['c1, (1, 0, 1, 1, 1)], ['c2, (0, 0, 1, 0, 1)], ['c3, (0, 0, 1, 0, 1)], ['c4, (1, 0, 1, 1, 1)]) ; ('c3 != 'c1 * 'c2) ('c4 != 'c1 + 'c2) ; 1 > =>* < CS:ClockSet ; CON:Constraints ; 6 > .

`Expected Result`: `1 Solution`

### Case 4(Infimum and Supremum):

`Order`: search [,10] < (['c1, (1, 0, 1, 1, 1)], ['c2, (0, 0, 1, 0, 1)], ['c3, (1, 0, 1, 1, 1)], ['c4, (0, 0, 1, 0, 1)]) ; ('c3 != 'c1 /\ 'c2) ('c4 != 'c1 \/ 'c2) ; 1 > =>* < CS:ClockSet ; CON:Constraints ; 6 > .

`Expected Result`: `1 Solution`


### Case 5(Subclock and Exclusion and Causality):

`Order`: search [,10] < (['c1, (1, 0, 0, 1, 0)], ['c2, (0, 0, 1, 0, 1)], ['c3, (1, 1, 1, 1, 1)], ['c4, (1, 0, 0, 1, 0)]) ; ('c1 # 'c2) ('c1 << 'c3) ('c4 <= 'c2); 1 > =>* < CS:ClockSet ; CON:Constraints ; 6 > .

`Expected Result`: `1 Solution`

