---
title: Áfabevallás (Németország)
description: Ez a témakör azt írja le, hogyan lehet a hivatalos XML-formátumban előlegbevallást (áfa- és áfabevallást) létrehozni Németország számára.
author: anasyash
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: ff52963c03ec2eb662eb0c20ef2a960e3b999167
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879532"
---
# <a name="vat-declaration-germany"></a>Áfabevallás (Németország)

[!include [banner](../includes/banner.md)]

Ez a témakör azt írja le, hogyan lehet a hivatalos XML-formátumban előlegbevallást (áfa- és áfabevallást) létrehozni Németország számára. Ez a cikk azt is bemutatja, hogy hogyan lehet az áfabevallást előnézetben látni a következőben:Microsoft Excel

A jelentés automatikus létrehozásához hozzon létre elég áfakódot ahhoz, hogy az előleg áfabevallásán minden egyes rovatban külön áfakönyvelés legyen. Ezenkívül az előzetes áfabevallás elektronikus jelentési (ER) formátumának alkalmazásspecifikus paramétereiben az áfakódokat hozzá kell társítani az áfabevallás mezőihez keresési eredményekhez.

Németország esetében be kell állítania a **Jelentés mezőkeresést**. Az alkalmazásspecifikus paraméterek beállításával kapcsolatos további [tudnivalókat](#set-up-application-specific-parameters-for-vat-declaration-fields) lásd a Cikk áfabevallási mezők alkalmazásspecifikus paramétereinek beállítása című részében.

A következő táblázatban a "Keresés eredménye" oszlop mutatja azt a keresési eredményt, amely az áfabevallási formátumban egy adott áfabevallási sorhoz előre konfigurálva van. Ezzel az információval lehet megfelelően társítani az áfakódokat a keresési eredményhez, majd az áfabevallás sorhoz.

### <a name="vat-declaration-overview"></a><a name="vat-declaration-overview"></a> Áfabevallás áttekintése

Az előleg áfabevallása Németországban a következő adatokat tartalmazza.

**SZAKASZ – SZÁLLÍTÁSOK ÉS EGYÉB SZOLGÁLTATÁSOK**

**Adóköteles értékesítések**

| Sor | Doboz – adóalap | Doboz – adó összege | Leírás                                                                                                                                      | Keresési eredmény                                                                             |
|-----|----------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 20  | 81             | Kód nélkül     | 19 százalékos áfakulcsú adóköteles értékesítés.                                                                                                       | 20-TaxableSalesStandard</br>73-BadDebtsWriteOffStandard (81/50) – mínusz előjellel             |
| 21  | 86             | Kód nélkül     | 7 százalékos áfakulcsú adóköteles értékesítés.                                                                                                        | 21-TaxableSalesReable</br>73-BadDebtsWriteOffRealma (86/50) – mínusz előjellel               |
| 22  | 35             | 36               | Adóköteles értékesítés egyéb adómértékekkel.                                                                                                                | 22- TaxableSalesOtherRates</br>73-BadDebtsWriteOffOtherRates (35/36/50) – mínusz előjellel      |
| 23  | 77             | *Nincs adóösszeg*  | A német áfatörvény 24. törvénye (UStG) 24. törvényének megfelelően az olyan vevőknek történő szállítás, amelyek áfaazonosító számmal rendelkezik. | 23-EUSalesAgeRate24</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50) – mínusz előjellel |
| 24  | 76             | 80               | Azok az értékesítések, amelyekre az áfát be kell fizetni, az UStG szerinti 24 cikk (adóügyi termékek, gyógyszerek és likvid termékek) alapján.                                | 24-SalesAverageRate24</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50)                    |

**Adómentes értékesítés az előzetesen felszámított adó levonásával**

| Sor | Doboz – adóalap | Doboz – adó összege | Leírás                                                                       | Keresési eredmény                       |
|-----|----------------|------------------|-----------------------------------------------------------------------------------|-------------------------------------|
| 26  | 41             | *Nincs adóösszeg*  | Áfaazonosítóval azonosított vevőknek való közösségen belüli szállítások.                       | 26-EUSales                          |
| 27  | 44             | *Nincs adóösszeg*  | Új járművek közösségen belüli szállításai a vásárlóknak, ha nincs áfaazonosítójuk.    | 27-EUSalesNewVehicles               |
| 28  | 49             | *Nincs adóösszeg*  | Új járművek közösségen belüli szállításai a vállalaton kívül.                     | 28-EUSalesNewVehiclesOutsideCompany |
| 29  | 43             | *Nincs adóösszeg*  | Egyéb adómentes értékesítések, amelyekre előzetesen levont adó, például exportszállítások. | 29-ExportOtherTaxFreeSales          |

**Adómentes értékesítés az előzetesen felszámított adó levonása nélkül**

