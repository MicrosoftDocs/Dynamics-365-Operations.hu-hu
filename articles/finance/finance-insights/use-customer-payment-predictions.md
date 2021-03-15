---
title: Vevői fizetési előrejelzések használata (előzetes verzió)
description: Ez a témakör az előfeltételeket és a Pénzügyi betekintések próbaverziójának használatához szükséges átfogó lépéseket mutatja be.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: e0445046d8016dfa2c02c1ff1a05bdd148f9409a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969253"
---
# <a name="use-customer-payment-predictions-preview"></a>Vevői fizetési előrejelzések használata (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan kell használni a Vevői kifizetési előrejelzéseket. A funkció használata előtt győződjön meg arról, hogy végrehajtotta a beállítási lépéseket. További információkért lásd: [Vevői kifizetés előrejelzések engedélyezése](enable-cust-paymnt-prediction.md).

A **Vevőnkénti kifizetési előrejelzések** a **Vevői jóváírás és gyűjtemények** munkaterületen, valamint az egyes vevőkhöz tartozó **Tranzakciónkénti kifizetési előrejelzések** alapján tekinthetők meg.

### <a name="manage-customer-credit-and-collections-workspace"></a>Vevői jóváírás és gyűjtemények munkaterület

A **Vevői jóváírás és gyűjtemények kezelése** munkaterület két új csempét tartalmaz: **Tranzakciónkénti fizetési előrejelzés** és az **Előre jelzett magas egyenlegű vevők** lehetőséget.

- A **Tranzakciónkénti fizetési előrejelzés** csempe azokat a nyitott vevői tranzakciókat jeleníti meg, amelyeknek a kifizetése 50 százalékban kisebb, mint az **Időben** gyűjtő. Ezt a mozaikot akkor válassza, ha a **Tranzakciónkénti fizetési előrejelzés** lapon nyithatja meg.
- Az **Előre jelzett magas egyenlegű vevők** csempe száma azt jelzi, hogy a teljes egyenleg több mint fele (50 százaléka) várhatóan késve és/vagy túl későn lesz kifizetve. Ezt a mozaikot akkor válassza, ha a **Vevőnkénti fizetési előrejelzés** lapon nyithatja meg.

[![Vevői jóváírás és gyűjtemények munkaterület](./media/manage-customer-credit-collections.png)](./media/manage-customer-credit-collections.png)

### <a name="payment-predictions-per-transaction-list-page"></a>Tranzakciónkénti fizetési előrejelzések listaoldal

A **Tranzakciónkénti fizetési előrejelzések** lapon megtekintheti a nyitott tranzakciók fizetésének valószínűségét az **Időben**, a **Későn** és a **Nagyon későn** gyűjtőkben. A rácsban lévő mindegyik tranzakcióhoz az **Idővalószínűség** oszlop jelzi, hogy a számla fizetése a határidőre vagy azt megelőzően történik. Ha egy időben történő fizetés valószínűsége 50 százaléknál kisebb, akkor egy piros kör jelenik meg az **Idővalószínűség** oszlop százalékos értéke mellett, hogy jelezze a késedelmes fizetés kockázatát.

