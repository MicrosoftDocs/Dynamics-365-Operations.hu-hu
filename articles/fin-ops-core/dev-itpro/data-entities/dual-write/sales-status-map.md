---
title: Az értékesítési rendelés állapot mezőihez tartozó hozzárendelés beállítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani az értékesítési rendelés állapotmezőit a kettős íráshoz.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: dce4b6310e2f6d31a115302efa7fbc132799e48f
ms.sourcegitcommit: 4ba10abe5be8a21b95370cd970a622e954970984
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2020
ms.locfileid: "3829285"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a>Az értékesítési rendelés állapot mezőihez tartozó hozzárendelés beállítása

[!include [banner](../../includes/banner.md)]

Az értékesítési rendelés állapotát jelző mezők a Microsoft Dynamics 365 Supply Chain Management és a Dynamics 365 Sales alkalmazásban eltérő számértékekkel rendelkeznek. Ezeknek a mezőknek a leképezéséhez a kettős írásban további beállítás szükséges.

## <a name="fields-in-supply-chain-management"></a>A Supply Chain Management mezői

A Supply Chain Management alkalmazásban két mező tükrözi az értékesítési rendelés állapotát. A leképezni kívánt mezők az **Állapot** és a **Dokumentum állapota**.

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

## <a name="fields-in-sales"></a>A Sales mezői

A Sales alkalmazásban két mező jelzi az értékesítési rendelés állapotát. A leképezni kívánt mezők az **Állapot** és a **Feldolgozás állapota**.

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
| Visszavonva           | Visszavonva       | Visszavonva                         |

## <a name="setup"></a>Beállítás

Az értékesítési rendelés állapot mezőinek leképezésének beállításához az **IsSOPIntegrationEnabled** és a **isIntegrationUser** attribútumokat engedélyeznie kell.

Az **IsSOPIntegrationEnabled** attribútum engedélyezéséhez kövesse az alábbi lépéseket.

1. Lépjen egy böngészőben a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations` címre. Cserélje le a **\<test-name\>** elemet a vállalat a Sales alkalmazásra mutató hivatkozásra.
2. A megnyitott lapon keresse meg a **organizationid** elemet, és jegyezze fel az értéket.

    ![Az organizationid megkeresése](media/sales-map-orgid.png)

3. A Sales alkalmazásban meg a böngésző konzolt, majd futtassa a következő parancsfájlt. A 2. lépésből használja az **organizationid** értéket.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![JavaScript-kód a böngésző konzolján](media/sales-map-script.png)

4. Ellenőrizze, hogy a **IsSOPIntegrationEnabled** **igaz** értékre legyen állítva. A 1. lépésből használja az URL-címet az érték ellenőrzéséhez.

    ![A IsSOPIntegrationEnabled igaz értékre van állítva](media/sales-map-integration-enabled.png)

Az **isIntegrationUser** attribútum engedélyezéséhez kövesse az alábbi lépéseket.

1. A Sales alkalmazásban nyissa meg a **Beállítás \> Testreszabás \> Rendszer testreszabása** lehetőséget, válassz a **Felhasználói entitás** lehetőséget, és nyissa meg a **Képernyő \> Felhasználó** elemet.

    ![A feéhasználó képernyő megnyitása](media/sales-map-user.png)

2. A Mezőkezelőben keresse meg **Integráció felhasználói mód** lehetőséget, majd kattintson rá duplán, hogy hozzáadja a képernyőhöz. Mentse el a módosítást.

    ![Az integrációs felhasználói mód mező hozzáadása a képernyőhöz](media/sales-map-field-explorer.png)

3. Az Sales alkalmazásban nyissa meg a **Beállítás \> Biztonság \> Felhasználók** lehetőséget és a nézetet módosítsa **Engedélyezett felhasználók** helyett **Alkalmazás felhasználói** értékre.

    ![A nézet módosítása az Engedélyezett felhasználókról az Alkalmazás felhasználóira](media/sales-map-enabled-users.png)

4. Válassza ki a **DualWrite IntegrationUser** két bejegyzését.

    ![Alkalmazásfelhasználók listája](media/sales-map-user-mode.png)

5. Módosítsa az **integrációs felhasználói mód** mező értékét **Igen** értékre.

    ![Az integrációs felhasználói mód mező értékének módosítása Igen értékre](media/sales-map-user-mode-yes.png)

Az értékesítési rendeléseket már le vannak képezve.
