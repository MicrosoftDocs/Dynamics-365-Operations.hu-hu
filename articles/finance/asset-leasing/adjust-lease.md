---
title: Lízingek kiigazítása
description: A témakör azt mutatja be, hogyan lehet beállítani egy lízinget. Előfordulhat, hogy kiigazításra van szükség a lízingfeltételek módosításakor, a lízing meghosszabbításakor vagy más körülmény változásakor.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1dce99e9fb553cce8de9cefc7e01c8755e9d2090
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825771"
---
# <a name="adjust-leases"></a>Lízingek kiigazítása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A témakör azt mutatja be, hogyan lehet beállítani egy lízinget. Előfordulhat, hogy kiigazításra van szükség a lízingfeltételek módosításakor, a lízing meghosszabbításakor vagy más körülmény változásakor. Az eszközök lízingelése megfelel a 842 (ASC 842) és a nemzetközi pénzügyi beszámolási szabvány 16. (IFRS 16) szerinti számviteli szabványoknak, amelyek a lízing módosítását írják elő. Az ASC 842-20-15-1 meghatározza a lízing módosítását olyan szerződések feltételeinek bármilyen változása esetén, amelyek a lízing hatókörét vagy ellenértékét eredményezik. Az IFRS 16 39. pontja szerint a lízingbevevőnek át kell értékelnie a lízingkötelezettséget, hogy az tükrözze a lízingdíjfizetések változását.

Az ASC 842 vagy IFRS 16 szabványoknak megfelelő szervezetek esetében a lízinget újra kell mérni, hogy a jövőbeli minimális lízingdíjfizetések jelenértéke (PVFMLP) változását tükrözzék. Ha a PVFMLP növekszik, akkor a létrehozott naplóbejegyzés tartozik a használatijog-eszközszámlához (ROU), valamint az új PVFMLP és az előző PVFMLP közötti különbséghez a lízingkötelezettség számlájára történő jóváírás. Ha a PVFMLP csökken, akkor a naplóbejegyzés tartozik a lízingkötelezettség számlájához, és különbözet a ROU-eszközszámlához tartozó jóváíráshoz.

Ha a korrekció a ROU-eszköznek a 0 (nulla) alá csökkenti az értékét, akkor a program jóváírja a maradékot a **Lízing feladási számlák** lapon megadott nyereségre a lízing módosítási számláján. Ezeknek a tranzakcióknak és egyéb helyesbítési bejegyzéseknek a rendszerszámlái, mint például az osztályozási változtatások, a kezdeti közvetlen költségek, a lízingösztönzők, az előlegek és a lízingmódosításokból eredő kiadások.

A lízingkorrekciós tranzakciókkal kapcsolatos konkrét útmutatást lásd az IFRS 16 és ASC 842 szabványban.

## <a name="lease-adjustment-wizard"></a>Lízingkorrekciós varázsló

Lízing módosítását a következő lépésekkel végezheti el. A módosított adatok frissítik a lízingütemezéseket, miután elvégzi a feladást a **Lízingkorrekció** varázslóból. A munkát mentheti és bármikor bezárhatja a varázslót, majd később visszatérhet és folytathatja a munkát.

A **Lízingkorrekció** varázslónak a lízingösszegzésből való megnyitásához kövesse ezeket a lépéseket.

1. Lépjen az **Eszközlízing \> Lízingek \> Lízingösszesítő** felületre. 
2. Válassza ki a módosítani kívánt lízinget, majd válassza a **Korrekciós varázsló** lehetőséget.
3. Kövesse a varázslóban megjelenő kérdéseket a szükséges módosítások beírásához.

Már folyamatban lévő módosítás esetén a **Lízingkorrekció** varázsló **Lízingkorrekciók** oldalról történő megnyitásához hajtsa végre ezeket a lépéseket.

1.  Lépjen a **Lízing \> Lízingek \> Lízingkorrekciók** lehetőségre.
2.  Válasszon egy **Folyamatban** beállítási állapotú lízinget, majd válassza a **Korrekciós varázsló** lehetőséget.
3.  A **Módosítás kezdő dátuma** és **Feladási dátum** mezőben adja meg a megfelelő dátumokat.
4.  Válassza ki **Következő** lehetőséget.

    A lízinget most hozzáadta **Lízingkorrekciók** laphoz, ahol beírhatja az új információkat.

    A lízing korrekciója után a ROU-szempontok mezői vonatkoznak rá. Ha nincs kezdeti közvetlen költség, lízingösztönzők, előlegek vagy lebontási költségek vannak társítva a módosított lízinghez, akkor a megfelelő mezőket üresen kell hagyni. Az eredeti összegek nem vonatkoznak a frissített lízingre. 

    Egy bérbeadó például egy 1.000 dollár ösztönzést nyújt a lízingkiegészítéshez való hozzájáruláshoz. Ebben az esetben a lízingkiterjesztéskor történő elszámoláskor az **1000** értéket kell megadni a **Korrekcióból származó lízingösztönzők** mezőben.

    A fizetési ütemezés sorai most a hónapból és a későbbi hónapokból származó összes kifizetést mutatják a **Módosítás kezdő dátuma** mezőben. Mivel a módosítások potenciálisak, a fizetési ütemezés sorai nem kezdődhetnek a módosítás kezdete előtt. A módosítás kezdő dátuma előtti fizetési ütemezési sorok megtekintéséhez lépjen a **Lízingverzió előzménye** lapra.