[![Tranzakcióoldalankénti fizetési előrejelzés](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

A lap jobb oldalán található **Kapcsolódó** információ ablaktábla az előrejelzés részletes adatait tartalmazza:

- A rácsban kijelölt tranzakcióhoz a **Kifizetési előrejelzés** gyorslap az **Időben**, a **Későn** és a **Nagyon későn** gyűjtők részletes adatait jeleníti meg. A **Legfontosabb tényezők** szakasz az előrejelzések legfontosabb tényezőit jeleníti meg. A legfelső tényezők a kiválasztott tranzakció és/vagy a tranzakcióban szereplő vevő attribútumai.
- A **Customer Insights** gyorslap a kiválasztott tranzakcióra vonatkozóan megjeleníti a vevő aktuális számláját, kifizetését és beszedési statisztikáit.
- A **Vevő előzmények** gyorslap a vevő fizetési előzményeit az **Időben**, a **Későn** és a **Nagyon későn** gyűjtőkben jeleníti meg.

A **Legfontosabb tényezők** szakasz adatai, valamint a **Customer Insights** és a **Vevői előzmények** gyorslapok segítenek a kifizetési előrejelzések elmagyarázásában. Az előrejelzések hatékonyságának növelése érdekében fokozhatja a megbízhatóságát.

[![A kapcsolódó információ ablaktáblán látható kifizetési előrejelzések grafikai mutatói](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="payment-prediction-per-customer-list-page"></a>Vevői listaoldalonkénti fizetési előrejelzés

A **Vevőnkénti fizetési előrejelzés** lista oldalon látható a teljes nyitott egyenleg és az előre jelzett összeg az **Időben**, a **Későn** és a **Nagyon későn** gyűjtők.

[![Vevői listaoldalonkénti fizetési előrejelzések](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

A program kiszámítja az egyes gyűjtők kifizetési összegét a tranzakció egyenlege súlyozott átlagának összegével. Ez az összeg számítása az egyes gyűjtők fizetési valószínűségei alapján történik.

Egy vevőnek például három nyitott tranzakciója van, amelyek mindegyik gyűjtőben a következő kifizetéseket jeleníti meg.

| Tranzakció | Összeg | Időben történő kifizetésvalószínűség | Későn történő kifizetésvalószínűség | Nagyon későn történő kifizetésvalószínűség |
|-------------|--------|-----------------------------|--------------------------|-------------------------------|
| T1          | 100    | 10%                  | 50%               | 40%                    |
| T2          | 1000  | 50%                  | 30%               | 20%                    |
| T3          | 10,000 | 1%                   | 4%                | 95%                    |

Ebben az esetben a program a következő módon teljesíti a kifizetéseket az egyes gyűjtőknek.

| Gyűjtők   | T1 tranzakció      | T2 tranzakció         | T3 tranzakció            | Teljes |
|-----------|---------------------|------------------------|---------------------------|-------|
| Időben   | 100 × 10 ÷ 100 = 10 | 1.000 × 50 ÷ 100 = 500 | 10.000 × 1 ÷ 100 = 100    | 610   |
| Késedelmes      | 100 × 50 ÷ 100 = 50 | 1.000 × 30 ÷ 100 = 300 | 10.000 × 4 ÷ 100 = 400    | 750   |
| Nagyon késedelmes | 100 × 40 ÷ 100 = 40 | 1.000 × 20 ÷ 100 = 200 | 10.000 × 95 ÷ 100 = 9,500 | 9,740 |

A lap jobb oldalán található **Kapcsolódó** információ szakasz az előrejelzés részletes adatait tartalmazza:

- A rácsban kijelölt tranzakcióhoz a **Kifizetési előrejelzések** gyorslap az **Időben**, a **Későn** és a **Nagyon későn** gyűjtők részletes adatait jeleníti meg. A **Legfontosabb tényezők** szakasz a befolyásolt fizetések legfontosabb tényezőit jeleníti meg. A legfelső tényezők a kiválasztott tranzakció és/vagy a tranzakcióban szereplő vevő attribútumai.
- A **Customer Insights** gyorslap a kiválasztott tranzakcióra vonatkozóan megjeleníti a vevő aktuális számláját, kifizetését és beszedési statisztikáit.
- A **Vevő előzmények** gyorslap a vevő fizetési előzményeit az **Időben**, a **Későn** és a **Nagyon későn** gyűjtőkben jeleníti meg.

A **Legfontosabb tényezők** szakasz adatai, valamint a **Customer Insights** és a **Vevői előzmények** gyorslapok segítenek a kifizetési előrejelzések elmagyarázásában. Az előrejelzések hatékonyságának növelése érdekében fokozhatja a megbízhatóságát.

## <a name="improving-the-accuracy-of-payment-predictions"></a>A kifizetési előrejelzések pontosságának javítása

Megtekintheti a fizetési előrejelzések pontosságát a **Jóváírások és gyűjtemények \> Beállítás \> Pénzügyi információk \> Pénzügyi információ paraméterek** alapján. A **Vevői fizetési információk** lapon az **Előrejelzési modell** szakasz az előrejelzési modell pontosságát jeleníti meg százalékban.

[![A kifizetési előrejelzések pontossága](./media/finance-insights-parameters-accuracy-2nd.png)](./media/finance-insights-parameters-accuracy-2nd.png)

Ha nem elégedett a pontossággal, akkor a **Modell pontosságának javítása** hivatkozásra kattintva nyissa meg az AI Builder bővítményélményt. Az AI Builder bővítményélményben kiválaszthatja vagy törölheti a kiválasztott mezőket mindaddig, amíg be nem jelölte azokat a mezőket, amelyeket úgy gondolja, hogy a fizetési valószínűségek pontos előrejelzéséhez a legfontosabbak. Ha befejezte a munkát, egyszerűen átrendezheti a előrejelzési modellt, majd feladhatja a változtatásokat. Az újonnan betanított előrejelzési modell automatikusan felveszi az előrejelzéseket a Dynamics 365 Finance-ben.

[![AI Builder bővítményélmény](./media/ai-builder.png)](./media/ai-builder.png)

## <a name="release-details"></a>Kiadás adatai

A Finance Insights nyilvános előzetes verzió az Amerikai Egyesült Államokban, Európában és az Egyesült Királyságban is elérhető telepítéshez. A Microsoft fokozatosan adja hozzá a további régiók támogatását.

A nyilvános előzetes verziójú funkciók csak 2. szintű tesztkörnyezetekben szabad bekapcsolni. A tesztkörnyezetben létrehozott telepítési és AI-modellek nem telepíthetők át éles környezetbe. További információ: [A Microsoft Dynamics 365 előzetes verziók kiegészítő használati feltételei](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]