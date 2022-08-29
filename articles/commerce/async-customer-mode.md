---
title: Aszinkron vevőlétrehozási mód
description: Ez a témakör az aszinkron vevő-létrehozási módot írja le a Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 1ac1bc842d5d12ece8951ffed18157e6f9b50d14
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228723"
---
# <a name="asynchronous-customer-creation-mode"></a>Aszinkron vevőlétrehozási mód

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör az aszinkron vevő-létrehozási módot írja le a Microsoft Dynamics 365 Commerce.

A Commerce rendszer kétféle módon létrehozására használható: szinkron (vagy szinkron) és aszinkron (vagy aszinkron). Alapértelmezés szerint a vevők létrehozása szinkronban történik. Más szóval a Commerce Headquarters valós idejű létrehozásuk után jön létre. A szinkron vevő-létrehozási módra azért van hatással, mert az új vevők azonnal kereshetők a különböző csatornákon keresztül. Ennek azonban van egy hátránya is. Mivel [Commerce Data Exchange Valós idejű szolgáltatás](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) típusú hívásokat generál a Commerce központi felülete irányába, befolyásolhatja a teljesítményt, ha a rendszer sok egyidejű vevői létrehozási hívást kezdeményez.

Ha a **Vevő létrehozása aszinkron módban** beállítás értéke **Igen** az üzlet funkcióprofiljában (**Retail és Commerce \> Csatorna beállítás \> Online áruház beállítása \> Funkcióprofilok**), akkor a valós idejű szolgáltatás típusú hívások nem használhatók vevőrekordok létrehozásához a csatorna-adatbázisban. Az aszinkron vevő létrehozási módja nem befolyásolja a Commerce Headquarters teljesítményét. A rendszer minden új async Customer rekordhoz egy ideiglenes globálisan egyedi azonosítót (GUID) rendel, amely vevői számlaazonosítóként használatos. Ez a GUID nem jelenik meg a pénztári felhasználók számára. Ehelyett ezek a felhasználók a **Függőben lévő szinkronizálás** lehetőséget látják vevői számlaazonosítóként.

> [!IMPORTANT]
> Amikor a POS ki van kapcsolva, a rendszer automatikusan aszinkron módon hoz létre vevőket még akkor is, ha az aszinkron vevő létrehozási módja le van tiltva. Így függetlenül attól, hogy milyen beállításokat adott meg a szinkronizálás és az async Customer létrehozása között, a Commerce Headquarters rendszergazdáinak létre kell hozniuk és be kell ütemeznie egy ismétlődő kötegelt feladatot a **P-feladatra**, **a vevők és üzleti partnerek szinkronizálása aszinkron módból és a** 1010-es **feladatot,** hogy az aszinkron vevőket szinkronizálni tudja a Commerce Headquarters alkalmazás.

## <a name="async-customer-limitations"></a>Az aszinkron vevőkkel kapcsolatos korlátozások

Az async Customer funkcióira jelenleg a következő korlátozások vonatkoznak:

- Az aszinkron vevőknek csak akkor lehet hűségkártyákat kiadni, ha az új vevőazonosítót szinkronizálták a csatornával.

## <a name="async-customer-enhancements"></a>Async Customer továbbfejlesztései

Annak érdekében, hogy a szervezetek az aszinkron vevő-létrehozási módot használják a vevők kezelésére, valamint a Commerce Headquarters alkalmazással való valós idejű kommunikáció csökkentésére, a következő továbbfejlesztésekkel elérhető a szinkronizációs és az aszinkron üzemmódok paritása a csatornákban. 

