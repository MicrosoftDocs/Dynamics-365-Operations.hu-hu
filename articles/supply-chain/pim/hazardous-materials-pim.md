---
title: Veszélyes anyagok
description: Ez a témakör a környezetében tárolt veszélyes anyagi dokumentumokkal és adatokkal kapcsolatos információkat tartalmaz.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: feee6b348ac1870295a894ad988278b23a3f30a3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429664"
---
# <a name="hazardous-materials"></a>Veszélyes anyagok

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A veszélyes anyagokkal kapcsolatos információk a Termékinformáció-kezelés részben állíthatók be. Ez a modul a Raktárkezelés segítségével kinyomtatható dokumentumokat is tartalmaz.

A veszélyes áruknak minősített anyagok szállításakor a szállítmányoknak további papírmunkát kell tartalmazniuk. A veszélyes anyagokra vonatkozó funkciók segítségével az ügyfelek tárolhatják az osztályozási adatokat, és azt a kiadott elemekkel összekapcsolhatják. Ezt az információt ezután felhasználhatja a szállítási dokumentáció előkészítésére.

> [!IMPORTANT]
> A Microsoft Dynamics 365 Supply Chain Management veszélyes anyagokkal kapcsolatos szolgáltatásai egy olyan, hasznos termékinformációk-mezőből és a kapcsolódó funkciókból álló gyűjteményt kínál, amelyek segítik a veszélyes termékekkel kapcsolatos adatok rögzítését és hivatkozását. Ezek a szolgáltatások segítenek a szállítási dokumentumok tervezésében és kinyomtatásában is, amelyek tartalmazzák a szállítás alatt álló veszélyes anyagokra vonatkozó adatokat. A rendszer azonban nem biztosítja automatikusan a megfelelést az országa vagy a régiója vonatkozó jogszabályainak. Noha ezeknek az eszközöknek az a célja, hogy segítsenek megfelelni az általános szabályoknak, önmagában nem elégségesek, és nem is garantáljuk ezt. A szervezet felelős azért, hogy az összes vonatkozó előírás tudatában legyen, és minden szükséges lépést megtegyen azok teljesítéséhez.

Ez a funkció csak akkor használható, ha végrehajtotta az alábbi beállítást:

- **Termékinformáció-kezelés:** a kiadott termékekhez alkalmazható kódokat állít be.
- **Raktárkezelés:** további szállítási dokumentumok használata szállítási információk nyomtatására.

## <a name="product-information-management"></a>Termékinformáció-kezelés

A Termékinformáció-kezelés részben számos beállítási tábla adható hozzá a közúti, légi és tengeri fuvarozáshoz szükséges veszélyesáru-listákban szereplő hivatkozási adatokhoz.

Íme néhány gyakran hivatkozott előírás:

- **ADR** – a veszélyes áruk nemzetközi közúti fuvarozásával kapcsolatos szabályozások
- **CFR 49** – szabályozások a veszélyes áruk Egyesült Államokban történő szállítására
- **IMDG** – a Veszélyes Áruk Nemzetközi Tengerészeti (IMDG) kódexe
- **IATA** – a Nemzetközi Légiforgalmi Szövetség (IATA) veszélyes árukra vonatkozó szabályozásai

A szabályozások mindegyikének van egy veszélyesáru-listája, amely hivatkozási kódokat tartalmaz. A különböző típusú fuvarozások listája közös nemzetközi osztályozásokon alapszik. A Supply Chain Management tartalmaz egy hivatkozási táblát a lista közös kódjaihoz. Minden lista tartalmaz néhány egyedi kódot is, amelyeket Ön határozhat meg.

Az adatok konfigurálásának megkezdéséhez hozzon létre egy olyan szabályt, amelyet a kezdeti paraméterek konfigurálására használhat fel.

## <a name="warehouse-management"></a>Raktárkezelés

Egy szállítmány előkészítését követően számos új jelentést lehet kinyomtatni. Ezek a jelentések a Termékinformáció-kezelés részben megadott adatokat használják.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]