# os 
# memory management 
aim : to utilize meory space with high eff.,max utilization , less fragmentation 
types:
1. contigous : process store in contigous manner
2. non contogous : process is tored in non contigous manner

👨‍🦲 contigous:
1. fixed partition : memory is divided into equal parts
and then that equal parts process is assigned ex 5 mb dived into 5 pars of 1 mb but if process is of 500 kb so memory is wastage and internal fragmentation will be there as internal memory is not full uitlized
best fit means choose the fragment which is more closer to size of process

2. var. contigous partition sys :
in this we allocate that much of space tot the process that is needed nothing more so no internal frag.
like if process came which is = of size 100 kb only give 100 kb fro 1000 to 1100 for example next process cam of size 300kb so now next process will be from 1100 to 1400 kb
problem : take example if a process is complete and it is present b/w two prcess now that b/w space will still be vacant u can solve it by like moving all process to one sid e 

◀️ non contigous :
1. paging:
In this we basically used paging so here first process is divedd into pages then page table is maded where we store which page is stored where in main memory
page contain its own stck and array and extra bits
and page table is stored in main memory so two time acess karte during a processing of a process first page table to know where is partition and pages are
## theere is cal culaion see notes 
if a page size is 2b and 4 pages are there so now process size is 8byte and 2^3 so 3 bit ka address chaiye hoga usko store ke liye like ek page ab 2 byte and 8 pages hai main meroty see notes 


-----
# time to take process the req 
tlb is cache where most used pages get saved and time req to process a process is 
teff=h(timetlb+timemm)+(1-h)(time tlb+2tmm) so we can like if hit then it take from tlb and get the page from main memory if not then vis versa 
do question what is tag bit and all fully assicuate h
