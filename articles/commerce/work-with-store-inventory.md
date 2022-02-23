---
title: Üzleti árukészlet kezelése
description: A témakör ismerteti, hogy mely dokumentumtípusokat használhat a készlet kezeléséhez.
author: rubencdelgado
manager: AnnBe
ms.date: 05/15/2020
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
ms.openlocfilehash: a3e6450c358d12dc62c2ffa20e7ff529be86bbe5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412876"
---
# <a name="store-inventory-management"></a>Áruházi árukészlet kezelése

[!include [banner](includes/banner.md)]

Amikor a készletet kezeli a Microsoft Dynamics 365 Commerce alkalmazásban, és a pénztár (POS) alkalmazást használja, fontos, hogy a POS rendszer korlátozott támogatást biztosítson néhány készletdimenzióhoz és néhány készletelemtípushoz. A POS-alkalmazás nem támogatja a cikkek konfigurációs lehetőségeinek teljes tartományát, amely a Dynamics 365 Supply Chain Management cikkek konfigurációjára szolgáló beállításaival érhető el.

A POS-megoldás jelenleg nem támogatja a következő cikkdimenziókat és cikk-konfigurációkat:

- Termékdimenziók és anyagjegyzék (BOM) cikkek konfigurációja (kivéve a kiskereskedelmi csomag termékeit, amelyek az anyagjegyzék keretrendszer egyes összetevőit használják)
- Tényleges súllyal rendelkező cikkek
- Verzió termékdimenzió által vezérelt cikkek

A POS alkalmazás jelenleg nem támogatja a következő nyomon követési dimenziókat a POS-ben:

- Kötegkövetési-dimenzió
- Tulajdonosi dimenzió

A POS a következő dimenziókhoz korlátozott támogatást nyújt. Más szóval a POS ezen dimenziók némelyikét automatikusan megadhatja a készlettranzakciókban a raktár konfigurációja vagy az üzlet beállítása alapján. A POS nem teljes mértékben támogatja a dimenziókat, olyan módin, mintha az értékesítési tranzakció manuálisan lenne megadva a Commerce központban. 

