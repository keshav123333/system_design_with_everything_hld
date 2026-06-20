# os 
# memory management 
aim : to utilize meory space with high eff.,max utilization , less fragmentation 
types:
1. contigous : process store in contigous manner
2. non contogous : process is tored in non contigous manner
contigous:
1. fixed partition : memory is divided into equal parts
and then that equal parts process is assigned ex 5 mb dived into 5 pars of 1 mb but if process is of 500 kb so memory is wastage and internal fragmentation will be there as internal memory is not full uitlized
best fit means choose the fragment which is more closer to size of process

2. var. contigous partition sys :
in this we allocate that much of space tot the process that is needed nothing more so no internal frag.
like if process came which is = of size 100 kb only give 100 kb fro 1000 to 1100 for example next process cam of size 300kb so now next process will be from 1100 to 1400 kb
problem : take example if a process is complete and it is present b/w two prcess now that b/w space will still be vacant u can solve it by like moving all process to one sid e 
