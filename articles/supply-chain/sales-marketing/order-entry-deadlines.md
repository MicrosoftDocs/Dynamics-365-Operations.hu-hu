---
title: Rendelésbeviteli határidők
description: A cikk a rendelésbevitel határidőiről tartalmaz információkat. A rendelésbeviteli határidő, egy lezárási idő, amely meghatározza, hogy a vevői rendelés úgy lesz-e kezelve (és teljesítve), mintha az aktuális napon lett volna befogadva, vagy a következőn.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOrderEntryDeadlineGroup, InventOrderEntryDeadlineParameters, InventOrderEntryDeadlineTable, MCRAutoTaxRules
audience: Application User
ms.reviewer: kamaybac
ms.custom: 7151
ms.assetid: bbc4f9a2-df4b-4d92-9f18-25282a85541f
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 71748cb05346f7a31f51baebb86b9accc11c8478
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580528"
---
# <a name="order-entry-deadlines"></a>Rendelésbeviteli határidők

[!include [banner](../includes/banner.md)]

A cikk a rendelésbevitel határidőiről tartalmaz információkat. A rendelésbeviteli határidő, egy lezárási idő, amely meghatározza, hogy a vevői rendelés úgy lesz-e kezelve (és teljesítve), mintha az aktuális napon lett volna befogadva, vagy a következőn.

Számos vállalat esetében az értékesítési rendelések csak akkor számítanak még aznapi rendelésnek, ha még a nap egy bizonyos időpontja előtt be vannak vételezve. Minden olyan rendelés, amely ez után az időpont után van bevételezve, a következő munkanapon beérkezettként kezelendő. Ez az átfutási idő a rendelések esetében a rendelésbeviteli határidő.  

A rendelésbeviteli határidők bemenetként szolgálnak a rendelési ígérethez. Ezért segítenek megfelelni ügyfelei elvárásainak, ami a rendelések kiszállítását illeti. Például a vevők láthatják, hogy ha egy bizonyos időpont előtt leadnak egy rendelést, akkor a rendelést még ugyanazon a napon kiszállítják. Azonban, ha ennél később adják le a rendelést, akkor a szállítmány csak a következő munkanapon érkezik meg. A rendelésbeviteli határidőket a raktár lehetőségeinek és a szállítási ütemezéseknek megfelelően állíthatja be.  

A **Rendelésbeviteli határidők** lapon a hét egyes napjain érvényes rendelésbeviteli határidőket adhat meg. Ha a rendelések a meghatározott időpont után érkeznek be, a következő munkanapon beérkezettként kezelendők. Az alapértelmezés szerint beállított időpont 23:59 (vagyis egy perccel az adott nap vége előtt). Az alapértelmezett időpontokat módosítani lehet, hogy megegyezzenek a tényleges szállítási vagy bevételezési határidőkkel.  

Rendelésbeviteli határidőket be lehet állítani a vevők adott csoportja számára. Például azt szeretné, hogy a rendelésbeviteli határidők egy bizonyos vevőcsoport esetében később legyenek, mint a többi vevő esetében. Ebben az esetben előbb definiálni kell a csoportokat a rendelésbeviteli határidőknél a **Rendelésbeviteli határidőcsoportok** oldalon. Ezután hozzárendelheti a vevőcsoportokat a **Vevők** oldalon.  

Ha vállalata több telephellyel rendelkezik, beállíthat helyi rendelési határidőket mindegyik telephely számára. Ha a telephelyek különböző időzónákba esnek, a rendelési határidőket a helyi időzónának megfelelően kell beállítani. Azonban ha értékesítési rendelésekkel és értékesítési ajánlatokkal dolgozik, akkor rendelésbeviteli határidő az **Elérhető szállítási és kézhezvételi dátumok** oldalon át lesz állítva az Ön időzónájára.  

A **Rendelésbeviteli határidő-kombinációk aktiválása** lapon megadhatja a helyek és rendelésbeviteli határidőcsoport engedélyezett kombinációit.

