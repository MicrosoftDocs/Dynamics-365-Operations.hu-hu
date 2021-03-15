---
title: Számlajóváhagyások mobil munkaterület
description: Ez a témakör a Számlajóváhagyások mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást.
author: abruer
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 1a7aa1a03791b8ccb7050389097d1272f5930a49
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127569"
---
# <a name="invoice-approvals-mobile-workspace"></a>Számlajóváhagyások mobil munkaterület

[!include [banner](../includes/banner.md)]

Ez a témakör a **Számlajóváhagyások** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. A munkaterület a szállítói számla fejléce munkafolyamattal Önhöz rendelt számlák listáját tartalmazza. 

A mobil munkaterületet a Finance and Operations mobilalkalmazásban való használatra tervezték.

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
<td>A Microsoft Dynamics 365 Finance szolgáltatást telepíteni kell a szervezetében.</td>
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

A Finance and Operations mobilalkalmazás letöltése és telepítése:

-   [Android telefonok esetében:](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhone esetében:](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Bejelentkezés a mobilalkalmazásba

1.  Indítsa el az alkalmazást a mobileszközén.
2.  Adja meg a Microsoft Dynamics 365 URL-címét.
3.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.
4.  A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.

    [![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

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