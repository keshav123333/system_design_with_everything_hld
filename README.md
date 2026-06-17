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
