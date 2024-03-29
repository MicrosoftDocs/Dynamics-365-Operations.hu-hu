---
title: TDS-paraméterek beállítása Kötelezettségek és Kinnlevőségek esetében
description: Ez a cikk bemutatja, hogyan lehet beállítani a Kötelezettségek és kinnlevőségek paramétereit a forrásból levont adó (TDS) levonások támogatásához.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: e547b92f9f7e0ccc5b92df4cd991ce402369b568
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883150"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>TDS-paraméterek beállítása Kötelezettségek és Kinnlevőségek esetében

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet beállítani a Kötelezettségek és kinnlevőségek paramétereit a forrásból levont adó (TDS) levonások támogatásához.

1. Lépjen az **Adó \> Beállítások \> Paraméterek \> Kintlévőségek paraméterei** helyre.
2. A **Frissítések** lapon válassza a **Rendeléssorok frissítése** lehetőséget a **Rendeléssorok frissítése** párbeszédpanel megnyitásához.
3. A **TDS csoport** szakasz **TDS csoport frissítése** mezőjében adja meg a sor szintjén a TDS-csoport frissítéséhez használni kívánt módszert. Ez a beállítás akkor használatos, amikor a TDS-csoport frissül a rendelés fejlécében. Ehhez a következő lehetőségek állnak rendelkezésre:

    - **Soha** – A rendelésfejlécben való frissítéskor a rendeléssorok TDS-csoportja nem frissül.
    - **Mindig** – A rendelésfejlécben való frissítéskor a rendeléssorok TDS-csoportja automatikusan frissül.
    - **Kérdés** – A felhasználók egy üzenetet kapnak, amely kéri őket a rendeléssorok TDS-csoportjának frissítésére.
4. Válassza ki az **OK** lehetőséget.

    [![Rendeléssorok frissítése párbeszédpanel.](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)

5. Lépjen az **Adó \> Beállítások \> Paraméterek \> Kötelezettségek paraméterei** helyre.
6. Az **Általános** lap **Felosztás szállítási adatok szerint** gyorslapján állítsa **Igen** beállításra a **Termékbevételezés** lehetőséget különböző szállítási címekkel és adószámlaszámmal (TAN) rendelkező termékbevételezés felosztásához. Ha ez a beállítás **Nem**, nem lehet olyan beszerzési csomagjegyzéket sem elküldeni, amely más szállítási címekkel és TAN-ekkel rendelkezik.
7. A **Számla** beállítás **Igen** étékre állításával különböző szállítási címekkel rendelkező beszerzési számlát lehet feladni és felosztani.

    [![Felosztás a szállítási adatok alapján gyorslap.](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)

8. Zárja be a lapot.
