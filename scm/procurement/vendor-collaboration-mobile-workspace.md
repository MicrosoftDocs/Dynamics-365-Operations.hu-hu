---
title: "Szállító együttműködési mobil munkaterület Microsoft Dynamics 365 műveletek app"
description: "A szállító-együttműködési mobil munkaterület a szállítók is naprakész a beszerzési rendeléseken elküldött őket jóváhagyásra és új és frissített beszerzési megrendelések és a kapcsolattartók adatainak megtekintése."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 36 - 37
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: fe8e912d-8446-4584-8a24-d8892e9028cd
ms.search.region: global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 9f441508b745d22218316128572c9ec6aeb7207b
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Szállító együttműködési mobil munkaterület Microsoft Dynamics 365 műveletek app

A szállító-együttműködési mobil munkaterület a szállítók is naprakész a beszerzési rendeléseken elküldött őket jóváhagyásra és új és frissített beszerzési megrendelések és a kapcsolattartók adatainak megtekintése.

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
<td>Olvassa el a Microsoft Dynamics 365 műveletek mobil platform</td>
<td><a href="/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">365 Dynamics műveletek mobil platform</a></td>
</tr>
<tr class="even">
<td>365 Dynamics műveletek</td>
<td>Győződjön meg arról, hogy olyan környezetben, amely rendelkezik a Microsoft Dynamics 365 műveletek verzió 1611 használ, és a Microsoft Dynamics műveletek platform frissítése (November 2016) 3.</td>
</tr>
<tr class="odd">
<td><span style="color: #000000;">Mobil eszköz, amely a Dynamics 365 a műveletek alkalmazás telepítve van</span></td>
<td><span style="color: #000000;">Töltse le a mobil app store app műveletek esetében a Dynamics 365.</span></td>
</tr>
<tr class="even">
<td>A gyorsjavítás KB 3215650</td>
<td>A munkaterületek Dynamics 365 műveletekhez biztosított ahhoz, hogy a gyorsjavítás telepítése.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000;"><span style="color: #000000;">A gyorsjavítás KB 3216943</span> </span></td>
<td>Telepítse a gyorsjavítást ahhoz, hogy a szállító mobil együttműködési munkaterület.</td>
</tr>
<tr class="even">
<td>A Szállítói felhasználó kell hozzáférhetnek a szállító együttműködési webes felület Dynamics 365 műveletek és szállítói együttműködési felhasználó beállítása.</td>
<td>Beállítása és a szállító együttműködési webes felület használatához az alábbi témakörökben leírt lépéseket kövesse.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Szállító együttműködési használhatja a külső szállítók</a></li>
<li><a href="manage-vendor-collaboration-users.md">Szállítói együttműködés felhasználóinak kezelése</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Szállítói együttműködés beállítása és karbantartása</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Szállító együttműködés segítségével Dynamics 365 műveletekhez az ügyfelekkel való munka</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Áttekintés
A szállító mobil együttműködési munkaterület új beszerzési rendelések tájékoztatni, hogy lásd és beszerzési rendelésekhez a Dynamics 365 műveletek webes ügyfél válaszol szállítók tartja.  

**Megjegyzés:** kiegészítéseként a szállító együttműködési webes felület, de nem helyettesíti a mobil munkaterületet kell használni.  

A szállító-együttműködési mobil munkaterület a szállítók új beszerzési megrendeléseken a jóváhagyásra küldött megtekinthetők. Megrendelés adatai, például a termékek, a mennyiség és a kért leszállítási dátumot jeleníti meg. Ár információ áll rendelkezésre, az egyes szállítók konfigurációjától függően.  

Amikor egy felhasználó bejelentkezik a szállítóként, mely beszerzési rendelések válaszoltak, vagy amelyek megrendelések továbbra is váró vevő művelet látja. A szállító is javasolták, hogy a másik nem még megállapodott a vevővel, vevő műveletet vár a beszerzési rendelés szállítási dátum. A szállító beszerzési rendelések, amelyek megerősítették, de még ki nem szállított is látható.  

