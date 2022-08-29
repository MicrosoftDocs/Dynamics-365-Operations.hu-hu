---
title: Nem csatolt visszatérítések feldolgozása a Dynamics 365 Commerce Payment Connector az Adyen szolgáltatáshoz segítségével
description: Ez a témakör leírja Microsoft Dynamics, hogyan működik a nem kapcsolódó visszatérítés a 365 Payment Connector for Adyen használata esetén.
author: BrianShook
ms.date: 10/07/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 2b2bee7ad45bbff82c8b7de2741925fde29d8583
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284311"
---
# <a name="process-unlinked-refunds-with-the-dynamics-365-commerce-payment-connector-for-adyen"></a>Nem csatolt visszatérítések feldolgozása a Dynamics 365 Commerce Payment Connector az Adyen szolgáltatáshoz segítségével

[!include [banner](../includes/banner.md)]

Ez a témakör leírja [Microsoft Dynamics, hogyan működik a nem kapcsolódó visszatérítés a 365 Payment Connector for Adyen használata](adyen-connector.md) esetén. Azt is bemutatja, hogy a pénztárban vagy a hívásközpontban hogyan lehet visszatérítést feldolgozni egy új fizetési mód ellenében.

A Dynamics 365 Payment Connector az Adyen szolgáltatáshoz lehetővé teszi a visszatérítések feldolgozását az eredeti tranzakciónál alkalmazottól eltérő fizetési mód alkalmazásával. Bár azt ajánljuk, hogy a [csatolt visszatérítések](linked-refunds.md) segítségével dolgozzon fel egy visszatérítést a megadott eredeti kifizetési mód ellenében, bizonyos helyzetekben más módszerre fizetési móddal van szükség a visszatérítésre. Például előfordulhat, hogy az eredeti fizetéshez használt kártya lejárt vagy elveszett, vagy a felhasználó megszüntette.

## <a name="prerequisites"></a>Előfeltételek

Ahhoz, hogy a Dynamics 365 Payment Connector az Adyen szolgáltatáshoz feldolgozhassa a nem csatolt visszatérítéseket, a következő előfeltételeknek be kell teljesülnie:

- A [fizetési módok](../payment-methods.md) beállítása:
- A [többcsatornás fizetések beállítása](../omni-channel-payments.md).

## <a name="additional-configuration"></a>További konfiguráció

A Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz készen érkező megvalósítást biztosít az összes támogatott visszatérítési szituációhoz a következő szakaszban. Azokat a vevőket, akik nem használják a Dynamics 365 Payment Connector az Adyen rendszer gyári implementációját, be kell állítaniuk azt az összekötőt, amely támogatja a hitelkártyák tokenizációját.

## <a name="supported-refund-scenarios"></a>Támogatott visszatérítési esetek

A Dynamics 365 Commerce támogatja korábban jóváhagyott és visszaigazolt tranzakciók csatolt visszatérítéseit. A visszatérítés a tranzakció teljes vagy részleges visszatérítése lehet. A visszatérítések nem haladhatják meg az eredeti kifizetés teljes összegét. A nem összekapcsolt visszatérítéseket csak a POS és a hívásközpont támogatja.

## <a name="enable-unlinked-refunds-functionality"></a>A nem összekapcsolt visszatérítési funkció engedélyezése

Ha engedélyezni szeretné a Commerce központi felületén a nem összekapcsolt visszatérítéseket kövesse az alábbi lépéseket.

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce megosztott paraméterek** menüpontra.
1. A **Többcsatornás fizetések** lapon állítsa a **Többcsatornás fizetések használata** beállítást **Igen** értékre.

### <a name="supported-payment-method-variants"></a>Támogatott fizetési módok

A következő fizetésimód-változatok támogatják a nem csatolt visszatérítéseket gyári állapotban:

- Kártyák
- Pénztárca

Nem minden fizetésimód-változat támogatja a nem csatolt visszatérítéseket. Az alábbi táblázat felsorolja a gyakori fizetési módokat, és bemutatja, hogy az egyes módok támogatják-e a csatolt és a nem csatolt visszatérítéseket.

| Kifizetési mód        | Csatolt visszatérítés | Nem csatolt visszatérítés |
|-----------------------|:-------------:|:---------------:|
| amexcommercial        | Igen           | Igen             |
| amexconsumer          | Igen           | Igen             |
| amexcorporate         | Igen           | Igen             |
| amexdebit             | Igen           | Igen             |
| amexprepaid           | Igen           | Igen             |
| amexprepaidreloadable | Igen           | Igen             |
| amexsmallbusiness     | Igen           | Igen             |
| discover              | Igen           | Igen             |
| maestro               | Igen           | Igen             |
| maestrouk             | Igen           | Igen             |
| mc                    | Igen           | Igen             |
| mcalphabankbonus      | Igen           | Igen             |
| mcprepaidanonymous    | Igen           | Igen             |
| visa                  | Igen           | Igen             |
| visaalphabankbonus    | Igen           | Igen             |
| visacheckout          | Igen           | Igen             |
| visadankort           | Igen           | Igen             |
| visahipotecario       | Igen           | Igen             |
| visasaraivacard       | Igen           | Igen             |
| vpay                  | Igen           | Igen             |
| givex                 | **Nem**        | Igen             |
| svs                   | **Nem**        | Igen             |
| cup                   | Igen           | Igen             |
| diners                | Igen           | Igen             |
| interac               | **Nem**        | Igen             |
| jcb                   | Igen           | Igen             |
| jcb_applepay          | Igen           | Igen             |
| unionpay              | Igen           | Igen             |

### <a name="process-an-unlinked-refund-in-pos"></a>Nem csatolt visszatérítés feldolgozása a pénztárban

A vevő a megadott időszakon belül visszaküld egy cikket a pénztár pénztárosának, és érvényes nyugtával rendelkezik. A visszáru feldolgozása során a **Visszáru-kifizetés** párbeszédpanelen szerepel egy **Fizetési mód kiválasztása** beállítás. A pénztáros ezután kiválaszthatja a kívánt fizetési módot a támogatott visszatérítési fizetési módok (kártyák és kártyák) közül.

### <a name="process-an-unlinked-refund-in-call-center"></a>Nem csatolt visszatérítés feldolgozása a hívásközpontban

Amikor a nem csatolt visszatérítés feldolgozása hívásközponti rendeléssel szemben történik, a hívásközponti alkalmazott a származási módszertől eltérő fizetési módot választ. A program ezután kéri az alkalmazottat, hogy szerezzen be rendszergazdai felülbírálati személyes azonosítót (PIN-kód). A PIN-kód szükséges ahhoz, hogy a visszatérítés eltérő fizetési módjai feldolgozhatóak legyen.

#### <a name="set-up-an-administrator-override-pin-for-call-center"></a>Rendszergazdai felülbíráló PIN beállítása hívásközponthoz

A Commerce Headquarters alkalmazásban a rendszergazdai felülbíráló PIN-kód beállításához kövesse ezeket a lépéseket.

1. Menjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Hívásközpont-beállítás** menüben , vagy keressen az "Engedélyek felülbírálása" kifejezésre.
1. Válassza ki azt a szerepkört, amely számára engedélyezni kell a nem csatolt visszatérítések feldolgozási engedélyét.
1. Az **Visszáru** gyorslapon állítsa be az **Alternatív fizetés engedélyezése** beállítást **Igen** értékre.

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 Payment Connector az Adyen szolgáltatáshoz](adyen-connector.md)

[Korábban jóváhagyott és visszaigazolt tranzakciók csatolt visszatérítései](linked-refunds.md)
