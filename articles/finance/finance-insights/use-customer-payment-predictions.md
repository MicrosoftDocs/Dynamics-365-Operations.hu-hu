---
title: Vevői fizetési előrejelzések használata
description: Ez a témakör az előfeltételeket és a Pénzügyi betekintések próbaverziójának használatához szükséges átfogó lépéseket mutatja be.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ed70e133b93c783542d4669b679fc5b6d2d20240
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968912"
---
# <a name="use-customer-payment-predictions"></a>Vevői fizetési előrejelzések használata

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan kell használni a Vevői kifizetési előrejelzéseket. A funkció használata előtt győződjön meg arról, hogy végrehajtotta a beállítási lépéseket. További információkért lásd: [Vevői kifizetés előrejelzések engedélyezése](enable-cust-paymnt-prediction.md).

A vevői kifizetések előrejelzéseit a Vevői jóváírások és beszedése munkaterületen, valamint két új listaoldalon lehet megtekinteni: a tranzakciók fizetési előrejelzései és a vevői **kifizetések** **·** **előrejelzései**.

### <a name="manage-customer-credit-and-collections-workspace"></a>Vevői jóváírás és gyűjtemények munkaterület

A Vevői jóváírások és beszedése munkaterületen két új előrejelzés található: a tranzakciók fizetési előrejelzései és a vevői **kifizetések** **·** **előrejelzései**.

### <a name="transaction-payment-predictions-list-page"></a>Tranzakció-fizetési előrejelzések listaoldala

A Tranzakció- és fizetési előrejelzések listaoldalon megtekintheti a nyitott tranzakciók fizetési valószínűségét az Időben, a Késésben és a **Nagyon** **·** **·** **késedelmes** időszakban. A rácsban lévő mindegyik tranzakcióhoz az **Idővalószínűség** oszlop jelzi, hogy a számla fizetése a határidőre vagy azt megelőzően történik. Ha egy időben történő fizetés valószínűsége 50 százaléknál kisebb, akkor egy piros kör jelenik meg az **Idővalószínűség** oszlop százalékos értéke mellett, hogy jelezze a késedelmes fizetés kockázatát.

[![Tranzakcióoldalankénti fizetési előrejelzés.](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

A lap jobb oldalán található **Kapcsolódó** információ ablaktábla az előrejelzés részletes adatait tartalmazza:

- A rácsban kijelölt tranzakcióhoz a **Kifizetési előrejelzés** gyorslap az **Időben**, a **Későn** és a **Nagyon későn** gyűjtők részletes adatait jeleníti meg. A **Legfontosabb tényezők** szakasz az előrejelzések legfontosabb tényezőit jeleníti meg. A legfelső tényezők a kiválasztott tranzakció és/vagy a tranzakcióban szereplő vevő attribútumai.
- A **Customer Insights** gyorslap a kiválasztott tranzakcióra vonatkozóan megjeleníti a vevő aktuális számláját, kifizetését és beszedési statisztikáit.
- A **Vevő előzmények** gyorslap a vevő fizetési előzményeit az **Időben**, a **Későn** és a **Nagyon későn** gyűjtőkben jeleníti meg.

A **Legfontosabb tényezők** szakasz adatai, valamint a **Customer Insights** és a **Vevői előzmények** gyorslapok segítenek a kifizetési előrejelzések elmagyarázásában. Az előrejelzések hatékonyságának növelése érdekében fokozhatja a megbízhatóságát.

[![A kapcsolódó információ ablaktáblán látható kifizetési előrejelzések grafikai mutatói.](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="customer-payment-predictions-list-page"></a>Vevői kifizetések előrejelzési listaoldala

A Vevői kifizetések előrejelzése listaoldalon látható a teljes nyitott egyenleg, valamint az az összeg, amely az előre jelzett időben, késve és nagyon **késő** **·** **·** **időszakban** lesz kifizetve.

[![Vevői listaoldalonkénti fizetési előrejelzések.](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

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

- A rácsban kijelölt tranzakcióhoz a **Kifizetési előrejelzések** gyorslap az **Időben**, a **Későn** és a **Nagyon későn** gyűjtők részletes adatait jeleníti meg.
- A **Customer Insights** gyorslap a kiválasztott tranzakcióra vonatkozóan megjeleníti a vevő aktuális számláját, kifizetését és beszedési statisztikáit.
- A **Vevő előzmények** gyorslap a vevő fizetési előzményeit az **Időben**, a **Későn** és a **Nagyon későn** gyűjtőkben jeleníti meg.

A Vevői információk és a Vevői előzmények gyorselemzési funkcióval kapcsolatos adatok segítséget nyújtanak a **fizetési** előrejelzések **magyarázatában**. Az előrejelzések hatékonyságának növelése érdekében fokozhatja a megbízhatóságát.

## <a name="improving-the-accuracy-of-payment-predictions"></a>A kifizetési előrejelzések pontosságának javítása

Megtekintheti a fizetési előrejelzések pontosságát a **Jóváírások és gyűjtemények \> Beállítás \> Pénzügyi információk \> Pénzügyi információ paraméterek** alapján. A **Vevői fizetési információk** lapon az **Előrejelzési modell** szakasz az előrejelzési modell pontosságát jeleníti meg százalékban.

[![A kifizetési előrejelzések pontossága.](./media/finance-insights-parameters-accuracy-2nd.png)](./media/finance-insights-parameters-accuracy-2nd.png)

Ha nem elégedett a pontosságával, a hosszabbítási tapasztalat megnyitásához válassza a Modellpontosság **javítása** AI Builder hivatkozást. A hosszabbítás során addig választhatja vagy törölheti a mezők kijelölését, amíg be nem jelölte azokat a mezőket, amelyekről úgy gondolja, hogy a kifizetési valószínűségek pontos előrejelzése AI Builder a legfontosabb. Ha befejezte a munkát, egyszerűen átrendezheti a előrejelzési modellt, majd feladhatja a változtatásokat. Az újonnan betanított előrejelzési modell automatikusan felveszi az előrejelzéseket a Dynamics 365 Finance-ben.

[![AI Builder hosszabbítási tapasztalat.](./media/ai-builder.png)](./media/ai-builder.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
