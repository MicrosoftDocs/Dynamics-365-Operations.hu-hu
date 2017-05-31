---
title: "Könyvelési felosztások"
description: "A cikk a könyvelési felosztásokról nyújt tájékoztatást, valamint leírja a feldolgozásra alkalmas opciókat. A könyvelési felosztásokat egy forrásbizonylat pénzösszegeinek egy meghatározott főkönyvi számlára történő áthelyezésére használhatja."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 96ff984310ce5877c37a22f182064a5038d71752
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="accounting-distributions"></a>Könyvelési felosztások

[!include[banner](../includes/banner.md)]


A cikk a könyvelési felosztásokról nyújt tájékoztatást, valamint leírja a feldolgozásra alkalmas opciókat. A könyvelési felosztásokat egy forrásbizonylat pénzösszegeinek egy meghatározott főkönyvi számlára történő áthelyezésére használhatja. 

A könyvelési felosztások program szintű képesség, amelyet a forrásbizonylat használ és terejszt ki, úgy mint beszerzési rendelés, szállítói számla, költségjelentés és szabadszöveges számla. Alapértelmezés szerint az alapértelmezett könyvelési felosztás jön létre mindegyik forrásbizonylatsorhoz és pénzösszeghez, és módosításra feltételesen engedélyezve van. 

> [!Note] 
> Egyes dokumentumok támogatják a bizonylat fejlécében található pénzösszegeket, például a rendelések és számlák költségeit. 

Az általános könyvelési felosztás funkciók az alábbi lehetőségeket biztosítja a könyvelési felosztás feldolgozásához:

-   **Összegek felosztása** – Egy bizonyos bizonylat fejléchez, vagy sorhoz és alsorokhoz, például az adókhoz és díjakhoz tartozó könyvelési felosztások megtekintése és módosítása.
    -   A felső pénzösszeg felosztásokhoz (szülő felosztások) a fő számla és a pénzügyi dimenziók szerkeszthetőek a rács szegmentált bejegyzés vezérlőelemben. A kiterjesztett ár egy jellemző példa egy ilyen szülő elosztásra.
    -   A felosztások összegei a bizonylat pénznemén alapulnak. Ez a pénznem általában a tranzakció pénzneme. Könyvelési és jelentési pénznem összegek az analitikus könyvelésének lefoglalása részeként jönnek létre.
    -   A felosztás a számviteli eseményt és könyvelési dátumot jeleníti meg. Általában a számviteli esemény értéke **Nincs** a dokumentum feladásáig/naplózásáig. Ezen a ponton a számviteli esemény értéke **Eredeti**. A felosztások feladása után nem módosíthatja a felosztásokat.
    -   **Megosztott** gomba a szülő felosztásoknak engedélyezhető. **Megosztott** új könyvelési felosztásokat hoz létre, és a megosztás alapja lehet a százalék, összeg, vagy mennyiség.
    -   Az**Egyenló kiosztés** gomb együtt használható a **Megosztott** funkcióval, az automatikus felosztására az összes felosztás között.
    -   **Alaphelyzet** gomb engedélyezhető a szülő felosztások számára, ha több, mint egy felosztás található. Az **Alaphelyzet** funkció visszafordít minden manuálius változtatást, úgy, hogy kitörtöl minden felostást és újragenerálja az alapértelmezett felosztásokat.
    -   Bármely gyermekfelosztás, úgy mint engedmény, a költség és a forgalmi adó, mindig követi a szülő felosztását. Meg lehet tekinteni a szülő/gyermek kapcsolatot itt: **Hivatkozás** &gt; **Szülőadatok**.
    -   A fő számla és a pénzügyi dimenzió a gyermekek számára is engedélyezhetőek.
    -   A pénzügyi dimenziók a könyvelési felosztásokon egy alapértelmezési mintát követ, amelyet egy bizonylat kiterjeszthet. További részletekért lásd a kapcsolódó cikkeket.
    -   Eltérés felosztások egyező feltételeken generálódhatnak, úgy mint egyezés a szállítói számla és a beszerzési rendelés között. Meg lehet tekinteni a könyvelési felosztás egyezési kapcsolatait itt: **Hivatkozás** &gt; **Dokumentum adatai**.
    -   **Helyes** gomb jelenik meg, és engedélyezve van a dokumentumoknak, amelyeken elvégezhetők javítások. A **Megfelelő** új felosztásokat hoz létre. Először felosztások jönnek létre, amelyek megfordítják az eredeti felosztásokat. Ezek a felosztások nem módosíthatók. Ezután létrejönnek az új, megfelelő könyvelési felosztások. Ezeknek a felosztások módosíthatóak, ha az eredeti felosztások módosíthatók.
    -   A**Projektadatok** gomb használható kiterjesztésként, amikor a projekt egy sor kapcsolódik. Projekt könyvelési felosztása segítségével módosíthatja a részleteket, például a finanszírozási forrás és a sortulajdonság.
    -   Az aktuális dokumentum számviteli állapotát itt tekintheti meg: **Hivatkozás**. Az állapot a teljes dokumentumra vonatkozik, és jelzi, hogy a dokumentum folyamatban van vagy befejeződött-e.
-   ** Felosztások megtekintése** – A bizonylat összes sorához és a pénzösszegekhez tartozó könyvelési felosztás megtekintése. A könyvelési felosztásokat ebből a nézetből nem módosíthatja.


További tájékoztatás: [Könyvelési felosztások és az analitikus napló bejegyzései szabadszöveges számlákhoz](accounting-distributions-subledger-journal-entries-vendor-invoices.md).