| Sor | Doboz – adóalap | Doboz – adó összege | Leírás                                            | Keresési eredmény                           |
|-----|----------------|------------------|--------------------------------------------------------|-----------------------------------------|
| 30  | 48             | *Nincs adóösszeg*  | Adómentes értékesítés, amely nem adólevonást jelent. | 30-TaxFreeSalesWithoutInputTaxDeduction |

**Közösségi beszerzések**

| Sor | Doboz – adóalap | Doboz – adó összege | Leírás                                                                                                                   | Keresési eredmény                                                    |
|-----|----------------|------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| 33  | 91             | *Nincs adóösszeg*  | Egyes objektumok és befektetési arany adómentes közösségen belüli beszerzései.                                                    | 33-TaxFreeEUPurchase                                             |
| 34  | 89             | Kód nélkül     | Közösségen belüli adóköteles beszerzések 19 százalékos adókulcson.                                                             | 34-EUPurchaseStandard</br>34-UseTaxEUPurchaseStandard (89/61)        |
| 35  | 93             | Kód nélkül     | Közösségen belüli adóköteles beszerzések 7 százalékos adókulcson.                                                              | 35-EUPurchaseReűs</br>35-UseTaxEUPurchaseRexo (93/61)          |
| 36  | 95             | 98               | Egyéb adómértékekkel, közösségi adóköteles beszerzések                                                                      | 36-EUPurchaseOtherRates</br>36-UseTaxEUPurchaseOtherRates (95/98/61) |
| 37  | 94             | 96               | Az olyan szállítóktól származó adóköteles közösségen belüli beszerzések, amelyek nem tartalmaznak áfaazonosító számot, az általános adómkulcs szerint. | 37-EUPurchaseVehicles</br>37-UseTaxEUPurchaseVehicles (94/96/61)     |

**SZAKASZ – KEDVEZMÉNYEZETT ADÓSKÉNT**

| Sor | Doboz – adóalap | Doboz – adó összege | Leírás                                                                        | Keresési eredmény                                                                                        |
|-----|----------------|------------------|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 40  | 46             | 47               | Egyéb szolgáltatás a közösség egyéb szolgáltatásainak stb. alapján.        | 40-KedvezményezettTaxDebtor</br>40-UseTaxBeneficiaryTaxDebtor (46/47/66)                                                                              |
| 41  | 73             | 74               | A 13b. (2)-es szakaszba eső értékesítések UStG 3.                               | 41-KedvezményezettTaxDebtorRealEstateTransfer</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67) |
| 42  | 84             | 85               | A 13b. (2)-es szakaszba eső egyéb szolgáltatások 1, 2 és 4– 12 UStG. | 42-KedvezményezettTaxDebtor Más</br>42-UseTaxBeneficiaryTaxDebtorMás (84/85/67)                           |

**SZAKASZ – KIEGÉSZÍTŐ INFORMÁCIÓK AZ ÉRTÉKESÍTÉSRŐL**

| Sor | Doboz – adóalap  | Doboz – adó összege | Leírás                                                                                                | Keresési eredmény                                                                                    |
|-----|-----------------|------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| 48  | 42              | *Nincs adóösszeg*  | Az első vevő által szállítás háromszögügyletek esetén.                   | 48-DeliveriesFirstCustomerEUTriangular                                                           |
| 49  | 60              | *Nincs adóösszeg*  | A teljesítő értékesítés adóköteles értékesítései, amelyekért a szolgáltatás címzettje tartozik az adóval. | 49-SalesServicesReverseCharge                                                                    |
| 50  | 21              | *Nincs adóösszeg*  | Egyéb nem adóköteles szolgáltatások.                                                                                | 50-OtherServicesNonTaxable                                                                       |
| 51  | 45              | *Nincs adóösszeg*  | Egyéb nem adóköteles értékesítés, ha a teljesítmény helye nem Németországban van.                                    | 51-OtherSalesnonTaxable                                                                          |
| 52  | *Nincs adóösszeg* | *Nincs adóösszeg*  | Áfa                                                                                                       | 20. sor + 21. sor + 22. sor + 2. sor 4. sor + 34. sor + 35. sor + 36. sor + 37. sor + 40. sor + 41. sor + 42. sor |

**SZAKASZ – LEVONHATÓ BEMENETI ADÓ**

