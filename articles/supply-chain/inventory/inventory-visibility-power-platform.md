---
title: Készletláthatóság alkalmazás
description: Ez a témakör a Készletláthatóság alkalmazás használatát ismerteti.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a60fc00642a77d3dc595a6222727637f0d7cd588
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475060"
---
# <a name="use-the-inventory-visibility-app"></a>A készletláthatóság alkalmazás használata

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Ez a témakör a Készletláthatóság alkalmazás használatát ismerteti.

A Készletláthatóság modellvezérelt alkalmazást biztosít a vizualizációhoz. Az alkalmazás három oldalt tartalmaz: **Konfiguráció**, **Üzemeltetési láthatóság** és **Készlet-összefoglaló**. A következő jellemzőkkel rendelkezik:

- Felhasználói felületet (UI) biztosít a kézi konfigurációhoz és a lágy foglalások konfigurálásához.
- Támogatja a különböző dimenziókombinációk valós idejű készletlekérdezéseit.
- Felhasználói felületet biztosít a foglalási kérelmek feladásához.
- Egyénre szabott nézetet nyújt a termékek készletéről, az összes dimenzióval együtt.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt elkezdené, telepítse és állítsa be a Készletláthatóság bővítményt a [Készletláthatóság telepítés és beállítása](inventory-visibility-setup.md) című fejezetben leírtak szerint.

## <a name="open-the-inventory-visibility-app"></a>A készletláthatóság alkalmazás megnyitása

A Készletláthatóság alkalmazás megnyitásához jelentkezzen be a Power Apps környezetbe, és nyissa meg a **Készletláthatóság** alkalmazást.

## <a name="configuration"></a><a name="configuration"></a>Konfiguráció

A Készletláthatóság alkalmazás **Konfiguráció** oldala segít a kézi konfiguráció és a lágy foglalási konfiguráció beállításában. A bővítmény telepítése után az alapértelmezett konfiguráció tartalmazza a Microsoft Dynamics 365 Supply Chain Management (a `fno` adatforrás) alapértelmezett beállítását. Az alapértelmezett beállítást felülvizsgálhatja. Ezután az Ön üzleti követelményei és a külső rendszer készletkönyvelési követelményei alapján módosíthatja a konfigurációt, hogy egységesítse a készletváltozások könyvelésének, rendszerezésének és lekérdezésének módját több rendszerben.

A megoldás konfigurálásával kapcsolatos részletes információk itt olvashatók [Készletláthatóság konfigurálása](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Operatív láthatóság

Az **Operatív láthatóság** oldal a különböző dimenziókombinációk alapján egy valós idejű készletlekérdezés eredményeit mutatja be. Ha az *OnHandReservation* funkció be van kapcsolva, akkor az **Operatív láthatóság** oldalról is közzéteheti a foglalási kérelmeket.

### <a name="on-hand-query"></a>Kézi lekérdezés

Az **Kézi lekérdezés** lapon a valós idejű készletlekérdezés eredményei láthatók.

Amikor kiválasztja az **Kézi lekérdezés** lapot, a rendszer lekéri az Ön hitelesítő adatait, hogy megkapja a Bearer tokent, amely a Készletláthatósági szolgáltatás lekérdezéséhez szükséges. A **BearerToken** mezőbe egyszerűen beillesztheti a Bearer tokent, és bezárhatja a párbeszédpanelt. Ezután feltehet egy kézhez kapott lekérdezési kérelmet.

Ha a **BearerToken** mezőbe be kell illesztenie egy újat, ha a BearerToken jelszó érvénytelen vagy lejárt. Adja meg a megfelelő **ügyfél-azonosító**, **bérlőazonosító** és **ügyféltitok** értékeket, majd válassza a **Frissítés** lehetőséget. A rendszer automatikusan kap egy új, érvényes bearer tokent.

Kézi lekérdezés feladásához adja meg a lekérdezést a kérés törzsében. Használja a [lekérdezésben leírt mintát a post módszer használatával](inventory-visibility-api.md#query-with-post-method).

![Kézi lekérdezés beállításai](media/inventory-visibility-query-settings.png "Kézi lekérdezés beállításai")

### <a name="reservation-posting"></a>Foglalási feladás

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Használja a **Foglalások közzététele** lapot a foglalási kérelem feladásához. Mielőtt foglalási kérelmet adhatna fel, be kell kapcsolnia az *OnHandReservation* funkciót. A funkcióval kapcsolatos további információkért lásd a [Készletláthatósági fenntartások](inventory-visibility-reservations.md) című részt.

A foglalási kérelem elküldéséhez meg kell adnia egy értéket a kérelem törzsében. Használja az [Egy foglalási esemény létrehozása](inventory-visibility-api.md#create-one-reservation-event) című fejezetben leírt mintát. Ezután válassza a **Feladás** menüpontot. A kérelemre adott válasz részleteinek megtekintéséhez válassza a **Részletek megjelenítése** lehetőséget. A `reservationId` értéket a válasz adataiból is lekérdezheti.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Készlet-összesítő

A **Készletösszesítő** a *Készlet OnHand Sum Entitás* testreszabott nézete. A termékek készlet összesítését az összes dimenzióval együtt biztosítja. A készletösszegzési adatokat a rendszer rendszeres időközönként szinkronizálja a Készletláthatóságból. A **Készletösszegzés** lapon csak akkor tekintheti meg az adatokat, ha bekapcsolta az *OnHandMostSpecificBackgroundService* szolgáltatást a **Funkciókezelés** lapon.

A Dataverse által biztosított **Speciális szűrő** használatával létrehozhat egy olyan személyes nézetet, amely az Ön számára fontos sorokat mutatja. A fejlett szűrési lehetőségekkel a nézetek széles skáláját hozhatja létre, az egyszerűtől az összetettig. Lehetővé teszik továbbá, hogy csoportosított és egymásba ágyazott feltételeket adjon a szűrőkhöz. Ha többet szeretne megtudni a **Speciális szűrő** használatáról, lásd: [Személyes nézetek szerkesztése vagy létrehozása a speciális rácsszűrők használatával](/powerapps/user/grid-filters-advanced).

A testreszabott nézet tetején három mező található: **Alapértelmezett dimenzió**, **Egyéni dimenzió** és **Méret**. Ezekkel a mezőkkel szabályozhatja, hogy mely oszlopok legyenek láthatóak.

Kiválaszthatja az oszlopfejlécet az aktuális eredmény szűréséhez vagy rendezéséhez.

A testreszabott nézet alján olyan információk jelennek meg, mint például „50 rekord (29 kiválasztott)” vagy „50 rekord”. Ez az információ a **Speciális szűrő** eredményéből jelenleg betöltött rekordokra vonatkozik. A „29 kiválasztott” szöveg a betöltött rekordok oszlopfejlécszűrőjének használatával kiválasztott rekordok számára utal.

A nézet alján található a **Továbbiak betöltése** gomb, amellyel további rekordokat tölthet be a Dataverse rendszerből. A betöltött rekordok alapértelmezett száma 50. Ha a **Továbbiak betöltése** lehetőséget választja, a következő 1000 elérhető rekord kerül betöltésre a nézetbe. A **Továbbiak betöltése** gombon megjelenő szám a jelenleg betöltött rekordokat és a **Speciális szűrő** eredményének összes rekordját jelzi.

![Készlet-összesítő](media/inventory-visibility-onhand-list.png "Készlet-összesítő")
