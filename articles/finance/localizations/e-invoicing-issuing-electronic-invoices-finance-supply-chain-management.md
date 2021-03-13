---
title: Elektronikus számlák kibocstása a Finance és Supply Chain Management szolgáltatásokban
description: Ez a témakör bemutatja, hogyan állíthat ki elektronikus számlákat a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokban az Elektronikus számlázási bővítmény segítségével.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 187f5a20d088b4fcd7af2a6576357a69c2efc2c6
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104389"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Elektronikus számlák kibocstása a Finance és Supply Chain Management szolgáltatásokban

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ez a témakör bemutatja, hogyan állíthat ki elektronikus számlákat a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokban az Elektronikus számlázási bővítmény segítségével.


## <a name="feature-activation"></a>Funkció aktiválása

Ahhoz, hogy az elektronikus számlák Elektronikus számlázási bővítménnyel történő kiadása elkezdődjon, aktiválni kell a Finance and Supply Chain Management megoldásban a Funkcióhivatkozást.

Minden Funkcióhivatkozás egy adott elektronikus számlázási funkciónak felel meg, amely megfelel az adott ország/régió elektronikus számlázási követelményeinek.

Az alábbi tábla bemutatja az Elektronikus számlázási bővítmény által támogatott Funkcióhivatkozások listáját.

| Funkcióra mutató hivatkozás | Név                                              | Ország/régió |
|-------------------|---------------------------------------------------|----------------|
| BR-00053          | NF-e szövetségi – brazil elektronikus számla       | Brazília         |
| BR-00095          | NFS-e brazil elektronikus számlák               | Brazília         |
| DK-00001          | E-számlázás az állami szektorba (OIOUBL) – DK    | Dánia        |
| EG-00008          | E-számlázás Egyiptom esetén                             | Egyiptom          |
| ES-00025          | Elektronikus számla az állami szektornak           | Spanyolország          |
| EUR-00023         | Európai Unió e-számlázás az állami szektorba       | Európa         |
| ITA-00036         | IT – Elektronikus számlázás az állami szektor számára (FatturaPA) | Olaszország          |
| MX-00010          | E-számlázási CFDI                                  | Mexikó         |
| MX-00016          | E-számlázás CFDI – érvénytelenítési folyamat           | Mexikó         |

Abban az esetben, ha van egy örökölt elektronikus számlázási funkció, az ország honosítási köre támogatott, akkor a Funkcióhivatkozás aktiválása lehetővé teszi elektronikus számlák kiállítását az elektronikus számlázási bővítményen keresztül és kikapcsolja a korábbi funkciót.

## <a name="submit-electronic-documents"></a>Elektronikus dokumentumok elküldése

Az elektronikus dokumentumok beküldése jelenti a Finance and Supply Chain Management, valamint az Elektronikus számlázási bővítmény közötti kommunikáció egységes pontját. A kommunikációs folyamatok mindkét irányban folynak minden benyújtási esemény során:

- A **Finance and Supply Chain Management modultól az Elektronikus számlázási bővítményig** – a Finance and Supply Chain Management modul elküldi az absztrakt számlákat az Elektronikus számlázási bővítménybe. Szükség esetén az elektronikus számlázási funkciók részeként konfigurált változók tartalmát is elküldik.
- **Az Elektronikus számlázási bővítményből a Finance and Supply Chain Management modulba** – az elektronikus számlázási funkciótól függően a Finance and Supply Chain Management megoldás a korábban benyújtott számlák feldolgozási eredményeiről kap frissítéseket az Elektronikus számlázási bővítményből. Ezenkívül az elektronikus számlázási funkciók részeként konfigurált változók tartalmát is elküldik.

Ha elektronikus dokumentumokat szeretne benyújtani az Elektronikus számlázási bővítményhez a Finance and Supply Chain Management megoldásban, kattintson a **Szervezeti adminisztráció &gt; Időszakos &gt; Elektronikus dokumentumok &gt; Elektronikus dokumentumok benyújtása** lehetőségre.

A kiindulópont egy feladott számla. Ez a számla eltérő eredetű lehet, például értékesítési rendelésekből, projektszámlákból vagy szabadszöveges számlákból.

A benyújtási folyamat futtatható manuálisan vagy a háttérben.

