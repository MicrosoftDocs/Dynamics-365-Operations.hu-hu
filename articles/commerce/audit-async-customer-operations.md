---
title: Vevői műveletek auditálási szinkronizálása a központban
description: Ez a cikk bemutatja, hogyan lehet Microsoft Dynamics 365 Commerce a központi vevői műveletek szinkronizálását a webhely felhasználói problémáinak kijavítása érdekében auditálásra.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-28
ms.openlocfilehash: c615b0b436e01a1423b5611a72f0056b5b14f8e8
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690955"
---
# <a name="audit-synchronization-of-customer-operations-in-headquarters"></a>Vevői műveletek auditálási szinkronizálása a központban

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a cikk bemutatja, hogyan lehet Microsoft Dynamics 365 Commerce a központi vevői műveletek szinkronizálását a webhely felhasználói problémáinak kijavítása érdekében auditálásra.

Miközben a szervezetek elkezdik elfogadni a vevők aszinkron létrehozására és szerkesztésére való képességet, a webhelygazdáknak a webhely felhasználói kérései vagy a folyamat hibája alapján meg kell tekinteniük és el kell látnia a műveleteket, és hibaelhárítást kell kérniük. Ilyen helyzetekben a webhelygazdáknak lehetővé kell tenni a vevő-létrehozások auditálását és a műveletek szerkesztését, valamint az esetleges hibák kijavítését az önkiszolgáló rendszer használatával.

## <a name="customer-synchronization-status"></a>Vevői szinkronizálás állapota

Ha a vevőkezelés aszinkron módját és ennek megfelelő funkcióit használja, a Commerce Headquarters rendszergazdáinak létre kell hozniuk és be kell ütemezniük egy ismétlődő kötegelt feladatot a **P-feladatra**, **a vevők és üzleti partnerek szinkronizálása az aszinkron** módból és a 1010-es **feladatra,** hogy az aszinkron vevőket a Commerce Headquarters vevői szinkronizálják. A feladatok futtatásakor a vevőkezelési műveletek szinkronizálására kerül sor. A további tudnivalókat lásd [az Aszinkron vevő-létrehozási módban](async-customer-mode.md).

Üzlet tulajdonosaként a következő műveleteket végezheti el:

- A webhely felhasználóinak létrehozási/szerkesztési műveleteinek megtekintése. A részletek között szerepel az állapot és az időbélyeg.
- A műveletek szűrése a vevőtábla bármely mezőjének és értékeinek használatával a könyvvizsgálati napló szűkítésére.
- A változások rövid leírásának, valamint az állapot részleteinek megtekintése a műveletek felső szintű áttekintésének érdekében.
- Hiba esetén szerkessze és javítsa ki a problematikus mezőket, majd mentse és szinkronizálja az adott vevői műveleteket.

### <a name="elements-on-the-customer-synchronization-status-page"></a>A Vevőszinkronizálási állapot oldal elemei

Az összes szinkronizálási művelet listájának megtekintéséhez a Commerce Headquarters a **Commerce and Retail \> Customers Customer \> szinkronizálási állapotát jelzi**. Az alábbi ábra a vevőszinkronizálási **állapot lap egy példáját** mutatja be.

![Vevőszinkronizálási állapot lap a Commerce Headquarters szolgáltatásban](media/D365-Commerce-Customer-Mgmt-Audi-Async-Operations.png)

Alapértelmezés szerint a **vevőszinkronizálási** állapot oldalának bal oldalán található vevőszinkronizálási műveletek listája a következő oszlopokat tartalmazza:

- Csatorna neve
- Vevői számla
- Aszinkron vevői számla
- Műveletek időbélyegzőja
- Vevőszinkronizálás állapota

A lap jobb felső részén megjelenik a vevőkód részletei, **például** a Vevőkód, a **Retail async művelet**, **a Vevőszinkronizálási** állapot és **a Legutóbbi ismert hibaértékek**.

A **Módosítás leírása** szakasz a futtatott vevőkezelési művelet típusának leírását tartalmazza (például vevő létrehozása, számlafrissítés vagy szinkronizálási hiba a részletekkel).

A **Vevőattribútumok** szakasz egy rácsot tartalmaz, amely minden vevőattribútumot, valamint a régi és az új értékeket tartalmazza. Ez a szakasz akkor szerkeszthető, ha módosítani szeretné a vevő attribútumértékét, hogy kijavítsa a javítást, majd újra szinkronizálja őket.