| Sor | Doboz – adó összege | Leírás                                                                                                | Keresési eredmény                                                                                                                                                                |
|-----|------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 55  | 66               | Egyéb vállalatoktól, szolgáltatásokból és közösségen belüli háromszögtranzakciókból származó adóösszegek bevitele.     | 55-InputTax 40-UseTaxBeneficiaryTaxDebtor (46/47/66)</br>74-BadDebtsWriteOffInputTax (66/37) – mínusz előjellel                                                                   |
| 56  | 61               | Bemeneti adóösszegek a közösségen belüli árubeszerzésből.                                           | 56-InputTaxEUPurchase 34-UseTaxPURchaseStandard (89/61)</br>35-UseTaxEUPurchaseRexo (93/61)</br>36-UseTaxEUPurchaseOtherRates (95/98/61)</br>37-UseTaxEUPurchaseVehicles (94/96/61) |
| 57  | 62               | Felmerült import áfa.                                                                                 | 57-InputTaxImport                                                                                                                                                            |
| 58  | 67               | Szolgáltatások adóbevallási összegei az UStG 13b jelentésében.                                        | 58-InputTaxServices</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67)</br>42-UseTaxBeneficiaryTaxDebtorMás (84/85/67)                                                 |
| 59  | 63               | Az általános átlagmértékek alapján számított bemeneti adóösszegek.                                  | 59-InputTaxAgeRates</br>74-BadDebtsWriteOffInputTaxTakageRates (63/37) – mínusz előjellel                                                                                    |
| 60  | 59               | Adólevonás a vállalaton és kisvállalaton kívüli új járművek közösségen belüli szállítására. | 60-InputTaxXOPurchaseNewVehicles</br>74-BadDebtsWriteOffInputTaxPURchaseNewVehicles (59/37) – mínusz előjellel                                                                  |
| 61  | 64               | Az előzetesen levont adó javítása                                                                     | 61-InputTaxCorrection                                                                                                                                                        |
| 62  | \-               | A fennmaradó összeg.                                                                                      | 52. sor – 55. sor – 56. sor – 57. sor – 58. sor – 50. sor – 60. sor – 61. sor                                                                                                        |

**SZAKASZ – EGYÉB ADÓÖSSZEGEK**

| Sor | Doboz – adó összege | Leírás                                                                                                                                                                                                                                                         | Keresési eredmény                                 |
|-----|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 64  | 65               | Adó, ha az adókulcs megváltozása miatt adózási formát és további adót kell fizetni az adóköteles előlegek után.                                                                                                                                        | 64-AdditionalTaxDueChangeTaxRate              |
| 65  | 69               | A számlákon megjelenő adóösszegek és a 6a. (4)-es szakasz 2., 17. (1.) bekezdésének 7. vagy 25b. (2.) szakaszának megfelelő adóösszegek, illetve a kiszervezési vállalat vagy raktárvezetők tartozásai. | 65-TaxDecreaseCorrection                      |
| 67  | 39               | A fix speciális előlegfizetés levonása állandó hosszabbításhoz Ezt a sort általában csak az adózási időszak utolsó előzetes értesítése tölti ki.                                                                                                  | Felhasználó beviteli paramétere a jelentés párbeszédpanelen |
| 68  | 83               | A fennmaradó áfafizetés és a fennmaradó többlet. Mínusz napló be szerepeljen az összeg előtt.                                                                                                                                                          | 62. sor + 64. sor – 65. sor – 66. sor             |

**SZAKASZ – A CSÖKKENTÉSEK KIEGÉSZÍTŐ ADATAI**

| Sor | Doboz – adóalap | Doboz – adó összege | Leírás                                                            | Keresési eredmény                                                                                                                                                                                                    |
|-----|----------------|------------------|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 73  | 50             | \-               | Az adóalap csökkentése a 20–24. sor alapján.                      | 73-BadDebtsWriteOffStandard (81/50)</br>73-BadDebtsWriteOffRealma (86/50)</br>73-BadDebtsWriteOffOtherRates (35/36/50)</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50)</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50) |
| 74  | \-             | 37               | A levonható bemeneti adó összegének csökkentése az 55., 59. és 60. sorban. | 74-BadDebtsWriteOffInputTax (66/37)</br>74-BadDebtsWriteOffInputTaxTakageRates (63/37)</br>74-BadDebtsWriteOffInputTaxPURchaseNewVehicles (59/37)                                                                     |

#### <a name="purchase-reverse-charge-vat"></a>Beszerzés fordított áfával

Ha az áfakódokat úgy konfigurálja, hogy a bejövő fordított áfát az áfa használatával adja fel, **társítsa** az áfakódokat a név "UseTax" nevű jelentésmező-keresési eredményéhez.

Másik lehetőségként két külön áfakódot is be lehet állítani: egyet az esedékes áfára, egyet pedig az áfalevonásra. Ezután társítsa az egyes kódokat a Jelentés **mező keresésének megfelelő keresési eredményeihez**.

Például a szabványos kulcsú, közösségen belüli adóköteles beszerzések esetén a **UT_S_EU** **áfakódot hozzá kell állítani a forgalmi adóhoz, és azt társítani kell a Jelentés mezőkeresés 34-UseTaxPURchaseStandard** **keresési** eredményéhez. Ebben az esetben az áfakódot **UT_S_EU** 089-es és 061-es mezőkben (a 34. és 56. sor) is tükrözi.

