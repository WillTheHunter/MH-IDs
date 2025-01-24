---
### Prerequesits
* romfs dump from MH3U. (Citra can dump it for you)
* A hex editor of your choice. I like HxD, 010 works great too. (Photos will be of HxD if you want to follow along easier.)
---
* First step is checking IDs. All IDs for 3U are on this page because they can't be checked via kiranico like other games. Armour is [here](https://github.com/Jemdot/mh-things/wiki/MH3U-Armor-IDs) and weapons are here.
* Once you have the ID noted for both the base gear piece and the one you want to mog it to, we need to navigate to the proper folder to find the gear piece in our game dump. 
* Weapon files will be in \dump\romfs\00040000000AE400\arc\weapon\mod\wXX. Weapon type ID can be found [here](https://github.com/Jemdot/mh-things/wiki/Weapon-IDs). 
![image](https://github.com/Jemdot/mh-things/assets/122663239/e42c863c-b755-4d76-879b-c4019b02bca8) 
* Armour files will be in \dump\romfs\00040000000AE400\arc\player\mod\, f or m depending on gender, then the folders will contain all the gear of a set by ID.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/39b7afb2-d315-4dcb-8c5d-d3ddd4f0c52a)  

* We need to find the file for the gear piece we want to use as the transmog. 
* For the weapon example I'm going to be applying lucent bow to brachy bow. So the file we need to find here is w10_35.arc  
![image](https://github.com/Jemdot/mh-things/assets/122663239/6daacd96-7b36-45ca-8772-cfc7bb25e3d9)
* For a armour example I'll apply the leather headpiece to Gigginox helm X.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/64aa325c-7959-4aae-ac3d-037f33f3ffcf)  
* Once you have the files for your gear, we need to open them in our hex editor. 
* It's not mandatory but to make it easier to read you can set the bytes per row to 80.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/5bf04784-f41a-45ed-af30-87f506aca12d)
![image](https://github.com/Jemdot/mh-things/assets/122663239/50e55b4a-8764-4fd3-b24b-92607d15ab58)  
* This should result in the decoded text on the right lining up nicely.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/df1a52dd-58ef-4d46-b598-27527b7691eb)
![image](https://github.com/Jemdot/mh-things/assets/122663239/2afef44b-cd84-4618-9028-94b82d8b0329)
  
* We want to change the non BM values to be the gear we're applying the mog to. 
* So for Giggi helm X, thats 094, and for brachy bow, it's 037. Make sure you get both values per line neccessary.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/f6bfe8dd-3086-4840-ad80-2766f4447bfe)
![image](https://github.com/Jemdot/mh-things/assets/122663239/6736a9e1-960d-4fb0-b826-42aa06a77b71)  
* Now we can save the files, and additionally change the filename to the piece of gear we're applying to. 
 
![image](https://github.com/Jemdot/mh-things/assets/122663239/71ff819c-63db-42ba-8dfa-87dbcfe3fb03)
![image](https://github.com/Jemdot/mh-things/assets/122663239/bd50a0bb-3648-4dd4-9abf-236900909086)
![image](https://github.com/Jemdot/mh-things/assets/122663239/12451495-5921-4b7e-af3e-c282571cb354)
![image](https://github.com/Jemdot/mh-things/assets/122663239/7e59144a-6794-4370-9415-25c957c7cd67)  
* Finally, we need to place these files in our citra mods folder with proper filestructure for layeredFS.
* You MUST mimic the file directory properly or it won't load in game.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/b1afd5dc-36a0-47b1-a001-a366c3ca1a4e)
![image](https://github.com/Jemdot/mh-things/assets/122663239/ebae5fd1-101a-41ac-ab4e-e5a23dc9b044)
* Thats it, you should be able to load your game now and see the changes applied. This doesn't use any texture replacements so will function with HD texture packs and the like.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/0c3e9af5-81ea-4bf1-9ab2-b43288544d7e)  








