# Print_Tree
打印树结构

展示如下：


123456789	1层											n层
1			1       	2^0								2^(n-1)


123456789   2层
 1		 	2			2^1							
/ \			1 3			(2^1 - 2^0) (2^1 + 2^0)			(2^(n-1) - 2^(n-2)) (2^(n-1) + 2^(n-2))
2 3         1 3


123456789	3层
   1 		4			2^2
 /   \		2 6			(2^2 - 2^1) (2^2 + 2^1)
 2   3		2 6
/ \ / \ 	1 3 5 7		(2^2 - 2^1 - 2^0) (2^2 - 2^1 + 2^0) (2^2 + 2^1 - 2^0) (2^2 + 2^1 + 2^0)			(2^(n-1) - 2^(n-2) - 2^(n-3))
4 5 6 7		1 3 5 7		 																				(2^(n-1) - 2^(n-2) + 2^(n-3)) 
																										(2^(n-1) + 2^(n-2) - 2^(n-3)) 
																										(2^(n-1) + 2^(n-2) + 2^(n-3))


123456789111111			4层				
		 012345
       1	 			8			n=4			pos=2^(n-1)=2^3=8  
   /       \ 			4 12		n=n-1=3		offset=2^(n-1)=2^(3-1)=4 left_pos=parent_pos-offset=8-4=4 right_pos=parent_pos+offset=8+4=12 
   2       3 							
 /   \   /   \						n=n-1=2		offset=2^(n-1)=2 left_pos=4-offset=2 right_pos=4+offset=6 left_pos=12-offset=10 right_pos=12+offset=14
 4   5   6   7 							
/ \ / \ / \ / \                     n=n-1=1     offset=2^(n-1)=1 
8 9 1 1 1 1 1 1                               	left_pos=2-offset=1 right_pos=2+offset=3	
    0 1 2 3 4 5                                 left_pos=6-offset=5 right_pos=6+offset=7	
                                                left_pos=10-offset=9 right_pos=10+offset=11	
                                                left_pos=14-offset=13 right_pos=14+offset=15	
                                                
