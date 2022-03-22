---
title: TDS-paraméterek beállítása Kötelezettségek és Kinnlevőségek esetében
description: Ez a témakör bemutatja, hogyan lehet beállítani paramétereket a Kötelezettségek és Kinnlevőségek között a forrásnál levont adó (TDS) levonások támogatásához.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 2205ddc1b651ff851a4285b1ded17106600e6058c719fecf0b447ac8c87d43cb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755616"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>TDS-paraméterek beállítása Kötelezettségek és Kinnlevőségek esetében

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet beállítani paramétereket a Kötelezettségek és Kinnlevőségek között a forrásnál levont adó (TDS) levonások támogatásához.

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
