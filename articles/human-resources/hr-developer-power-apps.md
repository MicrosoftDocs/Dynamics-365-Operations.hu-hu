---
title: Talent bővítése a Power Apps és Power Automate szolgáltatásokkal
description: Ez a cikk néhány bővítési forgatókönyvet ír le a Microsoft Dynamics 365 Human Resources alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják.
author: negudava
manager: tfehr
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6885c67f42ead34b5e10cc1b1a80a88fd2d59b9
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115366"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Bővítés a Power Apps és a Power Automate szolgáltatással

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk néhány bővítési forgatókönyvet ír le a Microsoft Dynamics 365 Human Resources alkalmazáshoz, amelyek a Microsoft Power Apps és Microsoft Power Automate megoldásokat használják. Az egyes példákhoz társított megoldáscsomagot importálhatja a Power Apps környezetébe. Majd használhatja a csomagokat iránymutatásként vagy kiindulási pontként a szervezetre vonatkozó forgatókönyvek végrehajtásához.

> [!IMPORTANT]
> Ha a témakörben bemutatott sablonokat és alkalmazásokat „adott” állapotukban szeretné használni, ügyeljen arra, hogy tesztelje az összeset, és győződjön meg arról, hogy lefedik az Ön megvalósításához tartozó összes forgatókönyvet.

## <a name="prerequisites"></a>Előfeltételek

- Csomagok importálásához felhasználóknak rendelkezniük kell a **Környezetkészítő** engedéllyel.
- Az alkalmazások exportálásához vagy importálásához a felhasználóknak Power Apps Plan 2 licenccel, vagy Power Apps Plan 2 próbalicenccel kell rendelkezniük.

## <a name="integration-with-microsoft-365-power-automate"></a>Integráció a Microsoft 365 Power Automate szolgáltatással

Az **Integráció a Microsoft 365-tel** alkalmazás használható a csapatinformációk lekéréshez a bejelentkezett felhasználói számára a Microsoft 365-ből. A Human Resources szolgáltatásban található dolgozókra hivatkozik az alkalmazottazonosítók típusainak kiolvasásához. A vezetők ellenőrizhetik az alkalmazottazonosítók lejárati dátumát. Emlékeztetőt is küldhetnek e-mailben is, ha az alkalmazottazonosító típusa hamarosan lejár. Az emlékeztetőt a Power Automate és a Power Apps küldi együttműködve. A Power Automate visszaigazolást küld a Power Apps számára az emlékeztető elküldésekor. Az azonosítótípusok közé tartozik a jogosítvány, az útlevél és az azonosítók egyéb elfogadható formái.

Ez az alkalmazást egyéb esetekre is kiterjesztheti. Használhatja például a csapatok szabadságadatainak, a naptári események és a csapatok bármilyen eseményeinek megjelenítésére is.

Az **Integráció a Microsoft 365 és Power Automate-szolgáltatásokkal** alkalmazás letöltéséhez ugorjon az [Integráció a Microsoft 365 alkalmazással](https://go.microsoft.com/fwlink/?linkid=2081787) oldalra a Microsoft Letöltőközpontban.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – SQL csatlakozás és végrehajtás

A **Power Automate – SQL csatlakozás és végrehajtás** sablon csatlakozik a Microsoft SQL Server kiszolgálóhoz, és lehetővé teszi az SQL-lekérdezések futtatását.

Bár ez a sablon SQL-táblákat olvas be és frissít, kiterjesztheti azt, és más esetekhez is használhatja. Például használhatja a Dataverse szolgáltatásban az előkészítési táblák kitöltésére az SQL Serverről származó rekordokkal, és az előkészítési tábla rendszeres időközönkénti szinkronizálásához növekményes leküldéssel az SQL Server kiszolgálóról.

A Speciális lekérdezés szolgáltatás a Flow modullal integrálható az adatok átalakításának és a növekményes küldésének lehetővé tételéhez.

A **Power Automate – SQL csatlakozás és végrehajtás** sablon letöltéséhez nyissa meg a [Power Automate – SQL csatlakozás és végrehajtás](https://go.microsoft.com/fwlink/?linkid=2081789) elemet a Microsoft letöltőközpontban.

## <a name="additional-resources"></a>További erőforrások

[A Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>