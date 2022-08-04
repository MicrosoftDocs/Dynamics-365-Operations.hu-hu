---
title: Számlajóváhagyások mobil munkaterület
description: Ez a cikk a Számla-jóváhagyások mobil munkaterületről nyújt tájékoztatást.
author: abruer
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 4cc05d9fcea129cfb2ed8ed8df4bd4034a1fed4c
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066390"
---
# <a name="invoice-approvals-mobile-workspace"></a>Számlajóváhagyások mobil munkaterület

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../includes/mobile-app-deprecation-banner.md)]

Ez a cikk a Számla-jóváhagyások **mobil munkaterületről** nyújt tájékoztatást. A munkaterület a szállítói számla fejléce munkafolyamattal Önhöz rendelt számlák listáját tartalmazza. 

Ez a mobil munkaterület a Pénzügy és műveletek mobilalkalmazással való használatra szolgál.

## <a name="overview"></a>Áttekintés

A **Számlajóváhagyások** mobil munkaterület lehetővé teszi, hogy a kötelezettségekkel foglalkozó ügyintézők és vezetők megtekintsék a szállítói számla fejléce munkafolyamat részeként hozzájuk rendelt számlákat. A jól informált jóváhagyási döntések meghozatala érdekében megtekintheti a számlaadatokat, és akár a sor és a terjesztési részleteket is. A munkaterületről végrehajtott paranccsal végigviheti a számlát a munkafolyamaton. 

## <a name="prerequisites"></a>Előfeltételek

A mobil munkaterület csak a következő előfeltételek teljesülése esetén használható.

<table>
<thead>
<tr class="header">
<th>Előfeltételek</th>
<th>Szerep</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microsoft Dynamics A 365 Pénzügyet a szervezetben kell telepíteni.</td>
<td>Rendszergazda</td>
<td>Lásd: <a href="../deployment/deploy-demo-environment.md">Bemutatókörnyezet telepítése</a>.
</td>
</tr>
<tr class="even">
<td>A <strong>Számlajóváhagyások</strong> munkaterületet közzé kell tenni.</td>
<td>Rendszergazda</td>
<td>Lásd: <a href="publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>A mobilalkalmazás letöltése és telepítése

Töltse le és telepítse a Pénzügy és műveletek mobilalkalmazást:

-   [Android telefonok esetében:](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhone esetében:](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Bejelentkezés a mobilalkalmazásba

1.  Indítsa el az alkalmazást a mobileszközén.
2.  Adja meg a Microsoft Dynamics 365 URL-címét.
3.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.
4.  A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.

    [![Frissítés húzással.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a>Számlák jóváhagyása a Számlajóváhagyások mobil munkaterület használatával
1.  A mobileszközön válassza a **Számlajóváhagyások** munkaterületet.
2.  Válassza ki a számlát, amelyet a szállítói számla fejléce munkafolyamat által Önhöz hozzárendelték.
3.  A **Számlaadatok** oldalon tekintse át a számla fejlécadatait, többek között a dátum és a szállító adatait.
4.  Válasszon ki egy sort a számlán a részletes információk megtekintéséhez a **Számlasor részletei** nézetben.
5.  A **Számlasor részletei** nézetben válassza a **Felosztások** lehetőséget a sorfelosztások megjelenítéséhez. Itt megtekintheti a számlatétel könyvelési adatait. A megjelenített információ tartalmazza a pénzügyi dimenziókat és a fő számlát.
6.  A **Számla részletei** oldalon válassza a **Felosztások** lehetőséget az összes felosztás megjelenítéséhez. Itt megtekintheti a teljes számla könyvelési adatait. A megjelenített információ tartalmazza a pénzügyi dimenziókat és a fő számlákat. 
7.  Válassza ki a **Mellékletek** lehetőséget a számlához csatolt bármely megjegyzés vagy fájl megtekintéséhez.
8.  A **Számla részletei** lapon válassza ki a megfelelő munkafolyamat-műveletet az ellenőrzési folyamat befejezéséhez.
9.  Válassza a **Kész** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

