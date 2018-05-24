---
title: "Együttműködés a szállítókkal a Szállítói portálon keresztül"
description: "Ez a témakör bemutatja, hogy a megbízott beszerzők hogyan tudják a Szállítói portált a külső szállítókkal való együttműködésre használni a beszerzési rendelés visszaigazolási folyamata alatt. Az itt olvasható információk csak a Dynamics AX 2016. februári és 2016. májusi verzióira vonatkoznak."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2fa152c5586a1122a109762780d23fd8c2240702
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="collaborate-with-vendors-by-using-the-vendor-portal"></a>Együttműködés a szállítókkal a Szállítói portálon keresztül

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy a megbízott beszerzők hogyan tudják a Szállítói portált a külső szállítókkal való együttműködésre használni a beszerzési rendelés visszaigazolási folyamata alatt. Az itt olvasható információk csak a Dynamics AX 2016. februári és 2016. májusi verzióira vonatkoznak.

Az ebben a témakörben olvasható információk csak a Dynamics AX 2016 februári és 2016 májusi verzióira vonatkoznak. A Szállítói portál funkciót a Dynamics 365 for Operations rendszer 1611-es verziójának Kiterjesztett szállítói együttműködés funkciója váltotta le. Az új szállítói együttműködés funkcióval kapcsolatos további tudnivalókat lásd: [A szállítói együttműködés a külső szállítókkal való együttműködésre történő használata](vendor-collaboration-work-external-vendors.md).  

A Szállítói portál olyan szállítók számára készült, akik nem rendelkeznek Microsoft Dynamics AX electronic data interchange (EDI) integrációval a beszerzés rendelés (PO) információjának cseréjéhez. A portál lehetővé teszi, hogy a megbízott beszerzők a szállítóknak küldjék a PO-t, és közvetlenül a Dynamics AX-től kapják a Megerősítve vagy Elutasítva válaszokat.  

A folyamat konfigurálható, így a szállítótól érkező visszaigazolás automatikusan megerősíti a rendelés. Ez azt jelenti, hogy a követésre szükség van időnként, a rendelés elutasítása esetén, vagy ha szállító visszaigazolás választ regisztrált, de a beszerzési rendelés állapota nem módosul **Megerősítve** állapotra a visszaigazolás folyamat hibája miatt.

## <a name="po-confirmation-and-rejection"></a>Beszerzési rendelés visszaigazolása és visszautasítása
A beszerzési rendelések Dynamics AX-ben készülnek. Ha rendelkezik egy olyan beszerzési rendeléssel, aminek az állapota **Jóváhagyva**, visszaigazolási kérés generálásával elküldheti a szállítónak. Ha fel szeretné hívni a szállító figyelmét az új beszerzési rendelésre, elküldheti azt egy e-mailben is a nyomtatáskezelő rendszer segítségével. A beszerzési rendelés megjelenik a Szállítói portálon és a szállító megerősítheti vagy elutasíthatja azt. A szállító hozzászólások hozzáadásával oszthat meg olyan információkat, mint a beszerzési rendelés módosítása.  

A szállító láthatja a rendeléssorokat a Szállítói portálon. Ezek a sorok olyan információkat tartalmaznak, mint a külső termékszám, dimenziók, az árral kapcsolaton információk, szállítási dátum és szállítási cím. A szállítók létrehozhatnak egy jelentést, hogy lássák a beszerzési rendeléseket, és ezen szerepel a teljes ár is. A szállítóhoz kapcsolódó költségek akkor jelennek meg, ha a szállító rákattint a **Költségek** gombra a fejlécen vagy a soroknál. A szállítók importálhatják a beszerzési rendelésen szereplő adatokat a saját rendszerükbe az **Exportálás Excelbe** funkciókat segítségével.  

Az alábbi táblázat bemutatja a tipikus információcserét attól függően, hogy hogyan reagál a szállító, amikor egy beszerzési rendelés visszaigazolást küld nekik.

| Válasz típusa                                                                                                  | Eredmény                                                                                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A szállító visszaigazolja a rendelést. A rendszer a beszerzési rendelések automatikus visszaigazolására van konfigurálva, abban az esetben, ha a szállító visszaigazol.    | A rendelés állapota **Visszaigazolva** értékre frissül. Ha valami megakadályozza, hogy a rendelést frissítsék, a szállító válasza továbbra is **Visszaigazolva** értékű lesz, de a beszerzési rendelés **Külső ellenőrzés alatt** állapotú marad.                                                                       |
| A szállító visszaigazolja a rendelést. A rendszer nincs a beszerzési rendelések automatikus visszaigazolására konfigurálva, abban az esetben, ha a szállító visszaigazol. | A szállító válasza **Visszaigazolva** értékű lesz, de a beszerzési rendelés **Külső ellenőrzés alatt** állapotú marad.                                                                                                                                                                                      |
| A szállító elutasítja a rendelést.                                                                                     | A szállító válasza **Elutasítva** értékű lesz, de a beszerzési rendelés **Külső ellenőrzés alatt** állapotú marad. Az elutasítás indoklással és a változtatáshoz kapcsolódó javaslattal együtt érkezik meg. Ilyen javaslat például egy alternatív szállítási dátum. Ön frissíti a beszerzési rendelést és elküldi az új verziót ellenőrzésre. |