- **Kézi végrehajtás** – a kézi végrehajtáshoz a **Szűrő** beállítással kell meghatároznia a benyújtandó dokumentumok tartományát. A **Szűrők** oldalon beállíthatja a saját lekérdezését, hogy ki tudja választani a benyújtandó feladott számlákat. A kiválasztást követően manuálisan el kell kezdenie a feldolgozás végrehajtását, majd meg kell várnia a feldolgozás befejezését. Ha befejeződött a feldolgozás, a Műveletközpontban megjelenő üzenet megjeleníti a sikeresen benyújtott elektronikus dokumentumok számát.
- **Háttérbeli végrehajtás** – a háttérbeli végrehajtáshoz nem kell bejelentkezni vagy a nyitva hagyni a benyújtási párbeszédpanelt. Ütemezheti a folyamat úgy, hogy futtatássa és meghatározza a végrehajtás gyakoriságát.

## <a name="view-the-submission-logs"></a>A beküldési naplók megtekintése

A Finance and Supply Chain Management modulban a benyújtási naplók segítségével megtekintheti az Elektronikus számlázási bővítménybe küldött adatok feldolgozásának eredményeit. Lépjen a **Szervezeti adminisztráció &gt; Időszakos &gt; Elektronikus dokumentumok &gt; Elektronikus dokumentum benyújtása** lehetőségre, majd a **Dokumentumtípus** mezőben válasszon ki egy értéket, amely szűri a naplókban szereplő számlák típusát.

Három lehetséges benyújtási állapot lehetséges:

- **Ütemezve** – az Elektronikus számlázási bővítmény megkapta a Finance and Supply Chain Management modulból az adatokat, és folyamatban van az elektronikus számlázási funkció feldolgozása.
- **Befejeződött** – az Elektronikus számlázási bővítmény a konfigurált módon sikeresen feldolgozta az elektronikus számlázási funkciót.
- **Sikertelen** – az Elektronikus számlázási bővítmény hibát észlelt, vagy egy kivétel miatt leállt az elektronikus számlázási funkció feldolgozása közben.

> [!IMPORTANT]
> A benyújtási állapot a feldolgozás azon állapotát jelenti, amelyet az Elektronikus számlázási bővítmény az elektronikus számlázási funkción végez. Nem magát az elektronikus számla végső állapotát jelzi.
>
> Ha például egy elektronikus számlát egy külső webszolgáltatásnak kell jóváhagyásra benyújtani, a benyújtási állapot **Befejeződött**, de lehet, hogy az elektronikus számla állapota **Elutasítva**. Ebben az esetben az Elektronikus számlázási bővítmény a konfigurált módon sikeresen feldolgozta az elektronikus számlázási funkciót. Az elektronikus számlát azonban elutasították, mert nem felelt meg a webszolgáltatás által a számla jóváhagyására vonatkozóan létrehozott kritériumoknak.

A benyújtási naplók a következő további funkciókat foglalják magukban:

- **Benyújtás részletei** – a fő benyújtás részleteinek megtekintése. A vizualizáció az elektronikus számlázási funkcióban konfigurált műveletek teljes végrehajtási naplóját jeleníti meg. Lehetővé teszi továbbá a felhasználók számára a feldolgozás során létrehozott fájlok letöltését is. Olyan helyzetekben, amikor a számlát egy külső webszolgáltatásnak kell jóváhagynia, lehetővé teszi a felhasználók számára a számla állapotának megtekintését.
- **Kapcsolódó benyújtások** – a gyermekbenyújtások részleteinek megtekintése.
- **Beküldések érvénytelenítése** – ez a funkció speciális benyújtási folyamatot tesz lehetővé olyan helyzetekben, amikor az elektronikus számlát egy külső webszolgáltatásnak kell jóváhagynia. Arra utasítja az Elektronikus számlázási bővítményt, hogy a webszolgáltatásnak olyan üzenetet küldjön, amely egy jóváhagyott elektronikus számla állapotának érvénytelenítésére szolgál a webszolgáltatás adatbázisában.
- **Dokumentum újbóli benyújtása** – az Elektronikus számlázási bővítménybe már elküldött elektronikus dokumentum újbóli benyújtása. Teljesen új napló jön létre a **Benyújtás részletei** oldalon.
- **Kapcsolódó beküldés küldése**
