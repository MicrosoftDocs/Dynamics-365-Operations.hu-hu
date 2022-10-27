---
title: Pénztármodul hibahivatkozási kódjai
description: Ez a témakör a pénztármodul hibahivatkozási kódjait írja le, amelyek a felhasználó által látható hibaüzenetek között jelennek meg a modulban Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/20/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: cd8269a71e56f23dbe3782ec3ffc69ec3ea6b151
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709372"
---
# <a name="checkout-module-error-reference-codes"></a>Pénztármodul hibahivatkozási kódjai

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör leírja a pénztármodul hibakódját, amelyek a felhasználó által látható hibaüzenetek között jelennek meg a modulban Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce A <a0/te rendszer szabványos hibahivatkozásokat tartalmaz, amelyek az online csatorna online vevőinek megjelenő pénztári hibákban is szerepelni tudnak. A Commerce rendszer 10.0.31-es és újabb verzióiban a pénztári modul hibaüzenetei hibakódokat tartalmaznak, és felesleges információkat nem mutatnak be az online vevő számára. A hibakódok az ebben a cikkben részletezett hibákra vonatkoznak.

A történt hibáktól függően a cikk táblázata a következő adatokat tartalmazza:

- A hibát okozó feltétel leírása, vagy további részletek
- Figyelembe kell venni a környezet és a fizetési csatlakoztató konfigurációit.
- Olyan információk, amelyekre hivatkozni lehet a támogatási esetben, ha további segítségre van szükség.

## <a name="checkout-module-error-reference-codes"></a>Pénztármodul hibahivatkozási kódjai

A következő táblázatban további részleteket olvashat a vevők által biztosított vagy az online áruházban tapasztalt hibakódhivatkozásokkal kapcsolatban.