A beszerzési rendelés válaszolni a szállító szállító együttműködési web-felülettel érhető el a webes ügyfél műveletek Dynamics 365 rendelkezik. Ez akkor is, ha a szállító a rendelésen, például dokumentumok, mellékletek, a szállítási cím / sor és a szállítóhoz kapcsolódó költségek további információt kap.  

A szállító különleges biztonsági szerepkör, mely ügyfél egy szállítói számlára regisztrált személyek megtekinthetők. Ugyanolyan biztonsági szerepkörrel rendelkező szállító felhasználói kérelmet nyújtottak be, az állapotát tekintheti meg.  

Új ügyfelek létrehozása és új felhasználói kérelmek benyújtásának érhető el a webes ügyfél műveletek Dynamics 365 szállító együttműködési felületén kell elvégezni.  

A mobil-munkaterület a szállító is:

-   A szállítónak küldött új beszerzési rendelések megtekintése.
-   Beszerzési rendelések megtekintése, hogy a szállító válaszolt és váró vevő művelet.
-   A jóváhagyott állapotú beszerzési rendelések megtekintése és nincs teljesen bevételezve.
-   A szállítói számlára regisztrált kapcsolattartó adatainak megtekintése (egy további biztonsági szerepkör szükséges).
-   Információk megtekintése, és hajtsa végre a felhasználó kérésére a forgalmazó által benyújtott (egy további biztonsági szerepkör szükséges) állapotát.

## <a name="get-started"></a>Első lépések
Ismerkedés a mobileszközön:

1.  A mobil app-tárolóban töltse le és telepítse a Microsoft Dynamics 365 app műveletek esetében.
2.  Az alkalmazás indításához az eszközön.
3.  A Dynamics 365 URL-CÍMÉT adja meg.
4.  Adja meg a vállalat a bejelentkezéshez. Például, adja meg az **USMF**.
5.  Az első bejelentkezéskor kéri a felhasználónevet és jelszót a Microsoft Dynamics 365 költségszámla esetében. 

Az alkalmazás a bejelentkezést követően a munkaterületek láthatók. A mobil app munkaterületek megtekintéséhez először a kívánt munkaterületet kell közzétenni a vonatkozó műveletek app a Dynamics 365. A munkaterület közzététele rendszer felügyeleti engedéllyel kell rendelkeznie.

1.  Indítsa el a Dynamics 365 műveletekhez.
2.  Ugrás a **rendszer felügyeleti**&gt;**a telepítő**&gt;**Rendszerparaméterek**.
3.  Válassza ki **mobile alkalmazás kezelése**.
4.  Jelölje be a munkaterület **szállító együttműködési** a mobil platform közzétenni.
5.  Válassza ki **közzététele a munkaterület**.
6.  Frissítse az eszközt, és ellenőrizze a közzétett munkaterületek.
7.  Válassza ki a **szállító együttműködési** munkaterület. A program a következő lapra.

