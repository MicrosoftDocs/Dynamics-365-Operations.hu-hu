---
title: "Szállítói együttműködés mobil munkaterület a Microsoft Dynamics 365 for Operations alkalmazás számára"
description: "A szállítói együttműködési mobil munkaterületével a szállítók naprakészek maradhatnak a jóváhagyásra küldött megrendelésekre vonatkozóan, és megtekinthetik az új és frissített beszerzési rendelésekről és kapcsolattartókról szóló információkat."
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: mkirknel
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d5157e6f4b10b6158aa08279a9f68dae676f5666
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Szállítói együttműködés mobil munkaterület a Microsoft Dynamics 365 for Operations alkalmazás számára

[!include[banner](../includes/banner.md)]


A szállítói együttműködési mobil munkaterületével a szállítók naprakészek maradhatnak a jóváhagyásra küldött megrendelésekre vonatkozóan, és megtekinthetik az új és frissített beszerzési rendelésekről és kapcsolattartókról szóló információkat.

<a name="prerequisites"></a>Előfeltételek
-------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Előfeltételek</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tudnivalók a Microsoft Dynamics 365 for Operations mobilplatformról</td>
<td><a href="https://ax.help.dynamics.com/en/wiki/mobile-development-handbook/">Dynamics 365 for Operations mobilplatform</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 for Operations</td>
<td>Győződjön meg arról, hogy olyan környezetet használ, amely rendelkezik a Microsoft Dynamics 365 for Operations 1611-es verziójával és a Microsoft Dynamics for Operations 3-as platformfrissítésével (2016. november).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000">Mobileszköz, amelyre telepítve van Dynamics 365 for Operations alkalmazás</span></td>
<td><span style="color: #000000">Töltse le Dynamics 365 for Operations mobilalkalmazást a mobiljához tartozó alkalmazásáruházból.</span></td>
</tr>
<tr class="even">
<td>Gyorsjavítás – Tudásbázis, 4013633</td>
<td>Telepítse a gyorsjavítást a Dynamics 365 for Operationsben biztosított munkaterületek engedélyezéséhez.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000"><span style="color: #000000">Gyorsjavítás – Tudásbázis, 3216943</span> </span></td>
<td>Telepítse a gyorsjavítást ahhoz, hogy engedélyezze a szállítói együttműködés mobil munkaterületet.</td>
</tr>
<tr class="even">
<td>A szállítói felhasználónak hozzáférést kell biztosítania a Dynamics 365 for Operations szállítói együttműködési webes felületéhez, és létre kell hoznia egy szállítói együttműködő felhasználót.</td>
<td>Kövesse az alábbi témakörökben leírt lépéseket az eladói együttműködési webes felület beállításához és működtetéséhez.
<ul>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-external-vendors/">A külső szállítókkal történő szállítói együttműködés használata</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/manage-vendor-collaboration-users/">Szállítói együttműködés felhasználóinak kezelése</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/set-up-and-maintain-vendor-collaboration/">Szállítói együttműködés beállítása és karbantartása</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-customers-in-dynamics-365-for-operations/">Hogyan használja a szállítói együttműködést a vevőkkel történő munkában a Microsoft Dynamics 365 for Operations rendszerben?</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Áttekintés
A Szállítói együttműködési mobil munkaterület folyamatosan tájékoztatja a szállítókat az új beszerzési rendelésekről, hogy láthassák és válaszolhassanak a beszerzési rendelésekre a Dynamics 365 for Operations webes ügyfélnél. 

**Megjegyzés:** A mobil munkaterületet a szállító együttműködési webes felületének kiegészítéseként kell felhasználni, de nem helyettesíti azt. 

A Szállító együttműködési mobil munkaterületével szállítói megtekinthetik az új beszerzési rendeléseket, amelyeket jóváhagyásra beküldtek. Megjeleníti a megrendelési információkat, például a termékeket, a mennyiséget és a kért szállítási határidőket. Az árakra vonatkozó adatok rendelkezésre állnak, az egyes szállítók konfigurációjától függően. 

Amikor egy felhasználó bejelentkezik szállítóként, látni fogja, hogy mely beszerzési rendelésekre válaszoltak, illetve hogy mely beszerzési rendelések várnak még vevői műveletre. A szállító esetleg másik szállítási határidőt javasolt, amelyről még nem egyezett meg az ügyféllel, így a beszerzési rendelés ügyfélműveletre vár. A szállító megtekintheti a jóváhagyott, de még nem kiszállított beszerzési rendelések listáját. 

