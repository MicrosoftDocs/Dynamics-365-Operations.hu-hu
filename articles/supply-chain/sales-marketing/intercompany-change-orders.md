---
title: Vállalatközi rendelések módosítása
description: Ez a cikk bemutatja a vállalatközi rendelések funkcióváltását.
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
ms.openlocfilehash: f139678fbb59b9132ece1ab758e141ec7cdb7a19
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852186"
---
# <a name="change-intercompany-orders"></a>Vállalatközi rendelések módosítása

[!include [banner](../../includes/banner.md)]

Ha módosít egy vállalatközi értékesítési rendelést vagy beszerzési rendelést, akkor a kapcsolódó leányvállalat megfelelő értékesítési rendelése vagy beszerzési rendelése is tükrözi a módosítást.

## <a name="adding-new-lines"></a>Új sorok hozzáadása

Ha az eredeti értékesítési rendelés része a vállalatközi rendelésláncnak, akkor új sorokat lehet hozzáadni egy vállalatközi értékesítési rendeléshez és egy beszerzési rendeléshez. Akkor is hozzáadhat új sorokat, ha az eredeti értékesítési rendelés nem közvetlen kiszállítású. Ha az eredeti értékesítési rendelés közvetlen kiszállítású, akkor csak akkor lehet új rendelési sorokat hozzáadni a vállalatközi értékesítési rendeléshez és a beszerzési rendeléshez, ha az eredeti értékesítési rendelés **Vállalatközi beállítások** gyorslapján ki van választva a **Közvetett létrehozás engedélyezése** mező.

## <a name="changing-prices-and-discounts"></a>Árak és engedmények módosítása

Az árak és engedmények módosíthatók, ha a **Vállalatközi** oldalon be van jelölve az **Ár szerkesztésének engedélyezése** és az **Engedmények szerkesztésének engedélyezése** jelölőnégyzet.

Ha a vállalatközi értékesítési rendelés egy meglévő sorában módosítja az egységárat, akkor az a vállalatközi beszerzési rendelésben is megváltozik.

Ha bármelyik engedménymezőt módosítja a vállalatközi értékesítési rendelés sorában, akkor a a vállalatközi beszerzési rendelés megfelelő engedménymezőit is frissíti.

## <a name="changing-and-adding-new-charges"></a>Vegyes költségek módosítása és új költségek hozzáadása

A díjak módosíthatók, ha a **Vállalatközi** oldalon be van jelölve az **Ár szerkesztésének engedélyezése** és az **Engedmények szerkesztésének engedélyezése** jelölőnégyzet.

Ha új költséget ad hozzá a vállalatközi értékesítési rendelés fejlécéhez, és új költséget ad hozzá a vállalatközi értékesítési sorhoz, mindkét költséget átmásolja a program a vállalatközi beszerzési rendelésbe. Emiatt a vállalatközi értékesítési rendelés és a vállalatközi beszerzési rendelés végösszege azonos. A költségek soha nem másolódnak az eredeti értékesítési rendelésbe.

## <a name="copying-a-fee"></a>Díjak másolása

Ha díjat szeretne az eredeti értékesítési rendelésbe másolni, hozza létre új értékesítési sorkén amelynek **Szolgáltatás** típusú cikke van.

## <a name="changing-quantities-and-deleting-intercompany-purchases-and-sales-order-lines"></a>Mennyiségek módosítása és a vállalatközi beszerzési és értékesítési rendelések sorainak törlése

A mennyiséget csak akkor módosíthatja, a vállalatközi beszerzési rendelések sorait és értékesítési rendelések sorait pedig csak akkor törölheti, ha a sor közvetlenül az **Értékesítési rendelés** vagy a **Beszerzési rendelés** űrlapról lett létrehozva. E módosítás hatására a vállalatközi beszerzési rendelés vagy értékesítési rendelés vagy rendeléssor lesz a forrás.

## <a name="origins-of-orders-and-order-lines"></a>A rendelések és rendeléssorok eredetei

A vállalatközi rendelések és rendeléssorok eredete kétféle lehet:

- **Származtatott** A rendelés automatikusan jött létre egy vállalatközi rendelési lánc eredményeként.
- **Forrás** – a rendelést egy felhasználó hozta létre manuálisan.

Az eredetet a rendelés fejléce jelzi a vállalatközi beszerzési rendelések és értékesítési rendelések **Eredet** mezőjében. Ez a mező az értékesítési rendelés **Vállalatközi beállítások** gyorslapján és a beszerzési rendelés **Beállítás** gyorslapján található.

A **Származtatott** és a **Forrás** eredet csak a vállalatközi rendelésekre vonatkozik. Emiatt az **Eredet** mező minden más értékesítési, beszerzési rendelésben és rendeléssorban üres. Ugyanez a mező az eredeti értékesítési rendelésben is üres marad.

## <a name="example-derived-origin"></a>Példa: Származtatott eredet

Létrehoz egy eredeti értékesítési rendelés egy külső vevő számára. Az értékesítési rendelés egy rendeléssort tartalmaz. Ez az eredeti értékesítési rendelés létrehoz egy vállalatközi beszerzési rendelést, amely egy rendeléssort tartalmaz, amely pedig létrehoz egy vállalatközi értékesítési rendelést, amely szintén egy rendeléssort tartalmaz. A vállalatközi beszerzési rendelés fejléce és a rendeléssor automatikusan az eredeti értékesítési rendelésből jön létre.

Az **Eredet** mező értéke a vállalatközi beszerzési rendelés **Beállítások** gyorslapján és a vállalatközi értékesítési rendelés fejlécének **Vállalatközi beállítások** gyorslapján **Származtatott**. A beszerzési rendelés és az értékesítésirendelés-sorok **Sor részletei** lapján az **Eredet** mező értéke is **Származtatott**.

Ha egy rendeléssor eredete **Származtatott**, a rendeléssor nem törölhető közvetlenül. A rendeléssor csak abból a forrásból törölhető, amely létrehozta a rendeléssort. A rendelt mennyiség is csak abból a forrásból módosítható, amely létrehozta a rendeléssort.

Ha egy eredeti értékesítési rendelés vagy eredeti értékesítésirendelés-sor a vállalatközi rendeléslánc része, akkor a rendelt mennyiségek az eredeti értékesítési rendelésben módosíthatók, és a rendeléssorok is itt törölhetők.

## <a name="example-source-origin"></a>Példa: Forrás eredete

Létrehoz egy beszerzési rendelést egy vállalatközi szállító számára. A vállalatközi beszerzési rendelés és a rendeléssorok eredete is **Forrás** lesz. Ennélfogva ez a vállalatközi beszerzési rendelés lesz a szabályzó, a szállító vállalatban automatikusan létrejövő vállalatközi értékesítési rendelés a szállító vállalatban pedig **Származtatott** lesz.

Ezenkívül a vállalatközi beszerzési rendelésen létrehozott rendeléssorok rendelt mennyiségei nem módosíthatók a vállalatközi értékesítési rendelésen. A rendeléssor csak a vállalatközi beszerzési rendelésből törölhető. Ha egy új sort adnak hozzá a vállalatközi értékesítési rendeléshez, akkor a vállalatközi értékesítésirendelés-sor eredete **Forrás** lesz.

Ha egy eredeti értékesítési rendelés része a vállalatközi rendelésláncnak, akkor a vállalatközi rendelések és rendelések mindig szabályozhatók az eredeti értékesítési rendelésből.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
