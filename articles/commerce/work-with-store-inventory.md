---
title: Üzleti árukészlet kezelése
description: A témakör ismerteti, hogy mely dokumentumtípusokat használhat a készlet kezeléséhez.
author: rubencdelgado
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 64106cb1aeea01f1f227247d32b8b1dfdea98362
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020195"
---
# <a name="commerce-inventory-management"></a>Commerce-árukészlet kezelése

[!include [banner](includes/banner.md)]

Amikor készletekkel dolgozik a Microsoft Dynamics 365 Commerce szolgáltatásban, és a Commerce Scale Unit (CSU) szolgáltatáshoz kapcsolódó Commerce-alkalmazásokat használ, fontos tudni, hogy a CSU rendelésfeldolgozási logikája korlátozottan támogat egyes készletdimenziókat és egyes készletcikktípusokat. A Commerce-alkalmazások nem támogatják a cikkek konfigurációs lehetőségeinek teljes tartományát, amely a Dynamics 365 Supply Chain Management cikkek konfigurációjára szolgáló beállításaival érhető el.

A CSU-n futó Commerce-alkalmazások nem támogatják a következő cikkdimenziókat és cikk-konfigurációkat:

- Termékdimenziók és anyagjegyzék (BOM) cikkek konfigurációja (kivéve a kiskereskedelmi csomag termékeit, amelyek az anyagjegyzék keretrendszer egyes összetevőit használják)
- Tényleges súllyal rendelkező cikkek
- Verzió termékdimenzió által vezérelt cikkek

A CSU-n futó Commerce-alkalmazások nem támogatják a következő nyomonkövetési dimenziókat:
- Tulajdonosi dimenzió

- A pénztáralkalmazás korlátozott támogatást nyújt a következő dimenziókhoz. A pénztár ezen dimenziók némelyikét automatikusan megadhatja a készlettranzakciókban a raktár konfigurációja vagy az üzlet beállítása alapján. A pénztár azonban nem teljes mértékben támogatja a dimenziókat, olyan módon, mintha az értékesítési tranzakció manuálisan lenne megadva a Commerce központi felületén. 

- **Raktári hely** – Az új [Bejövő művelet](./pos-inbound-inventory-operation.md) és [Kimenő művelet](./pos-outbound-inventory-operation.md) POS-műveleteinek használata esetén a felhasználók kiválaszthatnak egy raktárkészlet-helyet, amelyben cikkeket fogadnak vagy amelyekből a kimenő szállítási rendelés cikkeit kiszállítják. Ha az elavult **Kitárolás és bevételezés** műveletet alkalmazzák, a bevételezéshez és a kimenő áthelyezések szállításához korlátozott helykezelési támogatás áll rendelkezésre. Ez a támogatás csak akkor érhető el, ha a **Raktárkezelési folyamatok alkalmazása** beállítás be van kapcsolva a cikkhez és az üzlet raktárához. A készlethely nem használható jelenleg a **Leltár** művelettel vagy a **Készletkeresés** művelettel.

- **Azonosítótábla** – Azonosítótábla csak akkor van használatban, ha a **Raktárkezelési folyamatok alkalmazása** beállítás engedélyezve van a cikkhez és az áruházi raktárban. Abban az esetben, ha a készletet a **Bejövő művelet** művelettel vagy olyan **Kitárolás és bevételezés** művelettel kerül bevételezésre egy raktárban, ahol a raktárkezelési folyamat be van kapcsolva, és ha a cikk bevételezéséhez kiválasztott hely azonosítótábla-ellenőrzést igénylő helyprofilhoz kapcsolódik, a POS-alkalmazás szisztematikusan egy azonosítótáblát alkalmaz a fogadó sorban. A POS-felhasználók nem tudják módosítani vagy kezelni ezt az azonosítótábla-adatot. Ha szükséges az azonosítótáblák teljes körű kezelése, akkor javasolt, hogy az üzlet a [raktározási alkalmazást](../supply-chain/warehousing/install-configure-warehousing-app.md) vagy a back office ügyfelet használja a cikkek fogadásának kezelésére.

- **Sorozatszám** – A POS-alkalmazás korlátozottan támogatja egy sorozatszám regisztrálását az értékesítési tranzakciók sorához olyan rendelések esetében, amelyek a pénztárban, sorszámozott cikkekkel lettek létrehozva. Ez a sorozatszám nincs ellenőrizve a már készleten lévő regisztrált sorozatszámokkal szemben. Ha egy értékesítési rendelést a hívásközpont-csatornában hoztak létre, vagy a vállalati erőforrás-tervezési (ERP) rendszeren keresztül van teljesítve, és több sorozatszám lesz regisztrálva egy értékesítési sorhoz az ERP teljesítési folyamata során, akkor ezek a sorozatszámok nem lesznek alkalmazhatók vagy ellenőrizhetők, ha visszárut dolgoznak fel a pénztárban ezekhez a rendelésekhez. Ha a készletet a **Bejövő művelet** használatával bevételezik, a felhasználók [regisztrálhatják vagy megerősíthetik a fogadott sorozatszámokat](./pos-serialized-items.md).

