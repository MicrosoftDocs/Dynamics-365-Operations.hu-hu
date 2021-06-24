---
title: Áfabevallás – Egyiptom
description: Ez a témakör bemutatja, hogyan kell konfigurálni és létrehozni az áfa-visszatérítési űrlapokat Egyiptom számára.
author: sndray
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9c776cedb65804f8cadbe324082c2abac435f906
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186614"
---
#  <a name="vat-declaration-for-egypt-eg-00002"></a>Áfabevallás – Egyiptom (EG-00002)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan állíthat be és hozhat létre áfa-visszatérítési űrlapot, valamint bevételi és kiadási számlakönyeveket egyiptomi jogi személyek esetében.

Az egyiptomi áfa-visszafizetési űrlap egy hivatalos dokumentum, amely összegzi a teljes esedékes kimeneti áfaösszeget, a visszatéríthetú teljes bemeneti áfaösszeget és a kapcsolódó áfa-kötelezettség összegét. Az űrlap az összes adófizetőtípushoz használható, és manuálisan kell kitölteni az adóhatósági portálon keresztül. Az áfa-visszatérítési űrlapot általános nevén áfa-áfa-visszatérítési dokumentumnak is nevezik.

Az áfa-visszatérítési űrlap a Dynamics 365 Finance rendszerben a következő jelentéseket tartalmazza:

- A 10-es számú áfa-visszatérítési űrlap, amely a jogszabályok által meghatározott módon részletezi az összegeket, a helyesbítéseket és a sortételenkénti áfaösszegeket.
- Értékesítési tranzakciók számlakönyve
- Beszerzési tranzakciók számlakönyve

## <a name="prerequisites"></a>Előfeltételek
A jogi személy elsődleges címének Egyiptomban kell lennie.
Engedélyezze a következő funkciót a **Funkció kezelése** munkaterületen:

   - (Egyiptom) Kategóriahierarchia az Értékesítési és beszerzési áfajelentéshez.

A funkciók engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Az **Elektronikus jelentéskészítés** munkaterületen importálja az adattárból a következő elektronikus jelentési formátumot:

- Áfa-bevallás Excel (EG)

> [!NOTE]
> A fenti formátum az **Adóbevallás modellen** alapul, és az **Adóbevallási modell-leképezését** használja. A további konfigurációkat a program automatikusan importálja.

