---
title: Juttatási konstrukció létrehozása
description: Juttatási konstrukciókat állíthat be a Dynamics 365 Human Resources rendszerben.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitPlanListPage, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 05d08862b880271fb4842bd7e77f04208f9c0bed
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112846"
---
# <a name="create-a-benefits-plan"></a>Juttatási konstrukció létrehozása

Ez a cikk bemutatja. hogyan lehet juttatási konstrukciókat beállítani a Dynamics 365 Human Resources alkalmazásban.

1. A **Juttatások kezelése** munkaterület **Konstrukciók** részén válassza a **Juttatási konstrukciók** elemet.

2. Válassza az **Új** lehetőséget.

3. Az **Általános** lapon adja meg a megfelelő értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Konstrukció** | A konstrukció egyedi azonosítója. |
   | **Leírás** | A konstrukció leírása. |
   | **Konstrukció típusa** | Amikor új konstrukciót hoz létre, meg kell adnia a konstrukció típusát. A konstrukciótípus a meghatározott típusú juttatások magas szintű csoportosítása. A konstrukciótípusok azt határozzák meg, hogy az alkalmazottak beléphetnek-e több adott típusú konstrukcióba, hogy a kapcsolattartók kedvezményezettek vagy függők felek-e, valamint meghatározzák a fedezeti beállításokat. Létrehozhat új egyéni konstrukciókat, amelyek megfelelnek a juttatási ajánlatainak. A konstrukciótervek fő típusai a következők: <ul><li>401K</li><li>ADD</li><li>Fogászati</li><li>Fitnesz</li><li>FSA</li><li>Élet</li><li>LTD</li><li>Orvosi</li><li>PTO</li><li>STD</li><li>Látás</li></ul> |
   | **Konstrukció típuskódja** | A konstrukció típusának kódja. |
   | **Program** | Azt a programot határozza meg, amelyet választhatóan hozzá lehet rendelni a konstrukcióhoz. |
   | **Csomag** | Azt a csomagot határozza meg, amelyet választhatóan hozzá lehet rendelni a konstrukcióhoz. |
   | **Fő** | Megadja, hogy a konstrukció az alapkonstrukció-e azon a csomagon belül, amelyhez hozzárendelték. |
   | **Állapot** | A juttatási konstrukció aktuális állapotát jelzi. Az alapértelmezett érték az Aktív. Ha az állapotot Inaktív értékűre állítja, a konstrukció nem lesz választható a belépés során. |
   | **Érvényesség kezdő dátuma és időpontja** | Az a dátum és időpont, amikor a konstrukció érvényessége kezdődik. Az alapértelmezett érték az aktuális rendszerdátum. |
   | **Érvényesség záró dátuma és időpontja** | Az a dátum és időpont, amikor a konstrukció érvényessége befejeződik (az állapot értéke Inaktív). Az alapértelmezett érték a 2154. 12. 31., ami a „soha” megfelelője. |

