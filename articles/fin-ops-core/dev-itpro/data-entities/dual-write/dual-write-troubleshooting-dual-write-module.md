---
title: A Finance and Operations alkalmazások kettős írással kapcsolatos problémáinak elhárítása
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak a Pénzügy és műveletek alkalmazások Kettős írású modulja hibáinak megoldásához.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 0696d525e985f1cfcac1998d4c0bd8a380ca9551
ms.sourcegitcommit: 7faf82fa7ce269c0201abb8473af861ef7ce00bf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2022
ms.locfileid: "8613882"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>A Finance and Operations alkalmazások kettős írással kapcsolatos problémáinak elhárítása

[!include [banner](../../includes/banner.md)]



Ez a témakör hibaelhárítási információkat tartalmaz a Pénzügy és művelet alkalmazások, illetve a Dataverse. Olyan információkat **tartalmaz**, amelyek segítségével kijavíthatja a problémákat a Pénzügy és műveletek alkalmazások Kettős írású modulja segítségével.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Nem lehet betölteni a kettős írású modult a Pénzügy és műveletek alkalmazásban.

Ha nem tudja megnyitni a **Kettős írás** lapot a **Kettős írás** csempe kiválasztásával az **Adatkezelés** munkaterületen, az adatintegrációs szolgáltatás valószínűleg üzemen kívül van. Hozzon létre egy támogató jegyet az adatintegrációs szolgáltatás újraindításának kérelmezéséhez.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Hiba történt, amikor új táblaleképezést próbál létrehozni

**A hiba javításához szükséges hitelesítő adatok:** ugyanaz a felhasználó, aki a kettős írást telepítette.

Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor új táblát próbál konfigurálni a kettős íráshoz. A kettős írási kapcsolatot beállító felhasználó hozhatja csak létre a leképezést.

*A válasz állapotkódja nem sikert jelez: 401 (Nem engedélyezett).*

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Hiba a kettős írás felhasználói felületének megnyitásakor

Előfordulhat, hogy a következő hibaüzenet jelenik meg, amikor megpróbálja elérni a kettős írást az **Adatkezelés** munkaterületről:

*login.microsoftonline.com elutasította a csatlakozást.*

A hiba elhárításához jelentkezzen be egy InPrivate-ablakon a Microsoft Edge-ben, rejtett ablakban Chromiumon, vagy rejtett ablakban a Google Chrome-ban. Ezenkívül fel kell oldania vagy törölni kell a külső féltől származó cookie-kat.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Hiba, amikor a környezetet összekapcsolja kettős íráshoz, vagy új táblaleképezést ad hozzá

**A probléma megoldásához szükséges szerepkör: a** rendszergazda a Pénzügy és a Műveletek alkalmazásokban és a Dataverse.

A következő hiba merülhet fel összekapcsoláskor vagy leképezések létrehozásakor:

```dos
Response status code does not indicate success: 403 (tokenexchange).
Session ID: \<your session id\>
Root activity ID: \<your root activity\> id
```

Ez a hiba akkor fordulhat elő, ha nincs megfelelő jogosultsága a kettős írás összekapcsolásához vagy a leképezések létrehozásához. Ez a hiba akkor is előfordulhat, ha a Dataverse-környezet alaphelyzetbe állítása a kettős írás csatolásának felbontása nélkül történt. Bármely felhasználó, aki rendszergazdai szerepkörrel van mind a Pénzügy, mind az Üzemeltetési Dataverse alkalmazásokban, és összekapcsolhatja a környezeteket. Csak a kettős írás kapcsolatot beállító felhasználó adhat hozzá új táblaleképezéseket. A telepítés után bármely rendszergazdai szerepkörrel rendelkező felhasználó nyomon követheti az állapotot, és szerkesztheti a leképezéseket.

## <a name="error-when-you-stop-the-table-mapping"></a>Hiba a táblaleképezés leállításakor

A következő hibaüzenetek jelenhetnek meg a táblaleképezések leállításakor:

