---
title: Vevői fizetési előrejelzések használata
description: Ez a cikk végigvezeti az előfeltételeken és a pénzügyi információk próbaverziója szükséges széles lépéseken.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 330642624b55a6772ef149b70873021401a6bd83
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901402"
---
# <a name="use-customer-payment-predictions"></a>Vevői fizetési előrejelzések használata

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a vevői kifizetések előrejelzésének használatát. A funkció használata előtt győződjön meg arról, hogy végrehajtotta a beállítási lépéseket. További információkért lásd: [Vevői kifizetés előrejelzések engedélyezése](enable-cust-paymnt-prediction.md).

A vevői kifizetések előrejelzéseit a Vevői jóváírások és **beszedése** munkaterületen, valamint két új listaoldalon lehet megtekinteni: **·** **a tranzakciók fizetési előrejelzései és a vevői kifizetések előrejelzései**.

### <a name="manage-customer-credit-and-collections-workspace"></a>Vevői jóváírás és gyűjtemények munkaterület

A **Vevői jóváírások és beszedése munkaterületen** két új előrejelzés található: a **·** **tranzakciók fizetési előrejelzései és a vevői kifizetések előrejelzései.**

### <a name="transaction-payment-predictions-list-page"></a>Tranzakció-fizetési előrejelzések listaoldala

A Tranzakció - **fizetési** előrejelzések listaoldalon **megtekintheti a nyitott tranzakciók fizetési valószínűségét az időben**,**·** **késve és nagyon késő** időszakban. A rácsban lévő mindegyik tranzakcióhoz az **Idővalószínűség** oszlop jelzi, hogy a számla fizetése a határidőre vagy azt megelőzően történik. Ha egy időben történő fizetés valószínűsége 50 százaléknál kisebb, akkor egy piros kör jelenik meg az **Idővalószínűség** oszlop százalékos értéke mellett, hogy jelezze a késedelmes fizetés kockázatát.

[![Tranzakcióoldalankénti fizetési előrejelzés.](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

A lap jobb oldalán található **Kapcsolódó** információ ablaktábla az előrejelzés részletes adatait tartalmazza:

- A rácsban kijelölt tranzakcióhoz a **Kifizetési előrejelzés** gyorslap az **Időben**, a **Későn** és a **Nagyon későn** gyűjtők részletes adatait jeleníti meg. A **Legfontosabb tényezők** szakasz az előrejelzések legfontosabb tényezőit jeleníti meg. A legfelső tényezők a kiválasztott tranzakció és/vagy a tranzakcióban szereplő vevő attribútumai.
- A **Customer Insights** gyorslap a kiválasztott tranzakcióra vonatkozóan megjeleníti a vevő aktuális számláját, kifizetését és beszedési statisztikáit.
- A **Vevő előzmények** gyorslap a vevő fizetési előzményeit az **Időben**, a **Későn** és a **Nagyon későn** gyűjtőkben jeleníti meg.

A **Legfontosabb tényezők** szakasz adatai, valamint a **Customer Insights** és a **Vevői előzmények** gyorslapok segítenek a kifizetési előrejelzések elmagyarázásában. Az előrejelzések hatékonyságának növelése érdekében fokozhatja a megbízhatóságát.

[![A kapcsolódó információ ablaktáblán látható kifizetési előrejelzések grafikai mutatói.](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="customer-payment-predictions-list-page"></a>Vevői kifizetések előrejelzési listaoldala

A **Vevői kifizetések** előrejelzése listaoldalon látható a teljes nyitott egyenleg, valamint az az összeg, **amely** az előrejelzések szerint a megfelelő időben, **·** **késve** és nagyon késő időszakban lesz kifizetve.

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

A Vevői információk **és** **a Vevői előzmények** gyorselemzési funkcióval kapcsolatos adatok segítséget nyújtanak a fizetési előrejelzések magyarázatában. Az előrejelzések hatékonyságának növelése érdekében fokozhatja a megbízhatóságát.

## <a name="improving-the-accuracy-of-payment-predictions"></a>A kifizetési előrejelzések pontosságának javítása

Megtekintheti a fizetési előrejelzések pontosságát a **Jóváírások és gyűjtemények \> Beállítás \> Pénzügyi információk \> Pénzügyi információ paraméterek** alapján. A **Vevői fizetési információk** lapon az **Előrejelzési modell** szakasz az előrejelzési modell pontosságát jeleníti meg százalékban.

Ha nem elégedett a pontosságával, **·** AI Builder a hosszabbítási tapasztalat megnyitásához válassza a Modellpontosság javítása hivatkozást. A hosszabbítás AI Builder során addig választhatja vagy törölheti a mezők kijelölését, amíg be nem jelölte azokat a mezőket, amelyekről úgy gondolja, hogy a kifizetési valószínűségek pontos előrejelzése a legfontosabb. Ha befejezte a munkát, egyszerűen átrendezheti a előrejelzési modellt, majd feladhatja a változtatásokat. A dynamics 365 Pénzügy új előrejelzési modelljét a rendszer automatikusan előrejelzési modellként használja.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