4. A **Konfiguráció** lapon adja meg a megfelelő értékeket a következő mezőkben a létrehozandó konstrukció típusától függően:

   | Konstrukció típusa | Mező | Leírás |
   | --- | --- | --- |
   | Orvosi (orvosi, fogászati, látás, HMO) | COBRA | Megadja, hogy a konstrukció megfelel-e COBRA (Consolidated Omnibus Budget Reconciliation Act) törvénynek. |
   | Orvosi (orvosi, fogászati, látás, HMO) | HIPAA | Megadja, hogy a konstrukció megfelel-e HIPAA (Health Insurance Portability and Accountability Act) törvénynek. |
   | <ul><li>Orvosi (orvosi, fogászati, látás, HMO)</li><li>Egyéb (PTO, fitnesz)</li><li>Egyéb</li><li>Hosszú távú fogyatékosság</li><li>ADD (alapszintű, önkéntesség)</li><li>Megtakarítások (például 401(k))</li><li>FSA</li></ul> | Adózás előtt jogosult | Megadja, hogy a konstrukcióhoz be lehet-e állítani hozzájárulásokat az adók alkalmazása előtt. |
   | <ul><li>Orvosi (orvosi, fogászati, látás, HMO)</li><li>Egyéb (PTO, fitnesz)</li><li>Hosszú távú fogyatékosság</li><li>ADD (alapszintű, önkéntesség)</li><li>Megtakarítások (például 401(k))</li><li>FSA</li></ul> | Adózás után jogosult | Megadja, hogy a konstrukcióhoz be lehet-e állítani hozzájárulásokat az adók alkalmazása után. |
   | <ul><li>Orvosi (orvosi, fogászati, látás, HMO)</li><li>Egyéb (PTO, fitnesz)</li><li>Hosszú távú fogyatékosság</li><li>ADD (alapszintű, önkéntesség)</li><li>Megtakarítások (például 401(k))</li><li>FSA</li></ul> | Hozzájáruló | Megadja, hogy ki járul hozzá a konstrukcióhoz: az alkalmazott, a munkáltató vagy mindkettő. |
   | <ul><li>Hosszú távú fogyatékosság</li><li>ADD (alapszintű, önkéntesség)</li></ul> | Minimális fedezet | A konstrukcióhoz szükséges biztosítási fedezet minimális összege. |
   | <ul><li>Hosszú távú fogyatékosság</li><li>ADD (alapszintű, önkéntesség)</li></ul> | Maximális fedezet | A konstrukcióhoz szükséges biztosítási fedezet maximális összege. |
   | <ul><li>Hosszú távú fogyatékosság</li><li>ADD (alapszintű, önkéntesség)</li></ul> | Fedezeti növekmények használata | Megadja, hogy kell-e ellenőrizni, hogy a fedezeti összeg megfelel-e egy érvényes növekményes összegnek. |
   | <ul><li>Hosszú távú fogyatékosság</li><li>ADD (alapszintű, önkéntesség)</li></ul> | Növekmény összege | A konstrukció biztosítási fedezetének növekményes összege. Ha például a növekményes összeg 1000, akkor az alkalmazottnak nem lehet $200 500 összegű biztosítása, hanem a $201 000 összegre kell felkerekíteni vagy a $200 000 összegre kell lekerekíteni azt. |
   | <ul><li>Hosszú távú fogyatékosság</li><li>ADD (alapszintű, önkéntesség)</li></ul> | Növekmény iránya | Megadja a kerekítés irányát – vagy felfelé, vagy lefelé –, amikor a fedezeti összeg nem elégíti ki a növekményösszeg értékét. |
   | ADD (alapszintű, önkéntesség) | Biztosíthatóság igazolása | Megadja, hogy az alkalmazottnak kell-e igazolnia a biztosíthatóságát. |
   | ADD (alapszintű, önkéntesség) | Összeg | A könyvelési pénznem összege. Ez a mező csak akkor aktív, ha a be van jelölve a Biztosíthatóság igazolása jelölőnégyzet. |
   | <ul><li>Megtakarítások (például 401(k))</li><li>FSA</li></ul> | Minimális éves hozzájárulás | A konstrukcióhoz szükséges hozzájárulás minimális összege. |
   | <ul><li>Megtakarítások (például 401(k))</li><li>FSA</li></ul> | Maximális éves hozzájárulás | A konstrukcióhoz szükséges hozzájárulás maximális összege. |
   | Megtakarítások (például 401(k)) | Munkáltatói maximális éves összeg | Az a maximális összeg, amellyel a munkáltató hozzájárulhat az alkalmazotti megtakarítási konstrukciójához egy juttatási időszakban. A mező használatához be kell jelölnie a Munkáltató megfelelés jelölőnégyzetet. |
   | Megtakarítások (például 401(k)) | Munkáltatói megfelelés | Megadja, hogy a munkáltató hozzájárul-e az alkalmazott megtakarítási konstrukciójához. |
   | Megtakarítások (például 401(k)) | Munkáltatói megfelelés százaléka | Az alkalmazotti hozzájárulásnak az a százaléka, amelyet a munkáltató fog fedezni. |
   | Megtakarítások (például 401(k)) | Munkáltatói megfelelés korlátja | A munkáltató által fedezett maximális százalék. Ha például a munkáltató az alkalmazott fizetésének 6%-áig fogja fedezni az alkalmazotti hozzájárulások 100%-át, akkor a munkáltatói megfelelés 6% lesz. |