Másik lehetőségként két áfakódot is be lehet állítani:

  - **VAT_S_EU**, amelynek -19 százalékos adókulcs-értéke
  - **InVAT_S_EU**, amelynek 19 százalékos adókulcs-értéke

Ezt követően a jelentés mezőkeresési eredményeihez **a** következő módon társítja a kódokat:

  - Társítsa **·** **VAT_S_EU 34 EUPurchaseStandard** keresési eredményhez.
  - A **InVAT_S_EU** **56-InputTaxPURchase** keresési eredményéhez társítja.

Ebben az esetben az áfakódot **VAT_S_EU** 089-es mező (34. sor) is tükrözi. Az áfakódot InVAT_S_EU **061**-es mezőben (56. sor) is tükrözi.

A fordított áfa beállításával kapcsolatos további tudnivalókat lásd: [Fordított költségek](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Rendszerparaméterek konfigurálása

Áfabevallás létrehozásához be kell állítania a szervezet adószámát (Steuernummer).

1. Nyissa meg a következőt: **Szervezetek adminisztrációja** > **Szervezetek** > **Jogi személyek**.
2. Válassza ki a jogi személyt, majd válassza ki a Regisztrációkhoz **való jogokat**.
3. Válassza ki vagy hozza létre a címet Németországban, majd válassza **a** Hozzáadás lehetőséget a Regisztrációs azonosító **gyorsgombra**.
4. A Regisztráció **típusa mezőben** válassza ki azt a regisztrációtípust, amely Németországhoz tartozik, **és amely a Vállalatazonosító (COID) regisztrációs** kategóriát használja.
5. A Regisztrációs **szám mezőbe** írja be az adószámot.
6. Az Általános **lap** Hatályos **mezőjébe** írja be azt a dátumot, amikor a szám hatályba lép.

A regisztrációs kategóriák és a regisztrációtípusok beállításának további tudnivalókat lásd [: Regisztráció-forgalmi adatok](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-for-germany"></a>Áfabevallás beállítása Németország számára

### <a name="import-er-configurations"></a>ER-konfigurációk importálása

Nyissa meg az Elektronikusjelentés-munkaterületet **·**, és importálja a következő vagy újabb ER-formátumokat:

   - Áfabevallás - Excel (DE).version.101.16.12.xml
   - Áfabevallási XML (DE).version.101.16.xml

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a> Alkalmazásspecifikus paraméterek beállítása az áfabevallási mezőkhöz

Áfabevallás automatikus létrehozásához társítsa az áfakódokat az alkalmazásban, és keresse meg az eredményeket az ER konfigurációban.

> [!NOTE]
> Javasoljuk, hogy engedélyezze az **Alkalmazásspecifikus paraméterek használata az elektronikus jelentéskészítési formátumok előző verzióiból** funkciót a **Szolgáltatáskezelés** munkaterületen. Ha ez a funkció engedélyezve van, akkor az ER-formátum korábbi verziójához beállított paraméterek automatikusan alkalmazhatók ugyanannak a formátumnak a későbbi verzióira is. Ha ez a funkció nincs engedélyezve, akkor explicit módon konfigurálnia kell az alkalmazásspecifikus paramétereket az egyes formátumverziókhoz. Az **Alkalmazásspecifikus paraméterek használata az elektronikus jelentéskészítési formátumok előző verzióiból** funkció a **Szolgáltatáskezelés** munkaterületen a Finance 10.0.23 verziójától érhető el. Az egyes jogi személyek ER-formátumának paramétereinek beállítását lásd: [Az ER-formátum paramétereinek beállítása jogi személyenként](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

A következő lépések szerint adhatja meg, hogy mely áfakódok generálják az áfabevallás mezőit.

1. Menjen a Munkaterületek **elektronikus** > **jelentési szolgáltatásba**, és válassza ki a Jelentéskészítési **konfigurációkat**.
2. Válassza ki az áfabevallás **XML-konfigurációját**, majd **a Konfigurációk \> alkalmazásspecifikus paramétereinek beállítását**.
3. Az Alkalmazásspecifikus **paraméterek lapon**, **a** Keresések gyorslapon válassza a Jelentés **mező keresését**.
4. A Feltételek **gyorscsoporton** állítsa be a következő mezőket az áfakódok és a jelentésmezők társítása érdekében.

    | Mező                  | Leírás                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Keresési eredmény          | A jelentésmező értékének kiválasztása. Az értékekről és az [áfabevallási sorokhoz való hozzárendelésükről a cikk korábbi, áfabevallási áttekintő](#vat-declaration-overview) szakaszában olvashat bővebben.                                                                                               |
    | Adókód               | A jelentésmezőhöz társítani kívánt áfakód kiválasztása. A kiválasztott áfakódot használják a feladott adótranzakciók a megfelelő bevallás mezőben lesznek összegyűjtve. Javasoljuk, hogy az áfakódokat úgy válassza el, hogy egy áfakód csak egy bevallásmezőben generáljon összegeket. |
    | Tranzakcióosztályozó | Ha a bevallás meghatározásához elegendő áfakódot hozott létre, válassza **\* a Nem üres lehetőséget\***. Ha nem létrehozott elég áfakódot ahhoz, hogy egy áfakód csak egy bevallásmezőben generáljon összegeket, akkor be lehet állítani egy tranzakcióosztályozót. A következő tranzakcióosztályozók érhetők el:</br>-   **Beszerzés**</br>-   **PurchaseExempt** (adómentes beszerzés)</br>-   **PurchaseReverseCharge** (beszerzés fordított áfafizetésből visszakövethető adója)</br>-   **Értékesítés**</br>-   **SalesExempt** (adómentes értékesítés)</br>-   **SalesReverseCharge** (a beszerzés fordított vagy fordított áfafizetésből fizetendő adója)</br>-   **Az adó használata.** </br>Minden tranzakcióosztályozónál elérhető a jóváírás osztályozója is. Például az egyik osztályozó a **PurchaseCreditNote** (beszerzési jóváírás).</br>Mindenképpen hozzon létre két sort mindegyik áfakódhoz: egyet a tranzakcióosztályozó értékével, és egyet a jóváírási érték tranzakcióosztályozóval. |

    > [!NOTE]
    > Minden áfakód társítása a keresési eredményekhez. Ha az áfakódok nem generálnak értékeket az áfabevalláson, társítsa őket az **Egyéb** keresés eredményhez.

    ![Alkalmazásspecifikus paraméterek oldal](media/69ecb881f12819259ca166b9b98b8303.jpg)

5. Az Állam **mezőben** módosítsa az értéket " **Befejezve" értékre**.
6. A munkaablakban válassza az Exportálás **lehetőséget** az alkalmazásspecifikus paraméterek beállításainak exportálásához.
7. Válassza ki az **áfabevallás Excel-konfigurációját, majd a munkaablakban válassza az Importálás** **lehetőséget az** ÁFAbevallási XML (DE) **konfigurált paraméterek importálása érdekében**.
8. Az **Állapot** mezőben válassza ki a **Befejeződött** értéket.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Áfabevallási formátum beállítása az összegek excelben való megtekintéséhez

1. A Funkciókezelés **munkaterületen** keresse meg és engedélyezze az áfabevallék-formátum **jelentési szolgáltatását**.
2. Ugrás a Főkönyv **beállítása** > **főkönyvi** > **paraméterekhez**.
3. Válassza az **Áfabevallási** **·** **Excel (DE) lehetőséget az Áfabeállítások gyorslap Áfabevallás formátumleképezés mezőjében.** **·**

   Ez a formátum a kiegyenlítési időszak áfajelentésének **futtatásakor kerül nyomtatásra**. Akkor is kinyomtatja, ha **az** Áfakifizetések **lapon** a Nyomtatás lehetőséget választja.

4. Az Adóhatóság **lapon** válassza ki az adóhatóságot, majd a **Jelentés elrendezése** mezőben válassza az Alapértelmezett **beállítást**.

Ha több áfaregisztrációval [rendelkező](emea-reporting-for-multiple-vat-registrations.md) jogi személynél konfigurálja az áfabevallást, kövesse a következő lépéseket:

1. Ugrás a Főkönyv **beállítása** > **főkönyvi** > **paraméterekhez**.
2. Válassza az **Áfabevallási** **Excel (DE)** ER formátumot az Ország-/**régiójelentések** gyorslapon, a DEU-s **sorban**.

## <a name="set-up-electronic-messages"></a>Elektronikus üzenetek beállítása

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Az elektronikus üzenetekhez példaként megadott adatcsomag letöltése és importálása

Az adatcsomag olyan elektronikus üzenet-beállításokat tartalmaz, amelyek az áfabevallás XML-formátumú előállításához, majd az Excel programban való előnézetének megtekintéséhez használatosak. Ezek a beállítások bővíthetők, de létrehozható egy saját beállítás is. Az elektronikus üzenetkezelés alkalmazásával és a saját beállítások beállításával kapcsolatos további tudnivalókat lásd: [Elektronikus üzenetkezelés](../general-ledger/electronic-messaging.md).

1. A [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2)**megosztott** eszköztárában válassza ki eszköztípusként az Adatcsomagot, **majd töltse le a DE áfabevallási EM csomagot.** A letöltött fájl neve **DE ÁFAbevallás EM package.zip**.
2. Válassza az Importálás lehetőséget a Dynamics 365 Pénzügy **eszköz** Adatkezelési **munkaterületén**.
3. Az Importálás **gyorscsoport** Csoportnév **mezőjébe** írja be a feladat nevét.
4. A **Kiválasztott entitások** gyorslapon válassza a **Fájl hozzáadása** elemet.
5. A **Fájl hozzáadása** párbeszédpanelen győződjön meg róla, **·** **·** **hogy** a Forrásadatok formátuma mező csomag, válassza a Feltöltés és hozzáadás lehetőséget, majd válassza ki a korábban letöltött zip-fájlt.
6. Válassza **Bezárás** lehetőséget.
7. Az adatentitások feltöltése után a műveleti ablaktáblán válassza az **Importálás** elemet.
8. Ugrás az Adó-lekérdezések **·** > **és jelentések** > **elektronikus** > **üzenetekhez** és az importált elektronikus üzenetek feldolgozásának ellenőrzéséről.

### <a name="configure-electronic-messages"></a>Elektronikus üzenetek konfigurálása

1. Ugrás az **Adóbeállítás** > **–** > **Elektronikus üzenetek –** > **Rekordok feltöltése műveletekhez**
2. Válassza ki az áfa-visszakérdezés **rekordjainak sorát**, majd válassza a **Lekérdezés szerkesztése lehetőséget**.
3. A szűrő használatával megadhatja a jelentésben szerepeletni kívánt kiegyenlítési időszakokat.
4. Ha más bevallásban kell jelentenie más kiegyenlítési időszakok adótranzakcióit, hozzon létre egy új Rekord feltöltése műveletet, és válassza ki a **megfelelő** kiegyenlítési időszakokat.

## <a name="preview-the-vat-declaration-in-excel"></a>Áfabevallás előnézete az Excel programban

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>Áfabevallás előnézete az Excel programban a forgalmi adó jelentésből a kiegyenlítési időszak ismétlődő feladatának megtekintéséhez

1. Ugrás az Adó – **Időszakos** > **feladatok** > **– Bevallás** > **– Áfajelentés** > **- áfa a kiegyenlítési időszakra**
2. A Kiegyenlítési **időszak mezőben** válasszon ki egy értéket.
3. Az Áfafizetés **verziószáma** mezőben válasszon a következő értékek közül:

    - **Eredeti**: Jelentés készítése az eredeti áfafizetés vagy az áfafizetés generálása előtti áfatranzakciókról.
    - **Korrekciók**: Jelentés készítése az adott időszakra vonatkozó összes ezt követő áfakifizetés áfatranzakcióiról.
    - **Összlista**: Jelentés készítése az adott időszak összes áfatranzakcióiról, az eredeti és az összes javítással együtt.

4. A Kezdő **dátum mezőben** válassza ki a jelentési időszak kezdő dátumát.
5. Válassza az **OK** gombra, és tekintse át az Excel-jelentést.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>Áfa kiegyenlítése és feladása

1. Ugrás az Adó – **Időszakos feladatokhoz** > **– Áfabevallások** > **áfafizetése** > **és áfa feladása** > **·**
2. A Kiegyenlítési **időszak mezőben** válasszon ki egy értéket.
3. Az Áfafizetés **verziószáma** mezőben válasszon a következő értékek közül:

    - **Eredeti**: a kiegyenlítési időszak eredeti áfafizetésének létrehozása.
    - **Legutóbbi korrekciók**: Helyesbítő áfakifizetés generálása a kifizetési időszak eredeti áfafizetésének létrehozása után.

4. A Kezdő **dátum mezőben** válassza ki a jelentési időszak kezdő dátumát.
5. Válassza ki az **OK** lehetőséget.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Áfabevallás előnézete az Excel programban egy áfafizetésből

1. Menjen az Adó **-** > **és jelentésjelentések** > **az Áfakifizetések** > **lekérdezéshez**, és válasszon egy áfafizetési sort.
2. Válassza a **Jelentés nyomtatása**, majd az **OK gombra való lehetőséget**.
3. Ellenőrizze a kiválasztott áfafizetési sorhoz létrehozott Excel-fájlt.

    > [!NOTE]
    > A jelentés csak az áfafizetés kiválasztott sorában jön létre. Ha például javító nyilatkozatot kíván létrehozni, amely az időszak összes korrekcióját tartalmazza, vagy egy pótnyilatkozatot, amely az eredeti adatokat és az összes javítást tartalmazza, **használja** az Áfajelentést a kiegyenlítési időszak ismétlődő feladatára.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Áfabevallás létrehozása elektronikus üzenetekből

Amikor elektronikus üzenetekkel generálja a jelentést, adóadatokat gyűjthet több jogi személytől. A további tudnivalókat [lásd a](#run-a-vat-declaration-for-multiple-legal-entities) cikk több jogi személyhez című szakaszának Áfabevallás futtatása című részében.

A következő eljárás az LCS megosztott eszköztárból importált elektronikus üzenet-feldolgozási példára vonatkozik.

1. Ugrás az Adó-lekérdezések **·** > **és jelentések** > **elektronikus üzenetekhez** > **·**
2. A bal oldali ablakban válassza ki a **DE áfabevallást**.
3. Az Üzenetek **gyorspanelen** válassza az Új **lehetőséget**, majd **a Futtatás feldolgozása párbeszédpanelen** válassza az **OK gombra.**
4. Válassza ki a létrehozott üzenetsort, adjon meg leírást, majd adja meg a nyilatkozat kezdő és záró dátumát.

    > [!NOTE]
    > Az 5–7. lépés nem kötelező.

5. Nem kötelező: Az Üzenetek gyors **oldalon** válassza az **Adatok** gyűjtése gombra, majd válassza az **OK gombra.** A program hozzáadja a korábban létrehozott áfafizetéseket az üzenethez. A további tudnivalókat lásd [a](#settle-and-post-sales-tax) cikk korábbi, Az áfafizetés és áfa feladás szakaszában. Ha kihagyja ezt a lépést, akkor is létrehozhat áfabevallást **a** **Bevallás** párbeszédpanel Adóbevallás verziómezője segítségével.
6. Nem kötelező: Az Üzenet –**cikkek** gyors oldalon ellenőrizze a feldolgozásra átvitt áfafizetéseket. Alapértelmezés szerint a kijelölt időszak minden olyan áfafizetése szerepel, amely nem szerepelt ugyanannak a feldolgozásnak más üzenetében.
7. Választható: Válassza az **eredeti dokumentumot** az áfakifizetések ellenőrzéshez, vagy válassza a Törlés **lehetőséget,** ha ki szeretné zárni az áfafizetéseket a feldolgozásból. Ha kihagyja ezt a lépést, akkor is létrehozhat áfabevallást **a** **Bevallás** párbeszédpanel Adóbevallás verziómezője segítségével.
8. Az Üzenetek **gyorsjelentésen** válassza a Frissítés **állapot beállítását**. A Frissítés állapota párbeszédpanelen **válassza a** **Generálra kész lehetőséget, majd kattintson az** OK gombra **.** Győződjön meg róla, hogy az üzenet állapota Kész **állapotra változott.**
9. Válassza a **Jelentés létrehozása lehetőséget**. Az áfabevallási összegek előzetes megtekintéséhez **válassza** **az** Előnézet jelentés lehetőséget a Futtatás párbeszédpanelen, majd **kattintson az OK gombra.**
10. Az Elektronikus jelentés **paraméterei** párbeszédpanelen állítsa be a következő mezőket, majd válassza az **OK gombra.**

    | **Mező**                                   | **Leírás**                                                                                                                                                                                                              |
    |---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Kifizetési időszak                           | Válassza ki a kiegyenlítési időszakot. Ha az **5**. lépésben az Adatok gyűjtése beállítást választotta, ezt a mezőt üresen hagyhatja. A program a beszedett áfakifizetések áfatranzakcióiról készít jelentést. |
    | Adóbevallás verziója                     | Válasszon a következő értékek közül:</br>-   **Eredeti** – jelentés készítése az eredeti áfafizetés vagy az áfafizetés generálása előtti áfatranzakciókról.</br>-   **Korrekciók** – jelentés készítése az adott időszakra vonatkozó összes ezt követő áfakifizetés áfatranzakcióiról.</br>-   **Összeglista** – jelentés készítése az időszak összes áfatranzakciójáról, az eredeti és az összes javítással együtt.|
    | Adózási képviselő | Válassza ki azt a felet, amely adózási képviselő az áfabevalláshoz, ha van ilyen. A kiválasztott fél adatait a **DatenLieferant** XML-elembe exportálja a rendszer. |
    | Kapcsolattartó | Válassza ki a szervezetnél azt a személyt, aki adatszolgáltató. A kijelölt személy adatai a **DatenLieferant** XML-elembe exportálhatók. |
    | Korrekciós visszatérítés | Az Igen **lehetőséget** válassza javító áfabevalláshoz. Ebben az esetben a KZ10 XML-elem értéke **1**.|
    | Alátámasztó bizonylatok | Válassza az **Igen** lehetőséget, ha a támogató dokumentumokat is elküldi. Ebben az esetben a KZ22 XML-elem értéke **1**.|
    | A SEPA közvetlen beszedési megbízás kivételként lesz visszavonva.| Válassza az **Igen** lehetőséget, ha a SEPA beszedési megbízási felhatalmazás visszavonása kivételként történik az előregisztrációs időszakban. Például az ellentételezési kérések miatt. A fennmaradó egyenlegeket külön kell kifizetni. Ebben az esetben a KZ26 XML-elem értéke **1**. |
    | A kívánt újrakifizetési összeg ellentételezése | Válassza az **Igen** lehetőséget, ha a kívánt visszatérítési összeg ellentételezését adja meg, vagy ha a visszatérítés összegét hozzárendelték. Ebben az esetben a KZ29 XML-elem értéke **1** lesz. |
    | Speciális előlegfizetés állandó melléke | A fix speciális előlegfizetés állandó kiterjesztésű levonási összegének beírható. Ezt a levonási összeget általában csak az adózási időszak utolsó előzetes regisztrációja során kell végrehajtani. Az összeget a 67. sorban (39. mező) és az áfabevallás KZ39-es XML-elemében exportálja a rendszer. |

11. Válassza **ki a** lap jobb felső sarkában a mellékleteket, majd válassza a Megnyitás **lehetőséget**.
12. Tekintse át az összegeket az Excel-dokumentumban, majd válassza a Jelentés **létrehozása lehetőséget**.
13. Ha XML-formátumú áfabevallást hoz létre, válassza **a Jelentés létrehozása lehetőséget a Futtatás** **párbeszédpanelen,** majd kattintson az OK gombra **.**
14. Az Elektronikus jelentés **paraméterei** párbeszédpanelen állítsa be a mezőket a 10. lépésben leírtak szerint.
15. Válassza **ki a** lap jobb felső sarkában látható mellékleteket, töltse le a fájlt, és használja az adóhatóságnak való benyújtásához.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a> Áfabevallás futtatása több jogi személyhez

Ha a formátumokat használni kívánt egy jogi személycsoport áfabevallásának jelentéséhez, először be kell állítania az összes kötelező jogi személy áfakódja ER-formátumára vonatkozó alkalmazásspecifikus paramétereit.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Elektronikus üzenetek beállítása különböző jogi személyektől származó adóadatok összegyűjtésére

A következő lépések szerint állíthatja be az olyan elektronikus üzeneteket, amelyek több jogi személytől gyűjtik össze az adatokat.

1. Ugrás a **Munkaterületek** > **funkciókezelésre**
2. Keresse meg és válassza **ki** a listában a Több vállalatot átfedő lekérdezéseket a rekordműveletek feltöltése funkcióhoz, majd válassza az **Engedélyezés lehetőséget**.
3. Ugrás az **Adóbeállítás** > **–** > **Elektronikus üzenetek – \> Rekordok feltöltése műveletekhez**
4. A Rekordok **feltöltése műveletlapon** válassza ki az Áfa-visszacsatlott áfa rekordjainak **feltöltése sort**.

   Az Adatforrások **beállítási rácsában** elérhető egy új **Vállalat** mező. Meglévő rekordok esetén ez a mező az aktuális jogi személy azonosítóját mutatja.

5. A DataSources **beállítási rácsában** adjon hozzá egy sort minden további jogi személyhez, amely részt fog venni a jelentésen. Minden új sornál állítsa be a következő mezőket.

    | Mező                  | Leírás                                                                                                                   |
    |------------------------|-------------------------------------------------------------------------------------------------------------------------------|
    | Név                   | Adjon meg egy értéket, amely alapján jobban megértheti, hogy honnan származik ez a rekord. Megadhatja például az **1. leányvállalat áfafizetését**. |
    | Üzenetelem típusa      | Áfa-visszaáru **kiválasztása**. Ez az érték az egyetlen olyan érték, amely minden rekord számára elérhető.                                    |
    | Számla típusa           | Az összes **kijelölése**.                                                                                                               |
    | Fő tábla neve      | TaxReportVoucher **megadása** minden rekordhoz.                                                                             |
    | Dokumentumszám mező  | Bizonylat **megadása** minden rekordhoz.                                                                                      |
    | Dokumentumdátum mező    | A **TransDate megadása** minden rekordhoz.                                                                                    |
    | Dokumentumszámla mező | TaxPeriod **megadása** minden rekordhoz.                                                                                    |
    | Vállalat                | Válassza ki a jogi személy azonosítóját.                                                                                            |
    | Felhasználó lekérdezése             | A lekérdezés szerkesztése lehetőség kiválasztásával automatikusan be van jelölve ez **a jelölőnégyzet**.                                 |

6. Minden új sornál válassza **a Lekérdezés** szerkesztése lehetőséget, és adjon meg egy kapcsolódó kiegyenlítési időszakot a **sor** Vállalat mezőjében megadott jogi személyhez.

Ha a beállítás befejeződött, **·** **az** Elektronikus üzenetek lapon található Adatgyűjtés funkció a megadott jogi személyektől gyűjt áfafizetéseket.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
