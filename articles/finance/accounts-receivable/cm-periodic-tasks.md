---
title: Időszakos hitelkezelési feladatok
description: Ez a témakör a vevők hitelkeret-kezelésének folyamatához szükséges időszakos feladatokat ismerteti.
author: JodiChristiansen
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9ad72463acba301f7fc931f9fe316a9a9758922e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888006"
---
# <a name="periodic-credit-management-tasks"></a>Időszakos hitelkezelési feladatok

[!include [banner](../includes/banner.md)]

Ez a témakör a vevők hitelkeret-kezelésének folyamatához szükséges időszakos feladatokat ismerteti.

## <a name="update-risk-scores"></a>Kockázati pontszámok frissítése

Mivel a vállalatok fejlődnek, és a körülmények megváltoznak, egy adott vevőre vonatkozó hitelkockázatok is megváltozhatnak. A vevőkre vonatkozó megfelelő hitelkeretek fenntartása érdekében időszakonként ellenőriznie kell a kockázati pontszám feltételeit, és frissíteni kell az egyes vevők pontszámait. A következő pontszámokat frissítheti a **Kockázati pontszámok frissítése** oldalon (**Hitel és beszedések \> Időszakos feladatok \> Hitelkezelés \> Kockázati pontszámok frissítése**). A program minden, a felhasználó által definiált számítást is feldolgoz.

- **Átlagos kifizetési napok** – Ez a pontszám azoknak a napoknak az átlagos száma, amennyi idő alatt a vevő a számlákat kifizeti.
- **Vevő ettől kezdve** -Ez a pontszám azoknak az éveknek a száma, amióta a vevő a szervezete vevője.
- **Mióta működik** – Ez a pontszám azoknak az éveknek a száma, amióta a vevő működik. A **Működés kezdete** mező értékét használja a **Vevők** oldalról.
- **Kintlevőség-elmaradási napok száma**– Ez a pontszám a kinnlevőségek egyenlege, az értékesítés bevételei és az elmúlt 12 hónapos időszakra vonatkozó napok száma.
- **Átlagos egyenleg** – Ez a pontszám az előző tizenkét hónapos időszak kinnlevőségek egyenlegén alapul.
- **Hitelkezelésicsoport**, **Számlaállapota** és **Országa** – Ezek a pontszámok a vevőtől származó adatokat használják.

## <a name="update-customer-balance-statistics"></a>Vevői egyenleg statisztikáinak frissítése

A **Vevői egyenleg statisztikái** folyamat futtatásával frissítheti az egyenlegstatisztika számítását, amely látható az **Egyenlegstatisztika lekérdezése** oldalon. Ezekkel az adatokkal lehet kiszámítani a kockázati pontszámokat és a **Vevő** lap hitel statisztikai adatterületen látható értékeket.

Amikor futtatja a folyamatot, egy vevőre vonatkozó vevői egyenleg statisztikáját frissíti. Ha azt szeretné, hogy egy kötegelt feladat több vevőnél is fusson, akkor az **Egyenlegstatisztika számítása** lapot (**Hitelkezelés \> Időszakos feladatok \> Egyenlegstatisztika számítása**) használhatja.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