8.  Válassza ki **Következő** lehetőséget.

    A következő oldalon megjelennek a várható lízingkorrekciókra vonatkozó kulcsfontosságú adatok, mint például a lízingkötelezettségnek a módosítás előtti raktári értéke, valamint az új várható lízingkötelezettség a módosítás után. A lapon a várható lízingkorrekció naplóbejegyzésének előnézete is megjelenik.

9.  Válassza a **Küldés a munkafolyamatba** lehetőséget, ha a lízingkorrekciót be kell nyújtani a munkafolyamat-rendszerbe, ha a lízingmódosítási munkafolyamat aktív, és a kiigazítást még nem hagyták jóvá. A lízingkorrekciós munkafolyamat használatáról a [Lízingkorrekciós munkafolyamatok használata](use-create-lease-wrkflw.md) című témakörben talál további információt.

    > [!NOTE]
    > Ezen a ponton a rendszer újraszámítja a kiigazítási változókat, hogy ellenőrizze, hogy a korrekciós áttekintés és a naplóbejegyzés kiigazításának első számítása óta nem történt-e tranzakció feladása a lízingbe. Ha bármelyik érték megváltozik, frissül a kiigazítás áttekintő rácsa, és a lízingmódosításoknak a munkafolyamat rendszerbe való újraküldése előtt áttekintheti az adatokat.

10. Ha egy munkafolyamat nem aktív, vagy ha a lízingkorrekció jóvá van hagyva, akkor a módosítások feldolgozásához és a korrekciós naplóbejegyzés feladához válassza a **Befejezés** lehetőséget.

    > [!NOTE] 
    > Ezen a ponton a rendszer újraszámítja a kiigazítási változókat, hogy ellenőrizze, hogy a korrekciós áttekintés és a naplóbejegyzés kiigazításának első számítása óta nem történt-e tranzakció feladása a lízingbe. Ha bármelyik érték megváltozik, frissül a kiigazítás áttekintő rácsa, és a **Befejezés** lehetőség kiválasztása előtt áttekintheti a módosításokat. Ha a munkafolyamat aktív, és a lízingkorrekciót jóváhagyták, a korrekció áttekintésének bármely módosítása azt fogja okozni, hogy a jóváhagyási állapot **Nincs elküldve** állapotúra áll vissza. Ebben az esetben újra el kell végeznie a lízingkorrekciót a munkafolyamat-rendszerben.

    A **Lízingkorrekciók** lapon a kiigazítás állapota **Befejeződött** lesz.

    A **Lízingkorrekciók** lapon továbbra is megtekintheti a **Kiigazítás áttekintése** és a **Kiigazítási bejegyzés előnézete** gyorslapot. A lízingadatok és dátumadatok megjelennek a lízing verzióelőzményében.

    A módosított adatok felhasználásával létrejön egy új lízingverzió és egy új ütemezéskészlet. 

13. Az új ütemezések megtekintéséhez lépjen a lízingre, majd válassza a **Könyvek** lehetőséget.
14. Az újonnan létrehozott fizetési ütemezés megtekintéséhez válassza a **Fizetési ütemezés** lehetőséget.
15. Ha meg szeretné tekinteni az új információkból létrejövő új lízingkötelezettség amortizációs ütemezését, zárja be a **Fizetési ütemezés** lapot, majd nyissa meg a **Kötelezettség amortizációs ütemezése** lapot.
16. Az újonnan létrejövő eszközértékcsökkenési ütemezés megtekintéséhez nyissa meg az **Eszköz értékcsökkenési ütemezése** lapot a **Könyv részletei** oldalon.
17. A naplóbejegyzés kiigazításának megtekintéséhez válassza ki a **Naplók \> Eszköz lízingcsoport** lehetőséget.

## <a name="cancel-a-lease-adjustment"></a>Lízingkorrekció visszavonása

A folyamatban lévő lízingkorrekció törléséhez hajtsa végre a következő lépéseket.

