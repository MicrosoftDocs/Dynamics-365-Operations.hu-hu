---
title: Intézkedési kódok szinkronizálása
description: Ez a cikk bemutatja a vállalatközi kereskedelem intézkedési kódjai szinkronizálását.
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: d347181dd6ba12de0e114d74d43cd46230ba4fb7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905660"
---
# <a name="synchronize-intercompany-disposition-codes"></a>Vállalatközi intézkedési kódok szinkronizálása

[!include [banner](../../includes/banner.md)]

A vállalatközi visszáruforgalom támogatása céljából a Microsoft Dynamics 365 Supply Chain Management lehetővé teszi, hogy a rendszeren kívül meghatározott intézkedési kódok leképezhetők legyenek a megfelelő belső intézkedési kódokra. Vállalatközi lánc beállításakor a két vállalat egymáshoz hozzárendelt intézkedési műveletének azonosnak kell lennie. Ha különböznek, a szinkronizálási folyamat sikertelen lesz.

## <a name="about-disposition-codes-for-three-legged-direct-returns"></a>Intézkedési kódok a háromszereplős közvetlen visszajuttatási láncban

Az intézkedési kódok szinkronizálása a vállalatközi értékesítési rendelésről az eredeti értékesítésirendelés-sor irányába történik. A szinkronizálás azonban csak egy azonnali hatást gyakorol az eredeti értékesítésirendelés-sorra. Ez a hatás az, hogy az A vállalatban beállított intézkedési kód és vegyes költség alapján törlődnek a sorok vegyes költségei. Az A vállalat az a vállalat, amelyik a visszárurendelést létrehozza.

Egy háromszereplős közvetlen szállítási láncban a vállalatközi értékesítési rendelési sorok minden intézkedési művelete támogatott. Abban, ha a terméket visszajuttatják a vevőnek, meg kell győződni arról, hogy a visszárurendelésen szereplő szállítási cím megegyezik a vevőnek az eredeti rendelésen megadott szállítási címével.

> [!NOTE]
> A beszerzési rendelésekhez nincsenek intézkedési kódok. Emiatt a vállalatközi értékesítési rendelés intézkedési kódjainak az eredeti visszárurendelésbe történő szinkronizálását értékesítési rendelések között kell lebonyolítani.

## <a name="replacing-returned-items"></a>A visszajuttatott cikkek cseréje

Ha a visszajuttatott cikk helyett másikat küldenek, és erre a célra a B vállalatban már létrehoztak egy csererendelést, akkor nem választható ki intézkedési kód, és az A vállalatban nem jön létre további csererendelés.

## <a name="rules-for-intercompany-direct-deliveries"></a>Vállalatközi közvetlen kiszállítások szabályai

A következő általános szabályok a vállalatközi közvetlen kiszállításban érintett eredeti visszárurendelésekre vonatkoznak:

- Ha az eredeti értékesítésirendelés-sorhoz a Jóváírás és selejtezés, a Jóváírás vagy a Vissza a vevőhöz az intézkedési művelet, a Jóváírás intézkedés lesz alkalmazva. A Visszaküldés a vevőhöz műveletkód azonban nullára (0) állítja a nettó összeget a meglévő sorra és a vállalatközi értékesítési rendelésből újonnan szinkronizált sorra. A selejtsorok ezenkívül soha nem lesznek szinkronizálva. Ha egy sort hozzáadnak egy vállalatközi értékesítési rendeléshez, akkor a program soha nem szinkronizálja olyan értékesítési rendelés esetén, amely pozitív mennyiséget és a selejtre vonatkozó intézkedési műveletet (például Jóváírés és selejtezés vagy Csere és selejtezés).
- A Jóváírás és csere, illetve a Selejtezés és csere mögöttes intézkedési művelet nem lesz felülbírálva. A Jóváírás és csere, illetve a Selejtezés és csere mögöttes intézkedési műveletként lesz kezelve. Ez a szabály akkor is érvényes, ha az A vállalatban nem hoznak létre selejtsort, és nem jön létre csererendelés a B vállalatban (abban a vállalatban, amely a visszaküldött cikket megkapta). Az A vállalatban csak akkor jön létre csererendelés, ha a rendelést frissítik a csomagjegyzék alapján.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
