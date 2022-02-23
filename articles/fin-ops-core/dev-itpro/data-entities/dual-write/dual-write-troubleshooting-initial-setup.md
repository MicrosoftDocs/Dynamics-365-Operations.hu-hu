---
title: Problémák elhárítása a kezdeti beállításkor
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével kijavíthatja azokat a problémákat, amelyek a Finance and Operations-alkalmazások és a Dataverse közötti kettős írásos integráció kezdeti beállításakor merülhetnek fel.
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
ms.openlocfilehash: 5ac6ec5003794fb5875fed6a2c4403c1444ab8b2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685586"
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

![Sikeres állapot-ellenőrzés](media/health_check.png)

A Finance and Operations és Dataverse környezetek összekapcsolásához Azure AD bérlői rendszergazdai hitelesítő adatok szükségesek. A környezetek összekapcsolása után a felhasználók a saját fiókjaik hitelesítő adataival jelentkezhetnek be, és módosíthatják a meglévő táblák leképezését.

## <a name="error-when-you-open-the-link-to-dataverse-page"></a>Hiba a Hivatkozás a Dataverse szolgáltatáshoz lap megnyitásakor

**A hiba javításához szükséges hitelesítő adatok:** Azure AD bérlői rendszergazda

A következő hibaüzenet jelenhet meg a **Hivatkozás a Dataverse szolgáltatáshoz** oldal megnyitásakor egy Finance and Operations alkalmazásban:

*A válasz állapotkódja sikertelenséget jelez: 404 (Nem található).*

Ez a hiba akkor fordul elő, ha a hozzájárulási lépést nem hajtották végre. A hozzájárulási lépés végrehajtásának ellenőrzéséhez jelentkezzen be a portal.Azure.com oldalra az Azure AD bérlői rendszergazdai fiókkal, és megtekintheti, hogy a **33976c19-1db5-4c02-810e-c243db79efde** azonosítóval rendelkező külső alkalmazás megjelenik-e az Azure AD **Vállalati alkalmazások** listájában. Ha nem, akkor meg kell adnia az alkalmazás hozzájárulását.

Az alkalmazás-hozzájárulás biztosításához kövesse az alábbi lépéseket.

1. Nyissa meg a következő URL-címet a rendszergazdai jogosultságok segítségével. Meg kell adni a jóváhagyást.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. Válassza az **Elfogadás** lehetőséget, ha hozzájárulását szeretné adni az **33976c19-1db5-4c02-810e-c243db79efde** azonosítóval rendlekező alkalmazás telepítésére az Ön bérlőjébe.

    > [!TIP]
    > Ez az alkalmazás szükséges a Dataverse és a Finance and Operations alkalmazások összekapcsolásához. Ha baj van ezzel a lépéssel, akkor nyissa meg a böngészőprogramot rejtett módban (a Google Chrome-ban) vagy az InPrivate-módban (a Microsoft Edge-ben).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>Győződjön meg arról, hogy a vállalati adatokat és a kettős írású csapatokat az összekapcsolás során helyesen állították be

A kettős írás helyes működésének biztosítása érdekében a konfiguráció során kiválasztott vállalatok a Dataverse-környezetben jönnek létre. Alapértelmezés szerint ezek a vállalatok csak olvashatók, az **IsDualWriteEnable** tulajdonság pedig **igaz** értékre van állítva. Ezenkívül létrejön az alapértelmezett részleg tulajdonosa és csoportja, amely tartalmazza a vállalat nevét. A leképezések engedélyezése előtt győződjön meg róla, hogy a csoport alapértelmezett tulajdonosa meg van adva. A **Vállalatok (CDM\_vállalat)** entitás megkereséséhez kövesse az alábbi lépéseket.

1. A Dynamics 365 modellvezérelt alkalmazásában válassza ki a szűrőt a jobb felső sarokban.
2. A legördülő listán válassza a **Vállalat** elemet.
3. Az eredmények megtekintéséhez válassza a **Futtatás** parancsot.
4. Válassza ki azt a vállalatot, amely a kettős írás konfigurálása során összekapcsolódott.
5. Győződjön meg arról, hogy az **Alapértelmezett tulajdonos csoport** mezőben szerepel érték. A következő ábrán az **Alapértelmezett tulajdonos csoport** mező értéke **USMF kettős írás**.

    ![Az alapértelmezett tulajdonos csoport ellenőrzése](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>A kettős íráshoz összekapcsolható táblák vagy vállalatok számához tartozó korlát megkeresése

A következő hibaüzenetek jelenhetnek meg a leképezések engedélyezésekor:

*Kettős írási hiba - A beépülő modul regisztrációja sikertelen: \[(Nem sikerült a projekt DWM partícióleképezésének lekérése-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Hiba: Túllépte a DWM-leképezések maxiálisan megengedett partícióinak számár-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], Egy vagy több hiba történt.*

A környezetek összekapcsolásánál érvényes aktuális korlát körülbelül 40 jogi tábla. Ez a hiba akkor fordul elő, ha engedélyezi a leképezéseket, és több mint 40 jogi tábla kapcsolódik a környezethez.
