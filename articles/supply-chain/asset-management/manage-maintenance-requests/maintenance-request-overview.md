---
title: Karbantartási kérések
description: Ez a témakör áttekintést ad az Eszközkezelés modul karbantartási kéréseinek kezeléséről.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6d247457b83036dba2fad8fd9f94e04c29a3aa5e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985253"
---
# <a name="maintenance-requests"></a>Karbantartási kérések

[!include [banner](../../includes/banner.md)]

A karbantartási kérések olyan jegyzetek vagy nyilatkozatok, amelyek létrehozásának célja egy vezető vagy tervező értesítése, hogy egy eszköznek karbantartási vagy javítási feladatra van szüksége, munkarendelés létrehozása nélkül. Ha a karbantartási kérelem tartalmát érvényesnek ítélik, akkor a karbantartási kérés alapján létre lehet hozni egy munkarendelést.

Karbantartási kéréseket az Eszközkezelésben bármilyen eszközhöz létre lehet hozni. Különböző típusú karbantartási kéréseket lehet létrehozni, attól függően, hogy hogyan használja a vállalat a karbantartási kéréseket. Íme néhány példa:

- Karbantartási kérések
- Megjegyzések
- Javítások vagy fejlesztések
- Befektetések
- Raktárjavítás (Ez a típus akkor használatos, amikor másik helyről kapnak eszközöket, amelyeken karbantartási vagy javítási feladatot kell végrehajtani, majd a feladat befejezése után visszaküldeni az eszközt.)

## <a name="view-maintenance-requests"></a>Karbantartási kérések megtekintése

A karbantartási kérelmek megtekintéséhez válassza az **Eszközkezelés** \> **Általános** \> **Karbantartási kérések** \> **Összes karbantartási kérés**, **Aktív karbantartási kérések** vagy **Saját munkavégzési helyszínhez tartozó karbantartási kérések** lehetőséget. Minden listaoldal megjelenít egy karbantartási kéréshez kapcsolódó adatok egy részét.

![Karbantartási kérések megtekintése.](media/01-manage-maintenance-requests.png)

> [!NOTE]
> A **Saját munkavégzési helyszínhez tartozó karbantartási kérések** listaoldal segítségével megtekintheti a karbantartási kérések listáját, amelyen vagy a dolgozóként Önhöz kapcsolódó munkavégzési helyszínek szerepelnek, vagy a munkavégzési helyszínekre telepített eszközök szerepelnek, amelyekhez dolgozóként kapcsolódik. (A karbantartási dolgozók munkavégzési helyszíneinek beállítására vonatkozó további tudnivalókért tanulmányozza a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) című témakört.)
> 
> Bár a vevői számlaadatok elérhetők az Eszközszolgáltatás-menedzsment modulban (külső karbantartás), ez nem áll rendelkezésre az Eszközkezelésben (belső karbantartás).

Ha meg szeretné nyitni a rekord részletetes nézetét, az **Összes karbantartási kérés** listaoldalon a rácsnézetben válasszon egy hivatkozást a **Karbantartási kérés** oszlopban.

![A karbantartási kérelem nézetrészletei.](media/02-manage-maintenance-requests.png)

A műveleti ablak gombjai lapokon vannak rendezve. A következő táblázat röviden leírja azokat a gombokat, amelyek az Eszközkezeléshez kötődnek.

| Gomb neve                      | Leírás |
|----------------------------------|-------------|
| Szerkesztés                             | A kijelölt karbantartási kérés szerkesztése. |
| Új                              | Hozzon létre új karbantartási kérést. |
| Eltávolítás                           | Törölje a kiválasztott karbantartási kérést. |
| Munkarendelés-gyűjtő                  | A kijelölt karbantartási kérést csatlakoztathatja egy munkarendelési gyűjtőhöz. |
| Munkarendelés                       | A kijelölt karbantartási kérés alapján hozzon létre egy munkarendelést. |
| Eszközhiba                      | Kattintson az **Eszközhibák** elemre, ahol rögzítheti a hibákat a kiválasztott karbantartási kérésen. |
| Munkarendelések                      | Az összes munkarendelés listáját megjelenítheti, amelyek a kijelölt karbantartási kéréshez kapcsolódnak. |
| Karbantartási kérés állapotának frissítése | Frissítheti a karbantartási kérés állapotát. |
| Életciklus-állapot naplója              | Megtekinthet egy naplót, amely a kiválasztott karbantartási kérés életciklus-állapotait mutatja. |
| Karbantartási kérés részletei      | Kinyomtathat egy jelentést, amely a kijelölt karbantartási kérés részleteit mutatja. |
| Kölcsönzött eszköz küldése                  | Válasszon ki egy kölcsönzött eszközt, amelyet ideiglenes helyettesítőként használhatnak egy eszköz helyett, amelyet a kijelölt karbantartási kérésen kiválasztottak. |
| Kölcsönzött eszköz visszaküldése                | A kölcsönzött eszközt visszaküldöttként rögzítheti. |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]