---
title: Problémák elhárítása a kezdeti beállításkor
description: Ez a témakör olyan információkat tartalmaz, amelyek segítségével kijavíthatja azokat a problémákat, amelyek a kettős írásos integráció kezdeti beállításakor merülhetnek fel.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c9bf5d9017579b4207e09769cff38361442e3938
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781440"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Problémák elhárítása a kezdeti beállításkor

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Ez a témakör pontosabban olyan információkat tartalmaz, amelyek segítségével kijavíthatja azokat a problémákat, amelyek a kettős írásos integráció kezdeti beállításakor merülhetnek fel.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Egy Finance and Operations alkalmazás nem kapcsolható a Dataverse szolgáltatáshoz

**Szükséges szerepkör a Kettős írás beállításához:** Rendszergazda a Finance and Operations alkalmazásokban és Dataverse alkalmazásban.

A **Hivatkozás beállítása a Dataverse szolgáltatáshoz** oldal hibáit általában hiányos beállítás vagy jogosultsági problémák okozzák. Győződjön meg arról, hogy a teljes állapot-ellenőrzés megfelelt-e a **Hivatkozás beállítása a Dataverse szolgáltatáshoz** oldalon, az alábbi ábrán látható módon. A kettős írás nem kapcsolható össze, hacsak a teljes állapot-ellenőrzés meg nem felelt.

![Sikeres állapot-ellenőrzés.](media/health_check.png)

A Finance and Operations és Dataverse környezetek összekapcsolásához Azure AD bérlői rendszergazdai hitelesítő adatok szükségesek. A környezetek összekapcsolása után a felhasználók a saját fiókjaik hitelesítő adataival jelentkezhetnek be, és módosíthatják a meglévő táblák leképezését.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>A kettős íráshoz összekapcsolható táblák vagy vállalatok számához tartozó korlát megkeresése

A következő hibaüzenetek jelenhetnek meg a leképezések engedélyezésekor:

*Kettős írási hiba - Beépülő modul regisztrációs hiba: [(Partíciós térkép nem található a DWM projekthez -1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Hiba A DWM-leképezéshez a partíciók megengedett maximális száma túllépve -1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], Egy vagy több hiba történt.*

A környezetek összekapcsolásánál érvényes aktuális korlát körülbelül 40 jogi tábla. Ez a hiba akkor fordul elő, ha engedélyezi a leképezéseket, és több mint 40 jogi tábla kapcsolódik a környezethez.

## <a name="connection-set-failed-while-linking-environment"></a>A környezet összekapcsolása során a kapcsolat sikertelen volt

A kettős írási környezet összekapcsolása során a művelet hibaüzenettel sikertelenül végződik:

*A kapcsolatkészlet mentése sikertelen! Egy azonos kulcsú elem már hozzá lett adva.*

A kettős írásmód nem támogatja a több, azonos nevű jogi személyt/céget. Például, ha két „DAT” nevű vállalat van a Dataverse-ben, akkor ez a hibaüzenet jelenik meg.

Az ügyfél blokkolásának feloldásához távolítsa el a duplikált rekordokat a **cdm_company** táblából a Dataverse-ben. Továbbá, ha a **cdm_company** táblában üres nevű rekordok vannak, távolítsa el vagy javítsa ki ezeket a rekordokat.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Hiba a Dual-write oldal megnyitásakor a Finance and Operations alkalmazásokban

A következő hibaüzenetet kaphatja, amikor megpróbálja összekapcsolni a Dataverse környezetet a kettős íráshoz:

*A válasz állapotkódja sikertelenséget jelez: 404 (Nem található).*

Ez a hiba akkor jelentkezik, ha az alkalmazás jóváhagyásának lépése nem fejeződött be. A hozzájárulás megtörténtét a `portal.azure.com` oldalon a bérlő adminisztrátori fiókjával történő bejelentkezéssel tudja ellenőrizni, és ellenőrizheti, hogy a `33976c19-1db5-4c02-810e-c243db79efde` azonosítóval rendelkező harmadik féltől származó alkalmazás megjelenik-e az AAD Enterprise alkalmazások listájában. Ha nem, akkor a következő szakaszban leírtak szerint ismételje meg a beleegyezési lépést.

### <a name="providing-app-consent"></a>Alkalmazás hozzájárulásának megadása

+ Indítsa el a következő URL-címet az adminisztrátori hitelesítő adatokkal.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ A hozzájáruláshoz válassza az **Elfogadom** lehetőséget. Ön hozzájárulását adja az alkalmazás telepítéséhez (a `id=33976c19-1db5-4c02-810e-c243db79efde` oldalon) a bérlőjénél.
+ Ez az alkalmazás szükséges ahhoz, hogy a Dataverse kommunikálni tudjon a Finance and Operations alkalmazásokkal.

    ![Kezdeti szinkronizálási beállítási hibaelhárítás.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Ha ez nem működik, indítsa el az URL-t a Microsoft Edge privát módjában vagy a Chrome inkognitó módjában.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>A Finance and Operations környezet nem felderíthető

A következő hibaüzenetet kaphatja:

A *Finance and Operations apps környezet \*\*\*.cloudax.dynamics.com nem található.*

Két dolog okozhat problémát azzal, hogy a környezet nem ismerhető fel:

+ A bejelentkezéshez használt felhasználó nem ugyanabban a bérlőben van, mint a Finance and Operations példány.
+ Vannak olyan régi Finance and Operations példányok, amelyek Microsoft-hostingoltak, és amelyeknél probléma volt a felderítéssel. A hiba kijavításához frissítse a Finance and Operations példányt. A környezet minden frissítéssel felismerhetővé válik.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
