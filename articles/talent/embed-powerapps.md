---
title: PowerApps alkalmazások beágyazása a Dynamics 365 – Core HR alkalmazásban
description: Ez a témakör ismerteti annak a problémának a megoldását, amikor a PowerApps menüelem eltűnik a Rendszerfelügyeleti modulból.
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
ms.openlocfilehash: 4fbc24c5ceb73389b84b125eb942ac31757928aa
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008430"
---
# <a name="embed-powerapps-apps-in-core-hr"></a>PowerApps alkalmazások beágyazása a Core HR alkalmazásban

[!include [banner](includes/banner.md)]

**Kibocsátás**

A **PowerApps** menüelem eltűnt a **Rendszerfelügyelet** modulból.

**Ok**

A felhasználói felület (UI) elrendezése megváltozott, a Microsoft PowerApps most már szerepel a szabványos testreszabási modellben.

**Feloldás**

A PowerApps alkalmazások beágyazási módja megváltozott. A PowerApps alkalmazásokat most a testreszabási modellen keresztül lehet hozzáadni. Felvehet PowerApps alkalmazásokat a Microsoft Dynamics 365 Talent majdnem minden lapjára.

A PowerApps alkalmazások a Talent szolgáltatásban való beágyazásával kapcsolatos részletes tudnivalókat lásd: [A PowerApps alkalmazások beágyazása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Minden PowerApps-vevőnek, aki beágyazott alkalmazásokat a módosítás előtt, már frissülnie kellett az új modellre.

A **PowerApps** gomb a Talent szolgáltatás majdnem minden oldalán megtalálható a jobb felső sarokban. Ez a gomb segítségével beszúrhat egy PowerApps alkalmazást.

Íme, egy példa.

1. Lépjen a **Személyzetkezelés \> Hivatkozások \> Dolgozók \> Alkalmazottak** menüpontra.
2. Válassza ki a **PowerApps** gombot, majd válassza a **PowerApp beszúrása** lehetőséget.

    ![PowerApps gomb](media/png.png)

3. Töltse ki a mezőket a **PowerApp beszúrása** párbeszédpanelen.

    ![PowerApp beszúrása párbeszédablak](media/insert-powerapp.png)

A következő lépéseket is követheti.

1. Az oldal Művelet panelén a **Beállítások** lap **Személyre szabás** csoportjában válassza a **Képernyő személyre szabása** elemet.

    ![Csoport személyre szabása a Beállítások lapon](media/options.png)

    Megjelenik a személyre szabási eszköztár.

2. Az eszköztáron válassza a **Beszúrás \> PowerApp** lehetőséget.

    ![A PowerApps alkalmazás beszúrása a személyre szabási eszköztár segítségével](media/powerapp-bar.png)