| Funkció javítása | Commerce rendszer verziója | Funkció részletei |
|---|---|---|
| Teljesítményjajavítások a vevői adatoknak a csatorna-adatbázisból való beolvasása során | 10:0.20 és később | A jobb teljesítmény érdekében az ügyfélentitás kisebb entitások között van felosztva. A rendszer ezután csak a szükséges adatokat olvassa be a csatorna-adatbázisból. |
| Aszinkron címszinkron létrehozási képesség a pénztárnál | 10.0.22 és később | <p>Funkciógomb: **Aszinkron létrehozás engedélyezése vevői címekhez**</p><p>Funkció részletei:</p><ul><li>Címek hozzáadásának képessége a Commerce Headquarters alkalmazásba való valós idejű szolgáltatási hívások nélkül</li><li>A címek egyedi azonosításának képessége a csatorna-adatbázisban rekordazonosító (**RecId** érték) használata nélkül.</li><li>A cím létrehozásának időbélyegzői</li><li>Címek szinkronizálása a Commerce Headquarters szolgáltatásban</li></ul><p>Ez a funkció az ügyfelek és az aszinkron vevők szinkronizálását is befolyásolja. Ha aszinkron módon szeretné szerkeszteni a címeket, és nem csak aszinkron módon szeretné létrehozni őket, **engedélyeznie kell a Vevők szerkesztése aszinkron módban** funkciót.</p> |
| Paritás engedélyezése a szinkron és az aszinkron vevő létrehozása között. | 10.0.24 és később | <p>Funkciógomb: **Az async Customer továbbfejlesztett létrehozásának engedélyezése**</p><p>Funkció részletei: További adatok, például a cím, az alapértelmezett vevő beosztásai és a másodlagos kapcsolattartási adatok (telefonszám és e-mail cím) rögzítésének képessége a vevők aszinkron létrehozása közben.</p> |
| Felhasználóbarát hibaüzenetek | 10.0.28 és később | Ezek a teljesítményjavító funkciók segítik a felhasználóbarát hibaüzeneteket, ha a felhasználó nem tudja azonnal szerkeszteni az adatokat a szinkronizálás feldolgozása közben. A fejlesztések engedélyezéséhez **a Commerce webhelyszerkesztő Webhely-beállítási bővítményeinél megadott Async Customer-beállításokkal** **\>** bizonyos felhasználói felületi elemeket nem lehet módosítani. |
| A vevői adatok aszinkron szerkesztésének képessége | 10.0.29 és később | <p>Funkciógomb: **Vevők aszinkron módban való szerkesztésének engedélyezése**</p><p>Funkció részletei: A vevői adatok aszinkron szerkesztésének képessége</p><p>Az aszinkron [vevői adatok aszinkron szerkesztésével kapcsolatos gyakori kérdésekre adott válaszokért lásd az aszinkron vevő-létrehozási mód gyakran ismételt kérdéseit](async-customer-mode-faq.md).</p> |

### <a name="feature-switch-hierarchy"></a>Funkcióváltás hierarchiája

A funkciócserék hierarchiája miatt a **vevők** aszinkron módban történő szerkesztésének engedélyezése előtt engedélyezni kell a következő funkciókat: 

- **A vevői rendelések és a vevői tranzakciók teljesítményét javítására a** Commerce rendszer 10.0.28-as verziója óta kötelező megadni. 
- **Továbbfejlesztett async Customer-létrehozás engedélyezése**
- **Aszinkron létrehozás engedélyezése a vevői címekhez**

A gyakori hibaelhárítási kérdésekre [a gyakori kérdésekre adott válaszok az Aszinkron vevő-létrehozási mód gyakori kérdéseknél tartalmaznak választ](async-customer-mode-faq.md). 

Miután engedélyezi a korábban említett funkciókat, ismétlődő kötegelt feladatot kell ütemeznie a P-feladatra **,** a Vevők és üzleti partnerek szinkronizálása aszinkron **módból és a 1010-es** feladatra, **hogy minden async Customers szinkronizálva legyen a** Commerce Headquarters alkalmazás vevőivel.

### <a name="customer-creation-in-pos-offline-mode"></a>Vevő létrehozása pénztári offline módban

Ahogy korábban említettük, amikor a POS ki van kapcsolva, a rendszer automatikusan aszinkron módon hoz létre vevőket még akkor is, ha az aszinkron vevő létrehozási módja le van tiltva. Emiatt a Commerce Headquarters rendszergazdáinak ismétlődő kötegelt feladatot kell létrehozniuk és ütemezniük a P-feladathoz **,** a vevők és üzleti partnerek szinkronizálása aszinkron módból **és a 1010-es** feladathoz, **hogy minden async Customers szinkronizálva legyenek a** Commerce Headquarters alkalmazás vevőivel.

> [!NOTE]
> Ha a **Megosztott vevői adattáblák szűrése** beállítása **Igen** a **Commerce-csatorna sémája** oldalon (**Retail és Commerce \> Központ beállítása \> Kereskedelmi ütemező \> Csatorna-adatbázis-csoport**), a vevőrekordok nem jönnek létre, ha a pénztár offline módban van. További tudnivalókért lásd: [Offline adatok kizárása](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>További erőforrások

[Vevők kezelése az üzletekben](customer-mgmt-stores.md)

[Aszinkron vevők átalakítása szinkron vevőkké](convert-async-to-sync.md)

[Vevőattribútumok](dev-itpro/customer-attributes.md)

[Offline adatok kizárása](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
