---
title: Üzleti árukészlet kezelése
description: A témakör ismerteti, hogy mely dokumentumtípusokat használhat a készlet kezeléséhez.
author: rubencdelgado
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 02f8afbe3bb6f94c66a8b5aa02531c219adc3963
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "339234"
---
# <a name="store-inventory-management"></a>Üzleti árukészlet kezelése

[!include [banner](includes/banner.md)]

A témakör ismerteti, hogy mely dokumentumtípusokat használhat a készlet kezeléséhez.

A következő típusú dokumentumok segítségével a kezelheti a szervezete készletét.

Készletek kezelésekor Dynamics 365 for Retail alkalmazásban és a POS alkalmazás használatakor, fontos megjegyezni, hogy POS korlátozott támogatást nyújt készletdimenziókhoz és az egyes készletcikk típusokhoz.  

A POS-megoldás nem támogatja a következő cikk-konfigurációkat:
- Anyagjegyzék-cikkek (kivéve a csomagtermékeket, amelyek használják az anyagjegyzék-keretrendszer bizonyos összetevőit)
- Tényleges súllyal rendelkező cikkek
- Kötegvezérelt cikkek

A POS alkalmazás jelenleg nem támogatja a következő nyomon követési dimenziókat a POS-ben:
- Kötegkövetési-dimenzió
- Tulajdonosi dimenzió

A POS-megoldás a következő dimenziókhoz korlátozott támogatást nyújt. Korlátozott támogatás azt jelzi, hogy a POS esetleg ezen dimenziók némelyikét a automatikusan készlettranzakciókká alakítja a raktár/üzlet a telepítési konfigurációja alapján. POS nem teljes mértékben támogatja a dimenziók, olyan módin, mintha az értékesítési tranzakció manuálisan lenne megadva az ERP-ben. 

- Tárolóhely
- Azonosítótábla (csak akkor vonatkozik, ha a **Raktárkezelési folyamatok alkalmazása** engedélyezve van a cikkhez és az áruházi raktárban)
- Sorozatszám
- Készlet állapota

> [!NOTE]
> Az összes szervezetnek tesztelnie kell a cikk-konfigurációkat a fejlesztés alatt álló POS-en tesztelési környezeten keresztül a termelésbe helyezés előtt. Teszteljék a cikkeket a megszokott készpénzes tranzakciók és ügyfélrendelések létrehozásával (ha van) az elemek a POS-en keresztül a cikkeivel. A tesztelésnek tartalmaznia kell teljes nyilatkozatközzétételi folyamatokat a tesztkörnyezetben, és ellenőrizni kell, hogy ne legyenek problémák.
> Cikkek konfigurálása oly módon, amelyet POS alkalmazás nem támogat megfelelő tesztelés nélkül, a kimutatás feladási folyamat hibáját okozhatja a termelés során, anélkül, hogy könnyen javítani lehetne a problémákat. Az alkalmazás partneri vagy ügyfél-testreszabásai esetleg megfontolhatók, hogy lehetséges legyen ezen feladási folyamatok sikeres elvégzése. Ha nincs szükség testreszabásokra, a szervezetnek biztosítania kell, hogy megtörtént a termékek a termékkonfigurációja oly módon, hogy azt a szokások POS alkalmazás/rendelés létrehozása/kimutatásfeladási folyamat támogassa.

## <a name="purchase-orders"></a>Beszerzési rendelések

A beszerzési rendeléseket a központi irodában készítik. Ha kiskereskedelmi raktár szerepel a beszerzési rendelés fejlécében, akkor a rendelés fogadása az áruháznál történhet a Modern POS (MPOS) vagy a felhőalapú POS segítségével a Microsoft Dynamics 365 for Retail szolgáltatásban. Az üzletben fogadott mennyiségek beírását követően az értékek helyben menthetők a további módosításokhoz. Másik lehetőségként a mennyiségek vállalhatóak és a központi irodába küldhetőek. A központi irodában az üzlet által bevételezett mennyiségek kijelzésre kerülnek a Dynamics 365 for Retail rendszerben a beszerzési rendelés **Fogadás** mezőjében.

## <a name="transfer-orders"></a>Átmozgatási rendelések

Az átmozgatási rendelés megadhatja, hogy egy adott üzlet egy olyan hely, ahonnan cikkek szállíthatóak. Ebben az esetben az átmozgatási rendelés megjelenik az üzletben Modern POS vagy Cloud POS rendszerben kitárolási kérelemként. Miután a kért mennységek kitárolódnak vállalásra kerülnek és a központi irodába lesznek küldve. A központi irodában az üzlet által felvett mennyiségek kijelzésre kerülnek a Dynamics 365 for Retail rendszerben az átviteli rendelés **Küldés** mezőjében. Az átmozgatási rendelés megadhatja, hogy egy adott üzlet egy olyan hely, ahová cikkek szállíthatóak. Ebben az esetben az átmozgatási rendelés megjelenik az üzletben az MPOS vagy Cloud POS rendszerben bevételezési kérelemként. Az üzletben fogadott mennyiségek beírását követően az értékek helyben menthetők a további módosításokhoz. Másik lehetőségként a mennyiségek vállalhatóak és a központi irodába küldhetőek. A központi irodában az üzlet által bevételezett mennyiségek kijelzésre kerülnek a Dynamics 365 for Retail rendszerben az átviteli rendelés **Fogadás** mezőjében.

## <a name="stock-counts"></a>Leltárok

A leltárok lehetnek ütemezettek és nem tervezettek is. A tervezett leltárokat a központi irodában kezdeményezik, ami meghatározza, hogy melyik cikkeket kell leltározni. A központi iroda létrehoz egy leltárbizonylatot, amelyet fogadni tudnak az üzletnél, ahol a tényleges készletmennyiségeket rögzítik az MPOS vagy a Cloud POS rendszerben. A nem ütemezett leltárakat az üzlet kezdeményezi, és a frissített tényleges készletmennyiségeket vagy az MPOS, vagy a Cloud POS rendszerben rögzítik. Az ütemezett leltárakkal ellentétben a nem ütemezett leltárak nem rendelkeznek a cikkek előre meghatározott listájával. Amikor bármely típusú leltár befejeződik vállalásra kerül és a központi irodába küldik. A központi irodában a leltárt ellenőrzik és feladják.

## <a name="inventory-lookup"></a>Keresés a készletben

A több üzlet és raktár számára elérhető aktuális készleten levő termékmennyiséget a Keresés a készletben lapon tekintheti meg. Az aktuális készleten levő mennyiségen túl az ígérethez rendelkezésre álló (ATP) mennyiségek az egyes üzletek esetében tekinthetők meg. Ehhez válassza ki azt az üzletet, amelyre vonatkozóan meg akarja jeleníteni az ígérethez rendelkezésre álló mennyiséget, és kattintson az **Üzlet elérhetőségének megjelenítése** lehetőségre.
