---
title: Az adó feladása nem a megfelelő főkönyvi számlára történik a bizonylaton
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak, amikor az adót nem a megfelelő főkönyvi számlára adják fel a bizonylaton.
author: qire
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 3d197046bd547757f32712a50949b41897f6fedf
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020091"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>Az adó feladása nem a megfelelő főkönyvi számlára történik a bizonylaton

[!include [banner](../includes/banner.md)]

A feladás során lehetséges, hogy az adó feladása nem a megfelelő főkönyvi számlára történik a bizonylaton. A probléma elhárításához igény szerint kövesse az alábbi szakaszok lépéseit. Az ebben a témakörben található példákban az értékesítési rendeléseket használjuk üzleti dokumentumként.

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>Keresse meg helytelenül feladott adótranzakció adókódját

1. A **Bizonylattranzakciók** lapon válassza ki a tranzakciót, amellyel dolgozni szeretne, majd válassza a **Feladott áfa** lehetőséget.

    [![A Feladott áfa gomb a Bizonylattranzakciók lapon](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. Ellenőrizze az értéket az **Áfakód** mezőben. Ebben a példában ez az **Áfa 19**.

    [![Áfakód mező a Feladott áfa lapon](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>Az adókód főkönyvi feladási csoportjának ellenőrzése

1. Ugrás az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódok** pontra.
2. Keresse meg és válassza ki az adókódot, majd ellenőrizze a **Főkönyvi feladási csoport** mezőben az értékét. Ebben a példában ez az **Áfa**.

    [![Főkönyvi feladási csoport mező az Áfakódok oldalon](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. A **Főkönyvi feladási csoport** értéke egy hivatkozás. A csoport konfigurációjának részleteinek megtekintéséhez válassza ki a hivatkozást. Másik lehetőségként jelölje ki és tartsa lenyomva (vagy kattintson a jobb gombbal) a mezőben, majd válassza a **Részletek megtekintése** lehetőséget.

    [![Részletek megtekintése parancs](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. A **Fizetendő áfa** mezőben ellenőrizze a számlaszám helyességét, a tranzakció típusának megfelelően. Ha nem, akkor válassza ki a megfelelő számlát, amelyre könyvelni kell. Ebben a példában az értékesítési rendelés forgalmi adóját a 222200-ás számlára kell könyvelni.

    [![A főkönyvi feladási csoportok lapon található forgalmi adó kötelezettségek mezője](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    Az alábbi táblázat a **Főkönyvi feladási csoportok** lap egyes mezőiről nyújt információkat.

    | Mező                  | Leírás |
    |------------------------|-------------|
    | Fizetendő áfa      | Az adóhatóságnak fizetendő kimenő áfa fő számlája. |
    | Visszaigényelhető áfa   | Az adóhatóságtól kapott bejővő áfa fő számlája. |
    | Importadó költsége        | Az a fő számla, amely a levonható jövedelemadók feladására használatos, ha a szállítók az Európai Unió (EU) fordított áfafizetésű áruk és szolgáltatások adója (GST)/Harmonizált forgalmi adó (GST) részeként nem jelentkeznek az adóhatóságnak, illetve nem jelentik be az adóhatóságnak. Az **Importadó** lehetőséget ki kell választani az áfakódhoz abból az áfacsoportból, amelyet a tranzakcióban használnak. Ez a mező nem elérhető, csak ha a **Főkönyvi paraméterek** oldalon be van jelölve a **Áfaadózási szabályok alkalmazása** lehetőség. |
    | Fizetendő importadó        | A fő számla, amely az adóhatóságok számára fizetendő bejövő importadók feladására használatos. |
    | Kiegyenlítési számla     | A fő számlát, amelyet a főkönyvi számlák nettó egyenlegének feladására használatos, amelyek a **Fizetendő importadó** és a **Visszaigényelhető áfa** mezőkben vannak definiálva. |
    | Szállító készpénzfizetési engedménye   | A fő számla, amely készpénzfizetési engedmények feladására használatos az áfakódokhoz, amelyek ezzel a főkönyvi feladási csoporttal vannak társítva. |
    | Vevő készpénzfizetési engedménye | A fő számla, amely készpénzfizetési engedmények feladására használatos az áfakódokhoz, amelyek ezzel a főkönyvi feladási csoporttal vannak társítva. |

    További információkért lásd: [Főkönyvi feladási csoportok beállítása az áfához](tasks/set-up-ledger-posting-groups-sales-tax.md)

## <a name="debug-in-code-to-check-ledger-dimensions"></a>Hibakeresés a kódban a főkönyvi dimenziók ellenőrzéshez

A kódban a feladási számlát a főkönyvi dimenzió határozza meg. A főkönyvi dimenzió menti az adatbázis egy számlájának rekordazonosítóját.

1. Értékesítési rendeléshez adjon meg egy töréspontot a **Tax::saveAndPost()** és **Tax::post()** metódusokhoz. Ügyeljen a **\_ledgerDimension** értékére.

    [![Értékesítési rendelés kódminta törésponttal](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    Beszerzési rendelés esetén adjon meg egy töréspontot a **TaxPost::saveAndPost()** és **TaxPost::postToTaxTrans()** metódusoknál. Ügyeljen a **\_ledgerDimension** értékére.

    [![Beszerzési rendelés kódminta törésponttal](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. A következő SQL-lekérdezés futtatásával keresse meg a számla megjelenítendő értékét az adatbázisban, a főkönyvi dimenzió által mentett rekordazonosító alapján.

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![A rekordazonosító megjelenő értéke](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. Vizsgálja meg a hívási vermet, és keresse meg **_ledgerDimension** érték hol van hozzárendelve. Az érték általában a **TmpTaxWorkTrans** helyről származik. Ebben az esetben egy töréspontot kell hozzáadnia a **TmpTaxWorkTrans::insert()** és **TmpTaxWorkTrans::update()** elemeknél, hogy megtudja hová van hozzárendelve az érték.

## <a name="determine-whether-customization-exists"></a>Annak meghatározása, hogy létezik-e testreszabás

Ha az előző szakaszokban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás. Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
