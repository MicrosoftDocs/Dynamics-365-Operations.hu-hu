---
title: Kompenzációs folyamat meghatározása és eredmények kiszámítása
description: A kompenzációs folyamatokkal határozhatók meg a fix is változó kompenzációs konstrukciókba besorolt alkalmazottak új kompenzációs összegei és jutalmai.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompProcess, HRMCompProcessLine, HRMCompEvent, HRMCompEventEmpl, HcmCompensationWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 196c907521bba5440f12149abcb2fc446c2aa523
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687051"
---
# <a name="define-compensation-process-and-calculate-results"></a>Kompenzációs folyamat meghatározása és eredmények kiszámítása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A kompenzációs folyamatokkal határozhatók meg a fix is változó kompenzációs konstrukciókba besorolt alkalmazottak új kompenzációs összegei és jutalmai. A Kompenzációs folyamatok többször is futtathatók többször „mi lenne ha” elemzés elvégzéséhez, hogy az összes módosítás és beállítások helyessége ellenőrizve legyen. Ez az eljárással egy kompenzációs folyamatot hoz létre, futtatja a folyamatot létrehozása, majd megtekinti az eredményeket. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-compensation-process"></a>Kompenzációs folyamat létrehozása
1. Ugorjon a **Kompenzációkezelés** > **Folyamat** > **Kompenzációs folyamatok** lehetőséghez.
2. Kattintson az **Új kompenzációs folyamat** lehetőségre.
3. Írjon be egy értéket a **Folyamat mezőbe**.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Válasszon egy lehetőséget a **Folyamattípus** mezőben.
    * A ciklus határozza meg a kompenzáció meghatározás használt kiértékelt időszakot. Az értékelés figyelembe veszi, hogy mely pozíciókban voltak alkalmazottak, mely teljesítményminősítéseket kell számba venni, a százalékos időtartamot, ameddig az alkalmazott alkalmazva volt a ciklusban és még több minden mást. Egy ciklus kezdő dátuma lehet például az elmúlt pénzügyi év első napja.  
6. A **Ciklus kezdete** mezőben adjon meg dátumot.
    * A ciklus záró dátuma fontos, mert a dátum azt határozza meg, mely alkalmazottak voltak aktívan foglalkoztatottak és lettek besorolva egy vagy több kompenzációs tervbe.  
7. A **Ciklus vége** mezőben adjon meg dátumot.
    * A tranzakció aktivitási dátuma az a dátum, amikor az új kompenzációs díjaknak érvénybe kell lépniük. Számos vállalat néhány hónap eltéréssel dolgozik egy ciklus vége és az új kompenzációs díjak életbelépése között. Az extra időt az új kompenzáció feldolgozására és átvizsgálására használják.  
8. A **Tranzakció aktivitási dátuma** mezőben adjon meg egy dátumot.
    * Az időpont szerinti dátumot használják a változtatható kompenzációs tervek, amelyek meghatározzák egy alkalmazott jutalomösszegét az adott időpont szerunti kompenzációs díjuk alapján.  
    * A fix fizetés a százalékos felvételi sérelmével meghatározott fix kompenzációs konstrukciókhoz **használható**. A ciklus kezdete és a fix fizetés arányosított felvételi dátuma között felvett alkalmazottak megkapják a kiszámított kompenzáció 100%-át az arányos százalék helyett.  
9. A **Fix fizetés arányosított felvételi dátuma** mezőben adjon meg egy dátumot.
    * Az átvizsgálási határidő az a dátum, amikorra minden folyamateredményt át kell nézni, hogy belehessen tölteni őket egy alkalmazott kompenzációs rekordjába a tranzakció aktivitási dátuma előtt. Ez a mező csak tájékoztatásra szolgál.  
10. Írjon be egy dátumot a **Felülvizsgálati határidő** mezőbe.
11. Kattintson a **Mentés** gombra.

## <a name="set-up-the-compensation-plans-and-actions-for-a-compensation-process"></a>Kompenzációs folyamat kompenzációs konstrukcióinak és műveletének beállítása
1. Kattintson a **Beállítások** elemre.
    * A **Beállítás** oldalt használva lehet kiválasztani, hogy melyik terv legyen feldolgozva a kompenzációs folyamat részeként, valamint hogy milyen műveleteket kell végrehajtani az egyes tervek szerint.  
