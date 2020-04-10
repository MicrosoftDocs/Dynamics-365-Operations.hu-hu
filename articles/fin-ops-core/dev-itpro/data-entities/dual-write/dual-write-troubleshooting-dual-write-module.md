---
title: A(z) Finance and Operations alkalmazásokban lévő problémák elhárítása a kettős írás modullal
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások kettős írás modullal kapcsolatos problémái.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172760"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>A(z) Finance and Operations alkalmazásokban lévő problémák elhárítása a kettős írás modullal

[!include [banner](../../includes/banner.md)]



Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások **kettős írás** modullal kapcsolatos problémái.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>A kettős írás modul nem tölthető be egy Finance and Operations-alkalmazásban

Ha nem tudja megnyitni a **Kettős írás** lapot a **Kettős írás** csempe kiválasztásával az **Adatkezelés** munkaterületen, az adatintegrációs szolgáltatás valószínűleg üzemen kívül van. Hozzon létre egy támogató jegyet az adatintegrációs szolgáltatás újraindításának kérelmezéséhez.

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a>Hiba történt, amikor új entitásleképezést próbál létrehozni

**A hiba javításához szükséges hitelesítő adatok:** Azure AD bérlői rendszergazda

Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor új entitást próbál konfigurálni a kettős íráshoz:

*A válasz állapotkódja sikertelenséget jelez: 401 (Nem engedélyezett)*

Ez a hiba azért fordul elő, mert új entitásleképezést csak Azure AD bérlői rendszergazda adhat hozzá.

A hiba javításához jelentkezzen be a Finance and Operations alkalmazásba Azure AD rendszergazda bérlőként. El kell látogatnia a web.PowerApps.com oldalra is, és újra érvényesíteni a kapcsolatot.

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Hiba a kettős írás felhasználói felületének megnyitásakor

Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor megpróbálja elérni a kettős írást az **Adatkezelés** munkaterületről:

*login.microsoftonline.com elutasította a csatlakozást.*

A hiba elhárításához jelentkezzen be egy InPrivate-ablakon a Microsoft Edge-ben, rejtett ablakban Chromiumon, vagy rejtett ablakban a Google Chrome-ban. Ezenkívül fel kell oldania vagy törölni kell a külső féltől származó cookie-kat.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a>Hiba, amikor a környezetet összekapcsolja kettős íráshoz, vagy új entitásleképezést ad hozzá

**A hiba javításához szükséges hitelesítő adatok:** Azure AD bérlői rendszergazda

A következő hiba merülhet fel összekapcsoláskor vagy leképezések létrehozásakor:

*A válasz állapotkódja sikertelenséget jelez: 403 (tokenexchange).<br> Munkamenet-azonosító: \<az Ön munkamenet-azonosítója\><br> Gyökérszintű tevékenységazonosító: \<az Ön gyökérszintű tevékenységazonosítója\>*

Ez a hiba akkor fordulhat elő, ha nincs megfelelő jogosultsága a kettős írás összekapcsolásához vagy a leképezések létrehozásához. A környezetek csatolásához és az új entitás-hozzárendelések hozzáadásához egy Azure AD bérlői rendszergazdai fiókot kell használnia. A telepítés után azonban nem rendszergazdai fiókkal lehet ellenőrizni az állapotot, és szerkesztheti a leképezéseket.

## <a name="error-when-you-stop-the-entity-mapping"></a>Hiba az entitásleképezés leállításakor

A következő hibaüzenetek jelenhetnek meg az entitásleképezések leállításakor:

*\[Tiltott\], \[{"status":403,"source":"","message":"Hiba a jogkivonat cseréjéből: A felhasználónak nincs engedélye a kapcsolathoz való hozzáféréshez dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.*

Ez a hiba akkor fordul elő, ha a csatolt Common Data Service-környezet nem érhető el.

A hiba elhárításához hozzon létre egy jegyet az adatintegrációs csoporthoz. A hálózati nyomkövetést csatolja annak érdekében, hogy az adatintegrációs csoport megjelölje a leképezéseket a háttérben **nem futóként**.
