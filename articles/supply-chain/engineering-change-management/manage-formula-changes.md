---
title: Receptúrák és receptúra-összetevők változásainak kezelése
description: Ez a témakör azt ismerteti, hogyan kezelhetők a receptúrák és a folyamatszerű gyártás alapadatainak változásai.
author: t-benebo
ms.date: 05/19/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d25ddfc992d49c9a3c24d03cb0c71d68f7aa21fa
ms.sourcegitcommit: 908a85987b604a7782407da70fb70ef75c07989f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/19/2021
ms.locfileid: "6641104"
---
# <a name="manage-changes-in-formulas-and-their-ingredients"></a>Receptúrák és receptúra-összetevők változásainak kezelése

[!include [banner](../includes/banner.md)]

Ha a folyamatszerű gyártáshoz a Microsoft Dynamics 365 Supply Chain Management funkcióit használja, akkor használhatja a kapcsolódó receptúrakezelési funkciókat a következő változások kezeléséhez:

- **Receptúra és tervezési cikkek:** A receptúrákban, a társtermékekben és a melléktermékekben lévő összetevők változásainak kezelése.
- **Társtermékek és melléktermékek:** A társ- és melléktermékek mennyiségének és más részletének szerkesztése a receptúrákban.
- **Tényleges súllyal rendelkező cikkek:** A tényleges súllyal rendelkező cikkek módosításainak kezelése.

## <a name="turn-on-this-feature-in-your-system"></a>A funkció bekapcsolása a rendszerben

A képesség használatához az alábbi feladatokat kell elvégeznie:

1. Engedélyezze a *Tervezési változáskezelés* funkciót és a funkció konfigurációs kulcsát a [Tervezési változáskezelés áttekintése](product-engineering-overview.md) részben leírtak szerint. Amint az említett témakörben is szerepel, győződjön meg arról, hogy engedélyezve van a **Változáskezelés a folyamatszerű gyártáshoz**, a fő **Tervezési változáskezelés** licenckulcs alá beágyazott licenckulcs.
1. Kapcsolja be a *Receptúrák és az összetevőik módosításainak kezelése* funkciót a [Funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="feature-naming-conventions"></a>Funkcióelnevezési konvenciók

A Supply Chain Management felhasználói felületén (UI) és dokumentációjában a változáskezelési funkciót általában *tervezési változáskezelésként*, a kezelhető termékeket pedig általában *tervezési termékekként* említjük. Bár ez a terminológia többnyire nem használatos a folyamatszerű gyártás képleteinek kezelésénél, a tervezési változáskezelés felfogható egyszerű változáskezelésként, a tervezési termékek pedig verziószámmal rendelkező termékként.

## <a name="work-with-formula-change-management-features"></a>A receptúra változáskezelési szolgáltatásainak használata

Az alábbi listában összefoglaltuk, hogyan érintik a tervezési változáskezelési funkciók a receptúrakezelést. A lista a további információkra mutató hivatkozásokat is tartalmaz. Mivel a receptúrák változáskezelése a tervezési változáskezelési funkciókat használja, érdemes megismerni a tervezési változáskezelés általános működését, hogy használni tudja a receptúrák és az összetevőik kezeléséhez.

- **Központosított termékadat-kezelés** – olyan szervezet beállítása, amely felügyelt kiadási folyamaton keresztül gondoskodik arról, hogy pontos és releváns termékadatok legyenek elérhetők a vállalat felhasználói számára. További tájékoztatás: [Mérnöki vállalatok és az adatok tulajdonlásának szabályai](engineering-org-data-ownership-rules.md).
- **Termék verziószámozása** – a termékek változásainak nyomon követése a termékverziókon keresztül, és a termék felügyelete az ellátási lánc minden állomásán. Ezzel a megoldással nyomon követheti a receptúrák változásait. A további tudnivalókat lásd: [Mérnöki verziók és a mérnöki termékkategóriák](engineering-versions-product-category.md).
- **Termékéletciklus kezelése** – a termékadatok láthatóságának kezelése a szervezeten belül, és a termékverziók elérhetőségének szabályozása az ellátási lánc mindegyik fázisában. Részletesen szabályozhatja, hogy egy termékverzió mikor használható konkrét üzleti folyamatokban, és az üzleti igényekhez igazodó saját életciklus-állapotokat hozhat létre. További információ: [Termékéletciklus-állapotok és tranzakciók](product-lifecycle-state-transactions.md).
- **Receptúraváltozások kezelése** – a szervezet felhasználói kérhetik a receptúrák módosítását. A módosítási utasításokkal értékelheti és dokumentálhatja a javasolt módosítások hatását. Munkafolyamatok hozzáadása a módosítási folyamat és a termék és a termékreceptúra új verziói kiadásának kezeléséhez. További tájékoztatást [A mérnöki termékek módosításának kezelése](engineering-change-management.md) részben talál.
- **Készenléti ellenőrzés** – a rendszerellenőrzések és a felhasználói útmutatások (kérdőívek és ellenőrzőlisták) használatával gondoskodhat arról, hogy az összes szükséges termékadat teljes mértékben meg legyen adva a termék kiadása előtt. További információ: [Termékkészenlét](product-readiness.md).
- **Továbbfejlesztett termék-kiadási funkció** – a termék teljes körűen definiált verzióinak és a termék receptúráinak kiadása egy szervezettől (jogi személytől) más jogi személyeknek. Azt is eldöntheti, hogy a termék adatait ellenőrizni kell-e vagy szerkeszteni kell-e a kiadás előtt. További információért lásd: [Termékstruktúrák kiadása](release-product-structure.md)

Ne feledje, hogy az előző listában hivatkozott témakörök nagy része olyan példákat tartalmaz, amelyek anyagjegyzéken alapulnak. A receptúrák ugyanakkor hasonló módon működnek. Az alábbi néhány további fogalom jól használható annak megállapításához, hogy mikor érdemes változáskezelést (vagy csak receptúraváltozás-kezelést) használni a receptúrák és az anyagjegyzékek kezeléséhez:

- Minden [terméktervezési kategóriához](engineering-versions-product-category.md) megadható a termelés típusa (anyagjegyzék, receptúra vagy tervezési cikk). Megadhatja azt is, hogy szükséges-e a tényleges súly támogatása a kategóriát használt termékek esetében.
- A társtermékek és a melléktermékek nem tervezési termékek. Ennek megfelelően nincs verziószámuk. Ha módosítania kell őket, hozzon létre új terméket. Ezzel a módszerrel egyszerűbb a karbantartás.
- Kezelhetők az olyan végtermékek, amelyek anyagjegyzékek és amelyekhez gyermekreceptúrás cikkek tartoznak. Ez a funkció az olyan anyagjegyzékek valamennyi kombinációja esetén használható, amelyek receptúrákat és/vagy anyagjegyzéket tartalmazó receptúrákat tartalmaznak.
