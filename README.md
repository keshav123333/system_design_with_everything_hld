# system_design_with_everything_hld


1. There is db and to accesss some info through this db we need to write query and fetch info which is hard so application layer is introduced and it ease the process and make it more interactive it use rest api to fetch info and show and by this we can secure our db to as directly giving acess to customer of our main db is not safe 

2.

<img width="516" height="220" alt="image" src="https://github.com/user-attachments/assets/0449c011-4adb-4cf1-9251-3f195f7a5395" />
like you can see in this code application code is the frontend code which is also deployer on a server from where we fetch it and use it  and when applcation code fetch info it store some info in cache which is frequently being used 

****
3. 
<img width="369" height="174" alt="image" src="https://github.com/user-attachments/assets/1193d5f3-5f0e-457e-8e19-6c7c1d8736bb" />
like now see this image in this our application frontend code is pressent at two server as single server cant handle that amount of user so now load balacer will manage like which server have less customer and send new req to them 

****
4. Message que -: used in server and all or its third party tool used by our application server to perform any task 
 like example our site have work when customer order do threet hing plcae ordr send sms and sne email now all this task can be ascynchronously handlesd how this happen so all this task is feeded in msg que and whenever anytask comlted it notify the server and do other task this msg que automatically manage if errror unko retry and all kathis do all this 

----

## data extensive application 

like this type of application tackle and heavy rely ondata so they have to manage this insta for ex need to handle so many user they write and read continously and they perform different task they have cache the memory so latency can be reduced and all 

**** 
## compute extensive appplication 

ex some site heavely rely on cpu processing and gpu processing for the task to be performed eg chagpt use llm model at backgorund ml based website here most developer worries abt these things 
<img width="546" height="281" alt="image" src="https://github.com/user-attachments/assets/e6f61458-7f0e-497d-9f98-efc9d05c104f" />
 example youtube : it data extensive as need to show videos fetch and post new videos 
 but it also compute extensive as it have to run recomendation model in background which is using its power  


----
Requirement types 
1. functional requirement : what to do eg amazon should have feature to search and filter and sort and upload buy
2. non functional requirement : site should able to handle 1 million user ,downtime should be low , response time should be high , encrption should be there , availablity time show be high [this is how we will  going to implement the req. ]
**if i wrtie this on func in good way**:
1. sclablity
2. availabltiy: for this we sign contract with cleint sla which means a agrrement that atleast at this much time we are going to available
3. reliablity: no data loss
4. performance : latency
5. security : authourization , encryption,
6. maintainablity : code should be modular : writes in different modules so that if any change we had to made we can do easily
7. observabltiy : montior the system

-----
# Dns server 
<img width="1004" height="517" alt="image" src="https://github.com/user-attachments/assets/fa2e768c-4c4e-4955-8518-35ac99b926d7" />
1.so here as you can see that when u write google.com req go to dns resolver then dns resolver find the nearest rrrot server and send req to it
2.root server check okay its .com so now direct thsi req to tld of .com and give ip add of that resolver go to that 
3. so now tld give nearest name server address this name server are godady hostingr rom where you can configure your name server now this name server finally give ip add of the site 
4. and isp then redirect him to there 

One main things also like take example keshav.com have subdomains for courses and blogs so that subdomains are belog to keshav.com but have different ip so now in name server we will create zone for keshav.com so somewone came and intead of keshav.com he hitted courseskeshav....com so now name server will know okay this courses is subdomain of keshav.com so go to its zone 

os browser and dns all three have cache in them where they save most used site ip adresses to imp thing 

-----
# Api Interface 
so u have a db and a backend now imdb example ke liye so now imdb can build a api for his db through which other can also acess data as we cant give acess of db to others as he can delte and things and using api we can restrict what to add and what not it act as protective layer and it also easy for other user to use api instead of using imdb full db

1. we also build backend frontend seprate so now frontend can call bakcend we can coide bakcend in any alguage we want and frontend in different langage


**Types of api**:
1. Rest: so rest bascially use json get post and all this is rest
2. soap: its uses xml its is not used widely now but some leagcy website still used it as its bulky and we have to handle attributes
3. graphql : in this only one end point is there through which u fetch info how ?
   it bascially use query like frontend give query this single end point recive and excute the query like sql but for api so now frontend will send query and graphql through one endpoint handle it
4. grpc remote protocol call (grpc): so its lighter then json protocol buffer size is small and used in kicroservice where ur single app is devided into microservice so as these small compo have to communicate to each other for this this use grpc as it fast and these service have to communicate fast so that can give result fast to end user

so like 
nesting : its a technique where you send data {"mesage":123} like this and in body
filtering : when u send datathrough url user?toke=skkskks like this or user/{id} like this in bakcend 


<img width="484" height="281" alt="image" src="https://github.com/user-attachments/assets/645f8175-b1c3-4275-8154-1cd29a99627f" />
so like u can see above that path means when u send data info u want in url ex there is api user/{id} now it fetch id in backend this id can be what_is_java so now backend u fetch info related to id and give to frontend so for same forntend diff data can be shown its used in insta profile too where u can see that url ur username is changes and hit same endpoint so its the case at same endpoint u can see multiple things 

