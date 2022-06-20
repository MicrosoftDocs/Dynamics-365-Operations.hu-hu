---
title: A Tervezési optimalizálás által használt dátum- és időparaméterek
description: Ez a cikk a tervezés optimalizálási műveletei során használt dátum- és időparaméterekkel kapcsolatban tartalmaz tájékoztatást.
author: t-benebo
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 807834bf5cd062ed24e5e3f3512d8389717a2d39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885899"
---
# <a name="date-and-time-parameters-used-by-planning-optimization"></a>A Tervezési optimalizálás által használt dátum- és időparaméterek

[!include [banner](../../includes/banner.md)]

Ez a cikk a tervezés optimalizálási műveletei során használt dátum- és időparaméterekkel kapcsolatban tartalmaz tájékoztatást.

Míg a beépített alaptervezési motor minden számításban tranzakciódátumokat használ, a Tervezési optimalizálás a dátumokká konvertált dátum- és időértékeket használja. Ez a viselkedéssel kapcsolatos eltérés olyan helyzetekhez vezethet, amikor például az alaptervezés futtatásakor éjfélkor létrehozott előrejelzési tranzakciók nem szerepelnek, mivel a tervezési optimalizálás figyelembe veszi, hogy ezeket az aktuális dátum előtt hozták létre.

## <a name="parameters-for-issue-and-demand-transactions"></a>Paraméterek kiadási és igénytranzakciókhoz

Az alábbi táblázat felsorolja azokat a paramétereket, amelyeket a Tervezési optimalizálás használ a kiadási és igénytranzakciók kezelésekor.

| Paraméter | A paraméter neve a Tervezési optimalizálásban | Leírás | Egyenértékű mező a Microsoft Dynamics 365 Supply Chain Management alkalmazásban (a ReqTrans táblában) |
|---|---|---|---|
| Tervezett kiadás ideje | `PlannedIssueTime` | A kiadás tervezett dátuma. | **Záró dátum** (`FuturesDate`) és **Késleltetés ideje** (`FuturesTime`) |
| Kért kiadási idő | `RequestedIssueTime` | A felhasználó által kért és a Supply Chain Management alkalmazásban beállított kiadási dátum. Ez a paraméter csak a kiadott vagy jóváhagyott tervezett rendelésekre érvényes. Tervezett rendelések esetén alapértelmezés szerint üres. | **Igényelt dátum** (`ReqDateDlvOrig`) |
| Kért kiadási idő | `RequiredIssueTime` | A tervezési optimalizálással korrigált kért kiadási dátum. Ha a kért kiadási idő a Tervezési optimalizálás futtatásakor a múltban van, a szükséges kiadási időt a rendszer az első nyitott naphoz igazítja, amely nem korábbi a mai dátumnál. Ha a kért kiadási idő zároltként van megjelölve a naptárban, a kért kiadási időt az adott dátum előtti első nyitott naphoz igazítja a rendszer. | **Igény dátuma** (`ReqDate`) és **Igény időpontja** (`ReqTime`) |
| Kiadási idő késleltetése | `IssueTimeDelay` | A tervezett kiadási idő és a jóváhagyott és kiadási idő közötti időkülönbség és vagy az igényelt kiadási idő és kiadott rendelések vagy az igényelt kiadási idő. | **Késleltetés (napokban)** (`FuturesDays`) |

## <a name="parameters-for-receipt-and-supply-transactions"></a>A bevételezési és ellátási tranzakciók paraméterei

Az alábbi táblázat felsorolja azokat a paramétereket, amelyeket a Tervezési optimalizálás használ a bevételi és ellátási tranzakciók kezelésekor.

| Paraméter | A paraméter neve a Tervezési optimalizálásban | Leírás | A Supply Chain Management megfelelő mezője (a ReqTrans vagy a ReqPO táblában) |
|---|---|---|---|
| Tervezett elérhetőségi idő | `PlannedAvailabilityTime` | A bevételezés elérhetőségének tervezett dátuma. | **Igény dátuma** (`ReqDate`) és **Igény időpontja** (`ReqTime`) |
| Tervezett bevételezési idő | `PlannedReceiptTime` | Az a dátum, amikor a bevételezés meg fog érkezni a helyre. | **Záró dátum** (`FuturesDate`), **Késleltetés ideje** (`FuturesTime`), és **Szállítási dátum** (`ReqDateDlv`) vagy **Igényelt dátum** (`ReqDateDlvOrig`) ha a rendelés még nem lett kiadva. |
| Igényelt elérhetőségi idő | `RequiredAvailabilityTime` | A tervezési optimalizálással korrigált kért elérhetőségi dátum. | **Igény dátuma** (`ReqDate`) és **Igény időpontja** (`ReqTime`) |
| Várt bevételezési idő | `ExpectedReceiptTime` | A kiadott bevételezés várt kézhezvételi dátuma. Az értéket a felhasználó állítja be a Supply Chain Management alkalmazásban, és nem módosítja a Tervezési optimalizálás. Ez a paraméter csak a kiadott bevételezésekre vonatkozik. | **Igényelt dátum** (`ReqDateDlvOrig`) |
| Igényelt bevételezési idő | `RequiredReceiptTime` | A tervezési optimalizálással korrigált igényelt bevételezési dátum. | **Igény dátuma** (`ReqDate`) és **Igény időpontja** (`ReqTime`) |
| Tervezett rendelési idő | `PlannedOrderingTime` | A tervezési optimalizálással számított rendelési dátum. | **Rendelés dátuma** (`ReqDateOrder`) és **Rendelési ideje** (`ReqTimeOrder`) |
| Tervezett tevékenység kezdési ideje | `PlannedActivityStartTime` | Az a dátum, amikor a bevételezéshez tevékenységnek el kell kezdődnie. | **Kezdő dátum** (`SchedFromDate`) |
| Bevételezés idejének késleltetése | `ReceiptTimeDelay` | A tervezett bevételezési idő és az igényelt bevételezési idő közötti időkülönbség. | **Késleltetés (nap)** (`FuturesDays`) és **Késleltetés ideje** (`FuturesTime`) |

