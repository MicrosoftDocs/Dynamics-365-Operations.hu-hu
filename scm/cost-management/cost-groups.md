---
title: "Költségcsoportok"
description: "A költségcsoportok adják a legyártott cikk kiszámolt költségében a költség-hozzájárulások szegmentálásának és elemzésének alapját, mint például az anyag, a munka és a többletköltség költség-hozzájárulását. A költségcsoport-szegmentálásnak számos szinonimája létezik a gyártási környezetekben, például költséglebontás, költségszétbontás vagy költségosztályozás."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCostGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 50871
ms.assetid: 1855f744-f73f-4fa8-8290-a7ee126d368b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: fb335a521a1a79ea7d978171d233364c58765a0b
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="cost-groups"></a>Költségcsoportok

[!include[banner](../includes/banner.md)]


A költségcsoportok adják a legyártott cikk kiszámolt költségében a költség-hozzájárulások szegmentálásának és elemzésének alapját, mint például az anyag, a munka és a többletköltség költség-hozzájárulását. A költségcsoport-szegmentálásnak számos szinonimája létezik a gyártási környezetekben, például költséglebontás, költségszétbontás vagy költségosztályozás. 

A költségcsoport-szegmentálásnak számos szinonimája létezik a gyártási környezetekben, például költséglebontás, költségszétbontás vagy költségosztályozás. A költségcsoport-szegmentálás számos célt szolgálhat. Íme néhány példa:

-   A költségeket szegmentálja olyan különböző anyagtípusokra, mint a cikkekhez rendelt költségcsoporton alapuló összetevők és csomagolási anyagok egy konzervtermék esetében.
-   A különböző üzemi erőforrások szegmensköltségei, például a végzett munkák vagy a gépek típusai, az üzemi erőforrásokhoz és útvonalműveletekhez kapcsolt költségkategóriákhoz rendelt költségcsoportokon alapulnak.
-   Tudja szegmentálni a beállítási idő és a lefutási idő költségeit az útvonalműveletekben az útvonalműveletekkel kapcsolatos költségkategóriákhoz rendelt költségcsoportok alapján.
-   A különböző típusú többletköltségek szegmensköltségei, mint például a költségszámítási táblázatban a közvetett költségekhez rendelt, költségcsoportokon alapuló, munkával és géppel kapcsolatos többletköltségek.
-   A különféle gyártási többletköltségek kiszámításának alapja lehet a költségszámítási táblázatban. Ez a többletköltség különféle többletköltség értékeket foglalhat magában a vonatkozó útvonaltervezési információk alapján aszerint, hogy milyen üzemi erőforrásokról, beállítási ill. futási időkről van szó. A gyártási többletköltség kapcsolódhat az összetevők költség-hozzájárulásaihoz is, olyan eltérő gyártási szemléletmódot tükrözve ezzel, amely kiiktatja az útvonal-információk szükségességét.

A költségcsoport-szegmentálás egy legyártott cikk kiszámított költségeire vonatkozik, függetlenül attól, hogy a költség elszámolóárakon vagy tervezett költségeken alapult. Az **Összefoglaló** lap ezt a szegmentációt költségcsoport, szint vagy mindkettő alapján jeleníti meg. 

A több szinten keresztüli költségcsoport-szegmentálás megtartási képessége egy termékstruktúrában *megosztás* néven ismert. A megosztás csak legyártott cikkekre vonatkozik, amelyek egy elszámolóáras készletmodellt használnak. A megosztás nélkül a legyártott összetevő költsége anyagköltség-hozzájárulásként van kezelve. A főkönyvi alszámla költséglebontási készlet-paraméterei jelzik, hogy a költségcsoport-szegmentálás több szinten keresztül megmarad az elszámolóár számítások során. Ezzel szemben ha egy irányelv nem rendelkezik szintekkel, a költségcsoport-szegmentálás csak egyszintű kalkuláció esetére vonatkozik. Például a **Költségösszegzés költségcsoportok szerint** képernyő a költségcsoport-szegmentálást több szinten át jeleníti meg az elszámolóáras cikkekhez. 

A költségcsoport-szegmentálás egy elszámolóáras cikk eltéréseire is vonatkozhat. Egy második készletparaméter azt definiálja, hogy az eltérések a költségcsoport alapján lesznek azonosítva, vagy egyszerűen összegződnek. 

A költségcsoporthoz egy költségcsoport-típust lehet hozzárendelni és azt, hogy a kiegészítő szegmentálásnál miként viselkedjen.

-   **Költségcsoport-típus** − Minden költségcsoporthoz egy költségcsoport-típust kell hozzárendelni, amely jelzi, hogy a költségcsoport közvetlen anyag, közvetlen gyártás vagy közvetlen kiszervezés, vagy pedig közvetett, illetve definiálatlan. A költségcsoportok, amelyek közvetlen anyagként vannak meghatározva, cikkekhez rendelhetők hozzá. A közvetlen gyártási költségcsoportokat költségkategóriákhoz lehet hozzárendelni. A közvetlen kiszervezési költségcsoport szolgáltatási terméktípusokhoz rendelhető hozzá, amely lehetővé teszi a szolgáltatás beszerzési költségeinek alvállalkozói tevékenységekhez történő társítását. A közvetett költségcsoportok a felárak és pótdíjak közvetett költségéhez rendelhetők hozzá. A meghatározatlannak szánt költségcsoportokat cikkekhez, költségcsoportokhoz és közvetett költségekhez lehet hozzárendelni. Egy költségcsoport-típus társítása számos célt szolgál. Először is, korlátozza egy költségcsoport hozzárendelhetőségét és az alkalmazható költségcsoportok listájának megjeleníthetőségét. Másodszor, jelentési célokat szolgáló kiegészítő szegmentálást biztosít. Harmadszor, felhasználható arra, hogy főkönyvi számlákat rendeljenek az eltérésekhez.
-   **Viselkedés** − Minden költségcsoport opcionálisan hozzárendelhető egy viselkedéshez, amely jelzi, hogy a költségcsoport a fix költségekre vagy a változó költségekre vonatkozik. Az olyan költségcsoportot, amelynek viselkedése nulla értékre van állítva, változó költségként kezeli a program. A viselkedés hozzárendelése csak jelentési célokat szolgál. Például a költségeket megjelenítheti a költségszámítási táblázaton fix és változó költségek szegmentálásával és a**Költségösszegzés költségcsoportok szerint** oldalon. Ha százalékos nyereségbeállítást rendel az egyes költségcsoportokhoz, az anyagjegyzék-számítás megadja a „költség plusz árrés” elv alapján javasolt eladási árat.





