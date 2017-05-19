---
title: "Pénzügyi jelentés elkészítése"
description: "Ez a témakör általános tájékoztatást tartalmaz a pénzügyi jelentések létrehozásával kapcsolatban."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 13bef3abc381a903bf48daa18ef01b07103ef9ea
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="generate-a-financial-report"></a>Pénzügyi jelentés elkészítése

[!include[banner](../includes/banner.md)]


Ez a témakör általános tájékoztatást tartalmaz a pénzügyi jelentések létrehozásával kapcsolatban. 

A jelentés létrehozásához nyissa meg a jelentésdefiníciót, majd kattintson a Létrehozás gombra az eszköztárban. Az ekkor megnyíló Jelentés-várólista állapota ablak mutatja a jelentés helyét a várólistában. Alapértelmezés szerint a létrehozott jelentés a Webes megjelenítőben nyílik meg.
| ![Megjegyzés](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Megjegyzés")**Megjegyzés**        |
|------------------------------------------------------------------------------------------------|
| Csak olyan mappákba és helyekre hozható létre jelentés, amelyekhez hozzáférési engedéllyel rendelkezik. |

Az alábbi táblázatban a jelentések létrehozásához rendelkezésre álló beállítások magyarázata látható.

| Lehetőség                                                                                | További információ |
|---------------------------------------------------------------------------------------|----------------------|
| Állítson be egy ütemezést jelentés vagy jelentéscsoport automatikus létrehozásához              |                      |
| Győződjön meg arról, hogy a jelentésből nem hiányoznak számlák vagy adatok, és ellenőrizze a jelentés pontosságát |                      |

Jelentés készítésekor az Ön által a Jelentésdefiníció lapon megadott beállításokat használatosak. A Kimenet és Elosztás lapon megadhatja a jelentéstár helyét, amellyel egyszerűen megoszthatja a jelentést.

## <a name="schedule-report-generation"></a> Jelentés létrehozásának ütemezése
Számos vállalat rendelkezik egy olyan alapvető jelentéscsomaggal, amelyet az üzleti folyamatokhoz való igazodás érdekében ütemezett időközönként lefuttatnak. Lehetősége van egy jelentés rendszeres (például napi, heti, havi vagy évi) létrehozásának beütemezésére. Ez lehet egyetlen jelentés vagy egy több vállalatot is magában foglaló jelentéscsoport. Meg kell adnia minden egyes feltüntetett vállalat hitelesítő adatait, például azokat, amelyek egy jelentési fa definíciójában szerepelnek. Amennyiben a hitelesítő adatok nem érvényesek, a jelentés csak azokat az adatokat jeleníti meg, amelyekhez hozzáférési engedéllyel rendelkezik, például csak azt a vállalatot, amelyhez abban az időpontban be van jelentkezve. A kimeneti információ leolvasása elsőként a jelentéscsoportból, ezt követően pedig az egyes jelentésekből történik.

Jelentésütemezések létrehozásakor és mentésekor azok a navigációs ablaktáblában jelennek meg, a Jelentésütemezések alatt. A jelentések rendezéséhez mappákat hozhat létre. Ha egy ütemezésben nem fut egy jelentés, az összes többi jelentés futtatása folytatódik.
| ![Fontos](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Fontos")**Fontos**                                                                                                           |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jelentésütemezések létrehozásához, módosításához és törléséhez tervező vagy a rendszergazda szerepkörrel kell rendelkeznie. Jelentés futtatásakor a annak a felhasználónak a hitelesítő adatait használja a rendszer a jelentés létrehozásához, aki az ütemezést készítette. |

### <a name="create-a-report-schedule"></a>Jelentésütemezés létrehozása

1.  A Jelentéstervező Fájl menüjében kattintson az Új lehetőségre, majd válassza a Jelentésütemezés lehetőséget. Megnyílik az Új Jelentésütemezés párbeszédpanel.
2.  A Beállítások pont alatt válasszon egy jelentést vagy jelentéscsoportot, amelyet ütemezni kíván. Csak azok ahhoz a vállalathoz vagy építőelemhez tartozó jelentések vagy jelentéscsoportok érhetőek el, amelyhez éppen be van jelentkezve.
3.  A jelentésütemezés bekapcsolásához jelölje be az Aktív jelölőnégyzetet. Csak a jelentés létrehozója vagy egy rendszergazda teheti a jelentésütemezést aktívvá vagy inaktívvá.
4.  Kattintson az Engedélyek gombra a vállalati hitelesítő adatok beviteléhez. Alapértelmezés szerint a rendszer ahhoz a vállalathoz tartozó bejelentkezési adatokat használja, amelyikhez éppen be van jelentkezve. Amennyiben más vállalatok is szerepelnek, például a jelentési fák definícióiban, válassza ki a következőt: Különálló hitelesítő adatok használata, majd adja meg a jelentésütemezésben szereplő minden más vállalat hitelesítő adatait. Választhatja a Windows-hitelesítés lehetőséget, vagy írja be minden vállalathoz a felhasználónevet és a jelszót. Az ezekhez a vállalatokhoz tartozó hitelesítő adatok mentéséhez jelölje be a Hitelesítő adatok mentése jelölőnégyzetet, majd kattintson az OK gombra a párbeszédpanel bezárásához.
5.  A Gyakoriság lehetőségen belül az Ismétlődés kezdete mezőben válassza ki az ütemezés kezdő dátumát. Alapértelmezés szerint az ügyfélszámítógép aktuális rendszerdátuma kerül kiválasztásra.
6.  A Jelentés futtatása ekkor: mezőben válassza ki a jelentés futtatásának kívánt időpontját. Ha olyan időpontot ad meg, amely megelőzi az aktuális rendszeridőt, a jelentés a következő ütemezett dátumon fut le.
7.  Az Ismétlődési szabály területen adja meg, milyen gyakran fusson a jelentés. Alapértelmezés szerint a Napi lehetőség van kiválasztva és az Időtartam (napok) értéke 1. Egyéb lehetőségek: hetente, havonta és évente.
8.  Az Ismétlődés tartománya területen válassza ki, mikor fejeződjön be a jelentés létrehozása.
    -   Nincs záró dátum – a jelentésütemezés határozatlan ideig fut.
    -   Ismétlődések számának beállítása – a jelentésütemezés a megadott számú alkalommal lefut, majd inaktiválódik.
    -   Befejezés ekkor: – a jelentésütemezés a megadott dátummal befejeződik.

9.  Kattintson az eszköztár Mentés gombjára. A Mentés másként párbeszédpanelen írja be a jelentésütemezés egyedi nevét és leírását.

Jelentésütemezés másolásához tervező vagy a rendszergazda szerepkörrel kell rendelkeznie. A jelentés még abban az esetben is megtartja a jelentést létrehozó felhasználó hitelesítő adatait, ha a jelentésütemezést egy rendszergazda módosította.
### <a name="copy-a-report-schedule"></a>Jelentésütemezés másolása

1.  A Jelentéstervező navigációs ablakában kattintson a Jelentésütemezések lehetőségre, és nyisson meg egy másolni kívánt jelentésütemezést.
2.  A Fájl menüben kattintson a Mentés másként lehetőségre, majd adja meg az ütemezés új nevét és leírását a Mentés másként párbeszédpanelen. Kattintson az OK gombra, és az új ütemezés megjelenik a navigációs ablakban.
3.  Az új ütemezésben igény szerint módosítsa a mezőket és adatokat, majd kattintson a Mentés gombra az eszköztáron, vagy kattintson a Mentés lehetőségre a Fájl menüben.

Jelentésütemezést csak a jelentésütemezés tulajdonosa vagy egy rendszergazda szerepkörű felhasználó törölhet.
### <a name="delete-a-report-schedule"></a>Jelentésütemezés törlése

1.  A Jelentéstervező navigációs ablakában kattintson a Jelentésütemezések lehetőségre.
2.  Válassza ki a törölni kívánt jelentésütemezést, majd kattintson a Törlés gombra, vagy nyomja meg a Delete billentyűt.
3.  A törlés megerősítésének párbeszédpanelén kattintson az Igen gombra, hogy véglegesen törölje a jelentésütemezést. Ha az ütemezés törléséhez nem rendelkezik engedéllyel, egy üzenet jelenik meg és a jelentés nem törlődik.

### <a name="credentials-and-report-schedules"></a>Hitelesítő adatok és jelentésütemezések

Amennyiben nem adja meg a jelentésekben szereplő összes vállalathoz szükséges hitelesítő adatokat, a jelentésütemezés mentésekor a következő üzenet jelenik meg: „Meg kell adnia az ebben a jelentésütemezésben szereplő vállalatokra vonatkozó hitelesítési adatokat. Kattintson az Engedélyek gombra a hitelesítő adatok beviteléhez.”

Például Lilla bejelentkezik „A” Vállalatba saját bejelentkezési nevével és jelszavával. Létrehoz egy ütemezést egy olyan jelentéshez, amely több vállalattól való adatgyűjtésre használ egy jelentési fa definíciót. A jelentésütemezés mentésekor Lillának be kell vinnie a jelentési fa definíciójában megadott más vállalatok hitelesítési adatait. A hitelesítő adatok lejárta esetén a program nem hozza létre az érintett jelentéseket a jelentésütemezésben, amíg a hitelesítési adatok frissítése meg nem történik. Megjelenik egy üzenet a jelentés-várólistán, jelezve, hogy az engedélyeket frissíteni kell. A jelentésütemezés sikertelen lesz, amennyiben a következő esetek közül bármelyik teljesül (mivel ezekhez hitelesítő adatok szükségesek):
-   Új vállalatot adtak hozzá egy egyedi jelentés jelentési fájához.
-   Egy jelentéscsoport egyik jelentését módosították.
-   Egy másik vállalat egy új jelentését hozzáadták egy jelentéscsoporthoz.

A folytatáshoz kattintson az Engedélyek gombra a Jelentés ütemezése párbeszédpanelen, majd adja meg a megfelelő hitelesítő adatokat.

## <a name="missing-account-analysis-feature"></a> Hiányzó számla elemzése funkció
Rákereshet egy építőelem-csoport minden sordefiníciójában, jelentésifa-definíciójában és jelentésdefiníciójában az esetleges hiányzó pénzügyi számlákra és dimenziókra. Akkor hasznos, ha rövid idő alatt több számla vagy építőelem létrehozását vagy frissítését hajtja végre, és ellenőrizni akarja, hogy a jelentéseiben minden új információ szerepel.

A sordefiníció vagy jelentési-fa definíció legalacsonyabb és legmagasabb értékeinek használatával meghatározza a hiányzó számlákat, majd megjeleníti a sordefinícióban vagy jelentési-fa definícióban nem szereplő, de a pénzügyi adatokban megtalálható számlák listáját. Ha egy hiányzó számla nagyobb vagy kisebb mint a sordefinícióban szereplő értékek, akkor az nem szerepel a hiányzó számlák listájában.
| ![Tipp](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Tipp")**Tipp**                                             |
|----------------------------------------------------------------------------------------------------------------------------------|
| Ellenőrzés céljára, havi jelentések és új építőelemek létrehozása előtt futtassa ezt a folyamatot. |

Értéktartományokat tartalmazó jelentésekből kevésbé valószínű, hogy hiányzik számla. Amikor csak lehetséges, újonnan létrehozott számlák szerepeltetéséhez használjon tartományokat az építőelemben. Ha bármely jelentésdefiníció értéke @ANY vállalat, akkor bejelentkezhet egy adott vállalathoz és arra vonatkozóan hiányzó számlaelemzést futtathat.
| ![Megjegyzés](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Megjegyzés")**Megjegyzés**                                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ha új vállalat hozzáadására került sor, hozzá kell adnia azt a meglévő jelentések jelentési fáihoz, különben a vállalat nem fog szerepelni a hiányzó számla elemzésben. |

### <a name="run-missing-account-analysis"></a>Hiányzó számla elemzés futtatása

1.  A Jelentéstervezőben kattintson az Eszközök lehetőségre, majd a Hiányzó számla elemzés lehetőségre.
2.  A Vállalat szűrő mezőben válasszon ki egy vállalatot, amely szerint szűrni kívánja az eredményeket, vagy válassza az Összes (nincs szűrés) lehetőséget az összes elérhető vállalat eredményeinek megjelenítéséhez.
3.  A Dimenziószűrő mezőben válasszon ki egy dimenziót, amely szerint szűrni kívánja az eredményeket, vagy válassza az Összes (nincs szűrés) lehetőséget minden elérhető dimenzió minden dimenzióadatának megtekintéséhez.
4.  A Csoportosítás alapja: mezőben válasszon ki egy lehetőséget az eredmények rendezéséhez. Az eredményeket rendezheti az érintett építőelem szerint, vagy dimenzió és értékkészlet szerint.
5.  A megjelenített eredmények megtekintése. Amikor kiválaszt egy elemet a felső ablakban, az alsó ablak további információkat jelenít meg arról. Ez magában foglalja a kapcsolódó dimenziókat, értékeket és jelentéseket.
6.  Az érintett elem megnyitásához kattintson a listaablakon megjelenített társított ikonra, vagy kattintson a jobb egérgombbal az elemre és válassza a Megnyitás lehetőséget. Több elem kijelöléséhez tartsa lenyomva a Ctrl billentyűt, miközben az alsó ablakban kiválasztja az elemeket.
7.  Ha bármilyen, analízisben szerepeltetni nem kívánt értéket, építőelemet vagy jelentést kap vissza, az elem listából való eltávolításához kattintson a jobb egérgombbal az elemre és válassza a Kizárás lehetőséget, vagy jelölje be a Kizárás jelölőnégyzetet az elem mellett. A kizárt elemek a lista frissítése után már nem szerepelnek. Több elem kijelöléséhez tartsa lenyomva a Ctrl billentyűt, miközben az alsó ablakban kiválasztja a elemeket. Minden elem megtekintéséhez – beleértve a korábban kizárásra kijelölt elemeket – jelölje be a Kizárt építőelemek és értékek megjelenítése jelölőnégyzetet, majd kattintson a Frissítés gombra.
8.  Kattintson a Frissítés gombra a kiválasztott elemek frissítéséhez. Kattintson az Igen gombra az összes eredményre vonatkozó teljes frissítés végrehajtásához, vagy kattintson a Nem gombra a kiválasztott elemekre vonatkozó részleges frissítés végrehajtásához.
    | ![Megjegyzés](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Megjegyzés")**Megjegyzés**                    |
    |------------------------------------------------------------------------------------------------------------|
    | A képernyő automatikusan frissül megnyitáskor, kivéve, ha a képernyő meg lett nyitva az utolsó 15 percben. |

9.  Amikor megoldódtak a problémák, kattintson az OK gombra a párbeszédpanel bezárásához.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Billentyűparancsok a hiányzó számla elemzéshez
Hiányzó számla elemzésekor a következő billentyűparancsok használhatók.

| Teendő:                           | Billentyűparancs: |
|--------------------------------------|----------------------------|
| Szűrés vállalat szerint                    | ALT + C                      |
| Szűrés dimenzió szerint                  | ALT + D                      |
| A Csoportosítás alapja: mező kiválasztása            | ALT + G                      |
| Kizárt építőelemek és értékek megjelenítése      | ALT + S                      |
| Eredmények frissítése                      | ALT + R                      |
| A kijelölt építőelem kizárása  | ALT + X                      |
| A kiválasztott sordefiníció kizárása  | Ctrl + B                     |
| Az kiválasztott dimenzióérték kizárása | Ctrl + D                     |
| A kiválasztott jelentésdefiníció megnyitása  | Ctrl + R                     |
| A kiválasztott sordefiníció megnyitása     | Ctrl + O                     |

 
<a name="see-also"></a>Lásd még
--------

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)

[Jelentéstervező felület](report-designer-interface.md)



