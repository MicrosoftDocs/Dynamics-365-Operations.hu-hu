---
title: Saját csapat mobil munkaterület
description: Ez a témakör tájékoztatást nyújt a Saját csapat mobil munkaterületről, amely lehetővé teszi a vezetők számára a közvetlen beosztottjaik és a bővebb személyzet megtekintését.
author: ShielaSogge
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 06ddad1f2df895da4819a06e3552acab8e9aff78
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744733"
---
# <a name="my-team-mobile-workspace"></a>Saját csapat mobil munkaterülete

[!include [banner](../includes/banner.md)]

Ez a témakör a **Saját csapat** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. A munkaterület lehetővé teszi a vezetők számára a közvetlen beosztottjaik és a bővebb személyzet megtekintését. Emellett pozitív visszajelzést is küldhetnek beosztotti láncukban levő egyéneknek.

A mobil munkaterületet a Finance and Operations mobilalkalmazásban való használatra tervezték.

## <a name="overview"></a>Áttekintés 
A **Saját csapat** mobil munkaterület a következő műveletek végrehajtását teszi lehetővé a vezetők számára:

- A vezető közvetlen beosztottjait tartalmazó lista megtekintése.
- A vezető kiterjesztett beosztotti csapatát tartalmazó lista megtekintése.
- Részletes információk tekinthetők meg mindegyik csoporttagról, például születési dátum, szolgálati idő dátuma, foglalkoztatotti évek száma, kompenzációs és teljesítményadatok.
- Pozitív visszajelzés küldése egy személynek a vezető kiterjesztett beosztotti csoportjában.

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
<td>A következő termékek egyikének telepítve kell lennie a szervezeténél:
<ul><li>Egy Finance and Operations-alkalmazás</li>
<li>Microsoft Dynamics 365 Human Resources</li>
</ul>
</td>
<td>Rendszergazda</td>
<td>Ha a vállalati hálózatra még nincs telepítve a Finance and Operations alkalmazás, lásd a következő tudnivalókat: <a href="../deployment/deploy-demo-environment.md">Bemutatókörnyezet telepítése</a>. Ha a szervezetében még nincs telepítve az Emberi erőforrások, a rendszergazda hozzáférhet a próbaverzióhoz az <a href="https://dynamics.microsoft.com/human-resources/overview/">Emberi erőforrások weboldaláról</a>.
</td>
</tr>
<tr class="even">
<td>A <strong>Saját csapat</strong> mobil munkaterületet közzé kell tenni.</td>
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

## <a name="view-team-members-by-using-the-my-team-mobile-workspace"></a>Csoporttagok megtekintése a Saját csapat mobil munkaterület használatával
1.  A mobil alkalmazásában jelölje ki a **Saját csapat** munkaterületet. Megjelenik a csoporttagok listája. A lista emellett megjeleníti minden csapattag beosztását, valamint a tag közvetlen beosztottjait, ha vannak ilyenek.
2.  Válasszon ki egy csapattagot. Megjelenik a **Csapattag összefoglalója** lap. Az ezen a lapon található információk tartalmazzák a csapattag születési dátumát, a szolgálati ideje dátuma, azt, hogy hány éve foglalkoztatott, a jelenlegi beosztásban eltöltött évek számát, valamint a kompenzációs adatokat.

## <a name="view-extended-team-members-by-using-the-my-team-mobile-workspace"></a>Bővített csoport tagjainak megtekintése a Saját csapat mobil munkaterület használatával
1.  A mobil alkalmazásában jelölje ki a **Saját csapat** munkaterületet. Megjelenik a csoporttagok listája. A lista emellett megjeleníti minden csapattag beosztását, valamint a tag közvetlen beosztottjait, ha vannak ilyenek.
1.  Válassza ki a **Közvetlen beosztottak** hivatkozást. Megjelenik a bővített csoport tagjainak listája.
1.  Válasszon ki egy csapattagot. Megjelenik a **Csapattag összefoglalója** lap. Az ezen a lapon található információk tartalmazzák a csapattag születési dátumát, a szolgálati ideje dátuma, azt, hogy hány éve foglalkoztatott, a jelenlegi beosztásban eltöltött évek számát, valamint a kompenzációs adatokat.

## <a name="send-praise-about-team-members-by-using-the-my-team-mobile-workspace"></a>Pozitív visszajelzés a csoporttagokkal kapcsolatban a Saját csapat mobil munkaterület használatával
1.  A mobil alkalmazásában jelölje ki a **Saját csapat** munkaterületet. Megjelenik a csoporttagok listája. A lista emellett megjeleníti minden csapattag beosztását, valamint a tag közvetlen beosztottjait, ha vannak ilyenek.
1.  Válasszon ki egy csapattagot. Megjelenik a **Csapattag összefoglalója** lap.
1.  Válassza ki a **Dicséret küldése** lehetőséget. 
1. Adja meg az elküldeni kívánt pozitív visszajelzés szövegét. 
1. Válassza a **Kész** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]