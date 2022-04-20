---
title: Vevőkorosítási adattároló
description: Ez a témakör a vevők korosítási adatainak külső tárolási folyamatát írja le. A vevői korosítási adattárolási folyamat futtatásával elérhetővé teszi a kimenetet egy külső rendszerbe történő exportálásra.
author: JodiChristiansen
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 497d49da84f4df90877908bef3031e079bc36066
ms.sourcegitcommit: d0e99545d722c924db57ae2bd06f72154a1f1f97
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2022
ms.locfileid: "8557878"
---
# <a name="customer-aging-data-storage"></a>Vevőkorosítási adattároló

[!include [banner](../includes/banner.md)]


Ez a témakör a vevők korosítási adatainak külső tárolási folyamatát írja le. A Microsoft Dynamics 365 Pénzügyben futtathatja a vevők korosítási adattárolási folyamatát, hogy a kimenet elérhető legyen külső rendszerbe történő exportálásra. A folyamat futtatásakor ugyanazok a korosítási jelentések beállításai érhetők el a rendszerben, mint a külső rendszerek. A részletek mindig szerepelnek az exportált adatokban.

Hasznos lehet a külső rendszer számára elérhetővé tenni a vevők korosítási adatait olyan esetekben, amikor a kimenet sok vevőt és/vagy sok tranzakciót tartalmaz. Ha a meglévő vevőkorosítási **jelentés** időkorosítási időről van túl sok nyomtatható adat, akkor ez a funkció egy alternatív lehetőséget biztosít ugyanezek az adatok beszerkedéséhez.

## <a name="enable-the-customer-aging-data-storage-feature"></a>A Vevőkorosítási adatok tárolása funkció engedélyezése

A funkció használata előtt engedélyeznie kell azt a rendszerben. A rendszergazdák a szolgáltatáskezelési beállítások segítségével ellenőrizhetik és engedélyezhetik a funkció állapotát, amennyiben szükséges. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** Jóváírások és beszedési adatok
- **Funkció neve:** Vevő korosítási adatainak tárolása

## <a name="run-the-customer-aging-data-storage-process"></a>A Vevőkorosítási adatok tárolási folyamatának futtatása

1. Ugrás a Jóváírás **és beszedések lekérdezései \> és \> jelentések vevői \> korosítási adatainak tárolásához**.
2. Válassza az **Új** lehetőséget.
3. A Név **mezőben** adja meg a folyamat nevét.
4. Állítsa be a fennmaradó paramétereket a szükséges szerint.

    > [!NOTE]
    > A tranzakció részleteit a program mindig tartalmazza, és a feldolgozás mindig egy kötegelt feladatban történik.

5. Válassza ki az **OK** lehetőséget.
6. Frissítse a vevő korosítási **adatait tároló** oldalt **·** **·** **, hogy a Köteg neve és a Kötegelt futási idő értékei láthatók a Feldolgozás állapot értékével** együtt. Amikor a kötegelt feladat befejeződött, **a Feldolgozás állapota** **·** **mező** beállítása Befejezve, a Korosítási sorok száma mező pedig be van állítva. Ha a kötegelt feladat ismétlődő, akkor **a Feldolgozás állapota** mezőben a Várakozás beállítás **van meg.**
7. A Korosítási **sorok** száma **mező** melletti Szűrő gombbal áttekintheti a kötegelt feladathoz hozzáadott szűrőket.

A vevő **korosítási adatainak tárolási** lapja nem tartalmazza az eredményeket. A Vevő korosítási adatainak **tárolási adatai** entitás segítségével azonban bármilyen formátumba exportálhatja a kimenetet, amit az Adatkezelés támogat.

> [!NOTE]
> Exportálás előtt adjon hozzá egy szűrőt, hogy az exportált eredmények a legutóbbi korosításra korlátozzák az exportált eredményeket. Adja meg például a következő feltételeket a legutóbbi kötegelt futtatás visszaküldésére:
>
> (CustAgingDataStorageSysQueryRangeUtilgetLatestBatchName::())
>
> Másik lehetőségként adja hozzá a következő feltételeket az aktuális felhasználó legutóbbi futtatásának visszaküldésére:
>
> (CustAgingDataStorageSysQueryRangeUtilgetLatestBatchNameForCurrentUser::())