1.  Lépjen a **Lízing \> Lízingek \> Lízingkorrekciók** lehetőségre.
2.  Válassza ki a visszavonni kívánt, folyamatban lévő lízingkorrekciót.
3.  Válassza a **Korrekció visszavonása** lehetőséget. 
4.  Válassza ki az **OK** lehetőséget.

    > [!NOTE] 
    > Ha a **Lízingkorrekció** varázslóban a **Mégse** lehetőséget választja, akkor a varázslóban végzett legutóbbi módosítást visszavonja, de a folyamatban lévő korrekciót nem távolítja el.

## <a name="use-the-lease-adjustment-workflow"></a>A lízingkorrekciós munkafolyamat használata

Ez a szakasz bemutatja a lízingkorrekciós munkafolyamat használatát. A lízingkorrekciós munkafolyamat segítségével egységes módon kezelheti a lízingkorrekciókat, megadva a jóváhagyási lépések egy készletét, és hozzárendelve azokat az egyes felhasználókhoz, akik jóváhagyják a lízingkorrekciót, mielőtt az véglegessé válna. Miután a lízingkorrekciót jóváhagyták a munkafolyamatban, a **Lízingkorrekció** varázslóval befejezheti a lízingkorrekciót.

1.  A lízingkorrekció jóváhagyásra történő benyújtásához lépjen a **Lízing \> Lízingek \> Lízingkorrekciók** lehetőségre.
2.  Válassza ki a módosítani kívánt lízingkorrekció azonosítóját, majd válassza a **Korrekciós varázsló** lehetőséget.
3.  A varázsló utolsó lapján válassza a **Küldés jóváhagyásra** lehetőséget.
4.  Adja meg a kiigazítással kapcsolatos megjegyzését, majd válassza az **OK** gombot.

    A munkafolyamat állapota **Jóváhagyásra vár** értékre módosul, és a varázsló minden mezője zárolva van a szerkesztéshez.

5.  A lízingkorrekció jóváhagyásához lépjen a **Lízing \> Lízingek \> Lízingkorrekciók** lehetőségre.
6.  Válassza ki a lízingkorrekció lízingazonosítóját, és tekintse át a **Kiigazítás áttekintése** és a **Kiigazítási bejegyzés előnézete** gyorslapot.
7.  Válassza a **Munkafolyamat \> Jóváhagyva** lehetőséget.

    A **Lízingkorrekciók** lapon a munkafolyamat állapota **Jóváhagyva** lesz. Ezen a ponton a lízingkorrekció feladásra kész a naplóbejegyzés kiigazítása alapján.

8.  A lízingkorrekció feldolgozásának és a kiigazítási bejegyzés feladásához lépjen a **Lízing \> Lízingek \> Lízingkorrekciók**.
9.  Válassza ki a módosítani kívánt lízingkorrekció azonosítóját, majd válassza a **Korrekciós varázsló** lehetőséget.
10. Addig válassza a **Tovább** gombot, amíg el nem éri a varázsló utolsó lapját, majd válassza a **Befejezés** gombot.

A rendszer újraszámolja a lízinghez szükséges könyv szerinti értékeket, hogy a jóváhagyott kiigazítási változók mindig aktuálisak legyenek. Ha bármilyen változtatás történik, a jóváhagyási állapot **Vázlat** lesz, és újra be kell nyújtani a lízingkorrekciót a munkafolyamat-rendszerbe.

## <a name="view-lease-versions"></a>Lízingverziók megtekintése

Ha a lízinget kiigazították, megtekintheti a különböző verzióit. Megtekintheti a múltbeli ütemezéseket és a múltbeli lízing adatait is.

1. Válassza ki a másolni kívánt lízinget a **Lízingösszesítő** oldalon, majd a művelet ablaktáblán válassza a **Lízingverzió előzménye** parancsot.

    Ha a kijelölt lízing be van állítva, akkor a **Lízing verzióelőzmény** lap a különböző verzióit jeleníti meg. Az eredeti lízing **1**, és az azt követő verzió pedig növekvő numerikus sorrendben van.

    A kiválasztott lízingverzió esetében megtekinthetők a pénzügyi dimenziók, a szerződés részletei, a hely és a fizetési ütemezés sorai.

2. Ha meg szeretné tekinteni a múltbeli ütemezéseket, nyissa meg a **Lízingösszesítő** oldalon a módosított lízinget, válassza ki a kívánt könyvet, majd a művelet ablaktáblán válassza ki a **Könyv verziójának előzményeit**.
3. A **Könyvverzió** oldalon válasszon ki egy verziót és egy megtekinteni kívánt ütemezést.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]