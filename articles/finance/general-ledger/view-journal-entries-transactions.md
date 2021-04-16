---
title: Naplóbejegyzések és tranzakciók megtekintése
description: Ez a cikk a napló bejegyzések és tranzakciók megtekintésének számos módját ismerteti.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 60524def2a676845bbaff8f25669a70fd8c3f5c2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816907"
---
# <a name="view-journal-entries-and-transactions"></a>Naplóbejegyzések és tranzakciók megtekintése

[!include [banner](../includes/banner.md)]

Ez a cikk a napló bejegyzések és tranzakciók megtekintésének számos módját ismerteti. 

A felhasználók többféle módon is megtekinthetik a naplókat és tranzakciókat. Választhatnak a leásási lehetőséget nyújtó lekérdezés oldalak közül, vagy különböző jelentésbeállításokat használhatnak a főkönyvben.

## <a name="voucher-transactions"></a>Bizonylattranzakciók
**Bizonylattranzakciók** egy lekérdezési oldal, ahol választhat különböző táblák és mezők közül, a keresett egyenleg vagy tranzakció kritériumának megadására. Például megtekintheti egy meghatározott dátumra vagy a számlára az összes tranzakciót, vagy az összes tranzakciót megtekintheti a **Működik** típus összes tranzakcióját, amelyek egy adott feladási réteg típusban találhatóak. Alapértelmezés szerint a lap jelenítia meg a napló számát, bizonylatot, dátumot és fő számlát, de további táblákat, mezőkat és kritériumokat adhat meg a találatok szűkítésére.

## <a name="audit-trail"></a>Könyvvizsgálati ellenőrzés
**Könyvvizsgálati ellenőrzés** egy lekérdezési lap, amely tartalmazza a tranzakciótípusokat, leírásokat, tranzakciók létrehozóit, és a létrehozás idejét. A **Könyvvizsgálati** lekérdezési lapon tekinthetőek meg a bizonylati tranzakciók.

## <a name="financial-reports"></a>Pénzügyi jelentések
Böngészhet és elemezhet főkönyvi tranzakciókat a pénzügyi jelentések futtatásával is. Mivel a pénzügyi jelentések tervének alapulhatnak a számlákon, dimenziókon, főkönyviszámla-kategóriákok vagy ezek kombinációján, különböző leásással a tranzakciókat többféleképpen lehet megtekinteni. Ha további tájékoztatást szeretne a főkönyvi tranzakciókról, több tranzakció tulajdonságot is hozzáadhat a jelentésterv részeként. Ezenkívül ha meg szeretné tekinteni a tranzakciókat, amelyek általános főkönyvi egyenleg részei, leáshat számlatranzakciókhoz, csakúgy, mint a a **Főkönyvi kivonat** listaoldalán.

## <a name="ledger-reports"></a>Főkönyvi jelentések
A pénzügyi jelentéseken kívül a következő főkönyvi jelentések állnak rendelkezésre főkönyvi tranzakciók megtekintésére:

-   **Dimenziókimutatás** – Ez a jelentés mutatja a tranzakciókat nap és a számla szerint, ezenfelül van egy opció, amely a tranzakciókat dimenzió és időszak szerint jeleníti meg.
-   **Főkönyvi tranzakciók listája** – Ez a jelentés mutatja a tranzakciókat a tranzakcióban, könyvelést és jelentési pénznemet a számlához.
-   **Nyomtatási napló** – Ez a jelentés tartalmazza a feladott napló az eredményét. Futtathatja a jelentése naplószám vagy naplótípus alapján, vagy további mezők hozzáadásával.
-   **Feladott tranzakciók napló szerint** – Ez a jelentés bizonylat alapján csoportosítva a naplóba feladott tranzakciókat jeleníti meg.
-   **Dátum szerinti tranzakciólista** – Ez a jelentés mutatja az összes tranzakciót dátum alapján, a napló számával, a bizonylattal és a főkönyvi számlával. Ezen felül a tranzakciókat is mutatja tranzakcióban, könyvelésben és jelentési pénzegységben.
-   **Tranzakció eredete** – Ez a tranzakció jelentés mutatja a számlát napló szerint, és tranzakció, könyvelés és jelentési pénznem szerint. Ezen felül megjeleníti napló összes ellentételként használt sorát.


## <a name="additional-resources"></a>További erőforrások
- [Főkönyvi számlaegyenlegek](general-ledger-account-balances.md) 
- [Könyvelési források böngészője](../accounts-payable/accounting-source-explorer.md)
- [Pénzügyi jelentéskészítés – áttekintés](financial-reporting-getting-started.md)
- [Naplóbejegyzések vagy tranzakciók megtekintése](tasks/view-journal-entries-or-transactions.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]