## <a name="examples-of-date-parameter-use-by-planning-optimization"></a>Példák a Tervezési optimalizálás által használt dátumparaméterekre

Az alábbi ábrákon látható tervek napi szintűek, de a Tervezési optimalizálás részletesebb szinten fut. Mivel például a különbözet órákban lehet, a tervezési rendelési idő lehet 2021. január 22., 11:35 stb.

### <a name="example-1-simple-scenario"></a>1. példa: Egyszerű eset

Egy beszerzési rendelés igényelt kiadási ideje január 22., és egy értékesítési rendelés fedezi. A következő beállítások vannak használva:

- Nincs átfutási idő
- Nincsenek naptárak (minden nap nyitott.)
- Nincs különbözet

A következő ábrán ez a forgatókönyv látható. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Egyszerű forgatókönyv.](media/planning-service-dates-1-small.png)](media/planning-service-dates-1.png)

### <a name="example-2-lead-time-scenario"></a>2. példa: Átfutási idő forgatókönyv

Egy beszerzési rendelés igényelt kiadási ideje január 22., és egy értékesítési rendelés fedezi. A következő beállítások vannak használva:

- Három napos átfutási idő
- Nincsenek naptárak (minden nap nyitott.)
- Nincs különbözet

A következő ábrán ez a forgatókönyv látható. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Átfutási idő forgatókönyv.](media/planning-service-dates-2-small.png)](media/planning-service-dates-2.png)

### <a name="example-3-margin-scenario"></a>3. példa: Tűréshatár forgatókönyv

Egy beszerzési rendelés igényelt kiadási ideje január 22., és egy értékesítési rendelés fedezi. A következő beállítások vannak használva:

- Három napos átfutási idő
- Négynapos rendelési tűrés
- Ötnapos elérhetőségi tűrés
- Nincsenek naptárak (minden nap nyitott.)

A következő ábrán ez a forgatókönyv látható. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Tűréshatár forgatókönyv.](media/planning-service-dates-3-small.png)](media/planning-service-dates-3.png)

### <a name="example-4-delay-scenario"></a>4. példa: Késleltetés eset

Egy beszerzési rendelés igényelt kiadási ideje január 22., és egy értékesítési rendelés fedezi. Ez a példa a 3. példában megadott beállításokat használja, de a tervezési dátum át lett helyezve január 15-re. A visszafelé ütemezés (piros jelölők) sikertelen, mert a tervezett rendelési időnek a mai dátumnál korábban kellene lennie. Emiatt az alaptervezésnek előre kell ütemeznie, és késések fordulhatnak elő.

A következő ábrán ez a forgatókönyv látható. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Késleltetés eset.](media/planning-service-dates-4-small.png)](media/planning-service-dates-4.png)

### <a name="example-5-transfer-scenario"></a>5. példa: Átviteli eset

Az 1. raktár egyik kért kiadási idejét a január 22-i raktárból egy átviteli rendelés fedezi, amelyet egy tervezett beszerzési rendelés fedez a 2. raktárból. A következő beállítások vannak használva:

- Három napos átviteli átfutási idő (1. raktár)
- Két napos beszerzési átfutási idő (2. raktár)
- Nincsenek naptárak (minden nap nyitott.)

A következő ábrán ez a forgatókönyv látható. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Átviteli eset.](media/planning-service-dates-5-small.png)](media/planning-service-dates-5.png)

### <a name="example-6-lead-time-with-calendars-scenario"></a>6. példa: Átfutási idő naptári esetekkel

Egy beszerzési rendelés igényelt kiadási ideje január 22., és egy értékesítési rendelés fedezi. A következő beállítások vannak használva:

- Három napos átfutási idő
- Kiadási naptár (Pénteken lezárva)
- Elérhetőségi naptár (csütörtökön és pénteken lezárva)
- Bevételezési naptár (kedden, szerdán és vasárnap lezárva)
- Átfutási idő naptár (csütörtökön és pénteken lezárva)
- Rendelési naptár (hétfőre és szombatra nyitva)

A következő ábrán ez a forgatókönyv látható. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Átfutási idő naptári esetekkel.](media/planning-service-dates-6-small.png)](media/planning-service-dates-6.png)

### <a name="example-7-delay-with-calendars-scenario"></a>7. példa: Késleltetés naptári esetekkel

Egy beszerzési rendelés igényelt kiadási ideje január 22., és egy értékesítési rendelés fedezi. Ez a példa a 6. példában megadott beállításokat használja, de a tervezési dátum át lett helyezve január 13-re. A visszafelé ütemezés (piros jelölők) sikertelen, mert a tervezett rendelési időnek a mai dátumnál korábban kellene lennie. Emiatt az alaptervezésnek előre kell ütemeznie, és késések fordulhatnak elő.

A következő ábrán ez a forgatókönyv látható. (Válassza ki az ábrát egy nagyobb verzió megnyitásához.)

[![Késleltetés naptári esetekkel.](media/planning-service-dates-7-small.png)](media/planning-service-dates-7.png)
