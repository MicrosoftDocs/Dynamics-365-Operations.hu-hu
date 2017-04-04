---
title: "Diszkrét, feldolgozása és lean forrás tervezés mód - vegyes egyesítése"
description: "Ez a cikk a vegyes módú tervezéssel kapcsolatban nyújt tájékoztatást. A vegyes módú tervezésben modellezheti az anyagáramláson alapuló ellátási láncot. Biztosítja, hogy a Microsoft Dynamics 365 műveletekhez, hogy az anyagáram a modellek, függetlenül a szállítási politikája, amely követi a kijelölt (kanban, termelési rendelések, beszerzési rendelések, kötegelt rendelések vagy átadás rendelések)."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d635421112f6d1e79a47090de3ffc4178b36b132
ms.lasthandoff: 03/31/2017


---

# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>Diszkrét, feldolgozása és lean forrás tervezés mód - vegyes egyesítése

Ez a cikk a vegyes módú tervezéssel kapcsolatban nyújt tájékoztatást. A vegyes módú tervezésben modellezheti az anyagáramláson alapuló ellátási láncot. Biztosítja, hogy a Microsoft Dynamics 365 műveletekhez, hogy az anyagáram a modellek, függetlenül a szállítási politikája, amely követi a kijelölt (kanban, termelési rendelések, beszerzési rendelések, kötegelt rendelések vagy átadás rendelések). 

Kiválaszthatja a termék biztosítására szolgáló átfogó stratégiáját a termékstruktúrától függetlenül.  

Például, használhat kanbanvezérlést az összeszerelés során, ahol az összeszerelési terület számára válogatják az anyagokat termelési rendelés, kanbanok, szállítások, kötegrendelés vagy bármilyen, az ellátási lánc jellemzői számára megfelelő kombináció szerint, de továbbra is teljesen átláthatja a cikkeket. Ez a képesség optimalizált ellátásilánc-folyamatokat és az ellátási lánc jobb átláthatóságát eredményezi.  

Az alapütemezésben használt ellátási irányelvek részletessége a fedezeti dimenzióként engedélyezet tárolási dimenzióktól függ. A különböző típusú helyszínek ellátásának és feltöltésének ellenőrzésére szolgáló alapütemezés engedélyezéséhez (például a gyártószint különböző gyártási egységekre történő felosztásával vagy a különböző anyagtípusokat és kész termékeket tároló raktárak elválasztásával), ajánljuk a Hely és raktár fedezeti dimenzióként való engedélyezését. Másik lehetőségként a raktár kihagyható a fedezeti dimenziók közül. Ebben az esetben a haladó raktárkezelés használata során a raktáron belüli minden mozgást a raktármunka ellenőrzi, míg a raktárak között mozgásokat ellenőrizhetik a visszavonási kanbanok.

## <a name="supply-policies"></a>Ellátási irányelvek
365 Dynamics műveletek vegyes módú tervezési szabályozza, hogyan a termék szállított és, ellátás, hogyan származtatott követelmények alapján (egy anyagjegyzék cikkek anyagok \[AJ\]) adják ki. A rendeléstípus alapján a rendszer automatikusan biztosítja az anyagforrásokat, hogy megfeleljen a követelményeknek.  

Az ellátási irányelvek meghatározhatók a termék szintjén vagy a követelmény által támogatott bármilyen részletességgel. Az ellátási irányelvek részletességét Ön határozza meg az **Alapértelmezett rendelésbeállítások **oldalon.  

Az ellátási irányelvek szabályozhatók termék, cikkdimenzió (konfiguráció, szín és méret), hely és raktár szerint. Ez a beállítás a **Cikk fedezete **oldalon végezhető elé.  

Az alapértelmezett rendelési típus szabályozza, hogy mit generál a rendelés alaptervezése.  

Függetlenül attól, hogy az ellátási lánc modellezni Dynamics 365 műveletek támogatja az ellátási politikáknak a mix. Lehetnek kanban forrásokból származó termelési rendelései. Emellett lehet olyan kötegrendelése, amelyhez szállítással vagy kanbanokkal ellátott termék szükséges.  

365 Dynamics műveletek meggyőződik arról, hogy az anyagáram a modellt követi.  

Az anyagok kitárolására szolgáló raktár hozzárendelése dinamikusan történik futási idő közben az ellátási irányelvek meghatározása után.  

Általában a kanbanokat nem jövőbeni dátumokhoz hozzák létre, mivel a kanbanok rövid életciklusúak. Ahhoz, hogy az ellátási lánc teljesen átlátható maradjon, bevezettük a „tervezett kanban” új tervezési rendszerét, amely a származtatott követelmények kiszámításához szükséges, és segít garantálni, hogy a követelmények forrását ugyanazon logika mentén határozzák meg, mint amelyet az adott kanban létrehozásához használnak.  

Ez a megfontolás a többi ellátásiirányelv-típus esetében is jelen van. Így a hosszú távú anyagtervezés ugyanazon a logikán alapul, mint amit az adott rendelések esetén használni kíván a termelés és az ellátás jóváhagyása után.

## <a name="materials-allocation-crosssupply-policy--resource-consumption-on-boms"></a>Anyagok felosztása crosssupply házirend – anyagjegyzékekbe erőforrás-felhasználás
Erőforrás-felhasználás egy fontos funkciót. Az erőforrás felhasználás lehetővé teszi a raktár számára a kitárolási anyagok dinamikus kiválasztását az ellátási irányelvek (rendelési típus) alapján, és megkönnyíti az alapadatok karbantartását.  

Az erőforrás-felhasználáshoz szükséges, hogy a raktárat, ahonnan kitárolják az anyagokat, a termék ellátási módja alapján rendeljék hozzá. Más szavakkal futási idő közben a rendszer megtalálja a gyártáshoz szükséges erőforrásokat. Az erőforrások alapján a rendszer megtalálja a kitárolási raktárat.  

Az ellátási irányelvektől független munka esetében nem kell megváltoztatnia az anyagjegyzéken szereplő információt, ha az ellátás módosul. Ad hoc változásokat Dynamics 365 műveletek teszi meg arról, hogy a megfelelő raktárból kifejezéskészletébe anyagok.

## <a name="process-manufacturing--the-production-type"></a>Folyamatgyártás – A termelési típus
Vegyes módú teljes rugalmasságot ajánlott minden termék esetében használhatja a termelés típusa anyagjegyzék. A termelési rendelések, kanban, átmozgatási rendelések vagy beszerzési rendelések segítségével majd olyan terméket szállítanak. A folyamatgyártás esetében a következő termeléstípusok közül kell választani: **receptúra**, **társtermék**, **melléktermék** vagy **tervezési cikk**. A kanbanok és a termelési rendelések nem használhatók ezen termeléstípusok esetében.


