---
title: Szabadság- és távolléttípusok konfigurálása
description: Beállíthatja, hogy az alkalmazottak milyen típusú szabadságot vehetnek igénybe a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198050"
---
# <a name="configure-leave-and-absence-types"></a>Szabadság- és távolléttípusok konfigurálása

A Dynamics 365 Human Resources szabadságtípusai határozzák meg az alkalmazottak számára elérhető különböző típusú távolléteket. A szabadságtípusokat a szervezet igényeihez igazíthatja. Példák a szabadságtípusokra:

- Fizetett szabadság (PTO)
- Fizetés nélküli szabadság
- Fizetett szabadság
- Betegszabadság
- Betegszabadság
- Családi okokból történő
- Rövid távú fogyatékosság
- Haláleset miatti szabadság

## <a name="add-a-leave-type"></a>Szabadságtípus hozzáadása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás**területen válassza a **Szabadság- és távolléttípusok** lehetőséget.

3. Válassza az **Új** lehetőséget.

4. Írjon be a szabadságtípus nevét a **Típus** mezőbe, válasszon egy munkafolyamatot a **Munkafolyamat-azonosító** listáról, és adja meg a leírást a **Leírás** mezőben.

5. Az **Általános** lapon válassza ki a **Nincs**, az **Ütemezett** vagy a **Nem ütemezett** elemet a **Kategória** legördülő listáról.

6. Válasszon bevételkódot a **Bevételkód** legördülő listáról.

7. **Az okkódot meg kell adni** beállításnál válassza ki, hogy szeretné-e előírni az okkód megadását. Ha elő szeretné írni az okkódok használatát, akkor fel kell vennie ilyen kódokat. Az **Okkódok** területen válassza a **Hozzáadás** elemet, válasszon egy okkódot, és jelölje be a mellette található **Engedélyezve** jelölőnégyzetet.

8. A **Hozzáférés korlátozása a kijelölt szerepkörökre** beállításnál válassza ki, hogy szeretné-e korlátozni a hozzáférést. Ezután a **Szabadságtípus biztonsági szerepkörei** beállításnál válassza ki a biztonsági szerepköröket. A biztonsági szerepkörök a jelen eljárás korábbi pontján, a **Munkafolyamat-azonosító** beállításnál kiválasztott munkafolyamatban határozhatók meg.

9. Válassza a **Mentés** lehetőséget.

## <a name="configure-leave-type-rules"></a>A szabadságtípus-szabályok konfigurálása

1. Adja meg a szabadságtípus kerekítési beállításait. Választási lehetőségek: **Nincs**, **Fel**, **Le** és **Legközelebbi**. A szabadságtípus kerekítési pontosságát is megadhatja.

2. Adja meg a szabadságtípus **Munkaszünet-korrekció** beállítását. Ha bejelöli ezt a lehetőséget, akkor a Human Resources szolgáltatás a munkanapra eső napok száma alapján határozza meg, hogyan kell elszámolni a szabadságtípus távolléti idejét. Ha például karácsony napja hétfőre esik, akkor a Human Resources szolgáltatás levon egy napot a szabadságtípusból a könyvelés feldolgozásakor.

   A szabadnapokat a munkaidőnaptárban állíthatja be. További információ: [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md)
   
## <a name="configure-preview-features"></a>Előzetes funkciók konfigurálása

Ha engedélyezte a szabadság és a távollét előzetes funkcióit, akkor konfigurálnia kell azok beállításait.

[!include [banner](includes/preview-feature-leave-absence.md)]

1. Válassza ki a szabadságtípust, amelyhez az átviteli egyenlegek át lesznek irányítva. Az átvitelhez új szabadságtípust is létre lehet hozni. 

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
- [Szabadság- és távolléti terv létrehozása](hr-leave-and-absence-plans.md)
- [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md)