## <a name="changes-to-a-po"></a>Változtatások a beszerzési rendeléshez
Ha módosítani szeretne egy beszerzési rendelés, amit már korábban megerősítettek, elküldhet egy új beszerzési rendelést a szállítónak a Szállítói portálon keresztül. Az új beszerzési rendelés rendelkezni fog egy verziószám utótaggal, ami azt jelzi, hogy ez korábban közölt beszerzési rendelés módosított változata. A Szállítói portál lehetővé teszi a szállítóknak, hogy minden rendelés előzményét nyomon tudják követni. A beszerzési rendelés már korábban jóváhagyott verziója a jóváhagyott beszerzési rendelések listáján marad addig, amíg egy új beszerzési rendelés nem lesz jóváhagyva.  

A beszerzési rendelés visszavonásakor az állapot visszatér a **Jóváhagyva** állapotba. Vissza kell küldenie a beszerzési rendelést a szállítónak a Szállítói portálon keresztül, hogy a szállító megerősíthesse vagy elutasíthassa az érvénytelenítést. Az érvénytelenítés jóváhagyása után a beszerzési rendelés a jóváhagyott beszerzési rendelések listáján **Érvénytelenítve** értékkel fog megjelenni.

## <a name="versions-status-transitions-and-change-management"></a>Verziók, állapotváltozás és változáskezelés
Amikor egy beszerzési rendelést elküldenek a szállítónak, a rendszer ezt a beszerzési rendelés egy speciális típusaként regisztrálja, és az állapota **Jóváhagyva** állapotról **Külső ellenőrzés alatt** állapotra módosul. Ha később módosítja a beszerzési rendelést, egy új beszerzési rendelés jön létre, és az állapota újra **Jóváhagyva** állapotú lesz (vagy **Vázlat** állapotra módosul, ha a változáskezelés engedélyezett).  

Az alábbi táblázat szemlélteti azokat az állapot- és verzióváltozásokat, amik érinthetnek egy beszerzési rendelést.

| Művelet                                                   | Állapot és verzió                                                                                    |
|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| A beszerzési rendelés eredeti verzióját a Dynamics AX rendszerben hozzák létre. | Az állapota **Jóváhagyva**.                                                                           |
| A beszerzési rendelést elküldik a Szállítói portálra.                     | Egy verziót regisztrálnak a Szállítói portálon, és az állapota **Külső ellenőrzés alatt** állapotra módosul.    |
| Elvégezhet néhány módosítást, amit a szállító kér.  | Az állapot újra **Jóváhagyva** lesz.                                                            |
| Küldje el a beszerzési rendelés új verzióját a Szállító portálra. | Egy új verzió lesz regisztrálva a Szállítói portálon, és az állapota **Külső ellenőrzés alatt** állapotra módosul. |
| A szállító jóváhagyja a beszerzési rendelés új verzióját.           | Az állapot **Visszaigazolt** lesz.                                                                |

Ha meg akarja nézni a szállítónak elküldött beszerzési rendeléseket és a szállító válaszait, kattintson a **Naplók** &gt; **Visszaigazolási kérések** pontra a beszerzési rendelésnél.  

Azok a rendelések, amelyeket válaszért küldtek a szállítóknak, és **Külső ellenőrzés alatt** állapotúak, megjelenhetnek mind **A szállítói portálra küldött és válaszra váró beszerzési rendelések** és **A szállítói portálra küldött beszerzési rendelések, amelyekre a válasz műveletet igényel** listában is. Ha módosít egy olyan rendelést, amely el lett küldve a szállítónak, így annak állapota újra **Jóváhagyva** lesz, és a rendelés már nem szerepel a listákban. Ha meg szeretné tekinteni, hogy a rendelésre volt-e már korábban válasz, kattintson a **Naplók** &gt; **Visszaigazolási kérések** lehetőségre.  

