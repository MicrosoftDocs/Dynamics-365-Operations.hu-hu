---
title: Adóelőlegkódok beállítása a TDS adótípusokhoz
description: Ez a témakör elmagyarázza, hogyan kell adókódokat beállítani a forrásnál levont adóhoz (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: ced5902b5a2e822f84a40da8149bc319c94973ba
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724727"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>Adóelőlegkódok beállítása a TDS adótípusokhoz

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan kell adókódokat beállítani a forrásnál levont adóhoz (TDS).

1. Ugorjon az **Adó \> Közvetett adók \> Adóelőleg \> Adóelőlegkódok elemre**.

    [![Adóelőlegkódok oldal.](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)

2. A Műveletablakban válassza az **Új** lehetőséget a TDS adóelőlegkód létrehozásához, és adja meg a szükséges adatokat.
3. Az **Általános** gyorslapon mezőben az **Adótípusa** mezőben válassza a **TDS** lehetőséget az adókód TDS adókódként való kategorizálásához.
4. Az **Elszámolási időszak** mezőben válassza ki a TDS elszámolási időszakot a TDS-adókódhoz.
5. A **Főszámla** mezőben válassza ki azt a főkönyvi számlát, amelyre a TDS-összeget könyvelni kell.
6. A **Kintlévőség számla** mezőben válassza ki azt a kintlévőségi számlát, amelybe az értékesítési műveletekben levont TDS-összeget ki kell könyvelni.

    Az **Eredet** mező automatikusan a **Bruttó összeg százaléka** értékre van állítva, és az érték nem módosítható.

    > [!NOTE]
    > Nem állíthatja be az eredetet a TDS adótípus adókódjaihoz a **Nettó összegének százaléka** értékre.

7. Az **Adóelőleg-összetevő** mezőben válassza ki a TDS-adóösszetevő lehetőséget a TDS-adókódhoz.
8. Válassza az **Értékek** elemet a műveleti panelen az **Adóelőleg-összegek** oldal megnyitásához.
9. A **Kezdő dátum** mezőben adja meg a TDS-összeg kezdő dátumát. Adja meg a befejező dátumot a **Befejező dátum** mezőben.

    > [!NOTE]
    > A TDS-adótípus adókódjaihoz nem érhetők el a **Minimális korlát**, **Felső korlát** és a **Kizárási %** mezők.

10. Az **Érték** mezőben adja meg a TDS adókódhoz a TDS százalékát.
11. Az **Adóelőleg-értékek** lap bezárásával térjen vissza **Adóelőlegkódok** lapra.

    > [!NOTE]
    > Az **Adóelőlegkódok** oldalon található **Korlátok** gomb nem érhető el a TDS-adótípus adókódjaihoz.

12. Zárja be a lapot.
