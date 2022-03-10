---
title: Pénzügyi jelentések megtekintése
description: Ez a témakör bemutatja, hogy hogyan tekintheti meg és hogyan böngészheti a Microsoft Dynamics 365 Finance rendszer pénzügyi jelentéseit. Azokról a különféle beállítási lehetőségekről nyújt tájékoztatást, amelyek segítségével módosíthatja a pénzügyi jelentések megjelenését, illetve a bennük lévő adatokat.
author: kweekley
ms.date: 03/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 485d8f0aee791aa577432947d74b08caf484da0a3056d8119579e9d659ca3d57
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730506"
---
# <a name="view-financial-reports"></a>Pénzügyi jelentések megtekintése

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan tekintheti meg és hogyan böngészheti a pénzügyi jelentéseket. Azokról a különféle beállítási lehetőségekről nyújt tájékoztatást, amelyek segítségével módosíthatja a pénzügyi jelentések megjelenését, illetve a bennük lévő adatokat.

## <a name="financial-reporting-overview"></a>Pénzügyi jelentéskészítés – áttekintés

## <a name="open-a-financial-report"></a>Pénzügyi jelentés megnyitása
A jelentés megnyitásához válassza ki a jelentés nevét. A jelentés első megnyitásakor, automatikusan létrejön a jelentés az előző hónapra. Például, ha 2015 augusztusában nyit meg egy jelentést először, a jelentés a 2015. július 31-i dátumhoz jön létre. Egy jelentés megnyitása után elkezdheti annak böngészését bizonyos adatok utáni leásással, illetve módosíthatja a jelentés beállításait.

## <a name="drill-down-on-a-financial-report"></a>Leásás a pénzügyi jelentésben
A pénzügyi jelentés többszintű részletességgel rendelkezhet. A pénzügyi szint az első szint, amit lát, miután megnyitja a pénzügyi jelentést. A számla szinthez válassza ki az adatot, amiben a leásást kívánja elvégezni. Például, az értékesítési számla részletes adatainak megtekintéséhez válassza ki az értékesítési adatot, amit fel szeretne fedezni. A számla szintről leáshat, hogy megnézze a tranzakciókat, amikből a számlaegyenleg áll. Kétféle módon lehet megtekinteni a tranzakciókat: jelentés tranzakciók és bizonylat tranzakciók.

-   **Jelentés tranzakciók** – A tranzakciók olyan formában jelennek meg, ahogyan a pénzügyi jelentésben is. A formázott nézethez jelölje ki az adatot, amin le akar fúrni, majd kattintson a **Leásás a jelentés tranzakció szintre** gombra.
-   **Bizonylat tranzakciók** – Egy bizonylat tranzakció lekérdezés nyílik meg, ahol megtekintheti a tranzakciókat. A tranzakciók bizonylattranzakció-lekérdezésen belüli megtekintéséhez jelölje ki azt az adatot, amelyen el kívánja végezni a leásást, majd kattintson a **Számlázási tranzakciók megnyitása** gombra.

Ha az adat költségvetési adat, dönthet úgy, hogy megnyitja a költségvetési számla bejegyzéseit. A jelentés bármely szintjének bezárásához megnyomhatja az Esc billentyűt, vagy kattintson a **Bezárás** gombra (**X**) a jobb felső sarokban.

## <a name="change-report-options"></a>Jelentés beállításainak megváltoztatása
Alkalmazhat attribútum és dimenzió szűrőket, vagy megváltoztathatja a költségvetés változatát az **Tény és a tervezet költségvetésének összevetése** jelentésben. A műveleti ablakban kattintson a **Jelentés beállítások** menüre, majd kövessen legalább egy lépést az alábbiak közül:

-   Attribútum szűrő alkalmazásához egy jelentésen válassza ki az **Egy attribútum szűrő hozzáadása** lehetőséget. Válassza ki az attribútum típusát és az attribútum értékét, majd kattintson az **OK** gombra. Ha például bejelöli a **Számla kategória** attribútumot, adja az **Értékesítési** értéket az attribútumnak. Egy attribútum szűrő eltávolításához kattintson a **Törlés** gombra.
-   Dimenziószűrő alkalmazásához egy jelentésen válassza ki az **Egy dimenziószűrő hozzáadása** lehetőséget. Válassza ki a dimenziót, majd írja be a dimenzióazonosítót, vagy válassza ki a dimenziót a listából. Egy dimenzió szűrő eltávolításához kattintson a **Törlés** gombra.
-   Az eset módosításához egy **Tény és tervezet költségvetésének összevetése** jelentésen, válasszon ki egy új esetet, és kattintson az **OK** gombra. Ha a kiválasztott forgatókönyv egy másik pénzügyi évre vonatkozik, nem ad vissza eredményt. Ha például egy jelentés a 2015-ös pénzügyi évben lett generálva, és az aktuális forgatókönyv a 2015-ös pénzügyi évre vonatkozik, és az új kiválasztott forgatókönyv a 2016-os pénzügyi évre vonatkozik, nem lesznek visszaadva eredmények. Ha egy új forgatókönyv szükséges egy másik pénzügyi évhez, generáljon egy j verziót a jelentéshez a forgatókönyvhöz kapcsolódó pénzügyi évhez.

