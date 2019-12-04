---
title: Power Apps alkalmazások beágyazása a Dynamics 365 – Core HR alkalmazásban
description: Ez a témakör ismerteti annak a problémának a megoldását, amikor a Microsoft Power Apps menüelem eltűnik a Rendszerfelügyeleti modulból.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6d1b7f1dd71e6bcbf10c4d91fe33e9494b041a2c
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830209"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a>Power Apps alkalmazások beágyazása a Dynamics 365 – Core HR alkalmazásban

[!include [banner](includes/banner.md)]

**Kibocsátás**

A **Power Apps** menüelem eltűnt a **Rendszerfelügyelet** modulból.

**Ok**

A felhasználói felület (UI) elrendezése megváltozott, a Microsoft Power Apps most már szerepel a szabványos testreszabási modellben.

**Feloldás**

A Power Apps beágyazási módja megváltozott. A Power Apps alkalmazást most a testreszabási modellen keresztül lehet hozzáadni. A Power Apps a Microsoft Dynamics 365 Talent majdnem minden lapjához hozzáadható.

További információ a Power Apps Talent szolgáltatásban történő beágyazásáról: [A Microsoft Power Apps beágyazása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Minden Power Apps-vevőnek, aki beágyazott alkalmazásokat a módosítás előtt, már frissülnie kellett az új modellre.

A **Power Apps** gomb a Talent szolgáltatás majdnem minden oldalán megtalálható a jobb felső sarokban. Ezzel a gombbal lehetséges a Power Apps beszúrása.

Íme, egy példa.

1. Lépjen a **Személyzetkezelés \> Hivatkozások \> Dolgozók \> Alkalmazottak** menüpontra.
2. Válassza ki a **Power Apps** gombot, majd válassza a **PowerApp beszúrása** lehetőséget.

    ![Power Apps gomb](media/png.png)

3. Töltse ki a mezőket a **PowerApp beszúrása** párbeszédpanelen.

    ![PowerApp beszúrása párbeszédablak](media/insert-powerapp.png)

A következő lépéseket is követheti.

1. Az oldal Művelet panelén a **Beállítások** lap **Személyre szabás** csoportjában válassza a **Képernyő személyre szabása** elemet.

    ![Csoport személyre szabása a Beállítások lapon](media/options.png)

    Megjelenik a személyre szabási eszköztár.

2. Az eszköztáron válassza a **Beszúrás \> PowerApp** lehetőséget.

    ![A Power Apps alkalmazás beszúrása a személyre szabási eszköztár segítségével](media/powerapp-bar.png)
