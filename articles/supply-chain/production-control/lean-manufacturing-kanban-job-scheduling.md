---
title: Kanbanfeladat ütemezése lean manufacturing céljára
description: Ez a cikk a kanban-feladat ütemezés feletti vizuális ellenőrzésről és a kanban-feladatok ütemezésének különböző módszereiről nyújt tájékoztatást.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f70c3cf44ce90b13250836013636920267d2016d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570225"
---
# <a name="kanban-job-scheduling-for-lean-manufacturing"></a>Kanbanfeladat ütemezése lean manufacturing céljára

[!include [banner](../includes/banner.md)]

Ez a cikk a kanban-feladat ütemezés feletti vizuális ellenőrzésről és a kanban-feladatok ütemezésének különböző módszereiről nyújt tájékoztatást.  

A **Kanbanfeladat ütemezése** oldal a lean manufacturing munkacellák ütemezéseinek vizuális ellenőrzésére szolgál. Áttekintheti az összes kanbanfeladatot és szűréseket végezhet számos különféle módon. Erről az oldalról lehetősége van minden más, kanbanok konfigurálásával és végrehajtásával kapcsolatos oldalra átváltani.

## <a name="automatic-scheduling-of-kanban-jobs"></a>Kanbanfeladatok automatikus ütemezése
Az ütemezés indítása akkor történhet automatikusan, ha a kanbanszabályhoz megadja az **Automatikus tervezési mennyiség** paramétert. Amennyiben az **Automatikus tervezési mennyiség** értéke **1**, az egyes kanbanfeladatok a létrehozás után azonnal tervezetté válnak. Az eredmény egy műveletekből álló sorozat, amelynek végrehajtása a lekérés sorrendjében történik. Amennyiben az **Automatikus tervezési mennyiség** értéke 1-nél nagyobb, a rendszer a tervezés előtt csoportosítja a kanbanfeladatokat. 

Ez a koncepció lehetővé teszi, hogy a kanbanok méretét a tényleges gazdaságos kötegméret alá csökkentsük. Tegyük fel például, hogy egy adott cikk (vagy egy cikkcsalád) gazdaságos kötegmérete 30. Ez esetben 30-as termékmennyiséget használó kanbanok létrehozása helyett úgy is konfigurálhatja a kanbanszabályt, hogy a termék mennyisége 10, az **Automatikus tervezési mennyiség** pedig **3** legyen. Bár az automatikus tervezés csak akkor ütemezi a munkacella kanbanfeladatait, ha három nem tervezett feladat létezik, a tervező és az üzemirányítási felügyelő számára világosan látható, hogy két nem tervezett feladat végrehajtásra várhat. A tervező vagy üzemvezető ezután kézzel megtervezheti ezt a két feladatot, vagy ezek mellé további kanbanokat hozhat létre.

## <a name="manual-scheduling"></a>Kézi ütemezés
A Microsoft Dynamics AX 2012 rendszerben bevezettük a kézi ütemezésre szolgáló kanbanütemezési táblát. A kézi ütemezés kombinálható az automatikus ütemezéssel. A kanbanütemezési tábla segítségével tervezetté vagy nem tervezetté teheti a feladatokat, sorrendbe rakhatja, valamint időszakból időszakba helyezheti azokat. Azok a feladatok, amelyek **0**-nál nagyobb **Automatikus tervezés** értékű kanbanszabályon alapulnak, kézzel átállíthatók nem tervezetté. Azonban ezek a feladatok újra tervezetté válnak, amint megtörténik a következő automatikus tervezési esemény (tehát amint új kanban jön létre). Kézi ütemezés során a következő lehetőségek közül választhat:

-   Az **Ütemezés** lehetőség az esedékességi dátumok alapján ütemezi a kiválasztott feladatokat. (Az automatikus tervezéshez hasonlóan)
-   Az **Ütemezés megadott dátumtól előre** lehetőség megkísérli a kiválasztott feladatok esedékességi dátum szerinti ütemezését, azonban az eredményt a megadott legkorábbi kezdő dátum alapján leszűkíti.
-   A **Vissza** lehetőség visszafelé mozgatja a kiválasztott ütemezett feladatokat a sorban, az időszakon belül.
-   Az **Előre** lehetőség előrefelé mozgatja a kiválasztott ütemezett feladatokat a sorban, az időszakon belül.
-   Az **Előző időszak** lehetőség áthelyezi a kijelölt ütemezett feladatokat a megelőző időszak elejére vagy végére.
-   A **Következő időszak** lehetőség áthelyezi a kijelölt ütemezett feladatokat a következő időszak elejére vagy végére.
-   A **Terv** &gt; **Feladat állapotának visszaállítása** lehetőséggel visszavonhatja a már ütemezett feladatok ütemezését.

## <a name="lean-scheduling-groups"></a>Lean ütemezési csoportok
Minden egyes szín egy lean ütemezési csoportot jelöl. A lean ütemezési csoportok kötöttségek nélkül megadhatóak általános csoportokként vagy egyetlen munkacellához tartozó csoportokként. Az ütemezési csoportokhoz tetszőlegesen hozzárendelhetőek cikkek és dimenziók. Például a Festés cellákban ütemezési csoportok jelölhetik a termék színeit. Egy megadott eszközigényű munka során a cikkek csoportosíthatóak a szükséges szerszámok szerint, illetve egy csomagolási munkacella segítségével csomagolási sablon szerint. A lean ütemezési feladatokhoz nem kötelező, de ajánlott színeket használni. Ez javítja terv állapotának átláthatóságát. Például egyszerűen megállapítható, hogy milyen színek jelennek meg az egyes napokon, és egy pillanat alatt meg tudja mondani, hogyan optimalizálható ez a munka.

## <a name="work-cell-capacity-and-period-capacity"></a>Munkacella kapacitása és időszak kapacitása
Egy lean munkacella kapacitása mindig egyidejű. Ez azt jelenti, hogy egy munkacellában több feladat is lehet aktív ugyanabban az időpontban. A kapacitás nyomon követése kétféleképpen történhet: átfutás és idő alapján.

### <a name="throughput"></a>Átfutás

A munkacella kapacitását egy referencia időszak (szokásos munkanap, hét, vagy hónap) alatti átlagos átvitt mennyiség definiálja. A napra vagy hétre vonatkoztatott tényleges kapacitást a rendszer a munkacellához rendelt naptárban lévő munkaidő alapján számítja ki. Az egyes feladatokhoz tartozó kapacitásokat a munkacellában lévő cikk átviteli arányával korrigált, adott feladathoz tartozó mennyiségek adják meg.

### <a name="hours"></a>Órák

A napi vagy heti elérhető kapacitást a munkacellához rendelt naptár definiálja. Az egyes feladatokhoz tartozó kapacitásokat a munkacellában lévő cikk mennyiségével (alapértelmezett tevékenységmennyiség és tényleges feladatmennyiség összevetése) és átviteli arányával korrigált, adott tevékenységhez tartozó ciklusidők adják meg.

#### <a name="period-capacity-factbox"></a>Időszak kapacitása adatterület

A **Kanbanfeladat ütemezése** listaoldal tartalmaz egy olyan adatterületet, amely a kiválasztott munkacella elérhető és lefoglalt kapacitását mutatja időszakokra vonatkoztatva. A termelési folyamatmodellben kiválasztott ütemezési időszakoktól függően az időszakok napok vagy hetek lehetnek.

## <a name="additional-resources"></a>További erőforrások





[!INCLUDE[footer-include](../../includes/footer-banner.md)]