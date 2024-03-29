---
title: E-kereskedelmi fejlesztői környezet beállítása 1. szintű Retail Server virtuális géppel való hibakereséshez
description: Ez a cikk bemutatja, hogyan lehet beállítani az e-commerce fejlesztői környezetet egy 1. szintű Kiskereskedelmi kiszolgáló virtuális gép (VM) hibakereséséhez.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 64e03c742f7095e2e485f32ad534f2a755ddd062
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277879"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a>E-kereskedelmi fejlesztői környezet beállítása 1. szintű Retail Server virtuális géppel való hibakereséshez

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet beállítani az e-commerce fejlesztői környezetet egy 1. szintű Kiskereskedelmi kiszolgáló virtuális gép (VM) hibakereséséhez.

## <a name="description"></a>Leírás

A Microsoft Dynamics 365 Commerce 1. szintű környezeteket általában Commerce Runtime (CRT) és pénztári (POS) bővítmény fejlesztéséhez kell telepíteni. Ezek különálló környezetek. A szoftver szolgáltatásként (SaaS) architektúra jellege miatt nem tartalmaznak e-kereskedelmi összetevőket.

Bizonyos helyzetekben az 1. szintű környezetben érdemes tesztelni a bővítmények hívásait, hogy az e-kereskedelmi összetevőkből elvégezhesse a bővítmények hibakeresését. Általános tudnivalók: [Hibakeresés az 1. szintű Commerce fejlesztői környezetben](../e-commerce-extensibility/debug-tier-1.md).

Ha az 1. szintű környezetben hibakeresést végez, mivel a webhely egy másik Retail Server kiszolgálót hív, a több kiszolgálóra vonatkozó hívások a tartalombiztonsági házirendhez kapcsolódó, különféle hibákat okozhatnak.

A következő ábra egy olyan hibát mutat be, amely akkor fordulhat elő, ha a termék részleteit tartalmazó oldalon egy változatot választanak ki.

![Hiba történt, amikor egy változatot választottak ki a termék részleteit tartalmazó oldalon.](media/unhandled-rejection-error.jpg)

Az alábbi ábra a böngésző hibakereső eszközeiben (F12 Fejlesztői eszközök) található hasonló hibára mutat be példát. A hibaüzenet a tartalombiztonsági házirendjének megsértését említi.

![Hiba a hibakereső eszközökben.](media/debugger-tools-error.JPG)

## <a name="resolution"></a>Megoldás

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a>A webhely tartalombiztonsági házirendjének letiltása a Commerce webhelyszerkesztőben

1. Válassza ki azt a webhelyet, amelyen dolgozik.
1. Válassza a **Beállítások** lehetőséget, majd válassza ki a **Bővítmények** pontot.
1. Válassza a **Tartalombiztonsági házirend** lapon a **Tartalombiztonsági házirend letiltása** lehetőséget.
1. Válassza a **Mentés és közzététel** lehetőséget.

> [!NOTE]
> A cég és ügyfél (B2C) bejelentkezés helyi fejlesztőkörnyezetben nem működik. Vendégfizetésekkel és a buildoldalak próbaverzióival azonban szükség esetén szimulálhatja a felhasználók bejelentkezését.

## <a name="additional-resources"></a>További erőforrások

[Első lépések az e-kereskedelem online bővíthetőségének fejlesztésében](../e-commerce-extensibility/sdk-getting-started.md)

[Tartalombiztonsági házirend (CSP) kezelése az e-kereskedelmi webhelyen](../manage-csp.md)
