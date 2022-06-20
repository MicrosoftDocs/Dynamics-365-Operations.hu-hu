---
title: Terv a globális címjegyzékhez és egyéb címjegyzékekhez
description: Ez a témakör ismerteti a tervezési folyamat során el kell döntenie a szempontokat és a döntéseket.
author: msftbrking
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 288c96d8c877f5e3b3101080294b2f6cdeb39882
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863159"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>Terv a globális címjegyzékhez és egyéb címjegyzékekhez

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti a tervezési folyamat során, a globális címjegyzék és az esetleges további címjegyzékek beállítása és konfigurálása előtt szükséges szempontokat és döntéseket. Egyes döntések megkövetelik a korábban, a termék más területével kapcsolatban hozott döntések (pl. a szervezeti hierarchia) megerősítését.

## <a name="global-address-book"></a>Globális címjegyzék

A globális címjegyzék használata előtt meg kell határoznia az alapértelmezett értékeket. Ezeket az alapértelmezett értékeket a minden további címjegyzékhez felhasználják, amelyet létrehoz.

**Döntések**

- Milyen sorrendben kell a neveknek megjelennie a **Személy** típusának partnerrekordjai számára? Például egy sorozatot egy vezetéknevet, utónevet, keresztnevet tartalmaz.
- Törölni kell a felek rekordjait a címjegyzékből a szerepkör-rekord törlésekor? Például ha egy vevő rekord törlődik, törölni kell partnerrekordot is törölni kell?
- Új rekord létrehozásakor, értesíteni kell a felhasználókat, ha ismétlődő rekordot található a globális címjegyzékben?
- Szerepelnie kell Data Universal Numbering System (DUNS) számnak egy fél rekordjában lévő adatokban?
- Ha a DUNS szám szerepel a fél rekordjában, ellenőrizni kell a szám egyediségét?
- Szeretne egy alapértelmezett fél típust, személyt vagy szervezetet a címjegyzék-bejegyzés létrehozásakor a globális címjegyzékben?
- Mely felhasználói szerepkörnek kell rendelkeznie hozzáféréssel a privát címekhez és fél rekordjainak kapcsolattartási adataihoz?

## <a name="additional-address-books"></a>További címjegyzékek

Miután létrehozta a globális címjegyzéket, további címjegyzéket hozhat létre szükség szerint, például vállalatonként vagy az üzlet sorainként külön címjegyzéket hozhat létre a szervezetben. Például a Fabrikam egy nemzetközi szervezet, amely több vállalattal és több üzletággal rendelkezik. Fabrikam tervezi a címjegyzékek létrehozását az üzlet minden egyes sorához. Azoknál az üzletágaknál, amelyek egynél több helyen, például az eszközök pneumatikus üzletnél fordulnak elő. A Fabrikam minden egyes helyhez egy címjegyzék létrehozását tervezi. Chris, a Fabrikaminformatikai vezetője hozta létre a szükséges címjegyzékek alábbi listáját. Ez a lista bemutatja a fél azon rekordjait, amelyeket minden címjegyzéknek tartalmaznia kell.

- **Állami szektor szerződések (PubSC)** – A Fabrikam által gyakorló állami szektor szerződésekben érintett összes fél társrekordjai.
- **Magánszektor szerződések (PriSC)** – A Fabrikam által gyakorló magánszektor szerződésekben érintett összes fél társrekordjai.
- **Elektronikus eszközök (ET)** – Az elektronikus eszközök beszerzésében vagy értékesítésében érintett összes fél társrekordjai, vagy pedig a Fabrikam japán vállalatában a Fabrikam számára beszerzett vagy a Fabrikam által biztosított elektronikai eszközökkel kommunikál.
- **Pneumatikus eszközök (PTJPN)** – A pneumatikus eszközök beszerzésében vagy értékesítésében érintett összes fél társrekordjai, vagy pedig a Fabrikam japán vállalatában a Fabrikam számára beszerzett vagy a Fabrikam által biztosított pneumatikus eszközökkel kommunikál.
- **Pneumatikus eszközök (PTUSA)** – A pneumatikus eszközök beszerzésében vagy értékesítésében érintett összes fél társrekordjai, vagy pedig a Fabrikam amerikai vállalatában a Fabrikam számára beszerzett vagy a Fabrikam által biztosított pneumatikus eszközökkel kommunikál.

**Döntés:**

- Hány további címjegyzékek kíván létrehozni?


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]