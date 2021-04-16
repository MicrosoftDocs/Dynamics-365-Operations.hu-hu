---
title: Elektronikus számlák kibocstása a Finance és Supply Chain Management szolgáltatásokban
description: Ez a témakör bemutatja, hogyan állíthat ki elektronikus számlákat a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokban az Elektronikus számlázás segítségével.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8d6ef59b64a96e13bdc2e5ddf299ef7ab98e105c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840076"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Elektronikus számlák kiállítása a Finance és a Supply Chain Management szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthat ki elektronikus számlákat a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokban az Elektronikus számlázás segítségével.


## <a name="feature-activation"></a>Funkció aktiválása

Az elektronikus számlák Elektronikus számlázással történő kiadásához aktiválnia kell a Finance és a Supply Chain Management megoldásban a Funkcióhivatkozást.

Minden funkció egy adott elektronikus számlázási funkciónak felel meg, amely megfelel az adott ország/régió elektronikus számlázási követelményeinek.

Az alábbi tábla bemutatja az Elektronikus számlázás által potenciálisan támogatott funkciók listáját.

| Név                                              | Ország/régió |
|---------------------------------------------------|----------------|
|Osztrák elektronikus számla                        |Ausztria         |
|Belga elektronikus számla                         |Belgium         |
|NF-e szövetségi – brazil elektronikus számla       |Brazília          |
|NFS-e – Brazil szolgáltatás (városi) elektronikus számla|Brazília          |
|Dán elektronikus számla                          |Dánia         |
|Egyiptomi elektronikus számla                        |Egyiptom           |
|Észt elektronikus számla                        |Észtország         |
|Finn elektronikus számla                         |Finnország         |
|Francia elektronikus számla                          |Franciaország          |
|Német elektronikus számla                          |Németország         |
|PEPPOL – Globális elektronikus számla                 |Globális          |
|Olasz elektronikus számla                         |Olaszország           |
|CFDI – Mexikói elektronikus számla                  |Mexikó          |
|Holland elektronikus számla                           |Hollandia     |
|Norvég elektronikus számla                       |Norvégia          |
|Spanyol elektronikus számla                         |Spanyolország           |

Abban az esetben, ha van egy örökölt elektronikus számlázási funkció, amelyet az ország/régió honosítási köre támogat, ezen funkciók aktiválásának egyike kikapcsolja az örökölt funkciót és lehetővé teszi elektronikus számlák kiállítását az elektronikus számlázáson keresztül.

> [!IMPORTANT]
> Az Elektronikus számlázás integrációs funkciójának engedélyezése után az új elektronikus számlázási tapasztalat alapértelmezés szerint ki van kapcsolva. A funkciókoncepció segítségével szelektíven engedélyezheti a jogi személyek számára az ország-/régióspecifikus funkciókat használó új élmények használatát. A **Globális** beállítás meghatározza a fennmaradó azon megyék/területek új élményét, amelyek nem szerepelnek kifejezetten a táblában.

## <a name="submit-electronic-documents"></a>Elektronikus dokumentumok elküldése

Az elektronikus dokumentumok beküldése jelenti a Finance and Supply Chain Management, valamint az Elektronikus számlázás közötti kommunikáció egységes pontját. A kommunikációs folyamatok mindkét irányban folynak minden benyújtási esemény során:

- A **Finance and Supply Chain Management modultól az Elektronikus számlázásig** – a Finance és a Supply Chain Management modul elküldi az absztrakt számlákat az Elektronikus számlázásnak. Szükség esetén az elektronikus számlázási funkciók részeként konfigurált változók tartalmát is elküldik.
- **Az Elektronikus számlázásból a Finance and Supply Chain Management modulba** – az elektronikus számlázási funkciótól függően a Finance and Supply Chain Management megoldás a korábban benyújtott számlák feldolgozási eredményeiről kap frissítéseket az Elektronikus számlázásból. Ezenkívül az elektronikus számlázási funkciók részeként konfigurált változók tartalmát is elküldik.

Ha elektronikus dokumentumokat szeretne benyújtani az Elektronikus számlázáshoz a Finance and Supply Chain Management megoldásban, kattintson a **Szervezeti adminisztráció &gt; Időszakos &gt; Elektronikus dokumentumok &gt; Elektronikus dokumentumok benyújtása** lehetőségre.