## <a name="example-order-entry-deadline"></a>Példa: rendelésbeviteli határidő
A rendelésbeviteli határidő kedden 16:00 órára lett állítva. Egy keddi napon 17:00 órakor a jelenlegi dátumot próbálja szállítási dátumként beállítani. (Megjegyzendő, hogy ennél a példánál nincs átfutási idő.) Ha a **Szállításidátum-ellenőrzés** jelölőnégyzet be van jelölve, akkor figyelmeztetést kap, amely arról tájékoztat, hogy a dátum nem érvényes. Ez a figyelmeztetés az **Elérhető szállítási és kézhezvételi dátumok** lapon jelenik meg, amelyen ezután választhat másik dátumokat.

## <a name="example-different-order-entry-deadlines-per-site"></a>Példa: helyenként eltérő rendelésbeviteli határidők
Vállalata két helyből áll. A helyek eltérő időzónában találhatók, az alábbi táblázatban ábrázolt módon.

| A hely                      | B hely                      |
|-----------------------------|-----------------------------|
| Kalifornia                  | Florida                     |
| PST (Csendes-óceáni téli idő) | EST (Keleti téli idő) |

Az A és a B helyek a következő rendelésbeviteli határidőket definiálták.

| A hét napja             | A: Rendelésbeviteli határidők (PST) | B: Rendelésbeviteli határidők (EST) |
|-----------------------------|--------------------------------|--------------------------------|
| Hétfő                      | 13:00:00                          | 14:00:00                          |
| Kedd                     | 13:00:00                          | 14:00:00                          |
| Szerda                   | 13:00:00                          | 14:00:00                          |
| Csütörtök                    | 13:00:00                          | 14:00:00                          |
| Péntek                      | 13:00:00                          | 14:00:00                          |

Ön rendelésfeldolgozó, és Utah államban dolgozik, ahol az MST (hegyi téli idő) érvényes. Ez azt jelenti, hogy ameddig az A hely esetén 14:00 óra (MST) előtt, a B hely esetén pedig 12:00 óra előtt (MST) küld rendeléseket, azok mindkét hely rendelésbleviteli határidejének meg fognak felelni.  

A következő táblázatban az A és a B hely rendelésbeviteli határidői láthatók az MST időzónára konvertálva.

| A hely: PST         | A hely: MST        | B hely: EST           | B hely: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00:00               | 14:00:00              | 14:00:00                 | 12:00:00              |

**Megjegyzés:** Ha a nyári óraátállítás van érvényben, a rendelésbeviteli határidők aszerint módosulnak.

## <a name="example-same-order-entry-deadline-per-site"></a>Példa: ugyanaz a rendelésbeviteli határidő minden helynél
Vállalata két helyből áll. A helyek eltérő időzónában találhatók, az alábbi táblázatban ábrázolt módon.

| A hely                      | B hely                      |
|-----------------------------|-----------------------------|
| Kalifornia                  | Florida                     |
| PST (Csendes-óceáni téli idő) | EST (Keleti téli idő) |

Az A és a B helyek a következő rendelésbeviteli határidőket definiálták.

| A hét napja | PST és EST |
|-----------------|-------------|
| Hétfő          | 13:00:00       |
| Kedd         | 13:00:00       |
| Szerda       | 13:00:00       |
| Csütörtök        | 13:00:00       |
| Péntek          | 13:00:00       |

Ön rendelésfeldolgozó, és Utah államban dolgozik, ahol az MST érvényes. Ez azt jelenti, hogy ameddig az A hely esetén 14:00 óra (MST) előtt, a B hely esetén pedig 11:00 óra előtt (MST) küld rendeléseket, azok mindkét hely rendelésbleviteli határidejének meg fognak felelni. 

A következő táblázatban az A és a B hely rendelésbeviteli határidői láthatók az MST időzónára konvertálva.

| A hely: PST         | A hely: MST        | B hely: EST           | B hely: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00:00               | 14:00:00              | 13:00:00                 | 11:00:00              |

**Megjegyzés:** Ha a nyári óraátállítás van érvényben, a rendelésbeviteli határidők aszerint módosulnak.

## <a name="additional-resources"></a>További erőforrások

[Szállítási ütemezések](delivery-schedules.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]