A szállítóknak nem kell jóváhagyniuk a beszerzési rendelést a Szállítói portálon. Küldhetnek email üzenetet, illetve egyéb csatornákon keresztül is kommunikálhatják a beszerzési rendelés elfogadását. Ezután a rendelést manuálisan is jóváhagyhatja a Dynamics AX rendszerben. Ebben az esetben egy figyelmeztetést fog kapni, ami jelzi, hogy a rendelés jóvá lesz hagyva annak ellenére is, hogy nincs válasz a szállítótól. A beszerzési rendelés ezután megjelenik a jóváhagyási előzményekben a Szállítói portálon, úgy, mint egy megnyitott rendelés amelyre nem érkezett válasz. Ezenkívül a szállító többé nem tudja majd se elfogadni, se visszautasítani a beszerzési rendelést.  

**Megjegyzés:** A Dynamics AX rendszerben mindig a beszerzési rendelés legutolsó verziója érhető el a további folyamatok számára, még akkor is, ha ez a verzió nincs még regisztrálva.

### <a name="change-management"></a>Változáskezelés

Ha bekapcsolta a beszerzési rendelés számára a változáskezelést, a beszerzési rendelés egy jóváhagyási munkafolyamaton megy majd keresztül, hogy az állapota **Jóváhagyva** legyen. Ezt a folyamatot a szállító nem látja.  

Ha be van kapcsolva a változáskezelés a beszerzési rendelésnél, a beszerzési rendelés verziója a jóváhagyás után lesz regisztrálva, nem pedig a megerősítés vagy a szállítónak való küldés után.  

Az alábbi táblázat szemlélteti azokat az állapot- és verzióváltozásokat, amik érinthetnek egy beszerzési rendelést, ha a változáskezelés be van kapcsolva.


|                                                    Művelet                                                     |                                                                                                                                                                                                                      Állapot és verzió                                                                                                                                                                                                                      |
|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           A beszerzési rendelés eredeti verzióját a Dynamics AX rendszerben hozzák létre.                            |                                                                                                                                                                                                            Az állapota <strong>Vázlat</strong>.                                                                                                                                                                                                             |
| A beszerzési rendelést elküldik a jóváhagyási folyamatra. (Ez egy belső folyamat, amelyben a szállító nem vesz részt.) |                                                                                                                        Az állapot <strong>Vázlat</strong> állapotról <strong>Ellenőrzés alatt</strong> állapotra, majd <strong>Jóváhagyva</strong> állapotra módosul, ha a beszerzési rendelés nem kerül elutasításra a jóváhagyási folyamat alatt. A jóváhagyott beszerzési rendelés verzióként van regisztrálva.                                                                                                                        |
|                                      A beszerzési rendelést elküldik a Szállítói portálra                                      |                                                                                                                                                                      A verzió regisztrálva lesz a Szállítói portálon, és az állapota <strong>Külső ellenőrzés alatt</strong> állapotra módosul.                                                                                                                                                                       |
|                            Elvégezhet néhány módosítást, amit a szállító kér.                            |                                                                                                                                                                                                    Az állapot újra <strong>Vázlat</strong> lesz                                                                                                                                                                                                     |
|                              A beszerzési rendelést újra elküldik a jóváhagyási folyamatra.                               | Az állapot <strong>Vázlat</strong> állapotról <strong>Ellenőrzés alatt</strong> állapotra, majd <strong>Jóváhagyva</strong> állapotra módosul, ha a beszerzési rendelés nem kerül elutasításra a jóváhagyási folyamat alatt. Úgy is konfigurálhatja a rendszert, hogy a változás esetén ne legyen szükséges az adott mező ismételt jóváhagyása. Ebben az esetben az állapot <strong>Vázlat</strong> lesz, majd automatikusan frissül <strong>Jóváhagyva</strong> állapotra. A jóváhagyott beszerzési rendelés új verzióként lesz regisztrálva. |
|                           Küldje el a beszerzési rendelés új verzióját a Szállító portálra.                            |                                                                                                                                                                    Az új verzió regisztrálva lesz a Szállítói portálon, és az állapota <strong>Külső ellenőrzés alatt</strong> állapotra módosul.                                                                                                                                                                     |
|                                A szállító jóváhagyja a beszerzési rendelés új verzióját.                                 |                                                                                                                                                     Az állapot vagy automatikusan változik <strong>Visszaigazolva</strong> állapotra, vagy akkor, amikor megkapja a szállító válaszát, és megerősíti a beszerzési rendelést.                                                                                                                                                     |

<a name="additional-resources"></a>További erőforrások
--------

[Biztonsági funkciók konfigurálása a szállítói együttműködés felhasználói számára](configure-security-vendor-portal-users.md)

[Szállítói együttműködési számlázás munkaterület](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md)




