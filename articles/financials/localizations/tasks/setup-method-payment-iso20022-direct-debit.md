--- 
title: "Fizetési mód beállítása ISO20022 beszedési megbízáshoz"
description: "Ez az eljárás bemutatja, hogyan állítható be a vevői fizetési módja ISO20022 beszedési megbízásra vagy egyéb fizetési típusra elektronikus jelentéskészítés használatával."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 3a884837ab0b5a1f4211532969619b54206bbef4
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-method-of-payment-for-iso20022-direct-debit"></a>Fizetési mód beállítása ISO20022 beszedési megbízáshoz

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan állítható be a vevői fizetési módja ISO20022 beszedési megbízásra vagy egyéb fizetési típusra elektronikus jelentéskészítés használatával. 



A feladat elvégzése előtt be kell állítania a formátumkonfigurációkat és a fizetési számlákat.



Ez az eljárás a DEMF bemutatócég segítségével lett létrehozva.



Ez a harmadik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a vevői kifizetési folyamatot.

1. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési mód pontra.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a „Fizetési mód” mezővel az „ELEKTRONIKUS” értéket beírva.
3. Kattintson a Szerkesztés lehetőségre.
4. A Fizetési számla mezőben adja meg a „DEMF OPER” értékeket.
5. Bontsa ki a Fájlformátumok szakaszt.
6. Válassza az Igen beállítást az Általános elektronikus jelentéskészítés mezőben.
7. Az Exportformátum konfigurációja mezőben adjon meg vagy válasszon ki egy értéket.
    * A listán válassza ki az ISO20022 beszedési megbízást (DE).  Ha a lista üres, a vevői kifizetésnek nincs importált és aktivált exportálási konfigurációja.  
8. Válassza az Igen lehetőséget a Felhatalmazás szükséges mezőben.
    * Válassza ki a Felhatalmazás szükséges paramétert az olyan vevői fizetési formátumokhoz, amelyekhez felhatalmazási adat megadása szükséges a fizetési üzenethez, ahogyan a SEPA beszedési megbízás esetén.  
9. Kattintson a Mentés gombra.


