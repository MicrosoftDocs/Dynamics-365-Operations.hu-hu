---
title: Jelöltek forrásainak nyomon követése az Attract szolgáltatásban
description: Ez a témakör a jelölt profilok jelentkezések forráskövetésével kapcsolatban tartalmaz tájékoztatást.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8860f508eebc377042c4e101eeb08a14a737ba0c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461387"
---
# <a name="track-candidate-sources-in-attract"></a>Jelöltek forrásainak nyomon követése az Attract szolgáltatásban

[!include [banner](includes/banner.md)]

> [!NOTE] 
> A témakörben megjegyzett funkciók rendelkezésére állnak egy előzetes kiadás részeként. A tartalom és a funkciók megváltozhatnak. Ez a funkció használatához kérje meg a rendszergazdát az engedélyezésére az **Adminisztratív beállításokban** az Attract megoldásban. Egy későbbi verzió forráskövetési jelentéseket is kínál majd. További tudnivalókért lásd: [Talent – előnézeti funkciók elérése](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

Amikor a pályázók egy állásra jelentkeznek, az Attract automatikusan nyomon követi a pályázatok forrását így értékes információkat nyújt a toborzás célzásához. A toborzók és felvételi vezető kiválaszthatják egy jelentkezés forrását amikor manuálisan hozzáadnak egy jelentkezőt egy álláshoz vagy tehetségállományhoz.

A pályázat forrását a pályázati tevékenység részleteiben tekintheti meg a **Tevékenység** lapon, valamint a pályázati előzmények is elérhetők a **Profil** alatt a tehetségállományokban. A jelentkező profiljának forrását a jelentkező adatainál találja a **Profil** lapon jelentkezésekben és a tehetségállományokban is.

> [!NOTE] 
> A folyamatsablonokat az [Átfogó felvételi bővítményben](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) találja.

## <a name="pre-configured-sources"></a>Előre konfigurált források

Az alapértelmezett forráslista gyakori pályázatforrásokat tartalmaz. Bizonyos forrástípusok pl **Hirdetőfelület** és **Közösségi hálózat** további adatokat tartalmaznak. Péládul a **Közösségi hálózat** tartalmazza Facebook és Twitter oldalakat. Az **Ajánlás** forrástípus lehetővé teszi egy belső alkalmazott megadását ajánlóként. Az alapértelmezett forráslista a következő előre beállított forrásokat tartalmazza:

-   Attract karrierwebhely

-   Iroda

-   Állásbörze

-   Vállalati marketing

-   Konferenciák és kereskedelmi bemutatók

-   Szakmai egyesület

-   Hirdetőfelület

    -   Indeed

    -   Seek

    -   CareerBuilder

    -   Google Jobs

    -   Xing

    -   Glassdoor

    -   Monster Jobs

-   Magazinok és kiadványok

-   Közösségi hálózat

    -   Facebook

    -   Twitter

-   Egyetem toborzás

-   LinkedIn

-   Apróhirdetések

-   Javaslat

-   Toborzó által hozzáadva

-   Egyéb

## <a name="customize-the-source-list"></a>Forráslista testreszabása 

Az további jelentkezési források is szerepeltethetők a forráslistában. Ez a lista testreszabásához kövesse [Beállításkészletek kiterjesztése az Attract alkalmazásban](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract) utasításait. Szerkessze a **TalentSource** entitást további források felvételéhez. 

A felhasználói felület negatív befolyásolása elkerülésére nem szerkessze vagy törölje a **TalentCategory** enumerációs értékeket (nem nevek) a következőkhöz:

- **Javaslat**
- **LinkedIn**
- **Egyéb**

Ehelyett bővítheti a **TalentSource** enumeárciós értékeket más típusú adatforrások hozzáadásával.


[!INCLUDE[footer-include](../includes/footer-banner.md)]