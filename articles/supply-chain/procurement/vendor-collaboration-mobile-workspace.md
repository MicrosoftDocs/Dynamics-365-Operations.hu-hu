---
title: Szállítói együttműködési mobil munkaterület
description: Ez a cikk a Szállítói együttműködési mobileszköz munkaterületével kapcsolatban tartalmaz tájékoztatást. A munkaterület segítséget nyújt a szállítóinak a nekik jóváhagyásra elküldött beszerzési rendelések naprakészen tartásában. Emellett az új és módosított beszerzési rendelések és a kapcsolattartók adatait is megtekinthetik.
author: GalynaFedorova
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: gfedorova
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 75c044d1133e1c4765cd97f4ab7e2a08ba998c35
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112150"
---
# <a name="vendor-collaboration-mobile-workspace"></a>Szállítói együttműködési mobil munkaterület

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Ez a cikk a Szállítói együttműködési mobileszköz **munkaterületével kapcsolatban** tartalmaz tájékoztatást. A munkaterület segítséget nyújt a szállítóinak a nekik jóváhagyásra elküldött beszerzési rendelések naprakészen tartásában. Emellett az új és módosított beszerzési rendelések és a kapcsolattartók adatait is megtekinthetik.

Ez a mobil munkaterület a Pénzügy és műveletek (Dynamics 365) mobilalkalmazással való használatra szolgál.

## <a name="overview"></a>Áttekintés 
A **Szállítói együttműködési** mobil munkaterület folyamatosan tájékoztatja a szállítókat az új beszerzési rendelésekről, hogy láthassák és válaszolhassanak a beszerzési rendelésekre a webes kliensnél. 

>[!NOTE]
> A mobil munkaterületet a szállító együttműködési webes felületének kiegészítéseként kell felhasználni, de nem helyettesíti azt. 

A **Szállító együttműködés** mobil munkaterülettel szállítói megtekinthetik az új beszerzési rendeléseket, amelyeket nekik jóváhagyásra beküldtek. Megjeleníti a megrendelési információkat, például a termékeket, a mennyiségeket és a kért szállítási határidőket. Az árakra vonatkozó adatok is rendelkezésre állnak, az egyes szállítók konfigurációjától függően. 

Amikor egy felhasználó szállítóként jelentkezik be, látni fogja, hogy mely beszerzési rendelésekre válaszoltak, illetve hogy mely beszerzési rendelések várnak még vevői műveletre. Például megtörténhet, hogy a szállító esetleg másik szállítási határidőt javasolt, amelyről még nem egyezett meg az ügyféllel, így a beszerzési rendelés ügyfélműveletre vár. A szállító megtekintheti a jóváhagyott, de még nem kiszállított beszerzési rendelések listáját is. 

A beszerzési rendelésre válaszolva a szállítónak a webes ügyfélen elérhető szállítói együttműködési webes felületet kell használnia. Itt a szállító még több információt kaphat a rendelésről, például a dokumentummellékletekről, a soronkénti kézbesítési címről és a szállítóval kapcsolatos díjakról. 

Egy különleges biztonsági funkcióval a szállítók meg tudják nézni, hogy melyik kapcsolattartók vannak bejegyezve egy-egy szállítói fióknál. Ugyanezzel a biztonsági szerepkörrel a szállító megtekintheti a benyújtott felhasználói kérelmek állapotát. 

A webes ügyfélen levő szállítói együttműködési webhelyet kell használni az új kapcsolattartók létrehozásához és az új felhasználói kérelmek elküldéséhez. 

A **Szállítói együttműködés** mobil munkaterület lehetővé teszi egy szállító számára a következő műveletek elvégzését:

-   A szállítónak küldött új beszerzési rendelések megtekintése.
-   Megtekintheti azokat a beszerzési rendeléseket, amelyekre a szállító válaszolt, és amelyek vevői műveletre várnak.
-   A jóváhagyott állapotú, de nem teljes mértékben leszállított beszerzési rendelések megtekintése.
-   A szállítói számlához regisztrált kapcsolattartó adatainak megtekintése. (A feladathoz egy további biztonsági szerepkör szükséges.)
-   Információkat tekinthet meg egy, a szállító által benyújtott felhasználói kérelemről és követheti a kérelem állapotát. (A feladathoz egy további biztonsági szerepkör szükséges.)