5. A **Beállítás** lapon adja meg a megfelelő értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Regisztráció engedélyezése/folytatása** | Megadja, hogy az alkalmazottak beléphetnek-e a konstrukcióba, ha megfelelnek a jogosultsági követelményeknek.</br></br>A Nem érték megadása esetén a konstrukció nem lesz elérhető az alkalmazottak számára, amikor feldolgozza a jogosultságot. |
   | **Automatikus regisztráció előző év alapján** | Megadja, hogy a rendszer automatikusan regisztrálja-e a jogosult alkalmazottakat a konstrukcióba, ha az előző évben regisztrálva voltak. |
   | **Automatikus regisztráció alapértelmezés szerint** | Megadja, hogy kell-e választani alapértelemzés szerint konstrukciót a belépéshez. A konstrukció nem kötelező, ezért az alkalmazott módosíthatja az alapértelmezett választást. |
   | **Lezárva új regisztrációk elől** | Megadja, hogy a konstrukciót azokra a jogosult alkalmazottakra kell-e korlátozni, akik az előző évben léptek be a konstrukcióra. |
   | **Kötelező konstrukció** | Megadja, hogy a rendszer automatikusan belépteti-e az alkalmazottakat a konstrukcióba. Az alkalmazottak nem módosíthatják a belépésre vonatkozó beállítást. |
   | **Érvényességi dátum** | Az a dátum, amikor a konstrukció létre lett hozva a vállalatban. |
   | **Szállítói számla** (juttatás szállítója) | Az a szállító, amelynek a vállalat prémiumot fizet a konstrukcióért. |
   | **Név** (juttatás szállítója) | A szállító neve. |
   | **Szállítói hivatkozás** (juttatás szállítója) | A konstrukcióhoz tartozó szállító hivatkozása. Például a vállalat csoportkonstrukciójának száma. |
   | **Másodlagos hivatkozás** (juttatás szállítója) | A konstrukcióhoz tartozó szállító másodlagos hivatkozása. Például a vállalat számlaszáma. |
   | **Pénznem** (juttatás szállítója) | A szállítónak fizetett prémiumokhoz használt pénznem. |
   | **Költségszámla** (juttatás szállítója) | A konstrukcióhoz tartozó prémiumokhoz használt főkönyvi számla. |
   | **Szállítói számla** (juttatás adminisztrátora) | Az a szállító, amelynek a vállalat fizet a konstrukció adminisztrálásáért. Ha a konstrukció önkiszolgáló adminisztrálású, hagyja üresen ezt a mezőt. |
   | **Név** (juttatás adminisztrátora) | A juttatás adminisztrátori szállítójának neve. |
   | **Szállítói hivatkozás** (juttatás adminisztrátora) | A konstrukcióhoz tartozó adminisztrátori szállító hivatkozása. |
   | **Másodlagos hivatkozás** (juttatás adminisztrátora) | A konstrukcióhoz tartozó adminisztrátori szállító másodlagos hivatkozása. |
   | **Pénznem** (juttatás adminisztrátora) | A juttatási adminisztrátornak fizetett összegekhez használt pénznem. |
   | **Költségszámla** (juttatás adminisztrátora) | A konstrukció adminisztrációjához kapcsolódó költségek költségszámlájaként használt főkönyvi számla. |

6. A **Szűrők** lapon lehetőség van a szükség szerinti szűrésre. A szűrés a következő mezők szerint végezhető el:

   - **Üzleti egység**
   - **Részleg**
   - **Jogi személy**
   - **Helyszín**
   - **Beosztás**

