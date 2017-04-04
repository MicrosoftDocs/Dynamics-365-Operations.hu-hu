---
title: "Könyvelési felosztások"
description: "A cikk a könyvelési felosztásokról nyújt tájékoztatást, valamint leírja a feldolgozásra alkalmas opciókat. A könyvelési felosztásokat egy forrásbizonylat pénzösszegeinek egy meghatározott főkönyvi számlára történő áthelyezésére használhatja."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: a98ce08dc115bc96cec07c2d6ced10d774785fe9
ms.openlocfilehash: b1057caae6f47e5a17e194834fbbcb9d7d731605
ms.lasthandoff: 03/31/2017


---

# <a name="accounting-distributions"></a>Könyvelési felosztások

A cikk a könyvelési felosztásokról nyújt tájékoztatást, valamint leírja a feldolgozásra alkalmas opciókat. A könyvelési felosztásokat egy forrásbizonylat pénzösszegeinek egy meghatározott főkönyvi számlára történő áthelyezésére használhatja. 

A könyvelési felosztások program szintű képesség, amelyet a forrásbizonylat használ és terejszt ki, úgy mint beszerzési rendelés, szállítói számla, költségjelentés és szabadszöveges számla. Alapértelmezés szerint az alapértelmezett könyvelési felosztás jön létre mindegyik forrásbizonylatsorhoz és pénzösszeghez, és módosításra feltételesen engedélyezve van. 

> [!Note] 
> Egyes dokumentumok támogatják a fej dokumentum pénzösszegeket, például a rendelések és számlák díja is. 

Az általános könyvelési felosztás funkciók az alábbi lehetőségeket biztosítja a könyvelési felosztás feldolgozásához:

-   **Összegek felosztása** – Egy bizonyos bizonylat fejléchez, vagy sorhoz és alsorokhoz, például az adókhoz és díjakhoz tartozó könyvelési felosztások megtekintése és módosítása.
    -   A felső pénzösszeg felosztásokhoz (szülő felosztások) a fő számla és a pénzügyi dimenziók szerkeszthetőek a rács szegmentált bejegyzés vezérlőelemben. A kiterjesztett ár egy jellemző példa egy ilyen szülő elosztásra.
    -   A felosztások összegei a bizonylat pénznemén alapulnak. Ez a pénznem általában a tranzakció pénzneme. Könyvelési és jelentési pénznem összegek az analitikus könyvelésének lefoglalása részeként jönnek létre.
    -   A felosztás a számviteli eseményt és könyvelési dátumot jeleníti meg. Általában a számviteli esemény értéke **Nincs** a dokumentum feladásáig/naplózásáig. Ezen a ponton a számviteli esemény értéke **Eredeti**. A felosztások feladása után nem módosíthatja a felosztásokat.
    -   **Megosztott** gomba a szülő felosztásoknak engedélyezhető. **Megosztott** új könyvelési felosztásokat hoz létre, és a megosztás alapja lehet a százalék, összeg, vagy mennyiség.
    -   Az** Egyenló kiosztés** gomb együtt használható a **Megosztott** funkcióval, az automatikus felosztására az összes felosztás között.
    -   **Alaphelyzet** gomb engedélyezhető a szülő felosztások számára, ha több, mint egy felosztás található. Az **Alaphelyzet** funkció visszafordít minden manuálius változtatást, úgy, hogy kitörtöl minden felostást és újragenerálja az alapértelmezett felosztásokat.
    -   Bármely gyermekfelosztás, úgy mint engedmény, a költség és a forgalmi adó, mindig követi a szülő felosztását. Megtekintheti a szülő-gyermek kapcsolat, **referencia**&gt;**információ szülő**.
    -   A fő számla és a pénzügyi dimenzió a gyermekek számára is engedélyezhetőek.
    -   A pénzügyi dimenziók a könyvelési felosztásokon egy alapértelmezési mintát követ, amelyet egy bizonylat kiterjeszthet. További részletekért lásd a kapcsolódó cikkeket.
    -   Eltérés felosztások egyező feltételeken generálódhatnak, úgy mint egyezés a szállítói számla és a beszerzési rendelés között. Megtekintheti a számlázási eloszlás közötti megfelelő kapcsolatok **referencia**&gt;**adatai**.
    -   **Helyes** gomb jelenik meg, és engedélyezve van a dokumentumoknak, amelyeken elvégezhetők javítások. **Megfelelő** hoz létre új felosztásokat. Először a felosztások készülnek, amelyek visszaállítják az eredeti felosztások. Ezek a felosztások nem módosítható. Következő, új megfelelő könyvelési felosztások jönnek létre. Ezeknek a felosztások módosíthatóak, ha az eredeti felosztások módosíthatók.
    -   A** Projektadatok** gomb használható kiterjesztésként, amikor a projekt egy sor kapcsolódik. Projekt könyvelési felosztása segítségével módosíthatja a részleteket, például a finanszírozási forrás és a sortulajdonság.
    -   Az aktuális dokumentum számviteli állapotát tekintheti meg **referencia**. Az állapotot a teljes dokumentumot, és jelzi, hogy a dokumentum folyamatban van vagy befejeződött.
-   ** Megtekintése felosztások ** – a dokumentum összes sorból és pénzösszegek könyvelési felosztásainak megtekintése. A könyvelési felosztásokat ebből a nézetből nem módosíthatja.


További tudnivalókért lásd: [könyvelési felosztások és analitikus naplóbejegyzések a szabadszöveges számlákhoz](accounting-distributions-subledger-journal-entries-vendor-invoices.md).