## <a name="prerequisites"></a>Előfeltételek
Az előfeltételek eltérnek a Microsoft Dynamics 365 szervezeténél megvalósított verziója szerint.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Előfeltételek a Supply Chain Management használatakor
Amennyiben szervezete telepítette a Supply Chain Management rendszert, a rendszergazdának közzé kell tennie az **Szállítói együttműködés** mobil munkaterületet. Utasításokért lásd: [Mobil munkaterület közzététele](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Előfeltételek a Microsoft Dynamics 365 for Operations 1611-es verzió és Platform update 3 vagy újabb használatakor
Amennyiben szervezete telepítette a Microsoft Dynamics 365 for Operations 1611-es verziójánnak 3. vagy újabb Platformfrissítését, a rendszergazdának végre kell hajtania a következő előfeltételeket. 

<table>
<thead>
<tr class="header">
<th>Előfeltételek</th>
<th>Szerep</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>A KB 3216943 programot végre kell hajtani a 3. platformfrissítés használatakor.</td>
<td>Rendszergazda</td>
<td>A KB 3216943 egy bináris frissítés, amely a 3. platformfrissítés használata esetén szükséges. A KB végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.
<ol>
<li>Töltse le a KB 3216943 csomagot a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.</li>
<li>Telepítse a bináris frissítést, amely telepíthető csomagként jelenik meg. A telepíthető csomag alkalmazásával kapcsolatos tudnivalókat lásd: <a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Telepíthető csomag alkalmazása</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>A KB 4013633 végrehajtása kötelező.</td>
<td>Rendszergazda</td>
<td>A KB 4013633 egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza az <strong>Aktuális készlet</strong> mobil munkaterületet. A KB 4013633 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">A metaadatok gyorsjavítás letöltése az LCS-ről</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Telepítse a metaadatok gyorsjavítását</a>.</li><li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza a <strong>SCMMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Alkalmazza telepíthető csomagot</a>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>A <strong>Szállítói együttműködés</strong> munkaterületet közzé kell tenni.</td><td>Rendszergazda</td>
<td>Lásd: <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Mobil munkaterület közzététele</a>.</td>
</tr>
<tr class="even">
<td>A szállítói felhasználónak hozzáférést kell biztosítania a szállítói együttműködési webes felületéhez a webes ügyfélen, és létre kell hoznia egy szállítói együttműködő felhasználót.</td><td>Beszerzési szakértők és a rendszergazda</td>
<td>Kövesse az alábbi cikkek lépéseit a szállítói együttműködési webes felület beállításának és a velük való együttműködésnek érdekében.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">A külső szállítókkal történő szállítói együttműködés használata</a></li>
<li><a href="manage-vendor-collaboration-users.md">Szállítói együttműködés felhasználóinak kezelése</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Szállítói együttműködés beállítása és karbantartása</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Supply Chain Management rendszerben?</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>A mobilalkalmazás letöltése és telepítése

Töltse le és telepítse a Pénzügy és műveletek (Dynamics 365) mobilalkalmazást:

-   [Android telefonok esetében:](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhone esetében:](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Bejelentkezés a mobilalkalmazásba
1.  Indítsa el az alkalmazást a mobileszközén.
2.  Adja meg a Microsoft Dynamics 365 URL-címét.
4.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.
5.  A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.

    [![Frissítés húzással.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="use-the-vendor-collaboration-mobile-workspace"></a>Szállítói együttműködési mobil munkaterület használata
Ha bejelöli a **Szállítói együttműködés** munkaterületet, megjelennek a következő lehetőségek.

![Szállítói együttműködési mobil munkaterület.](./media/vendor-collaboration-mobile-app.png)

A **Szállítói együttműködési** munkaterület a következő lapokat tartalmazza.

### <a name="contacts"></a>Kapcsolattartók
A **Kapcsolattartók** lapon megtekintheti mindazokat a kapcsolattartókat, akiket beállított a szállítói számlához. Megjeleníti a kapcsolattartó személy nevét, az elsődleges e-mail-címét és felhasználói aliasát, ha a kapcsolattartó személynek van aliasa. A lap azt is megjeleníti, hogy a kapcsolattartó személy felhasználói fiókja aktív-e. Amikor kiválaszt egy kapcsolattartót, láthatja a kapcsolattartási adatokat, például azokat a jogi személyeket, akik esetében ez a felhasználó a kapcsolattartó. Láthatja a kapcsolattartási információkat is, például egy telefonszámot vagy egy másodlagos e-mail-címet.

### <a name="user-requests"></a>Felhasználókérések
A **Felhasználói kérelmek** lap segítségével megtekintheti azokat a felhasználói kérelmeket, amelyeket a szállítói együttműködés webes felületén keresztül nyújtott be. Nyomon követheti ezen kérelmek állapotát is. Amikor kiválaszt egy felhasználói kérelmet, akkor megtekintheti, hogy mit is kért, hozzáadhat vagy inaktívvá tehet egy felhasználót, módosíthatja a biztonságot, illetve megtekintheti, hogy mely biztonsági szerepköröket kértek a felhasználónak.

### <a name="purchase-orders-ready-for-review"></a>Beszerzési rendelések, melyek készen állnak ellenőrzésre
Az **Ellenőrzésre kész beszerzési rendelések** lapon megtekintheti a vevő által beküldött, de még meg nem válaszolt összes megrendelést. Megtekintheti a kijelölt adatokat a rendelésről, így például azt is, hogy mely termékeket kértek, és hogy mikor kell ezeket kiszállítani. Az árakra vonatkozó adatok is rendelkezésre állnak, a szállító konfigurációjától függően.

Megnézheti azt is, hogy a beszerzési rendeléshez tartoznak-e a megjegyzések és mellékletek. A jegyzetek és mellékletek megnyitásához azonban a webes ügyfél szállítói együttműködési webhelyét kell használnia. Válassza ki a **Beszerzési rendeléssor** lehetőséget a sorok részletekkel együtt való megjelenítéséhez. Vegye figyelembe, hogy minden egyes sor esetében egy jelző mutatja, hogy vannak-e jegyzetek vagy mellékletek, illetve hogy van-e olyan szállítási cím, amely eltér a fejlécben megjelenő címtől.

A beszerzési rendelés megválaszolásához a szállítói együttműködési webes felületet kell használnia a webes ügyfélen.

### <a name="awaiting-customer-action"></a>Várakozás vevői műveletre
A **Várakozás vevői műveletre** lap segítségével megtalálhatja azokat a beszerzési rendeléseket, amelyekre Ön vagy valaki más a vállalatánál, aki szintén hozzáfér a szállítói együttműködésekhez, válaszolt. A beszerzési rendelések csak akkor láthatók ebben a listában, ha a vevőnek végre kell hajtania az alábbi műveletek egyikét a beszerzési rendelésnél:

-   Ha a beszerzési rendelést elutasították, a vevőnek vagy frissítenie kell az eredeti rendelést, majd újra el kell küldenie, vagy törölnie kell a rendelést. A beszerzési rendelés az újbóli elküldést követően eltűnik a **Várakozás vevői műveletre** lapról.
-   Ha a beszerzési rendelést változtatásokkal fogadták el, a vevőnek vagy frissítenie kell az eredeti rendelést, majd újra el kell küldenie véleményezésre, vagy frissítheti a módosítások szerint, majd erősítse meg azonnal. A beszerzési rendelés mindkét esetben eltűnik a **Várakozás vevői műveletre** lapról.
-   Ha a beszerzési rendelést elfogadták, de még mindig megjelenik a **Várakozás vevői műveletre** lapon, ez azért van, mert a beszerzési rendelést az elfogadás befejezésekor nem erősítették meg automatikusan. Most arra vár, hogy egy beszerzési képviselő **Megerősítve** állapotra állítsa. A beszerzési rendelés általában a vevő és a szállító között létrejött megállapodásnak tekinthető, amint a szállító elfogadja a rendelést. Emiatt a **Megerősítve** állapotra történő frissítés általában csak formalitás.

Ha kiválaszt egy beszerzési rendelést, további részletek jelennek meg a válasszal kapcsolatban. Megtekintheti a sor részleteit és a választ minden sorra vonatkozóan. A sor állapota azt mutatja meg, hogy a következő válaszok közül melyiket adták:

-   Elfogadva
-   Elutasítva
-   Elfogadva módosításokkal
-   Helyettesített/helyettesítő
-   Felosztás ütemezésbe/Ütemezéssor

Vegye figyelembe, hogy a **Kézbesítés** mező értéke **Igen** vagy **Nem** annak megadása érdekében, hogy a sorokat kell-e szállítani. Megtörténhet, hogy a sor kiszállítása a következő okok miatt nem lehetséges:

- A sort elutasították.
- Helyettesítést hajtottak végre, és az eredeti sort nem kell szállítani, amint az a beérkezett rendelésben megjelent.
- A sort többsoros ütemezés sorra osztották fel, és az eredeti sort várhatóan nem kell szállítani, amint az a beérkezett rendelésben megjelent.

A rendelési soron végrehajtott összes módosítás megjelenik. A feltöltött jegyzetek és mellékletek azonban nem jelennek meg. A jegyzetek és mellékletek megnyitásához a webes ügyfél szállítói együttműködési webhelyét kell használnia.

### <a name="open-confirmed-orders"></a>Visszaigazolt rendelések megnyitása
Amikor a beszerzési rendelést megerősíti a vevő (ami azt jelenti, hogy a beszerzési rendelés **Megerősített** állapotra vált), megjelenik a nyitott és megerősített rendelésben. Mindaddig, amíg nincs regisztrálva fogadottként a vevő által, a listában marad.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