7. A **Jogosultsági szabályok** lapon adja meg a megfelelő értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Sor száma** | Jogosultsági szabály sorának száma. |
   | **Jogosultsági szabály** | A juttatási konstrukcióra alkalmazandó jogosultsági szabály. Ez a jogosultsági szabály lesz alkalmazva a megfelelő művelettípusra, és lesz társítva a megadott fedezeti várakozási időszakhoz és a levonásokhoz. |
   | **Művelettípus** | A jogosultsági szabályra alkalmazandó művelet: juttatásokok regisztrálása vagy juttatások lejárata. |
   | **Fedezet várakozási időszaka** | A Várakozási időszakok képernyőről származó érték. A fedezet várakozási időszaka határozza meg azon napok vagy hónapok számát, ameddig az alkalmazott várja a juttatás fedezetét vagy a juttatás lejáratát a jogosultsági szabályban és a művelettípusban található feltételek alapján. |
   | **Levonás várakozási időszaka** | A Várakozási időszakok képernyőről származó érték. A levonás várakozási időszaka határozza meg azon napok vagy hónapok számát, ameddig az alkalmazott várja a juttatás levonását a fizetéséből a jogosultsági szabályban és a művelettípusban található feltételek alapján. |

8. Válassza a **Mentés** lehetőséget.

## <a name="view-enrolled-workers"></a>Belépett dolgozók megtekintése

Megtekintheti a választott juttatási konstrukcióba belépett dolgozókat.

1. A **Juttatások kezelése** munkaterület **Konstrukciók** részén válassza a **Juttatási konstrukciók** elemet.

2. Válassza a **Kedvezményezett dolgozók** lehetőséget.

## <a name="attach-coverage-options"></a>Fedezeti beállítások csatolása

Fedezeti beállításokat adhat hozzá a kiválasztott juttatási konstrukcióhoz. A fedezeti beállítások megadása összekapcsolja a díj és a levonás beállítását egy fedezeti lehetőségbe.  Példa: Egészségügyi konstrukció esetében a felhasználó kiválaszthatja a Családi fedezet lehetőséget.  Ezután kiválasztja a családi díjat a hozzárendelt konstrukcióhoz (amely a díj beállításánál lett megadva), valamint a levonást a hozzárendelt konstrukcióhoz (amely a díj beállításánál lett megadva). Ez adja meg a választott fedezet költségét a munkáltató és az alkalmazott számára. Ezután megismétli a műveletet az Alkalmazott + 1 fedezet vagy Alkalmazott fedezet esetében.

1. A **Juttatások kezelése** munkaterület **Konstrukciók** részén válassza a **Juttatási konstrukciók** elemet.

2. Válassza a **Fedezeti beállítások csatolása** lehetőséget.

## <a name="override-eligibility-rules"></a>Jogosultsági szabályok felülbírálása

A konstrukciókba felvehet olyan dolgozókat, akik kivételnek számítanak a jogosultsági szabályok alól. Minden felvett dolgozó jogosult lesz a juttatási konstrukcióra.

1. A **Juttatások kezelése** munkaterület **Konstrukciók** részén válassza a **Juttatási konstrukciók** elemet.

2. Válassza a **Jogosultsági szabály felülbírálása** lehetőséget.

## <a name="view-attached-periods"></a>Hozzárendelt időszakok megjelenítése

Megtekintheti az elérhető juttatási időszakok listáját.

1. A **Juttatások kezelése** munkaterület **Konstrukciók** részén válassza a **Juttatási konstrukciók** elemet.

2. Válassza az **Időszakok** lehetőséget.

## <a name="view-plan-information"></a>Konstrukció adatainak megtekintése

A konstrukcióhoz megadhat leírást, amely segít az alkalmazottaknak a juttatások kiválasztásában. Az itt megadott konstrukcióadatok megjelennek az Alkalmazotti önkiszolgáló rendszerben, amikor a konstrukcióra viszik a mutatót a fedezeti lehetőségek listáján.

1. A **Juttatások kezelése** munkaterület **Konstrukciók** részén válassza a **Juttatási konstrukciók** elemet.

2. Válassza a **Konstrukció adatai** lehetőséget.

## <a name="view-flex-credit-programs"></a>Rugalmas jóváírási programok megtekintése

1. A **Juttatások kezelése** munkaterület **Konstrukciók** részén válassza a **Juttatási konstrukciók** elemet.

2. Válassza a **Rugalmas jóváírási programok** lehetőséget.
