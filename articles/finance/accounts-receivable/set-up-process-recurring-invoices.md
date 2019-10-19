---
title: Állítsa be és dolgozza fel az ismétlődő számlákat
description: Ez a cikk ismerteti az ismétlődő számlák beállítását és feldolgozását. Használhat ismétlődő számlákat, amennyiben a vevők részére rendszeresen azonos összegű számlákat kell kiállítania.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b443630d1612b5095fefa74b5ed6d057be534b7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188947"
---
# <a name="set-up-and-process-recurring-invoices"></a>Állítsa be és dolgozza fel az ismétlődő számlákat

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti az ismétlődő számlák beállítását és feldolgozását. Használhat ismétlődő számlákat, amennyiben a vevők részére rendszeresen azonos összegű számlákat kell kiállítania.

<a name="create-a-recurring-free-text-invoice-template"></a>Ismétlődő szabadszöveges számlák sablonjának létrehozása
---------------------------------------------

Vevőknek rendszeres, ugyanazon szolgáltatások számlázásához, hozzon lére szabadszöveges számlasablont, amelyet újra lehet használni további számlák létrehozásához. Ez a sablon a következő információkat tartalmazza:

-   Fejlécadatok, például az adócsoportok, fizetési feltételeket és fizetési mód
-   Soradatok, például a szolgáltatásleírás, a bevételi számlák, az egységár és a számla összege
-   Szállítási és kezelési költségek
-   Könyvelési felosztások a pénzügyi dimenzió adataival, például a költséghelyek és az üzleti egységek

Így létrehoz egy teljes számlát és sablonként menti el. A sablonokat beállíthatja az **Ismétlődő számlák** oldalon.

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a>Szabadszöveges számlasablon hozzárendelése vevőhöz és az ismétlődés részleteinek megadása
A sablon létrehozása után hozzárendelni kell a sablont a számlázandó vevőhöz. Ezenkívül meg kell adnia, mikor és milyen gyakran lesz a számla használva. A sablonokat hozzárendelheti a **Vevők** oldal **Számla** lapjá . Adja hozzá a sablont a listához, és frissítése a következő adatokat:

-   A kezdő dátum, illetve az ismétlődő számlázás záró dátuma
-   Az ismétlődő számlázás gyakorisága (például minden nap vagy havonta egyszer)
-   A maximális számlázási összeg (ha ezt az információt kötelező megadni)

Egy vevőnek lehet több, eltérő gyakorisággal rendelkező sablonja.

## <a name="generate-the-recurring-invoices"></a>Az ismétlődő számlák létrehozása
Az **ismétlődő számlák**oldalon van egy olyan feladat, amely az ismétlődő számlasablonokat dolgozza fel. Meghatározhatja a számla dátumát és a sablont a számlák létrehozásához. A számlák létrejönnek és feldolgozott minden számlacsoporthoz egy ismétlődő azonosítószám rendelődik.

<a name="post-recurring-free-text-invoices"></a>Szabadszöveges ismétlődő számlák feladása
---------------------------------

Ismétlődő számlák generálása után a számla ismétlődés azonosító jelenik meg a feladási feladatban az **Ismétlődő számlák**oldalon. Megtekintheti az ismétlődés azonosító összes számláját a hivatkozásra kattintva. Az ismétlődés azonosító számláiak ellenőrzése során törölheti az egyes számlákat. A vevő ismétlődési beállításai a sablon beállításaira áll, így azt újra lehet generálni később. Feladhat egy, több, vagy az összes ismétlődés azonosítót. Ha engedélyezve vannak a munkafolyamatok, rá kell kattintania **Küldés** lehetőségre a számlák feladása előtt.

<a name="print-recurring-free-text-invoices"></a>Szabadszöveges ismétlődő számlák nyomtatása
----------------------------------

Ismétlődő számlák feladása után, kinyomtathatja a számlákat a szabadszöveges számla listaoldalról. A kijelölt számlákat ki lehet nyomtatni, vagy kiválaszthat egy számlatartományt nyomtatásra.