További információért azzal kapcsolatosan, hogyan importálhat le Elektronikus jelentéstételi konfigurációkat, lásd: [Az elektronikus jelentéskészítési konfigurációk letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Elektronikus jelentéskészítési konfigurációk letöltése

Az Egyiptomra vonatkozó áfa-visszatérítési űrlap végrehajtása az elektronikus jelentéskészítési (ER) konfigurációkon alapul. A konfigurálható jelentésekkel kapcsolatos funkciókról és fogalmakról további információkat itt talál: [Elektronikus jelentéskészítés](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

A termelési és a felhasználói elfogadási tesztelési (UAT) környezetekkel kapcsolatban lásd: [Az elektronikus jelentéskészítési konfigurációk letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Az áfa-visszatérítési űrlap és a kapcsolódó jelentések egyiptomi jogi személyhez kapcsolódó létrehozásához töltse fel a következő konfigurációkat:

- Adóbevallás modell.verzió.70.xml vagy újabb verzió
- Adóbevallás modell-leképezés.verzió.70.120.xml vagy újabb verzió
- VAT bevallás Excel (EG).verzió.70.32 vagy újabb verzió

Miután letöltötte az ER-konfigurációkat a Lifecycle Services (LCS) szolgáltatásból vagy a globális adattárból, kövesse az alábbi lépéseket.

1. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** csempét.
1. A **Konfigurációk** oldalon a műveleti ablaktáblában válassza az **Átváltás** > **Betöltés XML-fájlból** elemet.
1. Töltse fel a fájlokat a fent felsorolt sorrendben. Miután minden konfigurációt feltöltött, a konfigurációs fának jelen kell lennie a Finance rendszerben.

## <a name="set-up-application-specific-parameters"></a>Alkalmazásfüggő paraméterek beállítása

Az alkalmazásspecifikus paraméterek segítségével meghatározhatja az áfatranzakcióknak a jelentés generálása sorának egyes sorokban való osztályba sorolásának és kiszámításának feltételét. A meghatározás alapja a cikkáfacsoportjának, áfacsoportjának, áfakódjának és a keresési definícióban meghatározott egyéb feltételeknek a konfigurációja.

Az egyiptomi bevételi és kiadási számlakönyvi jelentések olyan oszlopokat tartalmaznak, amelyek adott tranzakcióosztályozásnak felelnek meg, például az Egyiptomhoz kapcsolódó művelettípusok, terméktípusok és dokumentumtípusok. Ahelyett, hogy ezeket az új osztályozásokat új bejegyzési adatként határoznák meg a tranzakciók feladása során, az osztályozásokat a **Konfigurációk** > **Alkalmazásspecifikus paraméterek** > **Beállítás** pontban bevezetett különböző keresések alapján határozzák meg az egyiptomi áfajelentésekkel szemben támasztott követelményeknek való megfelelés érdekében. 

![Alkalmazásspecifikus paraméterek oldal](media/egypt-vat-declaration-setup1.png)

A következő keresési konfigurációk a beszerzési és értékesítési áfakönyvek tranzakcióinak osztályozására használhatók:

- **PurchaseItemTypeLookup** > O oszlop: cikk típusa
- **VATRateTypeLookup** > B oszlop: adótípus
- **VATRateTypeLookup** > C oszlop: táblacikk típusa
- **PurchaseOperationTypeLookup** > A oszlop: dokumentumtípus
- **CustomerTypeLookup** > A oszlop: Dokumentumtípus
- **SalesOperationTypeLookup** > N oszlop: művelettípus
- **SalesItemTypeLookup** > O oszlop: cikk típusa

A következő lépések alapján beállíthatja a VAT bevallást és vonatkozó könyvekkel kapcsolatos jelentéseket generáló különféle kereséseket. 

1. Az **Elektronikus jelentéskészítés** munkaterületen a **Konfiguráció** > **Beállítás** kiválasztásával állítsa be az áfatranzakció azonosítására vonatkozó szabályokat az áfa-visszatérítési űrlap kapcsolódó mezőjében.
2. Válassza ki az aktuális verziót, és a **Keresések** gyorslapon válassza ki a keresési nevet. Például: **SalesItemTypeLookup**. Ez a keresés azonosítja az adóhatóság által előírt áfakönyv-besorolások listáját.
3. Válassza ki a **Feltételek** gyorslapon a **Hozzáadás** lehetőséget, és a **Keresés eredménye** oszlopban az új sorban válassza ki azt a kapcsolódó sort, amely az **O oszlopban** található osztályozásnak felel meg.
4. Az **Áfacsoport** oszlopban válassza ki az osztályozás azonosításához használt áfacsoportot. Például: **Belföldi értékesítési számla**. Akkor is használhatja a cikkáfacsoportot, az áfakódok, illetve a faattribútumok kombinációját, ha a konfigurációt más módon határozza meg. 
5. A **Név** oszlopban válassza ki az áfatranzakció osztályozását.
6. Ismételje meg a 3–5. lépést az összes elérhető kereséssel.
7. Válassza a **Hozzáadás** lehetőséget a végső rekordsor beemeléséhez, és a **Keresés eredménye** oszlopban válassza a **Nem alkalmazható** lehetőséget. 
8. A többi oszlopban válassza a **Nem üres** lehetőséget. 
9. Az **Állapot** mezőben válassza ki a **Befejeződött** értéket.
10. Válassza a **Mentés** lehetőséget, majd zárja be az **Alkalmazáspecifikus paraméterek** lapot.

> [!NOTE]
> Az utolsó, **Nem alkalmazható** rekord hozzáadásakor a következő szabályt kell definiálni: Ha az áfacsoport, a cikkáfacsoport, az áfakód és az argumentumként átadott név nem felel meg a korábbi szabályoknak, akkor a tranzakciók nem szerepelnek az áfakönyvben. Bár ez a szabály nem használatos a jelentés generálása során, a szabály segít elkerülni a hibákat a jelentésgenerálóban, ha hiányzik egy szabálykonfiguráció.

Az alábbi táblák a leírt keresési konfigurációk javasolt konfigurációját mutatják be. 

**SalesItemTypeLookup**

| Keresési eredmény         | Sor | Áfacsoport    | Cikkáfacsoport    | Áfakód (kód) | Név                  |
|-----------------------|------|--------------------|-------------------------|-----------------|-----------------------|
| Belföldi              | 1    | VAT_LOCAL          | *Nem üres*             | *Nem üres*     | Értékesítés                 |
| Belföldi              | 2    | VAT_LOCAL          | *Nem üres*             | *Nem üres*     | SalesCreditNote       |
| Belföldi              | 3    | VAT_FINALC         | *Nem üres*             | *Nem üres*     | Értékesítés                 |
| Belföldi              | 4    | VAT_FINALC         | *Nem üres*             | *Nem üres*     | SalesCreditNote       |
| Belföldi              | 5    | VAT_PUBLIO         | *Nem üres*             | *Nem üres*     | Értékesítés                 |
| Belföldi              | 6    | VAT_PUBLIO         | *Nem üres*             | *Nem üres*     | SalesCreditNote       |
| Export                | 7    | VAT_EXPORT         | *Nem üres*             | *Nem üres*     | Értékesítés                 |
| Export                | 8    | VAT_EXPORT         | *Nem üres*             | *Nem üres*     | SalesCreditNote       |
| Gép és berendezés | 9    | *Nem üres*        | VAT_M&E                 | *Nem üres*     | Értékesítés                 |
| Gép és berendezés | 10   | *Nem üres*        | VAT_M&E                 | *Nem üres*     | SalesCreditNote       |
| Gépalkatrészek        | 11   | *Nem üres*        | ÁFA_ALKATRÉSZEK               | *Nem üres*     | Értékesítés                 |
| Gépalkatrészek        | 12   | *Nem üres*        | ÁFA_ALKATRÉSZEK               | *Nem üres*     | SalesCreditNote       |
| Mentességek            | 13   | VAT_EXE            | *Nem üres*           | *Nem üres*     | SaleExempt            |
| Mentességek            | 14   | VAT_EXE            | *Nem üres*           | *Nem üres*     | SalesExemptCreditNote |
| Nem alkalmazható        | 15   | *Üres*            | *Üres*                 | VAT_ADJ         | *Nem üres*           |
| Nem alkalmazható        | 16   | *Nem üres*        | *Nem üres*             | *Nem üres*     | *Nem üres*           |

 **SalesOperationTypeLookup**

| Keresési eredmény  | Sor | Cikkáfacsoport    | Adókód    | Név                  |
|----------------|------|-------------------------|-------------|-----------------------|
| Áru          | 1    | VAT_GOODS               | *Nem üres* | Értékesítés                 |
| Áru          | 2    | VAT_GOODS               | *Nem üres* | SalesCreditNote       |
| Áru          | 3    | VAT_GOODS               | *Nem üres* | SaleExempt            |
| Áru          | 4    | VAT_GOODS               | *Nem üres* | SalesExemptCreditNote |
| Szolgáltatások       | 5    | VAT_SERV                | *Nem üres* | Értékesítés                 |
| Szolgáltatások       | 6    | VAT_SERV                | *Nem üres* | SalesCreditNote       |
| Szolgáltatások       | 7    | VAT_SERV                | *Nem üres* | SaleExempt            |
| Szolgáltatások       | 8    | VAT_SERV                | *Nem üres* | SalesExemptCreditNote |
| Helyesbítések    | 9    | *Üres*                 | VAT_ADJ     | Értékesítés                 |
| Helyesbítések    | 10   | *Üres*                 | VAT_ADJ     | SalesCreditNote       |
| Nem alkalmazható | 11   | *Nem üres*             | *Nem üres* | *Nem üres*           |

**PurchaseItemTypeLookup**

| Keresési eredmény          | Sor | Cikkáfacsoport    | Adókód    | Név                     |
|------------------------|------|-------------------------|-------------|--------------------------|
| Áru                  | 1    | VAT_GOODS               | *Nem üres* | Beszerzés                 |
| Áru                  | 2    | VAT_GOODS               | *Nem üres* | PurchaseCreditNote       |
| Szolgáltatások               | 3    | VAT_SERV                | *Nem üres* | Beszerzés                 |
| Szolgáltatások               | 4    | VAT_SERV                | *Nem üres* | PurchaseCreditNote       |
| Gép és berendezés  | 5    | VAT_M&E                 | *Nem üres* | Beszerzés                 |
| Gép és berendezés  | 6    | VAT_M&E                 | *Nem üres* | PurchaseCreditNote       |
| Gépalkatrészek         | 7    | ÁFA_ALKATRÉSZEK               | *Nem üres* | Beszerzés                 |
| Gépalkatrészek         | 8    | ÁFA_ALKATRÉSZEK               | *Nem üres* | PurchaseCreditNote       |
| Mentességek             | 9    | VAT_EXE                 | *Nem bank*  | PurchaseExempt           |
| Mentességek             | 10   | VAT_EXE                 | *Nem üres* | PurchaseExemptCreditNote |
| Nem alkalmazható         | 11   | *Nem üres*             | *Nem üres* | *Nem üres*              |

**PurchaseOperationTypeLookup**

| Keresési eredmény  | Sor | Áfacsoport  | Adókód    | Név                     |
|----------------|------|------------------|-------------|--------------------------|
| Belföldi       | 1    | VAT_LOCAL        | *Nem üres* | Beszerzés                 |
| Belföldi       | 2    | VAT_LOCAL        | *Nem üres* | PurchaseCreditNote       |
| Belföldi       | 3    | VAT_LOCAL        | *Nem üres* | PurchaseExempt           |
| Belföldi       | 4    | VAT_LOCAL        | *Nem üres* | PurchaseExemptCreditNote |
| Importálva       | 5    | VAT_IMPORT       | *Nem üres* | Beszerzés                 |
| Importálva       | 6    | VAT_IMPORT       | *Nem üres* | PurchaseCreditNote       |
| Importálva       | 7    | VAT_IMPORT       | *Nem üres* | PurchaseExempt           |
| Importálva       | 8    | VAT_IMPORT       | *Nem üres* | PurchaseExemptCreditNote |
| Helyesbítések    | 9    | *Üres*          | VAT_ADJ     | PurchaseCreditNote       |
| Helyesbítések    | 10   | *Üres*          | VAT_ADJ     | Beszerzés                 |
| Nem alkalmazható | 11   | *Nem üres*      | *Nem üres* | *Nem üres*              |

**CustomerTypeLookup**

|    Keresési eredmény    | Sor | Áfacsoport |
|---------------------|------|-----------------|
| Szervezet        |  1   | VAT_LOCAL       |
| Szervezet        |  2   | VAT_EXPORT      |
| Szervezet        |  3   | VAT_EXE         |
| Végfelhasználó      |  4   | VAT_FINALC      |
| Nyilvános szervezet |  5   | VAT_PUBLIO      |
| Nem alkalmazható      |  6   | *Nem üres*     |

**VATRateTypeLookup**

| Keresési eredmény  | Sor | Áfakód (kód) |
|----------------|------|-----------------|
| GeneralGoods   | 1    | VAT_ST          |
| GeneralGoods   | 2    | VAT_RD          |
| FirstTable     | 3    | *Nem üres*     |
| SecondTable    | 4    | *Nem üres*     |
| Nem alkalmazható | 5    | *Nem üres*     |


## <a name="set-up-general-ledger-parameters"></a>Főkönyvi paraméterek beállítása

Az áfa-visszatérítési űrlap jelentéseinek Microsoft Excel formátumban való létrehozásához definiáljon ER-formátumot a **Főkönyvi paraméterek** oldalon.

1. Lépjen az **Adó** > **Beállítás** > **Főkönyvi paraméterek** pontra.
2. Az **Áfa** lapon az **Adózási beállítások** szakasz **Áfa-bevallás formátumleképezése** mezőben válassza az **Áfabevallás Excel (EG)** lehetőséget. Ha üresen hagyja ezt a mezőt, a normál áfajelentés SSRS-formátumban jön létre.
3. Válassza ki a **Kategóriahierarchia** lehetőséget. Ez a kategória lehetővé teszi a vámtarifakódot a Külkereskedelem lap tranzakcióiban, lehetővé téve a felhasználók számára az áruk és szolgáltatások kiválasztását és osztályozását. Ennek az osztályozásnak a részletes leírása az értékesítési és beszerzési tranzakciók jelentéseiben található. Ez a konfiguráció nem kötelező.

![Bevallás űrlapja](media/egypt-vat-declaration-setup2.png)


## <a name="generate-a-vat-return-report"></a>Áfa-visszatérítési jelentés létrehozása
Egy időszak áfa-visszatérítési jelentésének elkészítési és benyújtási folyamata az áfakifizetési feladat során feladott áfakifizetési tranzakciókon alapul. Az áfakifizetéssel és az áfabevallással kapcsolatos további tudnivalókat lásd: [Áfa áttekintése](../general-ledger/indirect-taxes-overview.md).

Az áfabevallási jelentés létrehozásához kövesse az alábbi lépéseket.

1. Lépjen az **Adó** > **Nyilatkozatok** > **Áfa** > **Áfa kimutatása a kiegyenlítési időszakhoz** vagy **Áfa kiegyenlítése és feladása** elemre.
2. Válassza ki a **Kifizetési időszak** lehetőséget.
3. Válassza ki a kezdő dátumot, majd válassza ki az áfafizetés verzióját.
5. Válassza ki az **OK** lehetőséget. 
6. Adja meg az előző időszakból származó jóváírási összeget (ha szükséges) vagy hagyja az összeget nullaként.
7. A **Jelentések részletei** mezőben válasszon egyet a következő elérhető lehetőségek közül. 
   - **Beszerzési áfakönyv**: A beszerzésiadó-tranzakciók részleteit tartalmazó jelentés készítése.
   - **Értékesítési áfakönyv**: Az értékesítésiadó-tranzakciók részleteit tartalmazó jelentés készítése.
   - **Áfabevallás**: Csak az áfa-visszatérítési űrlapot hozza létre.
8. Adja meg annak a személynek a nevét, aki regisztrálva van az űrlap hozzárendeléséhez.
9. Válassza ki a nyelvet. Minden jelentés fordítása **en-us** és **ar-eg**.
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]


