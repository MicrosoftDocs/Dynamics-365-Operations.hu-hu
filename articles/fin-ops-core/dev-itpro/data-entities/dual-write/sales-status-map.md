---
title: Az értékesítési rendelés állapotoszlopaihoz tartozó leképezés beállítása
description: Ez a cikk bemutatja, hogy hogyan lehet beállítani az értékesítési rendelések állapotoszlopait a kettős íráshoz.
author: dasani-madipalli
ms.date: 06/25/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: damadipa
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 2035985f16b5972e02f1ed60c6f02d306217f3be
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288884"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a>Az értékesítési rendelés állapotoszlopaihoz tartozó leképezés beállítása

[!include [banner](../../includes/banner.md)]

Az értékesítési rendelés állapotát jelző oszlopok a Microsoft Dynamics 365 Supply Chain Management és a Dynamics 365 Sales alkalmazásban eltérő számértékekkel rendelkeznek. Ezeknek az oszlopoknak a leképezéséhez a kettős írásban további beállítás szükséges.

## <a name="columns-in-supply-chain-management"></a>A Supply Chain Management oszlopai

A Supply Chain Management alkalmazásban két oszlop tükrözi az értékesítési rendelés állapotát. A leképezni kívánt oszlopok az **Állapot** és a **Dokumentum állapota**.

Az **Állapot** számozása a rendelés általános állapotát határozza meg. Ez az állapot jelenik meg a rendelés fejlécében.

Az **Állapot** számozás a következő értékekkel rendelkezik:

- Nyitott rendelés
- Teljesítve
- Számlázva
- Visszavonva

A **Dokumentum állapota** felsorolása a rendeléshez létrehozott legfrissebb dokumentumot határozza meg. Ha például a rendelés meg van erősítve, akkor ez a dokumentum egy értékesítési rendelés visszaigazolása. Ha egy értékesítési rendelést részben számláznak, és a fennmaradó sor meg van erősítve, akkor a dokumentum állapota a **Számla** marad, mivel a számla később jön létre a folyamatban.

A **Dokumentum állapota** felsorolás a következő értékekkel rendelkezik:

- Visszaigazolás
- Kitárolási lista
- Csomagjegyzék
- Számla

## <a name="columns-in-sales"></a>Oszlopok az Értékesítésben

A Sales alkalmazásban két oszlop jelzi az értékesítési rendelés állapotát. A leképezni kívánt oszlopok az **Állapot** és a **Feldolgozás állapota**.

Az **Állapot** számozása a rendelés általános állapotát határozza meg. Az alábbi értékekkel rendelkezik:

- Aktív
- Elküldve
- Teljesített
- Számlázva
- Visszavonva

A **Feldolgozási állapot** számozása azért lett bevezetve, hogy az állapot pontosabban legyen megfeleltetve a Supply Chain Management alkalmazással.

A következő táblázat bemutatja a Supply Chain Management **Feldolgozási állapotának** leképezését.

| Feldolgozás állapota   | A Supply Chain Management állapotai | Dokumentum állapota a Supply Chain Management alkalmazásban |
|---------------------|-----------------------------------|--------------------------------------------|
| Aktív              | Nyitott rendelés                        | None                                       |
| Visszaigazolva           | Nyitott rendelés                        | Visszaigazolás                               |
| Kitárolva              | Nyitott rendelés                        | Kitárolási lista                               |
| Részlegesen kiszállítva | Nyitott rendelés                        | Csomagjegyzék                               |
| Teljesítve           | Teljesítve                         | Csomagjegyzék                               |
| Részben számlázva  | Teljesítve                         | Számla                                    |
| Számlázva            | Számlázva                          | Számla                                    |
| Visszavonva           | Visszavonva                         | Nem alkalmazható                             |

A következő táblázat bemutatja a **Feldolgozási állapotának** leképezését a Sales és a Supply Chain Management között.

| Feldolgozás állapota   | Állapot a Sales alkalmazásban | A Supply Chain Management állapotai |
|---------------------|-----------------|-----------------------------------|
| Aktív              | Aktív          | Nyitott rendelés                        |
| Visszaigazolva           | Elküldve       | Nyitott rendelés                        |
| Kitárolva              | Elküldve       | Nyitott rendelés                        |
| Részlegesen kiszállítva | Aktív          | Nyitott rendelés                        |
| Részben számlázva  | Aktív          | Nyitott rendelés                        |
| Részben számlázva  | Teljesített       | Teljesítve                         |
| Számlázva            | Számlázva        | Számlázva                          |
| Visszavonva           | Visszavonva       | Érvénytelenített                         |

## <a name="setup"></a>Beállítás

Az értékesítési rendelés állapot oszlopainak leképezésének beállításához az **IsSOPIntegrationEnabled** és az **isIntegrationUser** attribútumokat engedélyeznie kell.

Az **IsSOPIntegrationEnabled** attribútum engedélyezéséhez kövesse az alábbi lépéseket.

1. Lépjen egy böngészőben a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations` címre. Cserélje le a **\<test-name\>** elemet a vállalat a Sales alkalmazásra mutató hivatkozásra.
2. A megnyitott lapon keresse meg a **organizationid** elemet, és jegyezze fel az értéket.

    ![Az organizationid megkeresése.](media/sales-map-orgid.png)

3. A Sales alkalmazásban meg a böngésző konzolt, majd futtassa a következő parancsfájlt. A 2. lépésből használja az **organizationid** értéket.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![JavaScript-kód a böngésző konzolján.](media/sales-map-script.png)

4. Ellenőrizze, hogy a **IsSOPIntegrationEnabled** **igaz** értékre legyen állítva. A 1. lépésből használja az URL-címet az érték ellenőrzéséhez.

    ![A IsSOPIntegrationEnabled igaz értékre van állítva.](media/sales-map-integration-enabled.png)

Az **isIntegrationUser** attribútum engedélyezéséhez kövesse az alábbi lépéseket.

1. A Sales alkalmazásban nyissa meg a **Beállítás \> Testreszabás \> Rendszer testreszabása** lehetőséget, válassz a **Felhasználói tábla** lehetőséget, és nyissa meg a **Képernyő \> Felhasználó** elemet.

    ![A feéhasználó képernyő megnyitása.](media/sales-map-user.png)

2. A Mezőkezelőben keresse meg **Integráció felhasználói mód** lehetőséget, majd kattintson rá duplán, hogy hozzáadja a képernyőhöz. Mentse el a módosítást.

    ![Az integrációs felhasználói mód oszlop hozzáadása a képernyőhöz.](media/sales-map-field-explorer.png)

3. Az Sales alkalmazásban nyissa meg a **Beállítás \> Biztonság \> Felhasználók** lehetőséget és a nézetet módosítsa **Engedélyezett felhasználók** helyett **Alkalmazás felhasználói** értékre.

    ![A nézet módosítása az Engedélyezett felhasználókról az Alkalmazás felhasználóira.](media/sales-map-enabled-users.png)

4. Válassza ki a **DualWrite IntegrationUser** két bejegyzését.

    ![Alkalmazásfelhasználók listája.](media/sales-map-user-mode.png)

5. Módosítsa az **Integrációs felhasználói mód** oszlop értékét **Igen** értékre.

    ![Az integrációs felhasználói mód oszlop értékének módosítása Igen értékre.](media/sales-map-user-mode-yes.png)

Az értékesítési rendeléseket már le vannak képezve.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
