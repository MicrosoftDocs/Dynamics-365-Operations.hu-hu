---
title: Broadbean integráció engedélyezése a Microsoft Dynamics 365 Talent - Attract megoldásban
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Talent - Attract megoldást konfigurálni állások közzétételére külső állásportálokon, például a Broadean portálon.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
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
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 808f91fb4b68ba9b5cee54d86423d23232df23a4
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008593"
---
# <a name="enable-broadbean-integration"></a>Broadbean integráció engedélyezése

[!include[banner](../includes/banner.md)]

A nyitott pozíciókat elehető legjobb alkalmas jelölt számára szeretné eljuttatni. A toborzási oldalak, például a Broadbean segítenek elérni ezt a célt. A Microsoft Dynamics 365 Talent: Attract lehetővé teszi, hogy állásokat tegyen közzé a Broadbean oldalon, és a Microsoft folyamatosan új ajánlatokat biztosít majd ezen a területen.

> [!NOTE]
> - Állások közzétételéhez külső webhelyeken rendelkeznie kell az [Átfogó felvételi bővítménnyel](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Az állásoknak a Broadbean felületére az Attract szolgáltatáson keresztül történő feladásához Broadbean előfizetés szükséges.
> - Ez a funkció jelenleg előnézetben van. Ha ki szeretné próbálni, akkor [be kell kapcsolnia az Attract rendszergazdai beállításai között](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

## <a name="configure-broadbean-integration"></a>Broadbean integráció konfigurálása

1. Jelentkezzen be Attract alkalmazásba rendszergazdaként

2. Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum) a lap jobb felső sarkában, majd válassza a **Felügyeleti központ** lehetőséget.

3. Forduljon a Broadbean-hoz, és adja meg az adatokat a **Felhasználónév**, **Ügyfélazonosító**, **Titkosítási Token** elemekhez.

4. Válassza a **Mentés** lehetőséget.

> [!WARNING]
> A Broadbean hitelesítő adatai kényes és bizalmas természetűek. Ezért átgondoltan ossza meg azokat. Mindenki akinek rendszergazdai szerepköre van az Attract megoldásban megtekintheti ezeket a hitelesítő adatokat.

> [!NOTE]
> A Microsoft és Attract vesz nem részt ezen értékek létrehozásában és kezelésében. Az Ön felelőssége naprakészen tartani azokat az Attract megoldásban, illetve az, hogy együttműködjön a Broadbeannel, hogy megoldja a hitelesítési adatokkal kapcsolatos esetleges problémákat.
