---
title: Cikk adócsoportjainak beállítása
description: Ez a cikk azt mutatja be, hogyan lehet cikkadócsoportokat beállítani az adószámítási szolgáltatásban.
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
ms.openlocfilehash: 3bc705bc8173ad2bc8ef883e6dc80b0a187314ad
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846463"
---
# <a name="set-up-item-tax-groups"></a>Cikk adócsoportjainak beállítása

[!include [banner](../includes/banner.md)]

Ez a cikk azt mutatja be, hogyan lehet cikkadócsoportokat beállítani az adószámítási szolgáltatásban. Bemutatja azt is, hogyan lehet beállítani a cikkadócsoport alkalmazhatósági szabálymátrixát, és konfigurálni a mátrix sorait.

Az Adószámítási szolgáltatás cikkadócsoportokkal kapcsolatos fogalma Microsoft Dynamics hasonlít a 365 Pénzügy cikk áfacsoportjának koncepcióhoz. Ezek adókódcsoportok. Az adószámítási szolgáltatás egy adócsoport és egy cikkadócsoport együttesét használja az áfakódok meghatározására.

> [!IMPORTANT]
> Az adószámítási szolgáltatásban a cikkadócsoportok beállítása jogi személy– nem független. Ezt a beállítást csak egyszer lehet végrehajtani az RCS (Regulatory Configuration Service) szolgáltatásban. Ha engedélyezi az Adószámítás szolgáltatást a Pénzügyben, a program automatikusan szinkronizálja a cikkadócsoportokat a kiválasztott jogi személyhez.

## <a name="set-up-an-item-tax-group"></a>Cikkadócsoport beállítása 

A következő lépések szerint állíthatja be a cikkadócsoportokat.

1. Jelentkezzen be a szabályozó [konfigurációs szolgáltatásba](https://marketing.configure.global.dynamics.com/).
2. Ugrás a Munkaterületek **globalizációs** \> **funkciói – Adószámítás** \> **·**
3. Válassza ki a beállítani kívánt szolgáltatást és verziót, majd válassza a Szerkesztés **lehetőséget**.
4. Az Általános **lapon** válassza ki a Konfiguráció **verziót**.
5. A Cikkadócsoport **lapon** válassza a Kezelés **oszlopot**. Ha az első alkalommal cikkadócsoportot ad meg, **az** Oszlop kezelése párbeszédpanel mezői automatikusan be vannak állítva.
6. A bal oldali listán bontsa **ki a Sorok** csomópontot, és jelölje **be a Cikkadócsoport jelölőnégyzetet**.

    ![Az Oszlopok kezelése párbeszédpanel Sorok csomópontja alatt kiválasztott cikkadócsoport.](media/select-item-tax-group.png)

7. A jobbra nyílgombbal a cikkadócsoportot **hozzáadhatja** **a jobb oldalon kijelölt oszlopok** listájához.

    ![A Kijelölt oszlopok listájához hozzáadott cikkadócsoport.](media/add-item-tax-group.png)

8. Válassza ki az **OK** lehetőséget.

## <a name="configure-an-item-tax-group"></a>Cikkadócsoport konfigurálása

A cikkadócsoport beállítása után létrejön az alkalmazhatósági szabálymátrix. A mátrixba sorokat adhat a cikkadócsoport konfigurálása számára.

1. A Cikkadócsoport **lapon** válassza a Hozzáadás **elemet**.
2. A Cikkadócsoport **mezőbe** írja be a cikkadócsoport nevét.

    > [!IMPORTANT]
    > Javasoljuk, hogy a cikkadócsoport nevét legfeljebb 10 karakterre korlátozza. Ez a név szinkronizálva van a Pénzügy alkalmazással, amelynek legfeljebb 10 karakter hosszú neve lehet a cikk áfacsoportja.

3. Az Adókódok **mezőben** jelölje be mindegyik olyan adókód jelölőnégyzetét, amely a cikk adócsoportjában szerepel. Egy cikkadócsoportba több adókód is tartozhat.

    ![Több adókód van kiválasztva az Adókódok mezőben.](media/multiple-tax-codes-selection.png)

4. További cikkadócsoportok hozzáadásához ismételje meg az 1–3. lépést.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