A beszerzési rendelésre válaszolva a szállítónak a Dynamics 365 for Operations webes ügyfelén elérhető szállítói együttműködési webes felületet kell használnia. Itt kaphat még a szállító több információt a rendelésről, például a dokumentummellékletekről, a soronkénti kézbesítési címről és a szállítóval kapcsolatos díjakról. 

Egy különleges biztonsági funkcióval a szállító meg tudja nézni, hogy melyik kapcsolattartók vannak bejegyezve egy-egy szállítói fióknál. Ugyanezzel a biztonsági szerepkörrel a szállító megtekintheti a benyújtott felhasználói kérelmek állapotát. 

Az új kapcsolattartók létrehozása és az új felhasználói kérelmek benyújtása a Dynamics 365 for Operations webes ügyfélprogramjában elérhető szállítói együttműködési felületen történik. 

A következőkre lesz lehetősége a szállítójának a mobil munkaterületen:

-   A szállítónak küldött új beszerzési rendelések megtekintése.
-   Megtekintheti azokat a beszerzési rendeléseket, amelyekre a szállító válaszolt, és amelyek vevői műveletre várnak.
-   A jóváhagyott állapotú, de nem teljes mértékben leszállított beszerzési rendelések megtekintése.
-   A szállítói számlára regisztrált kapcsolattartó adatainak megtekintése (egy további biztonsági szerepkör szükséges).
-   Információkat tekinthet meg, és követheti a szállító által benyújtott felhasználói kérelem állapotát (további biztonsági szerepkör szükséges).

## <a name="get-started"></a>Első lépések
A használat megkezdése a mobileszközön:

1.  A mobiljához tartozó alkalmazásáruházból töltse le és telepítse a Microsoft Dynamics 365 for Operations alkalmazást.
2.  Indítsa el az alkalmazást a készülékén.
3.  Adja meg a Dynamics 365 URL-címét.
4.  Adja meg a vállalatot a bejelentkezéshez. Például írja be azt, hogy **USMF**.
5.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót a Microsoft Dynamics 365 for Operations-fiókjához.

Az alkalmazásba való bejelentkezést követően a munkaterületek láthatók. A munkaterületek a mobilalkalmazásban történő megtekintéséhez először a kívánt munkaterületeket közzé kell tenni Dynamics 365 for Operations alkalmazásban. A munkaterületen való közzétételhez a rendszergazda engedélyével kell rendelkeznie.

