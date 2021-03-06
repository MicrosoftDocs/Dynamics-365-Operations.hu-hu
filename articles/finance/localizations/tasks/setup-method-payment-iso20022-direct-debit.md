---
title: Fizetési mód beállítása ISO20022 beszedési megbízáshoz
description: Ez az eljárás bemutatja, hogyan állítható be a vevői fizetési módja ISO20022 beszedési megbízásra vagy egyéb fizetési típusra elektronikus jelentéskészítés használatával.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9c6a692553867d7e8679099210dc44b9d9e4d0f1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838682"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a>Fizetési mód beállítása ISO20022 beszedési megbízáshoz

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]