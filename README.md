# Rendfejl-backup - Weboldal mentése az utókornak


### MakeYourMealModul: https://github.com/barnass1/MakeYourMeal-Modul.git
### Támogató modul: https://github.com/boginadudvari/RF-Support-modul.git

# DNN Weboldal Visszaállítása

1. **Weboldal fájlok**  
   Töltsd le és csomagold ki a `dnn_mentes.zip` fájlt a következő helyre:  
   `C:\Website\dnndev.me`.

2. **IIS beállítás és mentés**  
   - Töltsd le a  `IISBackup.zip` fájlt, csomagold ki egy ideiglenes mappába, pl. `C:\IISBackup`.  
   - Győződj meg róla, hogy a kicsomagolt mappa tartalmazza a mentés fájljait (`backup.xml` stb.).  
   - Futtasd a visszaállítást az alábbi paranccsal:  
     ```powershell
     %windir%\system32\inetsrv\appcmd restore backup "IISBackup"
     ```
     
3. **Adatbázis visszaállítása**  
   - Töltsd le a `MyDNNDatabase_backup.bak` fájlt.  
   - Az SQL Server Management Studio-ban állítsd vissza az adatbázist ebből a mentésből.

4. **Web.config módosítása**  
   - Nyisd meg a `web.config` fájlt a weboldal mappájában.  
   - Állítsd be a `<connectionStrings>` részben az adatbázis eléréshez szükséges kapcsolatot.  
   - Ha nem vagy biztos benne, kérj segítséget ChatGPT-től a pontos beállításhoz.

5. **Tesztelés**  
   - Nyisd meg a böngészőt, és látogasd meg az oldalt (pl. `http://dnndev.me` vagy `http://localhost`).  
   - Ellenőrizd, hogy minden funkció megfelelően működik.
