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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2241e7e6219f95115f55bc45a4d94550276e1e21
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683623"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>A(z) Finance and Operations alkalmazásokban lévő problémák elhárítása a kettős írás modullal

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások **kettős írás** modullal kapcsolatos problémái.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>A kettős írás modul nem tölthető be egy Finance and Operations-alkalmazásban

Ha nem tudja megnyitni a **Kettős írás** lapot a **Kettős írás** csempe kiválasztásával az **Adatkezelés** munkaterületen, az adatintegrációs szolgáltatás valószínűleg üzemen kívül van. Hozzon létre egy támogató jegyet az adatintegrációs szolgáltatás újraindításának kérelmezéséhez.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Hiba történt, amikor új táblaleképezést próbál létrehozni

**A hiba javításához szükséges hitelesítő adatok:** ugyanaz a felhasználó, aki a kettős írást telepítette.

Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor új entitást próbál konfigurálni a kettős íráshoz. A kettős írási kapcsolatot beállító felhasználó hozhatja csak létre a leképezést.

*A válasz állapotkódja sikertelenséget jelez: 401 (Nem engedélyezett)*


## <a name="error-when-you-open-the-dual-write-user-interface"></a>Hiba a kettős írás felhasználói felületének megnyitásakor

Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor megpróbálja elérni a kettős írást az **Adatkezelés** munkaterületről:

*login.microsoftonline.com elutasította a csatlakozást.*

A hiba elhárításához jelentkezzen be egy InPrivate-ablakon a Microsoft Edge-ben, rejtett ablakban Chromiumon, vagy rejtett ablakban a Google Chrome-ban. Ezenkívül fel kell oldania vagy törölni kell a külső féltől származó cookie-kat.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Hiba, amikor a környezetet összekapcsolja kettős íráshoz, vagy új táblaleképezést ad hozzá

**Szükséges szerepkör a hiba javításához:** Rendszergazda a Finance and Operations alkalmazásokban és Dataverse alkalmazásban.

A következő hiba merülhet fel összekapcsoláskor vagy leképezések létrehozásakor:

*A válasz állapotkódja sikertelenséget jelez: 403 (tokenexchange).<br> Munkamenet-azonosító: \<your session id\><br> Gyökérszintű tevékenységazonosító: \<your root activity id\>*

Ez a hiba akkor fordulhat elő, ha nincs megfelelő jogosultsága a kettős írás összekapcsolásához vagy a leképezések létrehozásához. Ez a hiba akkor is előfordulhat, ha a Dataverse-környezet alaphelyzetbe állítása a kettős írás csatolásának felbontása nélkül történt. Minden olyan felhasználó, aki rendszergazdai szerepkörrel rendelkezik a Finance and Operations alkalmazásokban és a Dataverse szolgáltatásban is, összekapcsolhatja a környezeteket. Csak a kettős írás kapcsolatot beállító felhasználó adhat hozzá új táblaleképezéseket. A telepítés után bármely rendszergazdai szerepkörrel rendelkező felhasználó nyomon követheti az állapotot, és szerkesztheti a leképezéseket.

## <a name="error-when-you-stop-the-table-mapping"></a>Hiba a táblaleképezés leállításakor

A következő hibaüzenetek jelenhetnek meg a táblaleképezések leállításakor:

*\[Tiltott\], \[{"status":403,"source":"","message":"Hiba a jogkivonat cseréjéből: A felhasználónak nincs engedélye a kapcsolathoz való hozzáféréshez dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.*

Ez a hiba akkor fordul elő, ha a csatolt Dataverse-környezet nem érhető el.

A hiba elhárításához hozzon létre egy jegyet az adatintegrációs csoporthoz. A hálózati nyomkövetést csatolja annak érdekében, hogy az adatintegrációs csoport megjelölje a leképezéseket a háttérben **nem futóként**.

## <a name="error-while-trying-to-start-an-table-mapping"></a>Hiba történt egy táblaleképezés indításának kísérlete közben

A következőhöz hasonlító hibaüzenet jelenhet meg, amikor a leképezés állapotát **Futás** értékre akarja állítani:

*A kezdeti adatszinkronizálás nem hajtható végre. Hiba: kettős írási hiba – a beépülő modul regiszrtálása nem sikerült: Nem sikerült a kettős írási keresési metaadat létrehozása. Hiba objektumreferenciája nincs beállítva egy objektum példányára.*

A hiba javítása a hiba okának függvénye:

+ Ha a leképezés függő leképezésekkel rendelkezik, akkor győződjön meg róla, hogy engedélyezi az táblaleképezés függő leképezését.
+ A leképezésből valószínűleg hiányzik a forrás- vagy célmezők. Ha hiányzik egy mező a Finance and Operations alkalmazásban, akkor kövesse a következő szakasz lépéseit: [Hiányzó entitásmezők problémája leképezésekben](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps). Ha hiányzik egy mező a Dataverse szolgáltatásból, kattintson a **Táblák frissítése** gombra a leképezésen, így a mezőket a rendszer automatikusan visszatölti a leképezésbe.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]