A kiindulópont egy feladott számla. Ez a számla eltérő eredetű lehet, például értékesítési rendelésekből, projektszámlákból vagy szabadszöveges számlákból.

A benyújtási folyamat futtatható manuálisan vagy a háttérben.

- **Kézi végrehajtás** – a kézi végrehajtáshoz a **Szűrő** beállítással kell meghatároznia a benyújtandó dokumentumok tartományát. A **Szűrők** oldalon beállíthatja a saját lekérdezését, hogy ki tudja választani a benyújtandó feladott számlákat. A kiválasztást követően manuálisan el kell kezdenie a feldolgozás végrehajtását, majd meg kell várnia a feldolgozás befejezését. Ha befejeződött a feldolgozás, a Műveletközpontban megjelenő üzenet megjeleníti a sikeresen benyújtott elektronikus dokumentumok számát.
- **Háttérbeli végrehajtás** – a háttérbeli végrehajtáshoz nem kell bejelentkezni vagy a nyitva hagyni a benyújtási párbeszédpanelt. Ütemezheti a folyamat úgy, hogy futtatássa és meghatározza a végrehajtás gyakoriságát.

## <a name="view-the-submission-logs"></a>A beküldési naplók megtekintése

A Finance and Supply Chain Management modulban a benyújtási naplók segítségével megtekintheti az Elektronikus számlázásba küldött adatok feldolgozásának eredményeit. Lépjen a **Szervezeti adminisztráció &gt; Időszakos &gt; Elektronikus dokumentumok &gt; Elektronikus dokumentum benyújtása** lehetőségre, majd a **Dokumentumtípus** mezőben válasszon ki egy értéket, amely szűri a naplókban szereplő számlák típusát.

Három lehetséges benyújtási állapot lehetséges:

- **Ütemezve** – az Elektronikus számlázás megkapta a Finance and Supply Chain Management modulból az adatokat, és folyamatban van az elektronikus számlázási funkció feldolgozása.
- **Befejeződött** – az Elektronikus számlázás a konfigurált módon sikeresen feldolgozta az elektronikus számlázási funkciót.
- **Sikertelen** – az Elektronikus számlázás hibát észlelt, vagy egy kivétel miatt leállt az elektronikus számlázási funkció feldolgozása közben.

> [!IMPORTANT]
> A benyújtási állapot a feldolgozás azon állapotát jelenti, amelyet az Elektronikus számlázás az elektronikus számlázási funkción végez. Nem magát az elektronikus számla végső állapotát jelzi.
>
> Ha például egy elektronikus számlát egy külső webszolgáltatásnak kell jóváhagyásra benyújtani, a benyújtási állapot **Befejeződött**, de lehet, hogy az elektronikus számla állapota **Elutasítva**. Ebben az esetben az Elektronikus számlázás a konfigurált módon sikeresen feldolgozta az elektronikus számlázási funkciót. Az elektronikus számlát azonban elutasították, mert nem felelt meg a webszolgáltatás által a számla jóváhagyására vonatkozóan létrehozott kritériumoknak.

A benyújtási naplók a következő további funkciókat foglalják magukban:

- **Benyújtás részletei** – a fő benyújtás részleteinek megtekintése. A vizualizáció az elektronikus számlázási funkcióban konfigurált műveletek teljes végrehajtási naplóját jeleníti meg. Lehetővé teszi továbbá a felhasználók számára a feldolgozás során létrehozott fájlok letöltését is. Olyan helyzetekben, amikor a számlát egy külső webszolgáltatásnak kell jóváhagynia, lehetővé teszi a felhasználók számára a számla állapotának megtekintését.
- **Kapcsolódó benyújtások** – a gyermekbenyújtások részleteinek megtekintése.
- **Beküldések érvénytelenítése** – ez a funkció speciális benyújtási folyamatot tesz lehetővé olyan helyzetekben, amikor az elektronikus számlát egy külső webszolgáltatásnak kell jóváhagynia. Arra utasítja az Elektronikus számlázást, hogy a webszolgáltatásnak olyan üzenetet küldjön, amely egy jóváhagyott elektronikus számla állapotának érvénytelenítésére szolgál a webszolgáltatás adatbázisában.
- **Dokumentum újbóli benyújtása** – az Elektronikus számlázásba már elküldött elektronikus dokumentum újbóli benyújtása. Új napló jön létre a **Benyújtás részletei** oldalon.
- **Kapcsolódó beküldés küldése**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