Amikor rákattint az **OK** gombra, a kiválasztott beállítások lesznek alkalmazva a jelentésre. Ha úgy dönt, hogy nem szeretné alkalmazni a kiválasztott beállításokat, kattintson a **Mégse** gombra.

## <a name="update-a-financial-report"></a>Pénzügyi jelentés frissítése
Frissíthet egy pénzügyi jelentést, hogy a jelentés készítési időszakához és évéhez tartozó legfrissebb adatokat mutassa. Például ha frissít egy 2015 októberéhez készített pénzügyi jelentést, a jelentés megmutat minden olyan új tranzakciót, amelyet 2015 októberére adtak fel. Pénzügyi jelentés frissítéséhez kattintson a Műveleti ablaktáblán a **Frissítés** gombra. A frissített jelentés csak azon személy számára elérhető, aki frissítette azt. Ahhoz, hogy mások is ugyan azokat az adatokat lássák, a jelentést közzé kell tenni.

## <a name="publish-a-financial-report"></a>Pénzügyi jelentés közzététele
Miután frissítette a pénzügyi jelentést, közzé teheti azt. Ezután a szervezet további tagjai is megtekinthetik azt. Jelentés közzétételéhez kattintson a műveleti ablakon a **Közzététel** gombra.

## <a name="display-a-financial-report-in-a-different-currency"></a>Pénzügyi jelentés megjelenítése másik pénznemben
A pénzügyi jelentés bármikor megjeleníthető bármely pénznemben. A jelentés másik pénznemben való megjelenítéséhez kattintson a műveleti ablakon a **Pénznem** gombra, majd válassza ki a pénznemet. A jelentés pénznemét átalakítja a rendszer, majd megjeleníti az eredményt. Bármely pénznemkód vagy szimbólum, ami a jelentés tervezetének a része, frissítésre kerül az új pénznemnek megfelelően. A pénznemek, amelyek szerepelnek a listában a Finance rendszerben beállított jelentési pénznemek.

## <a name="display-a-summarized-view-of-the-financial-report"></a>A pénzügyi jelentés összefoglalójának megjelenítése
A pénzügyi jelentés részletsorokat és összesítő sorokat tartalmazhat. A részletsorok fő számlákat vagy dimenziókat tartalmazó sorok. Az összesítő sorok leíró, összesítő és számítási sorok. A jelentés összesítő sorainak kizárólagos megjelenítéséhez kattintson a **Megjelenítés** gombra, majd kattintson a **Csak összesítő sorok megjelenítése** lehetőségre. A jelentés bezárul, és csak az összesítő sorok jelennek meg. A részletsorok és az összesítő sorok együttes megjelenítéséhez kattintson a **Megjelenítése** gombra, majd kattintson a **Csak összeszító sorok megjelenítése** lehetőségre újra.

## <a name="print-a-financial-report"></a>Pénzügyi jelentés nyomtatása
Pénzügyi jelentés nyomtatásával, egy manuálisan kinyomtatható PDF-fájlt hoz létre. Nomtatható pénzügyi jelentés létrehozásához kattintson a műveleti ablakon a **Nyomtatás** gombra, majd kövesse legalább az egyiket, az alábbi lépések közül a nyomtatás beállításához.

-   A különböző szintek megjelenítéséhez a kinyomtatott jelentésben, húzza a csúszkát vagy az **Igen** vagy a **Nem** oldalra. Ha a jelentés egy jelentés fát használ, kiválaszthatja, hogy szerepeljen-e az összes jelentési egység, vagy csak a jelenlegi jelentési egység.
-   A lap méretének megadásához válassza ki a lap méretét a listából.
-   Az oldal elrendezésének beállításához, válassza ki az elrendezés típusát a listából. Ha azt szeretné, hogy a jelentés tartalma elférjen a megadott szélességen, állítsa a csúszkát az **Igen** oldalra.
-   Az oldal margóinak beállításához írja be a felső, alsó, bal és jobb oldali margó méretét hüvelykben.

Miután befejezte a nyomtatási beállítások megadását, kattintson a **Nyomtatás** gombra a folytatáshoz, és a rendszermeg kérdezi, hogy át le szeretné tölteni a fájlt, vagy menteni ide: OneDrive vagy SharePoint. Ha úgy dönt, hogy nem szeretné folytatni, kattintson a **Mégse** gombra. Ha folytatja, a jelentés leképezése megkezdődik a kiszolgálón, és a rendszer kérni fogja, hogy töltse le a jelentést PDF formátumban. Most megtekintheti a jelentés a PDF-megjelenítőben, és innen kiválaszthatja, hogy mely nyomatatóra küldi le a jelentést, és megadhatja a nyomtatási beállításokat.

## <a name="export-a-financial-report"></a>Pénzügyi jelentés exportálása
Jelentés exportálásához kattintson a műveleti ablakon az **Exportálás** gombra. A jelentés Microsoft Excel fájlba lesz exportálva, majd a böngésző megkérdezi, hogy megnyitni vagy menteni akarja-e az exportált fájlt. Az exportálási beállítások, amik a jelentésre vonatkoznak, alkalmazva lesznek az exportált jelentésre.    

## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés](../../fin-ops-core/dev-itpro/analytics/financial-reporting-intro.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]