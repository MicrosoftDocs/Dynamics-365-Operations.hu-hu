---
title: Hitelkezelés – időszakos feladatok
description: Ez a témakör azt mutatja be, hogy milyen ismétlődő feladatok szükségesek az ügyfelek hitelkereteinek kezelési folyamataihoz.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: b41b87cd3e2e80b87318c5c771d45a4d0e5d4b85
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971703"
---
# <a name="periodic-credit-management-tasks"></a>Időszakos hitelkezelési feladatok

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogy milyen ismétlődő feladatok szükségesek az ügyfelek hitelkereteinek kezelési folyamataihoz.

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