-> Query parameter u send query and at backend u handle it like sort=asc so backend u handle if ac then sort the blog in asceneding etc 
-> body u send whole data 
<img width="413" height="300" alt="image" src="https://github.com/user-attachments/assets/14a96d55-bb47-4216-b261-40336c776670" />
200 OK → Success
201 Created → Resource created
204 No Content → Success, nothing returned
400 Bad Request → Client sent invalid data
401 Unauthorized → Authentication required/failed
403 Forbidden → Authenticated but not allowed
404 Not Found → Resource doesn't exist
500 Internal Server Error → Server-side problem


------
# databse 
 <img width="488" height="201" alt="image" src="https://github.com/user-attachments/assets/b7c097f7-26a8-4821-9dd5-26c2957207e3" />
so as ypu can see in sql based tbles is used whereas in nosql based data files folder is used to store the info 


## sql based 
<img width="561" height="387" alt="image" src="https://github.com/user-attachments/assets/3b1cd38f-ba43-4252-b385-74277d0652e5" />
4.  foreign key : col in a table refrence to some other col in othr table or same table 
5. default : this is used to give default value to a col 


then thre is join 
<img width="534" height="386" alt="image" src="https://github.com/user-attachments/assets/adb5f28d-35d4-4f28-b5c4-3abb4af6382e" />

here u seprate the table and other things from each other llike student and courses are seprate tables then u make a new table connecting both 

This down here is one -one relation
<img width="624" height="324" alt="image" src="https://github.com/user-attachments/assets/5992c5bf-ab6e-479c-9ee6-5a5f69127b03" />
 in this as u can see we created seprate table for video image and all and then at end we attach both of them with each other 

 Disadvantges of sql 
 as this for everything we have to vreate a table then attach taht table and connect so it need space scaling is an issue 
 why? 
 vertical scaling we add more space in same server but this limited as i mean how much u can add to single server 
 horizontal scaling u distribute your data in different server now as they are connected maintaing reln is hard like user table in some other db and post id tble in some other server 

 2. in sql like if your table column data type is seted as dict you can add fix no. of info ,
no sql use document to store info 
 in nosql  no limitation like in user is  dict so now dict can be of variable size so nosql is used where data scehma is not an issue  so that we can follow how evere you wnat to store your data 
<img width="602" height="426" alt="image" src="https://github.com/user-attachments/assets/ea192405-91d8-4f91-a277-b1c5fe91aa08" />

## No sql 
<img width="471" height="379" alt="image" src="https://github.com/user-attachments/assets/d6b2a52c-41d0-4a00-b198-d5d5387badd2" />

# YAAR YAHA PE CACH WALA PART SAVE NI KIYA THA USKO VIDEO SE EK BAAR LIKH KE ADD KAR DE PLEASE AND SAMJH LE  AND YAHA PE NO SQL KA BHI MISSING HAI TYPES AND ALL VO BHI KAR LE 






----


# LAODA BALANCER 

so google dont have only one server it have multiple server and dns dont give server ip add it give add of load balancer which then check and decide to which server to send this request 
functions of load balancer :
to choose server and observe maitain health of server 

**methods to allocate req to server**:
1. round robin : In this we basically sequentially give reqests to server and after last we once again go in starting and give request to strating server so its a cycle where every server will get equal amt of work
Disadv: as not all sevrer will have same specs and config : some server will have more ram cpu and processing power and some have less we cant give all of them equal work

2. geo based algo : it allot request to nearer sever like india will have its server and all request will go there mean load balacner choose nearer server
disadv: load balancer should have info about which server is where like indian server then chinese server every server info load balncer should have
- if a server near u is not working then it will allocate all work to other server but the server which is down should send all request to workig server that what requests and process it should process
- db maintain for every country
- vpn used then there can be issue as load blacner will hought its comming from some other place

3. least connection algo: load balancer will give the requst to server which will have least request to process
disadv first server is processig 20 heavy req ex ml req and other server is processing 50 light req like chat msg or etc but nownew req will gi to heavy req server which is not good as it will take time 

4. least time algo: so it give req to server acc to their res time like on server res time is high so next req will be tranfer to it as at any server load inc its res time dec so load balacer will now give req to other server
- it complex as load balcner have to claculate avg res time for evry server = no. of req/ time needed to process the req
- it is used where we have to like get req fast like stock pred or google searches


5. ip hash algo : in this we assign every server a ip range so now that server wil, handle req fron that range or ip but this is not good is s1 crash so req that it handling affected so s1 server have to then send all its session info to other server to maintain and i u add new server we have to config loadbalancer and server properly so that assign ip can go to that server
disadv already told old leagacy apps still use but new app where backend and frontend is seprate we dont need this as jwt token is only needed and required

6. weight round robin : in this we assign wieght to server hich have more specs so that it give priority to that server more

load balcner in real world combine two or more algo and use it 

