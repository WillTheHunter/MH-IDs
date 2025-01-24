---
###  Prerequesits 
* Your romfs dump from MHGU. (Ryujinx/Yuzu can dump it for you by right clicking > extract data/dump romfs.)
* Kuriimu and a hex editor of your choice, 010 works great, I personally use HxD when a template isn't needed. (Photos will be from HxD if you want a easier time following along.)
---
### Extracting BaseData 
* First you're going to want to make a copy of the resident.arc file found at nativeNX/loc/arc.   
![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/44dd2e92-105a-462b-97dd-690b84b85f73)
* Then you need to open this file with Karameru, a part of Kuriimu. You can find the option in the top right of Kuriimu, or through the .exe
* Once it's open, it will look like this:  
![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/8813e262-721b-4a98-969e-4cf5a57123f9)
* Next, select table on the directory tree. Scroll down on the right to the bottom, where you will see files named weaponXXLevelData and weaponXXBaseData. 
* Right click and extract the BaseData file for the weapon of your choice. IDs can be found [here](https://github.com/Jemdot/MHGU-Data/wiki/Weapon-IDs).
* Don't close Karameru just yet, we need it later. 
---
### Editing BaseData
* This is where you're going to use the hex editor. 
* First we need to set the proper bytes per row. For GS, SNS, Hammer, Lance, LS, HH, and Bow, set it to 33. SA, GL, DB, IG, and CB use 34. Guns use 32.   
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/e4773236-cc1c-40fb-970f-6c17aa0973ef)  
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/99861b02-c122-4043-b4a8-4ff731f36953)
* Next you need to get the weapon ID for the weapon you want to change, and the weapon you want to change it to. 
* Both can be found on [Kiranico](https://mhgu.kiranico.com) by finding the page of the weapon, inspecting element, and navigating to the photo of the weapon.   
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/31d4317d-15f8-4669-90e5-8d32303a9992)
* So for Mantis GS, our value is two181, or just 181. Do the same for the weapon you plan on changing it to. I'm going to use Toyohisa for the example, which is two198. 
* Now we go back to our hex editor, and search the integer value of our initial weapon. (Ctrl + F, integer number, search direction all for HxD.)  
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/ccb74ff7-1e7a-44d0-9f04-8f76cf80f1a1)
* This will find you two instances of the searched value, in columns 0C and 0E.   
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/b0e8cc3d-fedb-4e99-bdcc-dbc846870da3)
* You need to change these two values to the value of our transmog weapon. You can do this on the right panel in HxD, where it says UInt8.   
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/4de31a65-e736-4730-aeda-9acf8de7afd3)
![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/58bd36e2-fb27-40d2-a5dd-0b7d878badd3)
* Changed number should reflect on hex view.  
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/ebde63ce-811b-4943-afde-f563da9df13c)
* Now were good to save this file, and close our hex editor. 
---
### Replacing 
* Go back to Karameru, to the same place as before. Right click on the same BaseData file again, except this time select replace instead of extract. 
* Select your edited basedata file.   
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/df5c10ba-ceed-4618-855a-726812c1c2f7)
* The file will now appear in yellow to indicate that it's been changed. 
* You're now safe to save the resident.arc file, and close Karameru. 
---
### Using New resident.arc
* This isn't a switch modding page so will be assuming this is for emulator.
* Easiest way to use this is to right click the game in Ryujinx/Yuzu, and open mods directory. 
* Here you're going to create a new folder, named whatever you like. Just keep in mind you need to find this if you want to do more transmog later.   
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/879bf30b-d590-4236-9e97-2fdbc811265b)
* Inside this new folder, we need to mimic the games filesystem for layeredFS to work. So create a folder called romFS, then within that one called nativeNX, within that loc, and within that arc. Finally put our resident.arc file in the arc folder. 
* Final product should look like this:   
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/678ec1e5-9037-467e-bdb0-70538bb84a9c)
* That's it, you should be able to boot up the game now and see the changes. Sometimes they won't appear on character select screen, so make sure to load into the game fully.   
 ![image](https://github.com/Jemdot/MHGU-Data/assets/122663239/51d34c5f-3e56-44e2-8d07-d4dae8c52c21)




