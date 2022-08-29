---
title: Problémák elhárítása a kezdeti beállításkor
description: Ez a cikk olyan problémák megoldásához nyújt segítséget, amelyek a kettős írású integráció kezdeti beállítása során fordulnak elő.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d33fc6f4895b53f16cc6957a3a2fc6b1abe90a2f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289514"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Problémák elhárítása a kezdeti beállításkor

[!include [banner](../../includes/banner.md)]

Ez a témakör hibaelhárítási információkat tartalmaz a pénzügyek és a műveletalkalmazások, valamint a Dataverse. Ez a témakör pontosabban olyan információkat tartalmaz, amelyek segítségével kijavíthatja azokat a problémákat, amelyek a kettős írásos integráció kezdeti beállításakor merülhetnek fel.

> [!IMPORTANT]
> Az ebben a témakörben említett problémák egy része a rendszergazdai szerepkörhöz vagy a Microsoft Azure Active Directory (Azure AD) bérlői rendszergazdai hitelesítő adatokhoz lehet szükséges. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Pénzügyi alkalmazáshoz és műveletalkalmazáshoz nem csatolhatja. Dataverse

**A kettős írás beállításához szükséges szerepkör:** rendszergazda a pénzügyi és műveleti alkalmazásokban és a Dataverse.

A **Hivatkozás beállítása a Dataverse szolgáltatáshoz** oldal hibáit általában hiányos beállítás vagy jogosultsági problémák okozzák. Győződjön meg arról, hogy a teljes állapot-ellenőrzés megfelelt-e a **Hivatkozás beállítása a Dataverse szolgáltatáshoz** oldalon, az alábbi ábrán látható módon. A kettős írás nem kapcsolható össze, hacsak a teljes állapot-ellenőrzés meg nem felelt.

![Sikeres állapot-ellenőrzés.](media/health_check.png)

A pénzügyek, Azure AD műveletek és környezetek összekapcsolása érdekében bérlő-rendszergazdai hitelesítő adatokkal kell rendelkeznie Dataverse. A környezetek összekapcsolása után a felhasználók a saját fiókjaik hitelesítő adataival jelentkezhetnek be, és módosíthatják a meglévő táblák leképezését.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>A kettős íráshoz összekapcsolható táblák vagy vállalatok számához tartozó korlát megkeresése

A következő hibaüzenetek jelenhetnek meg a leképezések engedélyezésekor:

*Kettős írási hiba - Beépülő modul regisztrációs hiba: [(Partíciós térkép nem található a DWM projekthez -1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Hiba A DWM-leképezéshez a partíciók megengedett maximális száma túllépve -1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], Egy vagy több hiba történt.*

A környezetek összekapcsolásánál érvényes aktuális korlát körülbelül 40 jogi tábla. Ez a hiba akkor fordul elő, ha engedélyezi a leképezéseket, és több mint 40 jogi tábla kapcsolódik a környezethez.

## <a name="connection-set-failed-while-linking-environment"></a>A környezet összekapcsolása során a kapcsolat sikertelen volt

A kettős írási környezet összekapcsolása során a művelet hibaüzenettel sikertelenül végződik:

*A kapcsolatkészlet mentése sikertelen! Egy azonos kulcsú elem már hozzá lett adva.*

A kettős írásmód nem támogatja a több, azonos nevű jogi személyt/céget. Ha például két vállalat neve van a "DAT" Dataverse névvel, akkor ez a hibaüzenet jelenik meg.

Az ügyfél blokkolásának feloldásához távolítsa el a duplikált rekordokat a **cdm_company** táblából a Dataverse-ben. Továbbá, ha a **cdm_company** táblában üres nevű rekordok vannak, távolítsa el vagy javítsa ki ezeket a rekordokat.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Hiba történt a Kétírásos lap megnyitásakor a Pénzügyi és üzemeltetési alkalmazásokban

A következő hibaüzenetet kaphatja, amikor megpróbálja összekapcsolni a Dataverse környezetet a kettős íráshoz:

*A válasz állapotkódja sikertelenséget jelez: 404 (Nem található).*

Ez a hiba akkor jelentkezik, ha az alkalmazás jóváhagyásának lépése nem fejeződött be. A hozzájárulás megtörténtét a `portal.azure.com` oldalon a bérlő adminisztrátori fiókjával történő bejelentkezéssel tudja ellenőrizni, és ellenőrizheti, hogy a `33976c19-1db5-4c02-810e-c243db79efde` azonosítóval rendelkező harmadik féltől származó alkalmazás megjelenik-e az AAD Enterprise alkalmazások listájában. Ha nem, akkor a következő szakaszban leírtak szerint ismételje meg a beleegyezési lépést.

### <a name="providing-app-consent"></a>Alkalmazás hozzájárulásának megadása

+ Indítsa el a következő URL-címet az adminisztrátori hitelesítő adatokkal.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ A hozzájáruláshoz válassza az **Elfogadom** lehetőséget. Ön hozzájárulását adja az alkalmazás telepítéséhez (a `id=33976c19-1db5-4c02-810e-c243db79efde` oldalon) a bérlőjénél.
+ Ez az alkalmazás szükséges a pénzügyi Dataverse és műveleti alkalmazásokkal való kommunikációhoz.

    ![Kezdeti szinkronizálási beállítási hibaelhárítás.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Ha ez nem működik, indítsa el az URL-t a Microsoft Edge privát módjában vagy a Chrome inkognitó módjában.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>A pénzügyi és a műveleti környezet nem ismerhető fel.

A következő hibaüzenetet kaphatja:

*A Pénzügy és az Üzemeltetés alkalmazás környezete \*\*\* cloudax.dynamics.com nem ismerhető fel.*

Két dolog okozhat problémát azzal, hogy a környezet nem ismerhető fel:

+ A bejelentkezésre használt felhasználó nem ugyanaz a bérlő, mint a pénzügyi és műveleti példány.
+ Vannak olyan örökölt pénzügyek és műveletpéldányok, amelyek a Microsoft által működtetett környezetben voltak, és amelyekben probléma ad volt a észleléssel. A probléma megoldásáért frissítse a pénzügyi és a műveletpéldányt. A környezet minden frissítéssel felismerhetővé válik.

## <a name="403-forbidden-error-while-connections-are-being-created"></a>403 (Tiltott) hiba a kapcsolatok létrehozása közben

A kettős Power Apps írásos csatolási folyamat részeként a felhasználó nevében a kapcsolt környezetben két kapcsolat (*más néven Apihub-kapcsolat*) jön Dataverse létre. Ha az ügyfélnek nincs licence a Power Apps környezethez, akkor az ApiHub-kapcsolatok létrehozása sikertelen lesz, és 403 -as (tiltott) hiba jelenik meg. Megjelenik egy példa a hibaüzenetre:

> MSG=\[Nem sikerült beállítani két írási környezetet. Hiba részletei:A válaszállapot kódja nem jelzi sikeresnek: 403 (Tiltott). - A válaszállapot kódja nem mutatja sikeresnek: 403 (Tiltott).\] STACKTRACE=\[ – Microsoft.Dynamics.Integrator.ProjectManagementService.DualWrite.DualWriteConnectionSetProcessor.\<CreateDualWriteConnectionSetAsync\> d\_\_ 29.MoveNext() az X:\\ bt\\ 1158727\\ repo src\\\\ ProjectManagementService\\ DualWrite\\ DualWriteConnectionSetProcessor.cs:line 297 --- Veremkövetés vége egy korábbi helyről, ahonnan kivétel történt --- system.runtime.ExceptionServices.ExceptionDispatchInfo.Throw() at System.Runtime.CompilerServices.TaskButiter.HandleNonSuccessAndDebuggerNotification(Task task) at Microsoft.Dynamics.Integrator.ProjectManagementService.Controllers.DualWriteEnvironmentManagementController.\<SetupDualWriteEnvironmentAsync\> d\_\_ 34.MoveNext() az X:\\ bt\\ 1158727\\ repo\\ src\\ ProjectManagementService Controllers\\\\ DualWriteEnvironmentManagementController.cs:line 265\]

A hiba licenchiány miatt Power Apps fordul elő. Rendeljen a felhasználóhoz egy megfelelő licencet (Power Apps például 2. próbaterv), hogy a felhasználó engedélyt adjon a kapcsolatok létrehozására. A licenc ellenőrzéséhez a vevő a [Saját](https://portal.office.com/account/?ref=MeControl#subscriptions) fiók webhelyre használhatja a felhasználóhoz jelenleg hozzárendelt licenceket.

A licencekkel kapcsolatos további Power Apps tudnivalókat lásd a következő cikkekben:

- [Licencek hozzárendelése felhasználókhoz](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide)
- [Beszerzés Power Apps (saját szervezet)](/power-platform/admin/signup-for-powerapps-admin)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

