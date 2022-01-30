---
title: Veszélyes anyagok áttekintése
description: Ez a témakör áttekintést nyújt azokról a szolgáltatásokról, amelyek a termékadatok kezelése és a raktárkezelés során a veszélyes anyagok kezelésével és feldolgozásával kapcsolatosak.
author: t-benebo
ms.date: 06/10/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: cfea2cd6a2699bdf2a14de72a8bdeb3e8cd32a17
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986276"
---
# <a name="hazardous-materials-overview"></a>Veszélyes anyagok áttekintése

[!include [banner](../includes/banner.md)]

A szállítási és szállítmányozási előírásoknak való megfelelés érdekében azokat a szervezeteket, amelyeknek a veszélyes áruknak minősülő anyagokat szállítanak, további dokumentációt kell készíteniük a szállítmányokhoz. A veszélyes anyagok funkcióval a vevők a kiadott cikkekre vonatkozó adatokat tárolhatnak. Ezt az információt ezután felhasználhatja a szállítási dokumentáció előkészítésére. A veszélyes árukat szállító szervezetnek rendelkezniük kell saját folyamatokkal és eljárásokkal a szállítási folyamat kezeléséhez. A Microsoft Dynamics 365 Supply Chain Management csak egy eszköz, amely segítséget nyújt a szükséges dokumentumok előállításában.

A következő ábra a veszélyes anyagok funkció beállításához és használatához szükséges lépéseket mutatja be.

![A veszélyes anyagok funkció beállítása és használata.](media/hazmat-overview.png "A veszélyes anyagok funkció beállítása és használata")

A veszélyes anyagok funkció a Termékinformációk kezelésénél van beállítva, és olyan dokumentumokat biztosít, amelyek a Raktárkezelésen keresztül nyomtathatók. Ennek megfelelően túlnyomórészt a következő két fő területen tekinti át, állítja be és használja ennek a szolgáltatásnak a funkcióit:

- **Termékinformáció-kezelés:** – A kiadott termékekhez alkalmazható kódokat állíthatja be.
- **Raktárkezelés** – A szállítmányok számára nyomtatandó további szállítási dokumentumokkal végzett munka.

> [!IMPORTANT]
> Az Supply Chain Management veszélyes anyagokkal kapcsolatos szolgáltatásai egy olyan, hasznos termékinformációk-mezőből és a kapcsolódó funkciókból álló gyűjteményt kínál, amelyek segítik a veszélyes termékekkel kapcsolatos adatok rögzítését és hivatkozását. Ezek a szolgáltatások segítenek a szállítási dokumentumok tervezésében és kinyomtatásában is, amelyek tartalmazzák a szállítás alatt álló veszélyes anyagokra vonatkozó adatokat. A rendszer azonban nem biztosítja automatikusan a megfelelést az országa vagy a régiója vonatkozó jogszabályainak. Noha ezeknek az eszközöknek az a célja, hogy segítsenek megfelelni az általános szabályoknak, önmagában nem elégségesek, és nem is garantáljuk ezt. A szervezet felelős azért, hogy az összes vonatkozó előírás tudatában legyen, és minden szükséges lépést megtegyen azok teljesítéséhez.

## <a name="product-information-management"></a>Termékinformációk kezelése

A Termékinformáció-kezelés részben számos beállítási tábla adható hozzá a közúti, légi és tengeri fuvarozáshoz szükséges veszélyesáru-listákban szereplő hivatkozási adatokhoz.

A következő közös általános szabályozásokra támaszkodtunk a funkcionalitás fejlesztésekor:

- **ADR** – a veszélyes áruk nemzetközi közúti fuvarozásával kapcsolatos szabályozások
- **CFR 49** – szabályozások a veszélyes áruk Egyesült Államokban történő szállítására
- **IMDG** – a Veszélyes Áruk Nemzetközi Tengerészeti (IMDG) kódexe
- **IATA** – a Nemzetközi Légiforgalmi Szövetség (IATA) veszélyes árukra vonatkozó szabályozásai

A rendeletek mindegyik készlete a veszélyes áruk és hivatkozási kódok szabványosított listáját tartalmazza. Ennek megfelelően a Supply Chain Management tartalmaz egy hivatkozási táblát a listák közös kódjaihoz. Minden lista tartalmaz néhány egyedi kódot is, amelyek definiálhatók.

A veszélyes anyagokra vonatkozó előírások és értékek beállításával, valamint az értékek megfelelő termékekhez történő hozzárendelésével kapcsolatos további tudnivalókat lásd a következő témakörökben:

- [Veszélyes anyagok beállítása](hazmat-setup.md)
- [Termékekben, megrendelésekben, szállítmányokban és rakományokban lévő veszélyes anyagok](hazmat-items.md)

## <a name="warehouse-management"></a>Raktárkezelés

Amikor szállítmányt készít a Raktárkezelés modulban, számos új jelentést nyomtathat, amelyek a Termékinformációk kezelése modulban beállított adatokat használják. A rendelkezésre álló jelentésekről és azok használatáról a [Veszélyes anyagokkal kapcsolatos lekérdezések és jelentések](hazmat-reports.md) című témakörben olvashat bővebben.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]