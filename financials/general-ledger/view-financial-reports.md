---
title: "Pénzügyi jelentések megtekintése"
description: "Ez a cikk bemutatja, hogy hogyan tekintheti meg és hogyan böngészheti a Microsoft Dynamics AX rendszer pénzügyi jelentéseit. Azokról a különféle beállítási lehetőségekről nyújt tájékoztatást, amelyek segítségével módosíthatja a pénzügyi jelentések megjelenését, illetve a bennük lévő adatokat."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 632e43028c24813f00f2f71b478bbfd67c462ee4
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="view-financial-reports"></a>Pénzügyi jelentések megtekintése

[!include[banner](../includes/banner.md)]


Ez a cikk bemutatja, hogy hogyan tekintheti meg és hogyan böngészheti a Microsoft Dynamics AX rendszer pénzügyi jelentéseit. Azokról a különféle beállítási lehetőségekről nyújt tájékoztatást, amelyek segítségével módosíthatja a pénzügyi jelentések megjelenését, illetve a bennük lévő adatokat.

<a name="financial-reporting-overview"></a>Pénzügyi jelentéskészítés – áttekintés
----------------------------

## <a name="open-a-financial-report"></a>Pénzügyi jelentés megnyitása
A jelentés megnyitásához válassza ki a jelentés nevét. A jelentés első megnyitásakor, automatikusan létrejön a jelentés az előző hónapra. Például, ha 2015 augusztusában nyit meg egy jelentést először, a jelentés a 2015. július 31-i dátumhoz jön létre. Egy jelentés megnyitása után elkezdheti annak böngészését bizonyos adatok utáni leásással, illetve módosíthatja a jelentés beállításait.

## <a name="drill-down-on-a-financial-report"></a>Leásás a pénzügyi jelentésben
A pénzügyi jelentés többszintű részletességgel rendelkezhet. A pénzügyi szint az első szint, amit lát, miután megnyitja a pénzügyi jelentést. A számla szinthez válassza ki az adatot, amiben a leásást kívánja elvégezni. Például, az értékesítési számla részletes adatainak megtekintéséhez válassza ki az értékesítési adatot, amit fel szeretne fedezni. A számla szintről leáshat, hogy megnézze a tranzakciókat, amikből a számlaegyenleg áll. Kétféle módon lehet megtekinteni a tranzakciókat: jelentés tranzakciók és bizonylat tranzakciók.

-   **Jelentés tranzakciók** – A tranzakciók olyan formában jelennek meg, ahogyan a pénzügyi jelentésben is. A formázott nézethez jelölje ki az adatot, amin le akar fúrni, majd kattintson a **Leásás a jelentés tranzakció szintre** gombra.
-   **Bizonylat tranzakciók** – Egy bizonylat tranzakció lekérdezés nyílik meg, ahol megtekintheti a tranzakciókat. A tranzakciók bizonylattranzakció-lekérdezésen belüli megtekintéséhez jelölje ki azt az adatot, amelyen el kívánja végezni a leásást, majd kattintson a **Számlázási tranzakciók megnyitása** gombra.

Ha az adat költségvetési adat, dönthet úgy, hogy megnyitja a költségvetési számla bejegyzéseit. A jelentés bármely szintjének bezárásához megnyomhatja az Esc billentyűt, vagy kattintson a **Bezárás** gombra (**X**) a jobb felső sarokban.

## <a name="change-report-options"></a>Jelentés beállításainak megváltoztatása
Megváltoztathatja a jelentés dátumát, alkalmazhat attribútum és dimenzió szűrőket, vagy megváltoztathatja a költségvetés változatát az **Tény és a tervezet költségvetésének összevetése** jelentésben. A műveleti ablakban kattintson a **Jelentés beállítások**menüre, majd kövessen legalább egy lépést az alábbiak közül:

-   Az alap időszak és a jelentés alapévének megváltoztatásához válasszon ki egy alap időszakot és egy alap évet, majd kattintson az **OK**gombra.
-   Attribútum szűrő alkalmazásához egy jelentésen válassza ki az **Egy attribútum szűrő hozzáadása** lehetőséget. Válassza ki az attribútum típusát és az attribútum értékét, majd kattintson az **OK**gombra. Ha például bejelöli a **Számla kategória** attribútumot, adja az **Értékesítési** értéket az attribútumnak. Egy attribútum szűrő eltávolításához kattintson a **Törlés**gombra.
-   Dimenziószűrő alkalmazásához egy jelentésen válassza ki az **Egy dimenziószűrő hozzáadása** lehetőséget. Válassza ki a dimenziót, majd írja be a dimenzióazonosítót, vagy válassza ki a dimenziót a listából. Egy dimenzió szűrő eltávolításához kattintson a **Törlés**gombra.
-   Az eset módosításához egy **Tény és tervezet költségvetésének összevetése** jelentésen, válasszon ki egy új esetet, és kattintson az **OK**gombra. Ha a kiválasztott eset egy másik évhez tartozik, bizonyosodjon meg róla, hogy frissítette az alap évet. Például, ha az aktuális esetet az FY2015-höz tartozik, majd kiválaszt egy új esetet, ami az FY2016-hoz tartozik, akkor az alap évet a következőre kell változtatni: **2016**.

Amikor rákattint az **OK**gombra, a kiválasztott beállítások lesznek alkalmazva a jelentésre. Ha úgy dönt, hogy nem szeretné alkalmazni a kiválasztott beállításokat, kattintson a **Mégse** gombra.

