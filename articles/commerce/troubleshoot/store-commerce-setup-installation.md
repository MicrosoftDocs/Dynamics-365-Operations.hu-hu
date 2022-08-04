---
title: A Store Commerce beállítási és telepítési problémáinak elhárítása
description: Ez a témakör leírja, hogyan lehet elhárítani a Microsoft Dynamics 365 Commerce Store Commerce alkalmazás beállítási és telepítési problémáit.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 8af2c476ced05fc159a53131f8b51ad914a6c7c3
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/16/2022
ms.locfileid: "9168947"
---
# <a name="troubleshoot-store-commerce-setup-and-installation-issues"></a>A Store Commerce beállítási és telepítési problémáinak elhárítása

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan lehet elhárítani a Microsoft Dynamics 365 Commerce Store Commerce alkalmazás beállítási és telepítési problémáit.

## <a name="i-cant-activate-the-app-and-i-receive-a-connectivity-error-message"></a>Nem lehet aktiválni az alkalmazást, és hibaüzenet jelenik meg a kapcsolatról

Miután beírta az érvényes CPOS-url-címet a felhőben, a következő példához hasonló kapcsolati hibaüzenetet kaphat:

> Kapcsolati hiba történt, és az eszköz nem tud csatlakozni a CPOS-kiszolgálóhoz. A CPOS URL-cím beírta bizonyos problémákat okozhat.

Ebben az esetben ellenőrizze az URL-címet, hogy vannak-e hibák a hibák esetén, vagy állapítsa meg, hogy a CPOS nem érhető-e el, mert kapcsolat nélküli állapotban van.

Ezenkívül győződjön meg arról, hogy a felhőskálaegység (SCALE Unit) verziója 10.0.25 (9.35.\*.\*) vagy később. A Store Commerce alkalmazás csak a 10.0.25-ös vagy újabb verziójú CPOS-fájlok esetén használható.

## <a name="i-cant-install-the-app-because-modern-pos-is-already-installed"></a>Nem lehet telepíteni az alkalmazást, mert a Modern POS már telepítve van.

A telepítés során hibaüzenetet kaphat, például a következő példát:

> A termék (Modern POS) egy verziója (9.\*.\*.\*) már telepítve van az örökölt telepítővel.

A hiba kijavítás érdekében el kell távolítania a Modern Point of Sale (MPOS) alkalmazást a számítógépen található összes felhasználóra, majd újra próbálkozhat. A következő PowerShell parancs futtatásával megerősítheti, hogy minden felhasználónál törölték-e az MPOS-t.

```PowerShell
Get-AppxPackage | Where-Object {$_.PackageFullName -like "Microsoft.Dynamics.*.Pos"} | Remove-AppxPackage -Allusers
```

## <a name="i-cant-activate-the-app-because-of-an-invalid-url-or-an-error-state"></a>Érvénytelen URL-cím vagy hibaállapot miatt nem lehet aktiválni az alkalmazást.

Ha a megadott CPOS URL-cím érvénytelen, és módosítani szeretné, vagy ha az aktiválás során hibaállapotban van a Store Commerce alkalmazás, akkor az alkalmazás alaphelyzetbe állításával újraindíthatja a folyamatot. A Store Commerce alkalmazás csak egy érvényes CPOS-URL-címet ment.

A Következő lépések szerint állíthatja alaphelyzetbe a Store Commerce alkalmazást.

1. A Windows Start **menüjében** válassza ki és tartsa lenyomva az alkalmazást (vagy kattintson rá a jobb gombbal), majd válassza a **További \> alkalmazásbeállítások elemet**.
2. Görgetés lefelé az alkalmazásbeállítási lapon, amíg meg nem találja az Alaphelyzet **gombot**.
3. **Alaphelyzet** kiválasztása. Ezt követően a program megkérdezi, hogy vissza szeretné-e állítani az alkalmazást.