[![szállító-együttműködés-mobil-app](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Kapcsolattartók
A **kapcsolatok** lap lehetővé teszi az ügyfelek a szállítói számla beállítása témakörben talál. Mutatja a kapcsolattartó személy nevét, elsődleges e-mail és a felhasználók más, amennyiben az rendelkezésre áll. Azt is jelzi, hogy a kapcsolattartó személy felhasználói fiók aktív. Amikor kiválaszt egy ügyfelet, kapcsolattartási adatai, például mely jogalanyok személy egy ügyfél, lásd:, és kapcsolattartási adatait, például a telefonszám vagy egy másik e-mail címet.

## <a name="user-requests"></a>Felhasználókérések
A **felhasználói kérelmek** lap lehetővé teszi, hogy a felhasználó kéri, hogy nyújtottak be a szállító együttműködési webes felületén keresztül, és hajtsa végre az állapot látható. Ha a felhasználó kérésére, is lásd a Mi a kért, hozzáadja vagy felhasználó inaktiválására, biztonságának módosítása, és lásd a felhasználó mely biztonsági szerepkörök felkérték.

## <a name="purchase-orders-ready-for-review"></a>Beszerzési rendelések véleményezésre kész
A **beszerzési rendelések véleményezésre kész** jelenik meg a beszerzési rendelésekre lap lehetővé teszi az ügyfél által küldött, és még nem érkezett válasz. Megtekintheti a kijelölt adatait a rendelés, mely termékek kért, és mikor kell szállítani. Árinformáció csak akkor használható, ha ez van beállítva a szállítóhoz.  

Láthatja, hogy a beszerzési rendelés van-e a megjegyzéseket és mellékleteket. Mellékletek megnyitásához szüksége szállító együttműködési webes ügyfélprogramban. Válassza ki **beszerzési rendeléssor** részleteket a sorok. Fontos megjegyezni, hogy az egyes sorok indikátor jelennek meg jegyzetek vagy mellékleteket, vagy hogy van-e a szállítási címet, amely eltér a fejen látható.  

A beszerzési rendelés válaszolni, a szállító együttműködési webes ügyfélprogram kell használnia.

## <a name="awaiting-customer-action"></a>Várakozás vevői műveletre
A **vevő művelet vár** lap lehetővé teszi, hogy megtalálja megrendelések Ön, vagy valaki, aki is elérheti a szállító együttműködés, a vállalat válaszoltak. A beszerzési rendelések csak addig láthatók ebben a listában Ha hajtsa végre az alábbi műveletek egyikét a beszerzési rendelésen a vevőnek.

-   Ha a beszerzési rendelés elutasították, a vevő lenne vagy frissíti az elküldött rendelést, és küldje el újra, vagy a megrendelés visszavonása és küldje el újra. A beszerzési rendelés küldött újra, ekkor eltűnik a **vevő művelet vár** oldalon.
-   Ha a beszerzési rendelés elfogadták a változások, a vevő az eredeti rendelés frissítése és küldje el véleményezésre, vagy frissítheti a módosítások szerint és győződjön meg arról, hogy azonnal kellene. Mindkét esetben a beszerzési rendelés eltűnik a **vevő művelet vár** oldalon.
-   Ha a beszerzési rendelés elfogadták, és megjelenik a **vevő művelet vár** oldalon van, mert a beszerzési rendelés megerősítése nem volt automatikus elfogadása a feladónak. A beszerzési ügynökök sorrendjének megváltoztatására, megerősítve vár. Általában a beszerzési rendelés tekinthető a vevői és szállítói között létrejött, amint a szállító elfogadja a rendelést. Áthelyezése a beszerzési rendelés megerősítve állam lenne a formalitások.

Ha a beszerzési rendelés, további részletek jelennek meg a válasszal kapcsolatban. A sor részletei és a válasz minden sorban látható. A sor állapota azt mutatja, amely a következő válaszok adtak ki.

-   Elfogadva
-   Elutasítva
-   Elfogadva módosításokkal
-   Helyettesített/helyettesítő
-   Ütemezés/kimutatási sor felosztása

Vegye figyelembe, hogy az állapotjelző mutatja **kézbesítése**= igen/nem, amelyek jelzésére szolgál, hogy a sorok nem lesznek kézbesítve. Ez akkor fordulhat elő a sor el lett utasítva vagy helyettesíteni, ha az eredeti sorok nem várnak el kell szállítani, vagy egy sor, többsoros ütemezés választották szét, és az eredeti sor várhatóan nem kézbesíthető a beérkezett rendelés kért.  

A rendelési sor válasz módosításai jelennek meg, kivéve a feltöltött megjegyzéseket és mellékleteket, melyek a szállító együttműködési webes felület használatával tekintheti.

## <a name="open-confirmed-orders"></a>Nyissa meg a visszaigazolt rendelések
Amikor a beszerzési rendelés megerősíti a vevő, ami azt jelenti, hogy a beszerzési rendelés változik megerősítve állam jelenik meg a nyitott megerősített rendelés. Mindaddig, amíg nem kapott a vevő által regisztrált marad a listában.


