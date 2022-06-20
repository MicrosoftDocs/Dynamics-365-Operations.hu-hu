---
title: Adócsoportok beállítása
description: Ez a cikk bemutatja, hogyan lehet adócsoportokat beállítani az adószámítási szolgáltatásban.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 89c5670ee7e78f2dc51f128c3ae8d284bb6b925b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862899"
---
# <a name="set-up-tax-groups"></a>Adócsoportok beállítása

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet adócsoportokat beállítani az adószámítási szolgáltatásban. Bemutatja az adócsoport alkalmazhatósági szabálymátrixának beállítását és a sorok mátrixba való konfigurálát is.

Az Adószámítási Microsoft Dynamics szolgáltatásban használt adócsoportok koncepciója hasonlít a 365-ös pénzügyi áfacsoport koncepcióhoz. Ezek adókódcsoportok. Az adószámítási szolgáltatás egy adócsoport és egy cikkadócsoport együttesét használja az áfakódok meghatározására.

Az adószámítási szolgáltatás adócsoportja azonban különbözik a Pénzügyben használt áfacsoportoktól, mivel nincs további paraméterük(**·** **például a használatadó és a mentességi adó)**. Ehelyett ezek a paraméterek érhetők el az adókód szintjén.

> [!IMPORTANT]
> Az adószámítási szolgáltatásban az adócsoportok beállítása jogi személy–nem független. Ezt a beállítást csak egyszer lehet végrehajtani az RCS (Regulatory Configuration Service) szolgáltatásban. Ha engedélyezi az Adószámítás szolgáltatást a Pénzügyben, a program automatikusan szinkronizálja az adócsoportokat a kiválasztott jogi személyhez.

## <a name="set-up-a-tax-group"></a>Adócsoport beállítása

A következő lépések szerint állíthatja be az adócsoportokat.

1. Jelentkezzen be a szabályozó [konfigurációs szolgáltatásba](https://marketing.configure.global.dynamics.com/).
2. Ugrás a Munkaterületek **globalizációs** \> **funkciói – Adószámítás** \> **·**
3. Válassza ki a beállítani kívánt szolgáltatást és verziót, majd válassza a Szerkesztés **lehetőséget**.
4. Az Általános **lapon** válassza ki a Konfiguráció **verziót**.
5. Az Adócsoport **lapon** válassza az Oszlop **kezelése lehetőséget**. Ha az első alkalommal adócsoportot ad meg, **az** Oszlop kezelése párbeszédpanel mezői automatikusan be vannak állítva.
6. A bal oldali listán bontsa **ki a Sorok** csomópontot, és jelölje be **az Adócsoport jelölőnégyzetet**.

    ![Az Oszlopok kezelése párbeszédpanel Sorok csomópontja alatt kiválasztott adócsoport.](media/select-tax-group.png)

7. A jobbra nyílgombbal adócsoportot **adhat hozzá** **a jobb oldalon lévő Kijelölt oszlopok** listájához.

    ![A Kijelölt oszlopok listájához hozzáadott adócsoport.](media/add-tax-group.png)

8. Válassza ki az **OK** lehetőséget.

## <a name="configure-a-tax-group"></a>Adócsoport konfigurálása

Az adócsoport beállítása után létrejön az adócsoport alkalmazhatósági szabálymátrixa. A mátrixba sorokat felvehet az adócsoport konfigurálása segítségével.

1. Az Adócsoport **lapon** válassza a Hozzáadás **lehetőséget**.
2. Az Adócsoport **mezőbe** írja be az adócsoport nevét.

    > [!IMPORTANT]
    > Javasoljuk, hogy az adócsoport nevét legfeljebb 10 karakterre korlátozza. Ez a név szinkronizálva van a Pénzügy alkalmazással, amelynek 10 karakteres korlátja van az áfacsoportok nevéhez.

3. Az Adókódok **mezőben** jelölje be mindegyik olyan adókód jelölőnégyzetét, amely szerepel az adócsoportban. Egy adócsoportba több adókód is tartozhat.

    ![Több adókód van kiválasztva az Adókódok mezőben.](media/multiple-tax-codes-selection.png)

4. További adócsoportok hozzáadásához ismételje meg az 1–3. lépést.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