2. A **Terv** mezőben adjon meg vagy válasszon ki egy értéket.
3. Kattintson a **Mentés** gombra.
4. Kattintson a **Hozzáadás** parancsra.
5. Válasszon ki egy **Saját tőke** típusú műveletet a **Művelet** mezőben.
6. Kattintson a **Hozzáadás** parancsra.
7. Válasszon ki egy **Érdem** típusú lehetőséget a **Művelet** mezőben.
    * Kompenzációs műveleteket is lehet "láncba kötni" az **Előző eredmény használata** mező segítségével, hogy a kijelölt művelet az alkalmazottak alapfizetését használja-e vagy az előző művelet eredményét kiindulási pontként ezen művelet kiszámításhoz.  
8. Válassza az **Igen lehetőséget az** Előző eredmény használata **mezőben**.
9. Kattintson a **Hozzáadás** parancsra.
10. A **Művelet** mezőben válasszon egy **Általánosl** típusú műveletet.
    * A különböző kompenzációs tevékenységtípusok különböző mezőket engedélyeznek. Egy Általános kompenzációs tevékenységtípushoz egy százalékos vagy egy összegszerű növekményt lehet definiálni.  
11. Válassza a **Növekményösszeg kiválasztása** lehetőséget.
12. Az **Összeg növelése** mezőbe írjon be egy számot.
13. Kattintson a **Hozzáadás** parancsra.
14. A **Művelet** mezőben válasszon egy **Előléptetés** típusú műveletet.
    * A Promóció és az Egyéb szintváltási művelettípusok lehetővé teszik a felhasználóknak, hogy az alkalmazott kompenzációját manuálisan módosítsák. Ajánlások is lehet engedélyezni ezen, illetve más művelettípusokhoz, hogy új javasolt kompenzációs értéket lehessen megadni egy alkalmazott esetében.  
15. Kattintson a **Hozzáadás** parancsra.
16. A **Típus** mezőben válasszon ki egy lehetőséget.
    * Az fix és változó kompenzációs konstrukciók futhatnak ugyanabban a kompenzációs folyamatban.  
17. A **Terv** mezőben adjon meg vagy válasszon ki egy értéket.
    * Használja a **Fizetés engedélyezése teljesítményért** jelölőnégyzetet, ha szeretné meghatározni, hogy ki kell igazítani a fix és változó kompenzációs összegeket az alkalmazott teljesítményminősítése alapján.  
    * Az emelést felül lehet bírálni a változó kompenzációs konstrukciók esetében.  
18. Kattintson a **Mentés** gombra.
19. Kattintson a **Hozzáadás** parancsra.
20. Zárja be a lapot.

## <a name="run-the-compensation-process"></a>A kompenzációs folyamat futtatása
1. Kattintson a **Folyamat futtatása** elemre.
    * A **Feldolgozási eredmények** ellenőrzési vezérlővel megtekintheti a teljes kompenzációs folyamat feldolgozási üzeneteit, amikor a feldolgozás befejeződött.  
2. Válassza az **Igen** lehetőséget a **Feldolgozási eredmények mutatása** mezőben.
3. Kattintson az **OK** gombra.

## <a name="view-the-results"></a>Az eredmények megtekintése
1. Kattintson a **Folyamateredmények** megtekintése elemre.
2. Kattintson az **Alkalmazotti eredmények** elemre.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. Bontsa ki **a Fix kompenzáció szakaszt**.
    * Bontsa ki a gyorslapokat a folyamatok eredményeinek megtekintéséhez. Ha egy kompenzációs művelethez meg lett jelölve a **Javaslatok engedélyezése**, akkor a **Javaslat** mezők engedélyezve lesznek az adott művelethez.  
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Az eredményeket egyetlen alkalmazott esetében az **Eredmények megtekintése** gombra kattintva tekintheti meg.  
    * Felülírhatja a kiszámított kompenzációs összeget (százalék) a százalék vagy a növekményösszeg módosításával a **Javaslat** mezőkben.  
6. Adjon meg egy számot a **Javasolt százalék** mezőben.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. Adjon meg egy számot a **Javasolt százalék** mezőben.
    * Az Újraszámítás funkcióval figyelmen kívül hagyhatók egy létező rekordon végzett módosítások, és új kompenzációs eredmény hozható létre a kiválasztott alkalmazotthoz.  
    * Amikor végzett a változtatásokkal egy alkalmazotthoz esetében, módosítsa az állapotot **Jóváhagyottra**.  
9. Kattintson az **Állapot módosítása** elemre.
10. Kattintson a **Jóváhagyott** lehetőségre.
    * A rekordot a jóváhagyása után be lehet tölteni az alkalmazott hivatalos kompenzációs rekordjába. Az új kompenzáció a kompenzációs folyamathoz beállított tranzakciós dátummal lép érvénybe.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
