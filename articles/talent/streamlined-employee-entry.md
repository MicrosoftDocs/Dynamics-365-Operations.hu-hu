---
title: Korszerű alkalmazotti belépés és navigálás
description: A Dynamics 365 for Talent dolgozóira vonatkozó adatbevitel révén gyorsan be lehet vinni az adatokat minden egykori, aktív és jövőbeli dolgozó esetében. Frissítettük az egyszerűsített/összesített navigációs modellt, hogy gyorsan meg lehessen találni a keresett információkat, illetve végre lehessen hajtani a szükséges módosításokat.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: be0253ffc4396f36050ef02c51a20d378e44473d
ms.sourcegitcommit: 4176c333ce3f88c5c68e95bd47e5791d32365dd2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/22/2019
ms.locfileid: "1918203"
---
# <a name="streamlined-employee-entry-and-navigation"></a>Korszerű alkalmazotti belépés és navigálás

[!include [banner](includes/banner.md)]

A Dynamics 365 for Talent lehetővé teszi az alkalmazotti és foglalkoztatási adatok hatékony bevitelét. A múltbeli, aktív és jövőbeli alkalmazottak és alvállalkozók esetében gyorsan frissítheti a munkaelőzmények adatait.

Továbbá engedélyezhet egy egyszerűsített navigációs élményt is, hogy gyorsan megtalálhassa a kapcsolódó adatokat, és elvégezhesse a szükséges módosításokat. Ez a funkció jelenleg a sandbox környezetekben érhető el. A funkció bekapcsolásához navigáljon a **Rendszer-adminisztráció > Hivatkozások > Beállítás > Rendszerparaméterek > előnézeti funkciók** ponthoz. Válassza a **Továbbfejlesztett dolgozói képernyő és navigáció** lehetőséget. Ez minden felhasználó számára engedélyezi a változtatásokat. Ezt a beállítást bármikor ki lehet kapcsolni.

## <a name="view-options"></a>Nézet beállításai

A dolgozói képernyő **Nézetbeállításaival** kiválaszthatja az alkalmazottak és alvállalkozók tetszőleges kombinációját egyetlen listából. Ezen beállítások segítségével a jogi személyeknél vagy a jelenleg bejelentkezett jogi személynél nézheti meg a dolgozókat. Ezenkívül megtekintheti az aktív, függő és kilépett dolgozókat, és a dolgozó (alkalmazott vagy vállalkozó) típusától függően korlátozhatja a találatokat. Ha a speciális biztonság engedélyezve van, akkor csak azokat az alkalmazottakat és alvállalkozókat fogja látni, akik az Ön számára hozzáférhető jogi személynél találhatók.

A listanézet oszlopai az Ön választásai alapján változnak. A kilépett alkalmazottak megtekintésekor például a megszűnés dátuma és az okkódok a lista további oszlopaiként jelennek meg. 

[![Nézet beállításai](./media/Worker-view-option.png)](./media/worker-view-option.png)

## <a name="navigation-and-banner"></a>Navigáció és szalagcím

A szalagcímek az egyes dolgozókra vonatkozó alapvető információkat jelenítik meg. Az aktív dolgozók szalagcímei a következő mezőket jelenítik meg:

- **Beosztás**
- **Részleg**
- **Beosztás típusa**
- **Dolgozó típusa**
- **Vezető**
- **Jogi személy**

A távozó dolgozók szalagcímei a következő mezőket jelenítik meg:

- **Kilépés dátuma**
- **Jogcím**

A függőben lévő dolgozók szalagcímei a következő mezőket jelenítik meg:

- **Beosztás**
- **Részleg**
- **Beosztás típusa**
- **Vezető**
- **Kezdő dátum**
- **Jogi személy**

A dolgozói oldal műveleti ablakát átrendeztük, így kevesebb beállítás jelenik meg rajta. A rendszer mostantól a következő kategóriákba rendezi az adatokat: 

- Munka
- Személy
- Kilépés
- Kompenzáció
- Előnyök
- Megfelelés

Ezenkívül a fő dolgozói lap **Hivatkozások** lapján a felhasználók egy központi helyen férhetnek hozzá a kapcsolódó információkhoz egy dolgozóról.

A változtatások miatt előfordulhat, hogy az adatok más helyen jelennnek meg, mint eddig. Például a dolgozói képernyőn korábban megjelenő bérlista-adatok megjelennek a műveleti ablaktáblában a **Kompenzáció > Bérlista** pontnálmodulban, és a **Személyes adatok** lap mostantól tartalmazza a **További információk** gombot a nem gyakran megnyitott mezők elrejtéséhez.

[![Szalagcím](./media/Banner.png)](./media/Banner.png)

## <a name="work-history"></a>Munkaelőzmények

A **Munkaelőzmények** lapon láthatók a munkaelőzmények az összes jogi személyre vonatkozóan, és elérhetők a kilépett, az aktív és a függőben lévő alkalmazottakhoz és alvállalkozókhoz is. Mostantól bármikor megtekintheti az összes munkaelőzményt az Ön számára elérhető jogi személyeknél. Ezenkívül az egyes munkaelőzmények bejegyzéseivel kapcsolatos adatokat az adatkörnyezet módosítása nélkül is szerkesztheti. Az összes adatot közvetlenül a lapon frissítheti. 

[![Munkaelőzmények](./media/Worker-work-history.png)](./media/Worker-work-history.png)

## <a name="position-history"></a>Beosztások előzményei

A fő dolgozói lap **Beosztások** lapja teljes áttekintést nyújt a szervezeten belüli beosztásokról, beleértve a múltbeli, a jelenlegi és a jövőbeli hozzárendeléseket is. A műveletablakban továbbra is közvetlenül a dolgozó beosztásának előzményeihez lehet navigálni.

[![Beosztások](./media/Worker-position-history.png)](./media/Worker-position-history.png)

