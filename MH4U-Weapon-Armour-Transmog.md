---
### Prerequesits
* romfs dump from MH4U. (Citra can dump it for you)
* A hex editor of your choice. I like HxD, 010 works great too. (Photos will be of HxD if you want to follow along easier.)
---
### Method
* Very first step is checking IDs. Armor can be found on the below ID pages, rest of method is the same. For weapons, go to [Kiranico](https://kiranico.com/en/mh4u) and find the weapons you want to transmog to and from.
* On the weapons pages, you want to inpsect element, and find the photo of the weapon. (Easiest way is to right click directly on the render of the weapon when you inspect.)
![image](https://github.com/Jemdot/mh-things/assets/122663239/3078d332-4dd6-417d-b0f1-cbefee80d5bf)
* So for CGore ls, our value is ken081 and saya081, or just 081. 
* Now you need to navigate to your dumped romfs, to the data folder. 
 ![image](https://github.com/Jemdot/mh-things/assets/122663239/9e1096cc-cde0-4ac7-ac12-0026c72b79b4)
* From here you want to search the ID of the weapon/armour you want to use as the transmog. (Some weapons don't show their internal name on kiranico, so check [here](https://github.com/Jemdot/mh-things/wiki/Weapon-IDs).)  So in this case, swo081.
* Make a copy and open the arc file for your equipment piece with your hex editor. 
* You can set the bytes per row to 80 to make this step easier visually, but it's not mandatory.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/601138e9-5801-49bc-b197-3e334f918a7a)  
![image](https://github.com/Jemdot/mh-things/assets/122663239/81f390a0-79cf-43d4-9a10-bc72a9f543e3)  
* This should result in the right side where the decoded text is looking like this.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/215b608e-50bc-4008-8d63-f4f1ba549d38)
* You want to change the non BM and non wave IDs to be the weapon/armour you want to transmog. 
* In this case it would be these ones.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/88e30be4-968e-4acd-a94d-94ee935b7089)
* Some weapons and armour will only have one, some will have more. LS for this example has four. 
* Remember to change both IDs per address. For the example I'm going to use the jaggi LS as our base.  
![image](https://github.com/Jemdot/mh-things/assets/122663239/dddc17e7-ccf4-4d97-a50d-892c4aab00a7)  
* Now save this file, and change the .arc filename to the base gear piece.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/45066692-bee3-433c-a0f0-dbe68d5964bb)   
![image](https://github.com/Jemdot/mh-things/assets/122663239/67072f15-bd8c-436e-965e-4871e26dd77f)  
* Now to add it to the game, open your mods directory for the game from citra.   
![image](https://github.com/Jemdot/mh-things/assets/122663239/b7425fde-9fe8-408a-b3d3-f220ab4528e2)  
* And add the file in the same structure as the game files, inside gameID/romfs/data/ like so.  
![image](https://github.com/Jemdot/mh-things/assets/122663239/60b3e0cd-8c72-40cd-83c0-b42e05397f49)  
* This works with custom textures, so no need to worry if you're using any upscales or retextures. 
* Launch game and the changes should be visible. 
![image](https://github.com/Jemdot/mh-things/assets/122663239/96dea439-59c9-4f82-8f8b-36da54243f7d)