| Hibakód | Dynamics-relációval érintett hibakód | Hiba leírása |
| ---------- | ------------------------------ | ----------------- |
| CCR001     | Microsoft\_ Dynamics\_ Commerce\_ runtime\_ UnableToAuthorizePaymentCardTypeMissingOrNotSupported | A fizetést nem sikerült engedélyezni. Hiányzik a Kártyatípus azonosítója **a TokenizedPaymentCard** eszközből, vagy a megadott kártyatípus-azonosító nem támogatott. |
| CCR002     | Microsoft\_ Dynamics\_ Commerce\_ runtime\_ UnableToAuthorizePayment | Csökkent. A fizetést nem sikerült engedélyezni. |
| CCR003     | Microsoft\_ Dynamics\_ Commerce\_ Runtime\_ UnableToAuthorizePaymentCardAdditionalContextRequired | A fizetést nem sikerült engedélyezni. További információk szükségesek a vevőtől. |
| CCR004     | Microsoft\_ Dynamics\_ Commerce\_ runtime\_ UnableToRetrieveCardPaymentAcrieResult | Valamilyen hiba történt. Nem sikerült megszerezni a kártyás fizetés elfogadásának eredményét. Próbálkozzon újra, vagy forduljon a rendszergazdához. |
| CCR005     | Microsoft\_ Dynamics\_ Commerce\_ Runtime\_ PaymentRequiresMerchantProperties | Nem lehet fizetni, mert hiányoznak a kereskedői fizetési tulajdonságok. Forduljon a rendszergazdához. |
| CCR006     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ InvalidPaymentRequest | Nem sikerült beolvasni a művelethez a fizetőeszköz-szolgáltatást. A kiválasztott fizetőeszköz-típus fizetési mód beállításának ellenőrzése. |
| CCR007     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ MultipleCustomerAccountPaymentsNotAllowed | Már alkalmaztak vevői számlafizetést, és tranzakciónként csak egy kifizetés megengedett. |
| CCR008     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ CustomerAccountLimitSignDifferentFromAmountDue | A vevő számlakorlátja eltér az esedékes összegtől. Próbálkozzon egy másik fizetési mód használatával, vagy segítségért forduljon az ügyfélszolgálathoz. |
| CCR009     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ CustomerAccountPaymentExceedsTotalAmountForCarryOutAndReturnItems | A vevői számla fizetése meghaladja a felsorolt cikkeknél esedékes végösszeget. Próbálkozzon újra később, vagy segítségért forduljon az ügyfélszolgálathoz. |
| CCR010     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ PaymentUsingUnauthorizedAccount | A vevői számlához a saját számlára vagy egyező számlaszámra van szükség egy fizetési sorban. |
| CCR011     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ CustomerAccountPaymentExceedsCustomerAccountFlszámlálásLimit | Nem sikerült jelenleg a vevői számla fizetésének feldolgozása – túllépte az alsó korlát értékét. |
| CCR012     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ CustomerAccountPaymentForCustomerWithoutAllowOnAccount | Ennek a vevőnek nincs engedélyezve a számlára való fizetés. |
| CCR013     | Microsoft\_ Dynamics\_ Commerce\_ runtime\_ UnableToCancelPayment | Valamilyen hiba történt. A fizetést nem sikerült érvénytelenni. Próbáld újra. |
| CCR014     | A Microsoft\_ Dynamics\_ Commerce\_ futásideje\_ nem olvasCardTokenInfo | Hiba történt a kifizetés feldolgozásakor. Később próbálja meg újra. |
| CCR015     | Microsoft\_ Dynamics\_ Commerce\_ Runtime\_ NotEnwardRewardPoints | A tranzakcióban használt hűségkártya fizetési összege meghaladja a megengedettet. |
| CCR016     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ RefundAmountMorethanAllowed | A tranzakcióban használt hűségkártya visszatérítési összege meghaladja a megengedettet. |
| CCR017     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ invalidLoyaltyCardNumber | Nem található a hűségkártyaszám. Aktiválja a hűségkártya számát, vagy adjon meg másik kártyaszámot, majd próbálkozzon újra. |
| CCR018     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ blockedLoyaltyCard | A hűségkártya száma nem érhető el. Adjon meg egy másik kártyaszámot, majd próbálkozzon újra. |
| CCR019     | Microsoft\_ Dynamics\_ Commerce\_ runtime\_ NoTenderLoyaltyCard | Ez a hűségkártya nem jogosult hűségpontok beváltása erre a tranzakcióra. |
| CCR020     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ GiftCardCurrencyMismatch | Az ajándékutalvány száma hibát észlelt. Próbálkozzon egy másik ajándékutalványsal, vagy segítségért forduljon az ügyfélszolgálathoz. |
| CCR021     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ PaymentAmountExceedsGiftBalance | Az összeg meghaladja az ajándékutalvány egyenlegét. Adjon meg más összeget, majd próbálkozzon újra. |
| CCR022     | Microsoft\_ Dynamics\_ Commerce\_ runtime\_ NoMoreThanOneLoyaltyTender | A tranzakció nem tartalmazhat több hűségpontos fizetési sort. |
| CCR023     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ PaymentAlreadyVoided | A fizetési adatok helytelenek vagy hiányoznak az adatokból. Ellenőrizze a fizetési adatokat, majd próbálkozzon újra. |
| CCR024     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ FraudRisk | A rendelés most nem feldolgozható. Később próbálja meg újra. |
| CCR025     | Időtúllépés az előlapon a pénztár API-ja számára | Az első záró művelet időkorrekciót ért el. Erősítse meg, hogy a rendelés feldolgozása a központban történt-e Dynamics 365 Commerce. |
| CCR026     | Az eredeti engedélyezett összeg megváltozott | A rendelés összege módosult a fizetési átjárónál feldolgozott eredeti engedélyezési összegről. Ennek az lehet az oka, hogy egy utalvány, promóció vagy értékesítés lejárt. |
| CCR027     | Microsoft\_ Dynamics\_ Commerce\_ futásidejű\_ InvalidCartVersion | Hiba történt egy kifizetés feldolgozásakor. A Cart API-hoz megadott hivatkozás a várttól eltérő hivatkozást tartalmaz (és a pénztári folyamat során inkonzisztenciát ismer). |
| CCR028     | Microsoft\_ Dynamics\_ Commerce\_ runtime\_ MissingRequiredCartTenderLines | A megkísérelt fizetési mód hibát észlelt. Lépjen kapcsolatba a támogatási csoporttal a számlabeállítások ellenőrzéséhez, vagy próbálkozzon újra egy másik fizetési mód használatával. |

## <a name="additional-resources"></a>További erőforrások

[Kifizetésekkel kapcsolatos GYIK](dev-itpro/payments-retail.md)

[Pénztármodul](add-checkout-module.md)

[Fizetési modul](payment-module.md)
