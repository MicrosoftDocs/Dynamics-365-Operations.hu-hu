---
title: Aszinkron vevő-létrehozási mód
description: Ez a témakör az aszinkron vevő-létrehozási módot írja le a Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 22bb4eaf3d4897904412120fa5580c42637b56e0
ms.sourcegitcommit: eef5d9935ccd1e20e69a1d5b773956aeba4a46bc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/11/2021
ms.locfileid: "7913773"
---
# <a name="asynchronous-customer-creation-mode"></a>Aszinkron vevő-létrehozási mód

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör az aszinkron vevő-létrehozási módot írja le a Microsoft Dynamics 365 Commerce.

A Commerce rendszer kétféle módon létrehozására használható: szinkron (vagy szinkron) és aszinkron (vagy aszinkron). Alapértelmezés szerint a vevők létrehozása szinkronban történik. Más szóval a Commerce központi felületén jönnek létre valós időben. A szinkron vevő-létrehozási módra azért van hatással, mert az új vevők azonnal kereshetők a különböző csatornákon keresztül. Ennek azonban van egy hátránya is. Mivel [Commerce Data Exchange Valós idejű szolgáltatás](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) típusú hívásokat generál a Commerce központi felülete irányába, befolyásolhatja a teljesítményt, ha a rendszer sok egyidejű vevői létrehozási hívást kezdeményez.

Ha a **Vevő létrehozása aszinkron módban** beállítás értéke **Igen** az üzlet funkcióprofiljában (**Retail és Commerce \> Csatorna beállítás \> Online áruház beállítása \> Funkcióprofilok**), akkor a valós idejű szolgáltatás típusú hívások nem használhatók vevőrekordok létrehozásához a csatorna-adatbázisban. Az aszinkron vevő létrehozási módja nem befolyásolja a Commerce Headquarters teljesítményét. A rendszer minden új async Customer rekordhoz egy ideiglenes globálisan egyedi azonosítót (GUID) rendel, amely vevői számlaazonosítóként használatos. Ez a GUID nem jelenik meg a pénztári felhasználók számára. Ehelyett ezek a felhasználók a **Függőben lévő szinkronizálás** lehetőséget látják vevői számlaazonosítóként.

> [!IMPORTANT]
> Amikor a POS ki van kapcsolva, a rendszer automatikusan aszinkron módon hoz létre vevőket még akkor is, ha az aszinkron vevő létrehozási módja le van tiltva. Így függetlenül attól, hogy milyen beállításokat adott meg a szinkronizálás és az async Customer létrehozása között, a Commerce Headquarters rendszergazdáinak ismétlődő kötegelt feladatot kell létrehozniuk és ütemezniük a P-feladatra, a vevők és üzleti partnerek szinkronizálása aszinkron módból (korábban vevők és üzleti partnerek szinkronizálása aszinkron módból) és **a** **·** **·** **1010-es** feladatra, hogy az async Customers szinkronizálva legyenek a Commerce Headquarters alkalmazás vevőivel.

## <a name="async-customer-limitations"></a>Az aszinkron vevőkkel kapcsolatos korlátozások

Az async Customer funkcióira jelenleg a következő korlátozások vonatkoznak:

- Az aszinkron vevő rekordjai csak akkor szerkeszthetők, ha a vevőt a Commerce központi felületén hozták létre, és az új vevői számlaazonosítót már visszaszinkronizálták a csatornával.
- Az aszinkron vevőknek csak akkor lehet hűségkártyákat kiadni, ha az új vevőazonosítót szinkronizálták a csatornával.

## <a name="async-customer-enhancements"></a>Async Customer továbbfejlesztései

A Commerce rendszer 10.0.24-es verziójának kiadásában engedélyezheti az Async Customer továbbfejlesztett létrehozására szolgáló funkciót a Funkciók **kezelése** **munkaterületen**. Ez a funkció a következő módokon teremti meg a pos rendszer és az e-commerce rendszer aszinkron és szinkron vevő-létrehozási módjai közötti hiányt:

- A fiókokat aszinkron vevőkhöz lehet hozzárendelni.
- Az aszinkron vevőkhöz címeket lehet hozzáadni.
- Az aszinkron vevőkhöz másodlagos e-mail címek és telefonszámok is rögzítettek.

A Commerce rendszer 10.0.22-es verziójának kiadásában engedélyezheti az aszinkron létrehozás engedélyezése vevői címekhez funkciót **a** **Szolgáltatáskezelési** munkaterületen. Ez a funkció lehetővé teszi az újonnan létrehozott vevői címek aszinkron mentését mind a szinkron, mind az aszinkron vevők számára.

Miután engedélyezi a korábban említett funkciókat, ismétlődő kötegelt feladatot kell ütemeznie a P-feladatra, a Vevők és üzleti partnerek szinkronizálása aszinkron módból és **a** **·** **1010-es** feladatra, hogy minden async Customers szinkronizálva legyen a Commerce Headquarters alkalmazás vevőivel.

### <a name="customer-creation-in-pos-offline-mode"></a>Vevő létrehozása pénztári offline módban

Ahogy korábban említettük, amikor a POS ki van kapcsolva, a rendszer automatikusan aszinkron módon hoz létre vevőket még akkor is, ha az aszinkron vevő létrehozási módja le van tiltva. Emiatt a Commerce Headquarters rendszergazdáinak ismétlődő kötegelt feladatot kell létrehozniuk és ütemezniük a P-feladathoz, a vevők és üzleti partnerek szinkronizálása **aszinkron** módból és **a** **1010-es** feladathoz, hogy minden async Customers szinkronizálva legyenek a Commerce Headquarters alkalmazás vevőivel.

> [!NOTE]
> Ha a **Megosztott vevői adattáblák szűrése** beállítása **Igen** a **Commerce-csatorna sémája** oldalon (**Retail és Commerce \> Központ beállítása \> Kereskedelmi ütemező \> Csatorna-adatbázis-csoport**), a vevőrekordok nem jönnek létre, ha a pénztár offline módban van. További tudnivalókért lásd: [Offline adatok kizárása](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>További erőforrások

[Vevők kezelése az üzletekben](customer-mgmt-stores.md)

[Aszinkron vevők átalakítása szinkron vevőkké](convert-async-to-sync.md)

[Vevőattribútumok](dev-itpro/customer-attributes.md)

[Offline adatok kizárása](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