### How load balancer check health
1. active check in this u send req to server and if its giving request on time
2. passive check u just check it health by asking it direct without giving request after time to time
and for this too there are ways to do
- intervals: u have to check ur server on certain intervals is it active
- timout : like if a req is takign more then threshold time then check like one eq taking 10 sec to process but onavg all req only take few ms so check if the code failed or serve rproblem
- threshold : after evry certain req check how much req fails if no. of failed req if more analysis why it fail does there any problem

-------
# Distributed Database

listen big comapny dont have only one db from which whole world acess the internet no if india india will have its own db and us will have its own db where it will update 
but like understand like indian db will not have all content as its really big it will have content only used in india freq if user acess to some other data our db will contact earby db for that data 

for this u can do differetn things first
- replication :same data is copied everywhere in other database too
- distribute: same  data is distributed in two or more db

## Replication 
keeping copy of data it helps in 
- spof : if one fail other handle it , availablty fast res : as if two db is there so it can handle more req and fst res will be there as req is distributed among , throughput is more

**Types of replication**:
1. single leader replication: single leader directly recvie req and update its slave db
<img width="553" height="260" alt="image" src="https://github.com/user-attachments/assets/f471a1a4-a5d0-4bec-ad2b-0cf4228dd45c" />
this is also two types
one is :
<img width="579" height="347" alt="image" src="https://github.com/user-attachments/assets/b2825720-0623-458b-b672-887fd24cede8" />
as above seen in image u can see that there can be like req came leader update db and give ok res but in backend also async update salve node
disadv :
if in this b/w leader fail so update will not be in slave db
<img width="532" height="314" alt="image" src="https://github.com/user-attachments/assets/24a77b5f-6250-46f5-9935-ea93f69ed04a" />



second sync approach :
<img width="553" height="385" alt="image" src="https://github.com/user-attachments/assets/f11b9a9b-c6fc-4923-b839-97f78fc62d78" />
so as u can see above final response only go when all slve db gets updated 
adv and disadv of sync :
<img width="367" height="244" alt="image" src="https://github.com/user-attachments/assets/4c358e75-8da2-4727-95f5-c533690cbafa" />

### Now if new db connected sho how it will connected to leader db 
so first new db will come and in this new db all content of db will be copied so tak that this copying started at 12 pm and finished at 3 pm so now these 4 hour updated content also needed to update in this db so now this 4 hr content will get coipied then finally get connected to leader

ques : if leader fail so the db which will be most updated will be next candidates for leader and every other will make this change in their system 

2. Multileader replication :
<img width="573" height="389" alt="image" src="https://github.com/user-attachments/assets/fc62dd8a-8157-43c7-b353-3cc1ade8878e" />
so here more leader is there and if u1 change in d1 it will tell its slve node and other leader node other leader node will then do thier updates
better performance and collabrative approach

<img width="714" height="414" alt="image" src="https://github.com/user-attachments/assets/1c50ede7-7165-4c7b-9f12-262451cb08c6" />
as u can see in this image here u1 rename file f1 so db1 acept the change and u2 also same time change f1 name db2 also accept when db1 db2 update this in each other they will realise that its conflicting so to avoid this there are few methods u can see in img
1. acc. to time who write last thier change will show
2. who is more poweful u1 u2 whose change will remain
3. application will ask user that two changes maded which name u prefer

3. Leader less replication :
<img width="641" height="385" alt="image" src="https://github.com/user-attachments/assets/b740a3e4-ddcd-43f7-b1f0-4dff381f2373" />
as above u can see that user req is go to every db read and write both req is go to every db it introduce some latency and take case u1 update db1 and sudden;ly send read req so from where this read req will handled if db2 still updating its prev data there can be chance that user may get stale data 

for solving this we had a mthod called as quorem 
**quorem**
so in this we send okay to user when majortiy db is updated example 3 db total and 2 of them has updated db1 db2 and db3 didnt updated yet but still will send okay when user immediately send read req  so this req also go to all db as leader less now 2 of them give updated and 1 give stale old output as updated is in mojority we will give that as res 


-----
# partition
as name suggest we will now partition the system or devide the data in more then on db such every db contein equal data not db should be overloaded or underloaded

1. partition by key:
like u store 1 to 50000 data in p1 partiton 1 and 50000 to 100000 in p2 so like whwenver req come it will go to respective partition but if req from 1 to 50000 inc then one partition is become hotspot which i not goof

2. partition by hashfunc :
so in this we try to random allcoate  data in partiton using some hash func but still chance that 1 db partiton become hotspot

3. partiton by index
liten in db when we search material = steel it dont go to whole big table and search whole row it go to a index col where it find where data is steel and then traverse that row only
<img width="1207" height="606" alt="image" src="https://github.com/user-attachments/assets/60344d92-432b-4d58-ad9e-2dd843f37cd8" />
like same if ur p1 contain db of car form 200 500 and it have blue cas from some index so every partition will have their index table req first chck if data it needed availble if not move to next db
disadv in this to he have tranverse to every db which inc load on db

4. global index
we maintain a global index of data if ser come for spefic first req go thier from thier it fetch where his target data is availabel and go thier direct 
