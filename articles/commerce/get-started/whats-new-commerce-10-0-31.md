---
title: A Dynamics 365 Commerce 10.0.31 (2023. február) előzetes verziója
description: Ez a témakör olyan funkciókat ír le, amelyek vagy Microsoft Dynamics 365 Commerce újak, vagy módosulnak a 10.0.31-ben.
author: josaw1
ms.date: 10/18/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-10-01
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: ed4325095163415d05a56128cb1f0334440fe0e5
ms.sourcegitcommit: c364f50ea0ad50bac5c30724b6ce301d9574b653
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2022
ms.locfileid: "9787526"
---
# <a name="preview-of-dynamics-365-commerce-10031-february-2023"></a>A Dynamics 365 Commerce 10.0.31 (2023. február) előzetes verziója

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek újak Microsoft Dynamics 365 Commerce vagy módosulnak a 10.0.31-es verzió előnézetében. Ennek a verziónak a buildszáma több 10.0.1406, és a következő ütemezésben érhető el:

- **A kiadás előzetes verziója** 2022. október
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2023. január
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2023. február

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Előfordulhat, hogy a cikk frissítése a cikk eredeti közzététele után a buildhez hozzáadott funkciókat is tartalmazza.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Hibakódok | A Commerce rendszer szabványos hibahivatkozásokat vezetett be, amelyek az online csatorna online csatorna-pénztári hibáiba bekerülnek.| [Pénztár modul hibakódja](../checkout-module-error-codes.md)  | Alapértelmezés szerint be |
| Fizetések | [A Dynamics 365 Payment Connector for Adyen fizetési engedélyezése](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-apple-pay-dynamics-365-payment-connector-adyen)  | Az e-commerce vevők a támogatott eszközök és böngészők használata esetén a Bevásárlókocsiba és a Pénztárba fizethet oldalokat használhatnak. | Fejlesztői jelentkezés |
| Fizetések  |  A Commerce hozzáadta a lehetőséget, hogy korlátozza az ismétlődő fizetési tokenekkel való felhasználói kapcsolatot a Commerce Headquarters felhasználói felületén. A fizetési képernyők (például **a Hívásközpont** értékesítési rendelése) már nem jelenítik meg a vevő korábban használt ismétlődő fizetési tokenját az új tranzakciókban való használatra. Új tranzakció kifizetésének feldolgozásakor a hívásközponti vagy a Commerce Headquarters felhasználói csak egy meghatározott "fájlkártya" jelennek meg a Commerce **Customer Payments** képernyőn, illetve egy értékesítési rendelésen keresztül történő fizetéssel egy vevővel kötött megállapodással. | [Fizetési kód használatának korlátozása](../dev-itpro/limit-token-usage.md)  |  Funkció kezelése<p>*Fizetési jogkivonat használatának korlátozása a rendelési környezetre*  |
| Pénztár | [Beszerzési rendelések létrehozása a POS-ból](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/create-purchase-orders-pos)  |  Továbbfejlesztett bejövő készletművelet a pénztári alkalmazásban, amely lehetővé teszi a felhasználók számára beszerzési rendelési kérelmek létrehozására, szerkesztésére és megerősítésére. |  Funkció kezelése<p>*Lehetőség a beszerzési rendelési kérések létrehozására a pénztárban*   |
| További nyelvek érhetők el | Négy további nyelv érhető el. | A preferált nyelvi listában négy új nyelv érhető el a felhasználók számára: Koreai, Portugál (Brazil), Vietnami és Kínai (Hagyományos). Ennek a beállításnak a kiválasztásához kattintson a Felhasználói beállítások **\>  \> beállításai - Nyelv és az ország/régió kívánt nyelvére.** | Honosított beállítások |  



## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Pénzügy és az Üzemeltetés alkalmazás platformfrissítései

A Microsoft Dynamics 365 Commerce 10.0.31 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügyi és műveleti alkalmazások 10.0.31-es verziójának Platformfrissítései (2023. február)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-31.md). 
  

### <a name="bug-fixes"></a>Hibajavítások

A 10.0.31-es verzióba foglalt frissítések hibajavításával kapcsolatos információk megtekintéséhez jelentkezzen be a Lifecycle Services szolgáltatásba, Microsoft Dynamics és tekintse meg a tudásbáziscikket [.](https://fix.lcs.dynamics.com/Issue/Details?bugId=758525)

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 és ipari felhők: 2022-es 2. kiadási hullám csomag

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Tekintse meg a [Dynamics 365 és ipari felhők: 2022-es 2. kiadási hullám csomag](/dynamics365-release-plan/2022wave2/) tartalmát. A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-commerce-features"></a>A Commerce rendszer eltávolította és elavult funkcióit

A [cikk Eltávolított vagy elavult Dynamics 365 Commerce](removed-deprecated-features-commerce.md) funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva vagy el vannak távolítva a Commerce rendszerből.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Commerce](removed-deprecated-features-commerce.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.


Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