## <a name="update-a-financial-report"></a>Pénzügyi jelentés frissítése
Frissíthet egy pénzügyi jelentést, hogy a jelentés készítési időszakához és évéhez tartozó legfrissebb adatokat mutassa. Például ha frissít egy 2015 októberéhez készített pénzügyi jelentést, a jelentés megmutat minden olyan új tranzakciót, amelyet 2015 októberére adtak fel. Pénzügyi jelentés frissítéséhez kattintson a Műveleti ablaktáblán a **Frissítés** gombra. A frissített jelentés csak azon személy számára elérhető, aki frissítette azt. Ahhoz, hogy mások is ugyan azokat az adatokat lássák, a jelentést közzé kell tenni.

## <a name="publish-a-financial-report"></a>Pénzügyi jelentés közzététele
Miután frissítette a pénzügyi jelentést, közzé teheti azt. Ezután a szervezet további tagjai is megtekinthetik azt. Jelentés közzétételéhez kattintson a műveleti ablakon a **Közzététel**gombra.

## <a name="display-a-financial-report-in-a-different-currency"></a>Pénzügyi jelentés megjelenítése másik pénznemben
A pénzügyi jelentés bármikor megjeleníthető bármely pénznemben. A jelentés másik pénznemben való megjelenítéséhez kattintson a műveleti ablakon a **Pénznem**gombra, majd válassza ki a pénznemet. A jelentés pénznemét átalakítja a rendszer, majd megjeleníti az eredményt. Bármely pénznemkód vagy szimbólum, ami a jelentés tervezetének a része, frissítésre kerül az új pénznemnek megfelelően. A pénznemek, amelyek szerepelnek a listában a Microsoft Dynamics AX rendszerben beállított jelentési pénznemek.

## <a name="display-a-summarized-view-of-the-financial-report"></a>A pénzügyi jelentés összefoglalójának megjelenítése
A pénzügyi jelentés részletsorokat és összesítő sorokat tartalmazhat. A részletsorok fő számlákat vagy dimenziókat tartalmazó sorok. Az összesítő sorok leíró, összesítő és számítási sorok. A jelentés összesítő sorainak kizárólagos megjelenítéséhez kattintson a **Megjelenítés**gombra, majd kattintson a **Csak összesítő sorok megjelenítése** lehetőségre. A jelentés bezárul, és csak az összesítő sorok jelennek meg. A részletsorok és az összesítő sorok együttes megjelenítéséhez kattintson a **Megjelenítése**gombra, majd kattintson a **Csak összeszító sorok megjelenítése** lehetőségre újra.

## <a name="open-a-financial-report-from-a-previous-month"></a>Egy korábbi hónap pénzügyi jelentésének megnyitása
A jelentéseket megtekintheti az aktuális, vagy a korábbi hónapokra vonatkozóan anélkül, hogy újból létrehozná a jelentést. Egy korábbi hónapra vonatkozó jelentés megnyitásához kattintson a **Megjelenítés**, majd az **Előző jelentések** lehetőségre. A korábbi hónapra vonatkozó jelentésekről létrejön egy lista. Bontsa ki a hónapot, amihez meg szeretné tekinteni a jelentést, válassza ki a dátumot, majd kattintson az **OK**gombra. Megjelenik a korábbi hónapra vonatkozó jelentés. Az aktuális havi jelentéshez való visszatéréshez kattintson a **Mégse** gombra.

## <a name="print-a-financial-report"></a>Pénzügyi jelentés nyomtatása
A pénzügyi jelentés nyomtatásához kattintson a műveleti ablakon a **Nyomtatás**gombra, majd kövesse legalább az egyiket, az alábbi lépések közül a nyomtatás beállításához.

-   A különböző szintek megjelenítéséhez a kinyomtatott jelentésben, húzza a csúszkát vagy az **Igen** vagy a **Nem** oldalra. Ha a jelentés egy jelentés fát használ, kiválaszthatja, hogy szerepeljen-e az összes jelentési egység, vagy csak a jelenlegi jelentési egység.
-   A lap méretének megadásához válassza ki a lap méretét a listából.
-   Az oldal elrendezésének beállításához, válassza ki az elrendezés típusát a listából. Ha azt szeretné, hogy a jelentés tartalma elférjen a megadott szélességen, állítsa a csúszkát az **Igen**oldalra.
-   Az oldal margóinak beállításához írja be a felső, alsó, bal és jobb oldali margó méretét hüvelykben.

Miután befejezte a nyomtatási beállítások megadását, kattintson a **Nyomtatás** gombra a jelentés nyomtatásához. Ha úgy dönt, hogy nem szeretné kinyomtatni a jelentést, kattintson a **Mégse** gombra. Megjelenik a jelentés nyomtatási képe. Kiválaszthatja, hogy melyik nyomtatóval nyomtatja ki a jelentést, és módosíthatja a nyomtatási beállításokat.

## <a name="export-a-financial-report"></a>Pénzügyi jelentés exportálása
Jelentés exportálásához kattintson a műveleti ablakon az **Exportálás** gombra. A jelentés Microsoft Excelbe lesz exportálva, majd a böngésző megkérdezi, hogy megnyitni vagy menteni akarja-e az exportált fájlt. Az exportálási beállítások, amik a jelentésre vonatkoznak, alkalmazva lesznek az exportált jelentésre.    

<a name="see-also"></a>Lásd még
--------

[Pénzügyi jelentéskészítés a Microsoft Dynamics AX rendszerben](/dynamics365/operations/dev-itpro/analytics/financial-reporting-intro)




