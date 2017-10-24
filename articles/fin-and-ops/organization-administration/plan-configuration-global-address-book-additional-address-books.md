---
title: "A globális címjegyzék és további címjegyzékek beállításának megtervezése"
description: "Ez a cikk ismerteti azokat a szempontokat, amelyeket a tervezési folyamat során – a globális vagy bármely más címjegyzék Microsoft Dynamics 365 Finance and Operations rendszerben történő beállítása és konfigurálása előtt – figyelembe kell venni, valamint az ekkor meghozandó döntéseket. Egyes döntések megkövetelik a korábban, a termék más területével kapcsolatban hozott döntések (pl. a szervezeti hierarchia) megerősítését."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: shiva.pandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 12bd0a02899c04b0511e2a50bc4a724d5074d13e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="plan-how-to-configure-the-global-address-book-and-additional-address-books"></a>A globális címjegyzék és további címjegyzékek beállításának megtervezése

[!include[banner](../includes/banner.md)]


Ez a cikk ismerteti azokat a szempontokat, amelyeket a tervezési folyamat során – a globális vagy bármely más címjegyzék Microsoft Dynamics 365 Finance and Operations rendszerben történő beállítása és konfigurálása előtt – figyelembe kell venni, valamint az ekkor meghozandó döntéseket. Egyes döntések megkövetelik a korábban, a termék más területével kapcsolatban hozott döntések (pl. a szervezeti hierarchia) megerősítését.

<a name="global-address-book"></a>Globális címjegyzék
-------------------

A globális címjegyzék használata előtt meg kell határoznia az alapértelmezett értékeket. Ezeket az alapértelmezett értékeket a minden további címjegyzékhez felhasználják, amelyet létrehoz. 

**Döntések:**

-   Milyen sorrendben kell a neveknek megjelennie a **Személy** típusának partnerrekordjai számára? Például egy sorozatot egy vezetéknevet, utónevet, keresztnevet tartalmaz.
-   Törölni kell a felek rekordjait a címjegyzékből a szerepkör-rekord törlésekor? Például ha egy vevő rekord törlődik, törölni kell partnerrekordot is törölni kell?
-   Új rekord létrehozásakor, értesíteni kell a felhasználókat, ha ismétlődő rekordot található a globális címjegyzékben?
-   Szerepelnie kell Data Universal Numbering System DUNS) számnak egy fél rekordjában lévő adatokban?
-   Ha a DUNS szám szerepel a fél rekordjában, ellenőrizni kell a szám egyediségét?
-   Szeretne egy alapértelmezett fél típust, személyt vagy szervezetet a címjegyzék-bejegyzés létrehozásakor a globális címjegyzékben?
-   Mely felhasználói szerepkörnek kell rendelkeznie hozzáféréssel a privát címekhez és fél rekordjainak kapcsolattartási adataihoz?

## <a name="additional-address-books"></a>További címjegyzékek
Miután létrehozta a globális címjegyzéket, további címjegyzéket hozhat létre szükség szerint, például vállalatonként vagy az üzlet sorainként külön címjegyzéket hozhat létre a szervezetben. Például a Fabrikam egy nemzetközi szervezet, amely több vállalattal és több üzletággal rendelkezik. Fabrikam tervezi a címjegyzékek létrehozását az üzlet minden egyes sorához. Azoknál az üzletágaknál, amelyek egynél több helyen, például az eszközök pneumatikus üzletnél fordulnak elő. A Fabrikam minden egyes helyhez egy címjegyzék létrehozását tervezi. Chris, a Fabrikaminformatikai vezetője hozta létre a szükséges címjegyzékek alábbi listáját. Ez a lista bemutatja a fél azon rekordjait, amelyeket minden címjegyzéknek tartalmaznia kell.

-   **Állami szektor szerződések (PubSC)** – A Fabrikam által gyakorló állami szektor szerződésekben érintett összes fél társrekordjai.
-   **Magánszektor szerződések (PriSC)** – A Fabrikam által gyakorló magánszektor szerződésekben érintett összes fél társrekordjai.
-   **Elektronikus eszközök (ET)** – Az elektronikus eszközök beszerzésében vagy értékesítésében érintett összes fél társrekordjai, vagy pedig a Fabrikam japán vállalatában a Fabrikam számára beszerzett vagy a Fabrikam által biztosított elektronikai eszközökkel kommunikál.
-   **Pneumatikus eszközök (PTJPN)** – A pneumatikus eszközök beszerzésében vagy értékesítésében érintett összes fél társrekordjai, vagy pedig a Fabrikam japán vállalatában a Fabrikam számára beszerzett vagy a Fabrikam által biztosított pneumatikus eszközökkel kommunikál.
-   **Pneumatikus eszközök (PTUSA)** – A pneumatikus eszközök beszerzésében vagy értékesítésében érintett összes fél társrekordjai, vagy pedig a Fabrikam amerikai vállalatában a Fabrikam számára beszerzett vagy a Fabrikam által biztosított pneumatikus eszközökkel kommunikál.

**Döntés:**

-   Hány további címjegyzékek kíván létrehozni?

### <a name="address-book-security"></a>Címjegyzék biztonság

Bármikor létrehozhat címjegyzéket, és bármikor beállíthatja a címjegyzékek biztonsági paramétereit. Nem szükséges a címjegyzékhez tartozó biztonsági jogosultság beállítása, de ha nem állítja be, akkor a szervezet összes munkavállalója megtekintheti a címjegyzékben szereplő összes rekordot. Beállíthatja a biztonsági jogosultságota címjegyzéken keresztül a fél rekordjaihoz. Csapatokon alapulnak a biztonsági jogosultságok. Ez a megközelítés garantálja, hogy csak olyan munkavállaló láthatja a címjegyzékben szereplő fél rekordjait, aki hozzá van rendelve egycímjegyzékhez. Ki kell választania azt a csoportot, amely minden egyes címjegyzékhez rendelkezik hozzáféréssel. Minden címjegyzékhez beállíthatja azokat biztonsági jogosultságokat, amelyek engedélyezik vagy megtagadják a hozzáférést az egyes csoportokhoz. Amennyiben hozzáférést biztosít egy csapat számára egy címjegyzékhez, ezen csapat összes tagja láthatja a címjegyzékben szereplő rekordokat. Amennyiben nem biztosít hozzáférést egy csapat számára egy címjegyzékhez, ezen csapat tagji nem láthatják a címjegyzéket és annak tartalmát. 

**Döntés:**

-   Mely csoportoknak kell hozzáféréssel rendelkeznie minden egyes új címjegyzékhez, amelyet létrehoz?