- **Kötegazonosító** – a pénztáralkalmazás korlátozott támogatást nyújt a kimutatásfeladás során, ha kötegvezérelt cikket értékesít, de a pénztár-felhasználók nem tudják meghatározni az eladott vagy kitárolt kötegazonosítót a pénztáralkalmazás használata esetén.

- **Készlet állapota** – A raktárkezelési folyamatot használó cikkek esetében, amelyekhez készletállapot szükséges, ez a mező nem állítható be vagy módosítható a pénztáralkalmazáson keresztül. A bolt raktárkonfigurátorában megadott készletállapot lesz használva, amikor a cikkek megérkeznek a készletbe.

> [!NOTE]
> Az összes szervezetnek tesztelnie kell a cikk-konfigurációkat a fejlesztés alatt álló Commerce-alkalmazásokban tesztelési környezeten keresztül a termelési környezetbe helyezés előtt. Tesztelje a cikkeket a megszokott készpénzes tranzakciók végrehajtásához való felhasználásukkal és ügyfélrendelések létrehozásával (ha van) a pénztáron, hívásközponton vagy e-keresdelmen keresztül, hogy meggyőződjön arról, hogy teljes mértékben támogathatók. Bármilyen cikk-konfiguráció telepítése előtt tesztelje a POS-teljesítéseket és a leltározási folyamatokat (például a készlet bevételezése és a rendelés teljesítése műveletek) is, hogy meggyőződjön róla, hogy a POS-alkalmazás támogatja-e azokat. A tesztelésnek tartalmaznia kell egy teljes kimutatásos/rendelési feladási folyamat futtatását a tesztkörnyezetben, és ellenőriznie kell, hogy a cikkek rendeléseinek Commerce-központban való feladása során nem történik probléma.
>
> Ha a cikkek úgy vannak konfigurálva, amelyet a Commerce-alkalmazások nem támogatnak, és a megfelelő tesztelés nem történik meg, adathibák fordulhatnak elő, amelyek nem könnyen vagy egyáltalán nem javíthatók.

## <a name="purchase-orders"></a>Beszerzési rendelések

A beszerzési rendelések a Commerce-központban jönnek létre. Ha az üzlet raktára szerepel a beszerzési rendelés fejlécében vagy a beszerzési rendelés soraiban, akkor a sorok fogadása az áruháznál történhet a POS [Bejövő művelet](./pos-inbound-inventory-operation.md) műveletével. 

## <a name="transfer-orders"></a>Átmozgatási rendelések

Az átmozgatási rendelések a Commerce-központban hozhatók létre, illetve a [Bejövő művelet](./pos-inbound-inventory-operation.md) vagy a [Kimenő művelet](./pos-outbound-inventory-operation.md) művelettel a POS-rendszerben. A **Bejövő művelet** POS-művelet használatával hozhat létre egy átmozgatási rendelést, amellyel készletet küldhet egy üzletbe egy másik raktárból vagy üzlethelyről. A **Kimenő művelet** POS-művelet használatával hozhat létre egy átmozgatási rendelést, amellyel készletet küldhet egy üzletből egy másik raktárba vagy üzlethelyre. Ha egy üzlethez átmozgatási rendelést hoz létre, az üzlet a pénztár **Bejövő művelet** műveletével kezelheti az átmozgatási rendeléshez tartozó készletbevételezést. Ha az üzlet egy másik helyre szállítja a készletet, a pénztár **Kimenő művelet** művelete használható az üzlet kimenő szállítási folyamatának kezelésére.

## <a name="stock-counts"></a>Leltárok

A leltárok lehetnek ütemezettek és nem tervezettek is. Az ütemezett leltározások a Commerce-központ használatával jönnek létre, létrehozva egy Leltárnapló dokumentumot, amely össze van kapcsolva az üzlet raktárával. Ez a napló a leltározandó cikkeket határozza meg. Az üzlet ezt követően elérheti ezeket az előre megadott leltárnaplókat, és a POS rendszerbeli **Leltározás** művelet használatával kezelheti azokat. Az üzletek felhasználói nem tervezett leltározást kezdeményeznek, mivel ez szükséges, amikor a pénztár **Leltározás** műveletét használják. Az ütemezett leltárakkal ellentétben a nem ütemezett leltárak nem rendelkeznek a cikkek előre meghatározott listájával. Amikor bármely típusú leltár befejeződik a pénztárban, véglegesítésre kerül és a központi irodába küldik. A központi irodában a leltárt ezután külön lépésként kell érvényesíteni és feladni a Commerce-központ alkalmazásban.

## <a name="inventory-lookup"></a>Keresés a készletben

A több üzlet és raktár számára elérhető aktuális készleten levő termékmennyiséget a **Keresés a készletben** lapon tekintheti meg. Az aktuális készleten levő mennyiségen túl az ígérethez rendelkezésre álló (ATP) mennyiségek az egyes üzletek esetében tekinthetők meg. Válassza ki az üzletet, amelynek ígérethez rendelkezésre álló mennyiségeit meg szeretné tekinteni, és válassza ki az **Üzlet elérhetőségének megjelenítése** lehetőséget. A rendelkezésre álló konfigurációs beállításokkal kapcsolatos további tudnivalókat lásd: [Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](./calculated-inventory-retail-channels.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]