*\[Tiltott\], \[{"status":403,"source":"","message":"Hiba a jogkivonat cseréjéből: A felhasználónak nincs engedélye a kapcsolathoz való hozzáféréshez dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.*

Ez a hiba akkor fordul elő, ha a csatolt Dataverse-környezet nem érhető el.

A hiba elhárításához hozzon létre egy jegyet az adatintegrációs csoporthoz. A hálózati nyomkövetést csatolja annak érdekében, hogy az adatintegrációs csoport megjelölje a leképezéseket a háttérben **nem futóként**.

## <a name="enable-parallel-processing-in-finance-and-operations-apps-to-improve-performance"></a>A párhuzamos feldolgozás engedélyezése a Pénzügy és a Műveletek alkalmazásokban a teljesítmény javítása érdekében

A párhuzamos feldolgozás engedélyezése csökkentheti a Dynamics 365 Microsoft Dataverse ügyfél-megállapodási alkalmazásokból és a Pénzügy és Műveletek alkalmazásokba történő adatimporthoz szükséges időt. 

Ha engedélyezni szeretné a párhuzamos feldolgozást a Pénzügy és a Műveletek alkalmazásokban, kövesse az alábbi lépéseket.

1. Jelentkezzen be a Pénzügy és műveleti környezetbe.
2. Ugrás az **Adatkezelési keretrendszer > paramétereihez**
3. Válassza ki az **entitásbeállításokat**, és válassza az Entitás-végrehajtási **paraméterek konfigurálása lehetőséget**.
4. A párhuzamos feldolgozás paramétereinek hozzáadása:
    - **Importálási küszöbérték rekordszáma** – a párhuzamos feldolgozás engedélyezése előtt teljesülnie kell a rekordoknak.
    - **Feladatszám importálása** – a párhuzamosan futtatott szálak (feladatok) száma.
5. Válassza a **Mentés** lehetőséget.


## <a name="errors-while-trying-to-start-a-table-mapping"></a>Hibák egy táblázat leképezésének elindítása közben

### <a name="unable-to-complete-initial-data-sync"></a>Nem sikerült befejezni a kezdeti adatszinkronizálást

Előfordulhat, hogy a következő hibaüzenetet kapja, amikor megpróbálja futtatni a kezdeti adatszinkronizálást:

*A kezdeti adatszinkronizálás nem hajtható végre. Hiba: kettős írási hiba – a beépülő modul regiszrtálása nem sikerült: Nem sikerült a kettős írási keresési metaadat létrehozása. Hiba objektumreferenciája nincs beállítva egy objektum példányára.*

Ha megpróbálja a leképezés állapotát **Futó** állapotra állítani, a következő hibaüzenetet kaphatja. A javítás a hiba okától függ:

+ Ha a leképezés függő leképezésekkel rendelkezik, akkor győződjön meg róla, hogy engedélyezi az táblaleképezés függő leképezését.
+ A leképezésből valószínűleg hiányzik a forrás- vagy céloszlopok. Ha hiányzik egy oszlop a Pénzügy és műveletek alkalmazásból, [kövesse a Hiányzó táblaoszlopok probléma a leképezések szakaszban található lépéseket](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Ha hiányzik egy oszlop a Dataverse szolgáltatásból, kattintson a **Táblák frissítése** gombra a leképezésen, így az oszlopokat a rendszer automatikusan visszatölti a leképezésbe.

### <a name="version-mismatch-error-and-upgrading-dual-write-solutions"></a>Verzióillesztési hiba és a dual-write megoldások frissítése

A következő hibaüzeneteket kaphatja, amikor megpróbálja futtatni a táblázat leképezéseit:

+ *Ügyfélcsoportok (msdyn_customergroups): Kettős írási hiba - Dynamics 365 for Sales megoldás 'Dynamics365Company' verzióeltérés. Verzió: '2.0.2.10' Kötelező verzió: '2.0.133'*
+ *Dynamics 365 for Sales megoldás 'Dynamics365FinanceExtended' verzióeltérés. Verzió: '1.0.0.0' Kötelező verzió: '2.0.227'*
+ *Dynamics 365 for Sales megoldás 'Dynamics365FinanceAndOperationsCommon' verzióeltérés. Verzió: '1.0.0.0' Kötelező verzió: '2.0.133'*
+ *Dynamics 365 for Sales megoldás 'CurrencyExchangeRates' verzióeltérés. Verzió: '1.0.0.0' Kötelező verzió: '2.0.133'*
+ *Dynamics 365 for Sales megoldás 'Dynamics365SupplyChainExtended' verzióeltérés. Verzió: '1.0.0.0' Kötelező verzió: '2.0.227'*

A problémák kijavításához frissítse a kettős írási megoldásokat a Dataverse-ben. Győződjön meg róla, hogy a legfrissebb megoldásra frissít, amely megfelel a kívánt megoldás verziójának.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