1.  Indítsa el a Dynamics 365 for Operationst.
2.  Lépjen a **Rendszerfelügyelet** &gt; **Beállítás** &gt; **Rendszerparaméterek** elemre.
3.  Válassza a **Mobilalkalmazás kezelése** lehetőséget.
4.  Válassza a **Szállítói együttműködés** munkaterületet a mobilplatformon való közzétételre.
5.  Válassza ki a **Munkaterület közzététele** lehetőséget.
6.  Frissítse az eszközt a közzétett munkaterületek ellenőrzéséhez.
7.  Válassza ki a **Szállítói együttműködés** munkaterületet. A következő lap jelenik meg.

    [![szállítói együttműködés mobilalkalmazása](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Kapcsolattartók
A **Kapcsolattartók** lapon megtekintheti mindazokat a kapcsolattartókat, akiket beállított a szállítói számlához. Megjeleníti a kapcsolattartó személy nevét, elsődleges e-mail-címét és a felhasználók aliasát, amennyiben az rendelkezésre áll. Azt is jelzi, hogy a kapcsolattartó személy felhasználói fiókja aktív-e. Amikor kiválaszt egy kapcsolattartót, megjelennek a kapcsolattartási adatai, például jogi személy esetén a szervezetet képviselő személy és a kapcsolattartási adatok, például a telefonszám vagy egy másik e-mail-cím.

## <a name="user-requests"></a>Felhasználókérések
A **Felhasználói kérelmek** lap segítségével megtekintheti azokat a felhasználói kérelmeket, amelyeket a szállítói együttműködés webes felületén keresztül nyújtott be, és követheti az állapotukat. Amikor kiválaszt egy felhasználói kérelmet, akkor megtekintheti, hogy mit is kért, hozzáadhat vagy inaktívvá tehet egy felhasználót, módosíthatja a biztonságot, illetve megtekintheti, hogy mely biztonsági szerepköröket kértek a felhasználónak.

## <a name="purchase-orders-ready-for-review"></a>Beszerzési rendelések, melyek készen állnak ellenőrzésre
A **Beszerzési rendelések, melyek készen állnak ellenőrzésre** lapon megtekintheti a vevő által beküldött, de még meg nem válaszolt összes megrendelést. Megtekintheti a kijelölt adatokat a rendelésről, így például azt is, hogy mely termékeket kértek, és hogy mikor kell szállítani. Árinformációk csak akkor állnak rendelkezésre, ha ez be van állítva a szállítónál. Megnézheti, hogy a beszerzési rendeléshez tartoznak-e a megjegyzések és mellékletek. A mellékletek megnyitásához a szállítói együttműködés webes ügyfélprogramját kell használnia. Válassza ki a **Beszerzési rendeléssor** lehetőséget a sorok részletekkel együtt való megjelenítéséhez. Vegye figyelembe, hogy minden egyes sor esetében egy jelző mutatja, hogy vannak-e jegyzetek vagy mellékletek, illetve van-e olyan szállítási cím, amely eltér a fejlécben megjelenő címtől. A beszerzési rendelés megválaszolásához a szállítói együttműködési webes ügyfélprogramot kell használnia.

## <a name="awaiting-customer-action"></a>Várakozás vevői műveletre
A **Várakozás vevői műveletre** lap segítségével megtalálhatja azokat a beszerzési rendeléseket, amelyekre Ön vagy valaki a vállalatánál, aki szintén hozzáfér a szállítói együttműködésekhez, válaszolt. A beszerzési rendelések csak akkor láthatók ebben a listában, ha a vevőnek végre kell hajtania az alábbi műveletek egyikét a beszerzési rendelésnél.

-   Ha a beszerzési rendelést elutasították, a vevőnek vagy frissítenie kell az elküldött rendelést, majd újra el kell küldenie, vagy törölnie kell a rendelést, és újra el kell küldenie azt. A beszerzési rendelés az újbóli elküldést követően eltűnik a **Várakozás vevői műveletre** lapról.
-   Ha a beszerzési rendelést változtatásokkal fogadták el, a vevőnek frissítenie kell az eredeti rendelést, majd újra el kell küldenie véleményezésre, vagy frissítheti a módosítások szerint, majd erősítse meg azonnal. A beszerzési rendelés mindkét esetben eltűnik a **Várakozás vevői műveletre** lapról.
-   Ha a beszerzési rendelés elfogadták, és megjelenik a **Várakozás vevői műveletre** lapon, ez azért van, mert a beszerzési rendelést az elfogadás befejezésekor nem erősítették meg automatikusan. Arra vár, hogy egy beszerzési képviselő Megerősítve állapotra állítsa. A beszerzési rendelés általában a vevő és a szállító között létrejött megállapodásnak tekinthető, amint a szállító elfogadja a rendelést. A beszerzési rendelés Megerősítve állapotúra állítása csupán formalitás.

Ha kiválasztja a beszerzési rendelést, további részletek jelennek meg a válasszal kapcsolatban. Megtekintheti a sor részleteit és a választ minden sorra vonatkozóan. A sor állapota azt mutatja meg, hogy a következő válaszok közül melyiket adták.

-   Elfogadva
-   Elutasítva
-   Elfogadva módosításokkal
-   Helyettesített/helyettesítő
-   Felosztás ütemezésbe/Ütemezéssor

Vegye figyelembe, hogy egy állapotjelző a **Kézbesítés**= igen/nem eredményt mutatja, ami annak jelzésére szolgál, hogy a sorok nem lesznek kiszállítva. Ez azért lehet, mert a sort elutasították vagy helyettesítették, ahol az eredeti sorok várhatóan nem kerülnek kiszállításra, vagy olyan sorról van szó, amely több ütemezésre lett felosztva, és az eredeti sor várhatóan nem a beérkező rendelésnek megfelelően lesz kiszállítva. A rendelési sor válaszánál végrehajtott minden módosítás megjelenik, kivéve a feltöltött jegyzeteket és mellékleteket, amelyeket a szállítói együttműködési webes felületének használatával tekinthet meg.

## <a name="open-confirmed-orders"></a>Megerősített rendelés megnyitása
Amikor a beszerzési rendelést megerősíti a vevő, ami azt jelenti, hogy a Beszerzési rendelés Megerősített állapotra vált, és megjelenik a nyitott és megerősített rendelésben. Mindaddig, amíg nincs regisztrálva fogadottként a vevő által, a listában marad.





