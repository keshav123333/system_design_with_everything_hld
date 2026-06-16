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