- **Raktári hely** – Az új [Bejövő művelet](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) és [Kimenő művelet](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) POS-műveleteinek használata esetén a felhasználók kiválaszthatnak egy raktárkészlet-helyet, amelyben cikkeket fogadnak vagy amelyekből a kimenő szállítási rendelés cikkeit kiszállítják. Ha az elavult **Kitárolás és bevételezés** műveletet alkalmazzák, a bevételezéshez és a kimenő áthelyezések szállításához korlátozott helykezelési támogatás áll rendelkezésre. Ez a támogatás csak akkor érhető el, ha a **Raktárkezelési folyamatok alkalmazása** beállítás be van kapcsolva a cikkhez és az üzlet raktárához. A készlethely nem használható jelenleg a **Leltár** művelettel vagy a **Készletkeresés** művelettel.
- **Azonosítótábla** – Azonosítótábla csak akkor van használatban, ha a **Raktárkezelési folyamatok alkalmazása** beállítás engedélyezve van a cikkhez és az áruházi raktárban. Abban az esetben, ha a készletet a **Bejövő művelet** művelettel vagy olyan **Kitárolás és bevételezés** művelettel kerül bevételezésre egy raktárban, ahol a raktárkezelési folyamat be van kapcsolva, és ha a cikk bevételezéséhez kiválasztott hely azonosítótábla-ellenőrzést igénylő helyprofilhoz kapcsolódik, a POS-alkalmazás szisztematikusan egy azonosítótáblát alkalmaz a fogadó sorban. A POS-felhasználók nem tudják módosítani vagy kezelni ezt az azonosítótábla-adatot. Ha szükséges az azonosítótáblák teljes körű kezelése, akkor javasolt, hogy az üzlet a [raktározási alkalmazást](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/install-configure-warehousing-app) vagy a back office ügyfelet használja a cikkek fogadásának kezelésére.
- **Sorozatszám** – A POS-alkalmazás korlátozottan támogatja egy sorozatszám regisztrálását az értékesítési tranzakciók sorához olyan rendelések esetében, amelyek a pénztárban, sorszámozott cikkekkel lettek létrehozva. Ez a sorozatszám nincs ellenőrizve a már készleten lévő regisztrált sorozatszámokkal szemben. Ha egy értékesítési rendelést a hívásközpont-csatornában hoztak létre, vagy a vállalati erőforrás-tervezési (ERP) rendszeren keresztül van teljesítve, és több sorozatszám lesz regisztrálva egy értékesítési sorhoz az ERP teljesítési folyamata során, akkor ezek a sorozatszámok nem lesznek alkalmazhatók vagy ellenőrizhetők, ha visszárut dolgoznak fel a pénztárban ezekhez a rendelésekhez. Ha a készletet a **Bejövő művelet** használatával bevételezik, a felhasználók [regisztrálhatják vagy megerősíthetik a fogadott sorozatszámokat](https://docs.microsoft.com/dynamics365/commerce/pos-serialized-items).
- **Készlet állapota** – A raktárkezelési folyamatot használó cikkek esetében, amelyekhez készletállapot szükséges, ez a mező nem állítható be vagy módosítható a pénztáralkalmazáson keresztül. A bolt raktárkonfigurátorában megadott készletállapot lesz használva, amikor a cikkek megérkeznek a készletbe.

> [!NOTE]
> Az összes szervezetnek tesztelnie kell a cikk-konfigurációkat a fejlesztés alatt álló POS-en tesztelési környezeten keresztül a termelési környezetbe helyezés előtt. Tesztelje a cikkeket a megszokott készpénzes tranzakciók végrehajtásához való felhasználásukkal és ügyfélrendelések létrehozásával (ha van) a pénztáron keresztül. Bármilyen cikk-konfiguráció telepítése előtt tesztelje a POS-teljesítéseket és a leltározási folyamatokat (például a készlet bevételezése és a rendelés teljesítése műveletek) is, hogy meggyőződjön róla, hogy a POS-alkalmazás támogatja-e azokat. A tesztelésnek tartalmaznia kell egy teljes kimutatásos feladási folyamat futtatását a tesztkörnyezetben, és ellenőriznie kell, hogy a cikkek rendeléseinek Commerce-központban való létrehozása és feladása során nem történik probléma.
>
> Ha a cikkek konfigurálása olyan módon történik, hogy a POS-alkalmazás nem biztosít támogatást, és a megfelelő tesztelés nem történt meg, akkor a rendelés létrehozási folyamata során nehezen javítható vagy a szokásos terméktámogatásban nem szereplő problémák merülhetnek fel.

## <a name="purchase-orders"></a>Beszerzési rendelések

A beszerzési rendelések a Commerce-központban jönnek létre. Ha az üzlet raktára szerepel a beszerzési rendelés fejlécében vagy a beszerzési rendelés soraiban, akkor a sorok fogadása az áruháznál történhet a POS [Bejövő művelet](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) műveletével. 

## <a name="transfer-orders"></a>Átmozgatási rendelések

Az átmozgatási rendelések a Commerce-központban hozhatók létre, illetve a [Bejövő művelet](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) vagy a [Kimenő művelet](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) művelettel a POS-rendszerben. A **Bejövő művelet** POS-művelet használatával hozhat létre egy átmozgatási rendelést, amellyel készletet küldhet egy üzletbe egy másik raktárból vagy üzlethelyről. A **Kimenő művelet** POS-művelet használatával hozhat létre egy átmozgatási rendelést, amellyel készletet küldhet egy üzletből egy másik raktárba vagy üzlethelyre. Ha egy üzlethez átmozgatási rendelést hoz létre, az üzlet a pénztár **Bejövő művelet** műveletével kezelheti az átmozgatási rendeléshez tartozó készletbevételezést. Ha az üzlet egy másik helyre szállítja a készletet, a pénztár **Kimenő művelet** művelete használható az üzlet kimenő szállítási folyamatának kezelésére.

## <a name="stock-counts"></a>Leltárok

A leltárok lehetnek ütemezettek és nem tervezettek is. Az ütemezett leltározások a Commerce-központ használatával jönnek létre, létrehozva egy Leltárnapló dokumentumot, amely össze van kapcsolva az üzlet raktárával. Ez a napló a leltározandó cikkeket határozza meg. Az üzlet ezt követően elérheti ezeket az előre megadott leltárnaplókat, és a POS rendszerbeli **Leltározás** művelet használatával kezelheti azokat. Az üzletek felhasználói nem tervezett leltározást kezdeményeznek, mivel ez szükséges, amikor a pénztár **Leltározás** műveletét használják. Az ütemezett leltárakkal ellentétben a nem ütemezett leltárak nem rendelkeznek a cikkek előre meghatározott listájával. Amikor bármely típusú leltár befejeződik a pénztárban, véglegesítésre kerül és a központi irodába küldik. A központi irodában a leltárt ezután külön lépésként kell érvényesíteni és feladni a Commerce-központ alkalmazásban.

## <a name="inventory-lookup"></a>Keresés a készletben

A több üzlet és raktár számára elérhető aktuális készleten levő termékmennyiséget a **Keresés a készletben** lapon tekintheti meg. Az aktuális készleten levő mennyiségen túl az ígérethez rendelkezésre álló (ATP) mennyiségek az egyes üzletek esetében tekinthetők meg. Válassza ki az üzletet, amelynek ígérethez rendelkezésre álló mennyiségeit meg szeretné tekinteni, és válassza ki az **Üzlet elérhetőségének megjelenítése** lehetőséget. A rendelkezésre álló konfigurációs beállításokkal kapcsolatos további tudnivalókat lásd: [Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).
