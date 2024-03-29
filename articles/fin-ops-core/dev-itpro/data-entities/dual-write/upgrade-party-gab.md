---
title: Frissítés a fél és globális címjegyzék modelljére
description: Ez a témakör azt ismerteti, hogyan lehet két írásos adatot frissíteni a fél és a globális címjegyzék modellel.
author: RamaKrishnamoorthy
ms.date: 03/10/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 7141f9c7ae4e27013bd655ce78892fc44c181315
ms.sourcegitcommit: e14648b01549bdc17998ffdef6cde273d4e78560
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/09/2022
ms.locfileid: "9242982"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Frissítés a fél és globális címjegyzék modelljére

[!include [banner](../../includes/banner.md)]



Az [Microsoft Azure adattáblák](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema) sablonjai segítségével kettős írású adatokat frissíthet a fél és a globális címjegyzék modellben: **adatokat** a Számla, **·** **a Kapcsolattartó és a Szállító** táblában, valamint a postai és az elektronikus címeket.

A következő három Data Factory sablon áll rendelkezésre. A pénzügyi és az üzemeltetési alkalmazásokból, valamint az ügyfél-biztosi alkalmazásokból származó adatok egyeztetését segítik.

- **[Félsablon](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json) (Adatok frissítése két írású fél-GAB sémára/arm_template.json)** – **·** **·** **ez** a sablon a fiók-,**·** **kapcsolattartó- és szállítóadatokhoz társított partner- és kapcsolattartó-adatok frissítésében segít.**
- **[Fél postai címének sablonja](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json) (Két írású fél-GAB sémára/Ügyfél postai címének frissítése - GAB/arm_template.json)** –**ez** a sablon segít frissíteni a számla-, **·** **kapcsolattartó**- és szállítóadatokhoz társított postai címeket.
- **[Fél elektronikus címsablonja](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json) (Két írású fél-GAB sémára/Partner elektronikus címének frissítése - GAB/arm_template.json)** –**ez** a sablon a fiók-, **·** **kapcsolattartó**- és szállítóadatokhoz társított elektronikus címek frissítésében segít.

A folyamat végén a program a következő, vesszővel elválasztott értékeket (.csv) generálja.

| Fájlnév | Alkalmazás célja |
|---|---|
| FONewParty.csv | Ez a fájl új Fél rekordokat hoz **létre** a Pénzügy és műveletek alkalmazáson belül. |
| ImportFONewPostalAddressLocation.csv | Ez a fájl segít létrehozni a **Postai cím hely új** rekordjait a Pénzügy és műveletek alkalmazásban. |
| ImportFONewPartyPostalAddress.csv | Ez a fájl segít létrehozni a **Fél postai címének új** rekordjait a Pénzügy és műveletek alkalmazásban. |
| ImportFONewPostalAddress.csv | Ez a fájl új postai címrekordok **létrehozásában** segít a Pénzügy és műveletek alkalmazásban. |
| ImportFONewElectronicAddress.csv | Ez a fájl segít létrehozni az **új elektronikus címrekordokat** a Pénzügy és műveletek alkalmazásban. |

Ez a témakör bemutatja az adatgyártott sablonok használatát és az adatok frissítését. Ha nincsenek testreszabásai, a sablonokat a sablonokkal egy módon használhatja. Ha azonban testreszabott beállításai vannak **a számla-,** **·** **kapcsolattartó- és szállítóadatokhoz, módosítania kell a sablonokat az ebben a cikkben leírt módon.**

> [!IMPORTANT]
> A felek postai cím- és e-mail címsablonjainak futtatására különleges utasítások vonatkoznak. Először a Fél sablont, majd a Fél postai cím sablonját, majd a Fél elektronikus címsablonját kell futtatni. Minden sablon egy külön adat üzemben történő importálásra van kialakítva.

## <a name="prerequisites"></a>Előfeltételek

A felekre és a globális címjegyzékmodellre való frissítés előtt a következő előfeltételeknek kell megfeleltetve lenni:

+ Azure-előfizetés [szükséges](https://portal.azure.com/).
+ Hozzá kell férnie a [sablonokhoz](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
+ Önnek kettős írású ügyfélnek kell lennie.

## <a name="prepare-for-the-upgrade"></a>Felkészülés a frissítésre

A frissítéshez a következő előkészületek szükségesek:

+ **Teljes szinkronizálás:** Mind a pénzügyi, mind az műveleti környezetben, mind a vevői kapcsolati környezetben teljesen szinkronizált állapotban van a számla (Vevő) **,** **a** Kapcsolattartó és a **Szállító tábla.**
+ **Integrációs kulcsok:** a **vevői (Vevő)**,**·** **a Kapcsolattartó és a Szállító** tábla a vevői kapcsolati alkalmazásokban a "box" integrációs kulcsokat használja. Ha testre szabta az integrációs kulcsokat, testre kell szabni a sablont.
+ **Fél száma:** A **frissítendő számla-**, **·** **kapcsolattartó**- és szállítórekordok mindegyikének van félszáma. Azokat a rekordokat, amelyek nem tartalmaznak félszámot, figyelmen kívül hagyja a rendszer. Ha frissíteni szeretné ezeket a rekordokat, adjon hozzá egy félszámot, mielőtt elindítja a frissítési folyamatot.
+ **Rendszerszünet:** A frissítési folyamat során a pénzügy és a műveleti környezet és az ügyfél-kapcsolat kapcsolatát is ki kell venni.
+ **Pillanatkép:** Pillanatkép készítése mind a pénzügyi, mind a műveleti alkalmazásokról, valamint az ügyfél-tevékenységi alkalmazásokról. Ezután a pillanatképek segítségével visszaállíthatja az előző állapotot, ha szükség van rá.

## <a name="deployment"></a>Telepítés

1. Töltse le a sablonokat a [Dynamics-365-FastTrack-Implementation-Assets webhelyről](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
2. Jelentkezzen be az [Azure portálra](https://portal.azure.com/).
3. Hozzon létre egy [erőforráscsoportot](/azure/azure-resource-manager/management/manage-resource-groups-portal).
4. Hozzon létre egy [tárolási fiókot](/azure/storage/common/storage-account-create?tabs=azure-portal) a létrehozott erőforráscsoportban.
5. Adat gyár [létrehozása](/azure/data-factory/quickstart-create-data-factory-portal) a létrehozott erőforráscsoportban.
6. Nyissa meg az adatgyárt, és válassza a Szerző **& Monitor csempe** lehetőséget.
7. A **Kezelés** lapon válassza ki az **ARM-sablont**.
8. Válassza az **ImportKAR sablont** a Fél sablon importálása **beállításhoz**.
9. A sablon importálása az adat-előállítóba. Adja meg az alábbi értékeket a **projekt részleteinél** és a **példányok részleteinél**.

    | Mező | Érték |
    |---|---|
    | Előfizetés | Az Azure-előfizetés |
    | Erőforráscsoport | Adja meg ugyanazt az erőforrást, mint amely alatt a tárolási fiók létre van hozva. |
    | Régió | A régió |
    | Gyár neve | Az üzem neve |
    | FO összekapcsolt Service_service alapkulcs | A pályázat kulcsa |
    | Azure Blob Storage_connection karakterlánc | Az Azure Blob tárolási kapcsolati karakterlánca |
    | Dynamics Crm kapcsolt Service_password | A felhasználónévként megadott felhasználói fiók jelszava |
    | FO összekapcsolt Service_properties_type Properties_url | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | FO összekapcsolt Service_properties_type Properties_tenant | Információ (tartománynév vagy bérlőazonosító) arról a bérlőről, aki a pályázat alatt található |
    | FO összekapcsolt Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | FO összekapcsolt Service_properties_type Properties_service Principal Id | Az alkalmazás ügyfélazonosítója |
    | Dynamics Crm csatolt Service_properties_type Properties_username | A Dynamics 365-hez való csatlakozáshoz használt felhasználónév |

    További információért tekintse át az alábbi témaköröket:

    - [Erőforrás-kezelő sablon manuális promóciója az egyes környezetek számára](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Kapcsolt szolgáltatás tulajdonságai](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Adatok másolása az Azure Data Factory segítségével](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. A telepítést követően ellenőrizze az adattárat, az adatáramlást és az adat-előállító kapcsolt szolgáltatását.

    ![Adatkészletek, adatáramlás és csatolt szolgáltatás.](media/data-factory-validate.png)

11. Ugrás a **kezeléshez**. A **Kapcsolatok** alatt válassza a **Csatolt szolgáltatás** lehetőséget. Ezután válassza a **DynamicsCrmLinkedService szolgáltatást**. A Csatolt **szolgáltatás szerkesztése (Dynamics CRM)** párbeszédpanelen írja be a következő értékeket.

    | Mező | Érték |
    |---|---|
    | Név | DynamicsCrmLinkedService |
    | Leírás | Az entitások adatainak beolvasására és a CRM-példányhoz való kapcsolódásra szolgáló kapcsolt szolgáltatások |
    | Csatlakozás integrációs modulon keresztül | AutoResolvelntegrationRuntime |
    | Telepítés típusa | Online |
    | Szolgáltatási URI | `https://<organization-name>.crm[x].dynamics.com` |
    | Hitelesítési típus | Office365 |
    | Felhasználónév | |
    | Jelszó vagy Azure Key Vault | Jelszó |
    | Jelszó | |

## <a name="prepare-to-run-the-data-factory-templates"></a>Felkészülés az adatiratsablonok futtatására

Ez a szakasz leírja a Felek postai címének és a Felek elektronikus címének adatattára sablonok futtatása előtt szükséges beállításokat.

### <a name="setup-to-run-the-party-postal-address-template"></a>A Fél postai cím sablonjának futtatása

1. Jelentkezzen be az ügyfél-naplózási alkalmazásokba, és lépjen a **Beállítások** \> **személyre szabási beállításai elemre.** Ezután az Általános lapon **konfigurálja** a rendszer rendszergazdai fiókjának időzóna-beállítását. Ahhoz, hogy a pénzügyi és műveleti alkalmazásokból frissíthető legyen az "érvényesség", illetve az "érvényesség be" dátuma, az időzónának UTC-ben kell lennie.

    ![A rendszer rendszergazdai fiókjának időzóna-beállítása.](media/ADF-1.png)

2. Hozza létre a következő globális paramétert **a Data Gyár Kezelés** lapján, **a** Globális paraméterek csoportban.

    | Szám | Név | Típus | Érték |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | karakterlánc | Ez a paraméter előtagként hozzáfűzi az újonnan létrehozott postai címekhez a sorozatszámot. Mindenképpen olyan karakterláncot adjon meg, amely nem ütközik a pénzügyi és műveleti alkalmazásokban és az ügyfél-kapcsolati alkalmazásokban használt postai címekkel. Például használja az **ADF-PAD-t**. |

    ![A Kezelés lapon létrehozott PostalAddressIdPrefix globális paraméter.](media/ADF-2.png)

3. Ha végzett, válassza az Összes közzététele **lehetőséget**.

    ![Az összes gomb közzététele](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>A Fél elektronikuscím-sablonjának futtatása

1. Hozza létre a következő globális paramétereket **az** Adat üzemben, a Kezelés **lapon**, a Globális paraméterek csoportban.

    | Szám | Név | Típus | Érték |
    |---|---|---|---|
    | 1 | IsFOSource | Bool | Ez a paraméter határozza meg, hogy mely elsődleges rendszercímek felülírása ütközés esetén. Ha az érték **igaz**, a pénzügyi és műveletalkalmazások elsődleges címei felülírják az ügyfél-tevékenységalkalmazások elsődleges címeit. Ha az érték **hamis**, a vevői tevékenységalkalmazások elsődleges címei felülírják a pénzügyi és műveleti alkalmazások elsődleges címeit. |
    | 2 | ElectronicAddressIdPrefix | karakterlánc | Ez a paraméter előtagként hozzáfűz egy sorozatszámot az újonnan létrehozott elektronikus címekhez. Mindenképpen olyan karakterláncot adjon meg, amely nem ütközik a pénzügyi és műveleti alkalmazásokban, valamint az ügyfél-kapcsolati alkalmazásokban használt elektronikus címekkel. Például használja az **ADF-EAD-t**. |

    ![A Kezelés lapon létrehozott IsFOSource és ElectronicAddressIdPrefix globális paraméterek.](media/ADF-4.png)

2. Ha végzett, válassza az Összes közzététele **lehetőséget**.

## <a name="run-the-templates"></a>A sablonok futtatása

1. Állítsa le a pénzügy- **és műveleti alkalmazásokat** **·** **·** **használnak** két írásos partner- és szállítói leképezéseket:

    + CDS-felek (msdyn_parties) 
    + Vevők V3 .(partnerek)
    + Vevők V3(kapcsolattartók)
    + CDS kapcsolattartók V2(kapcsolattartók)
    + CDS kapcsolattartók V2(kapcsolattartók)
    + Szállító V2 (msdyn_vendors)
    + Kapcsolattartók V2 (msdyn_contactforparties)
    + CDS fél postai címének helyei (msdyn_partypostaladdresses)
    + CDS postai címelőzmények V2 (msdyn_postaladdresses)
    + CDS fél postai címének helyei (msdyn_postaladdresscollections)
    + Fél kapcsolattartói V3 (msdyn_partyelectronicaddresses)

2. Győződjön meg róla, hogy a leképezések el vannak távolítva a **msdy_dualwriteruntimeconfig** táblából Dataverse.
3. [Kettős írású fél és globális címjegyzék megoldások](https://aka.ms/dual-write-gab) telepítése innen: AppSource.
4. A Pénzügy és műveletek alkalmazásban **futtassa az Initial Sync** műveletet a következő táblákra, ha adatokat tartalmaznak:

    + Üdvözlések
    + Személyes karaktertípusok
    + Udvarias levélzárás
    + Kapcsolattartó megszólításai
    + Döntéshozatali szerepkörök
    + Hűségszintek

5. A vevői kapcsolati alkalmazásban tiltsa le a következő beépülő modulok következő lépéseit:

    + Számla frissítése

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Számla frissítése
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Számla frissítése

    + Névjegyfrissítés

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Névjegyfrissítés
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Névjegyfrissítés

    + msdyn_party frissítése

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: msdyn_party frissítése

    + msdyn_vendor frissítése

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: msdyn_vendor frissítése

    + Customeraddress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Stbs.CreatePartyAddress: Customeraddress létrehozása

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Stbs.CreatePartyAddress: Customeraddress frissítése

        + Delete

            + Microsoft.Dynamics.GABExtended.Adatok.DeleteCustomerAddress: A customeraddress törlése

    + msdyn_partypostaladdress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Stbs.CreateCustomerAddress: Létrehozás msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Stbs.PartyPostalAddress: Létrehozás msdyn_partypostaladdress

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Stbs.CreateCustomerAddress: A msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Moduls.PartyPostalAddress: A msdyn_partypostaladdress

    + msdyn_postaladdress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Stbs.PostalAddress: Cím msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Stbs.PostalAddressPostCreate: Létrehozás msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Moduls.UpdateCustomerAddress: Létrehozás msdyn_postaladdress

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Keresőmezők.PostalAddressUpdate: A msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.FrissítésiCustomerAddress: Msdyn_postaladdress

    + msdyn_partyelectronicaddress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Bills.PartyElectronicAddressSync: Létrehozás msdyn_partyelectronicaddress

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Bills.PartyElectronicAddressSync: Msdyn_partyelectronicaddress

        + Delete

            + Microsoft.Dynamics.GABExtended.Bills.DeletePartyElectronicAddressSync: A(z) msdyn_partyelectronicaddress

6. Az ügyfélkapcsolati alkalmazásban tiltsa le a következő munkafolyamatokat.

    + Szállítók létrehozása a Partnerek táblában
    + Szállítók létrehozása a Partnerek táblában
    + Személy típusú szállítók létrehozása a Kapcsolattartók táblában
    + Személy típusú szállítók létrehozása a Szállítók táblában
    + Szállítók frissítése a Fiókok táblában
    + Szállítók frissítése a Szállítók táblában
    + Személy típusú szállítók frissítése a Kapcsolattartók táblában
    + Személy típusú szállítók frissítése a Szállítók táblában

7. Az adat üzemben futtassa a **sablont** az Eseményindító megjelenik az alábbi ábra szerint. A folyamat az adatmennyiségtől függően néhány óráig is igénybe vehet.

    ![A sablon futtatása](media/data-factory-trigger.png)

    > [!NOTE]
    > Ha testreszabott beállításai vannak a **számlához**,**·** **a** kapcsolattartóhoz és a szállítóhoz, módosítania kell a sablont.

8. Az új Fél rekordjainak **importálása** a Pénzügy és műveletek alkalmazásba.

    1. Töltse le **a FONewParty.csv fájlt** az Azure Blob tárolóból. Az elérési út partybootstrapping **/output/FONewParty.csv**.
    2. **A FONewParty.csv fájl** konvertálása Excel-fájlba, és az Excel-fájl importálása a Pénzügyi és műveleti alkalmazásba. Ha a CSV importálása az Ön számára is megfelelő, akkor közvetlenül importálhatja a .csv fájlt. Ez a lépés az adatmennyiségtől függően néhány óráig is igénybe vehet. A további tudnivalókat lásd: [Adatimportálási és -exportálási feladatok áttekintése](../data-import-export-job.md).

    ![A felek rekordjainak Dataverse importálása](media/data-factory-import-party.png)

9. Az adat üzemben futtassa a Fél e-mail címét, majd a Fél postai címsablonját, egymás után.

    + A Fél postai címsablonja a **vevői** kapcsolati alkalmazás összes postai címrekordját hozzárendeli a megfelelő számla-,**·** **kapcsolattartó- és szállítórekordhoz**. Ezenkívül három .csv fájlt generál: ImportFONewPostalAddressLocation.csv, ImportFONewPartyPostalAddress.csv és ImportFONewPostalAddress.csv.
    + A Fél elektronikus címsablonja az összes elektronikus címet megerősíti a vevői kapcsolati alkalmazásban, **és hozzárendeli azokat a megfelelő számla-,** **kapcsolattartó- és szállítórekordhoz** **.** Egy .csv fájlt is generál: ImportFONewElectronicAddress.csv.

    ![A Fél postai címének és a Fél elektronikus címsablonjainak futtatása](media/ADF-7.png)

10. Ahhoz, hogy ezzel az adatokkal frissítse a pénzügyet és a műveletek alkalmazást, a .csv fájlokat egy Excel-munkafüzetké [kell konvertálni, és be kell importálni a pénzügyi és műveleti alkalmazásba](../data-import-export-job.md). Ha a CSV importálása az Ön számára is megfelelő, akkor közvetlenül importálhatja a .csv fájlokat. A lépés a térfogattól függően néhány óráig is igénybe vehet.

    ![Az importálás sikeresen befejeződött.](media/ADF-8.png)

11. A vevői együttműködés alkalmazásában engedélyezze a következő beépülő modul lépéseit:

    + Számla frissítése

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Számla frissítése
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Számla frissítése

    + Névjegyfrissítés

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Névjegyfrissítés
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Névjegyfrissítés

    + msdyn_party frissítése

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: msdyn_party frissítése

    + msdyn_vendor frissítése

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: msdyn_vendor frissítése

    + msdyn_partypostaladdress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Stbs.CreateCustomerAddress: Létrehozás msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Stbs.PartyPostalAddress: Létrehozás msdyn_partypostaladdress

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Stbs.CreateCustomerAddress: A msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Moduls.PartyPostalAddress: A msdyn_partypostaladdress

    + msdyn_postaladdress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Stbs.PostalAddress: Cím msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Stbs.PostalAddressPostCreate: Létrehozás msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Moduls.UpdateCustomerAddress: Létrehozás msdyn_postaladdress

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Keresőmezők.PostalAddressUpdate: A msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.FrissítésiCustomerAddress: Msdyn_postaladdress
 
    + msdyn_partyelectronicaddress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Bills.PartyElectronicAddressSync: Létrehozás msdyn_partyelectronicaddress

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Bills.PartyElectronicAddressSync: Msdyn_partyelectronicaddress

        + Delete

            + Microsoft.Dynamics.GABExtended.Bills.DeletePartyElectronicAddressSync: A(z) msdyn_partyelectronicaddress

12. Ha korábban inaktiválta őket, aktiválhatja a következő munkafolyamatokat a vevői tevékenység alkalmazásban:

    + Szállítók létrehozása a Partnerek táblában
    + Szállítók létrehozása a Partnerek táblában
    + Személy típusú szállítók létrehozása a Kapcsolattartók táblában
    + Személy típusú szállítók létrehozása a Szállítók táblában
    + Szállítók frissítése a Fiókok táblában
    + Szállítók frissítése a Szállítók táblában
    + Személy típusú szállítók frissítése a Kapcsolattartók táblában
    + Személy típusú szállítók frissítése a Szállítók táblában

13. A Fél rekordhoz **kapcsolódó** leképezések futtatása a Fél [és a globális címjegyzékben leírtak szerint](party-gab.md).

## <a name="explanation-of-the-data-factory-templates"></a>Az adatattára-sablonok magyarázata

Ez a szakasz az egyes adat üzemben található sablonok lépéseit tartalmazza.

### <a name="steps-in-the-party-template"></a>A Fél sablon lépései

1. Az 1–6. lépés azonosítja azokat a vállalatokat, amelyek számára engedélyezve van a kettős írás és a szűrőzáradékok összeállítása.
2. A 7-1–7-9. lépés adatokat olvassa be a pénzügyi és az üzemeltetési alkalmazásból, valamint a vevői megbízás alkalmazásból, és a frissítésre való adatbeolvasás fázisát.
3. A 8–9. lépés **összeveti a fél számla-,** **·** **kapcsolattartó- és szállítórekordjait a pénzügyi és műveleti alkalmazás, valamint a vevői megállapodás alkalmazás között.** A program minden olyan rekordot kihagy, amely nem tartalmaz félszámot.
4. A 10. lépés két .csv fájlt hoz létre a vevői együttműködés alkalmazásában, valamint a Pénzügy és műveletek alkalmazásban létrehozva a felek rekordjaihoz.

    - **FOCDSParty.csv** – ez a fájl mindkét rendszer összes félrekordját tartalmazza, függetlenül attól, hogy a vállalatnál engedélyezve van-e a kettős írás.
    - **FONewParty.csv** – ez a fájl tartalmazza a Dataverse fél rekordjainak egy olyan részkészletét, **amely tud róla (például a potenciális vevő típusú számlák**).

5. A 11. lépés létrehozza a feleket a vevői megállapodás alkalmazásában.
6. A 12. lépés beolvassa a felek globális egyedi azonosítóit (GUID- azonosítókat) **a** vevői kapcsolat alkalmazásból, és a következő lépésekben beolvassa őket, hogy társítható legyen a számla-, **·** **kapcsolattartó**- és szállítórekordhoz.
7. A 13. lépés a **számla**-**,** **kapcsolattartó- és szállítórekordokat** a fél GUID azonosítóihoz társítja.
8. A 14-1–14-3 **·**. lépés a partner GUID azonosítóival frissíti a vevői kapcsolatfelvételi alkalmazás számla-, **·** **kapcsolattartó**- és szállítórekordjait.
9. 15-1–15-3. lépés a partnerrekordok előkészítésére a számla-, **·** **kapcsolattartó- és szállítórekordok esetén.** **·** **·**
10. A 16-1–16-7. lépés beolvassa a hivatkozási adatokat, például az üdvözléseket és a személyes karaktertípusokat, **és társítja a Partnerrekordok kapcsolattartója** rekordjaihoz.
11. A 17. lépés egyesíti **a Kapcsolattartó fél** rekordjait **a** számla-,**·** **kapcsolattartó- és szállítórekordok** esetén.
12. A 18. lépés importálja **a Felek kapcsolattartója rekordokat** a vevői kapcsolati alkalmazásba.

### <a name="steps-in-the-party-postal-address-template"></a>A Fél postai cím sablonjának lépései

1. Az 1–1–10. lépés beolvassa az adatokat a pénzügyi és az üzemeltetési alkalmazásból, valamint a vevői megbízás alkalmazásból, és beolvassa az adatokat frissítésre.
2. A 2. lépés a postai cím normalizálása a pénzügyi és műveleti alkalmazásban úgy, hogy csatlakozik a postai címhez és a fél postai címéhez.
3. 3. lépés, amely az ismétlődő adatok másolását és a vevői kapcsolatfelvételi alkalmazásból származó számla-, kapcsolattartó- és szállítói címadatokat egyesít.
4. A 4. lépéssel .csv fájlokat hozhat létre a Pénzügy és műveletek alkalmazás számára, hogy új címadatokat hozzon létre, amelyek a számla-, kapcsolattartó- és szállítói címeken alapulnak.
5. Az 5-1. lépés .csv fájlokat hoz létre a vevői együttműködés alkalmazáshoz, hogy minden címadatot létrehozzon, mind a pénzügyi, mind a műveleti alkalmazás, mind a vevői tevékenység alkalmazás alapján.
6. Az 5-2. lépés a .csv fájlokat a pénzügyi és a műveletek importálási formátumára alakítja át a manuális importáláshoz.

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. A 6. lépés importálja a postai címeket a vevői megbízás alkalmazásba.
8. A 7. lépés a postai cím beszedési adatait olvassa be a vevői együttműködés alkalmazásból.
9. A 8. lépés létrehozza a vevői címadatokat, és társítja a postai címgyűjtemény azonosítóját.
10. 9-1– 9-2. lépés: társítsa a fél- és postai címgyűjtemények megfelelő postai címeit és postai címeit.
11. 10-1– 10-3. lépés: vevői címek, postai címek és fél postai címének importálása a vevői együttműködés alkalmazásába.

### <a name="steps-in-the-party-electronic-address-template"></a>A Felek elektronikus címsablonjának lépései

1. Az 1–1–5. lépés beolvassa az adatokat a pénzügyi és az üzemeltetési alkalmazásból, valamint a vevői megbízás alkalmazásból, és beolvassa az adatokat frissítésre.
2. 2. lépés: a vevői kapcsolati alkalmazás elektronikus címeit fiók-, kapcsolattartó- és szállítói entitások alapján vonja össze.
3. A 3. lépés egyesíti az elsődleges e-mail címadatokat a vevői együttműködés alkalmazásból, valamint a Pénzügy és műveletek alkalmazásból.
4. A 4. lépés a .csv fájlokat hozza létre.

    - Új elektronikus címadatok létrehozása a pénzügyek és műveletek alkalmazás számára a számla, a kapcsolattartó és a szállítói címek alapján.
    - Új elektronikus címadatok létrehozása a vevői kapcsolati alkalmazás számára a pénzügyi és műveleti alkalmazásban megadott e-mail, számla, kapcsolattartó és szállítói címek alapján.

5. Az 5-1. lépés elektronikus címeket importál a vevői együttműködés alkalmazásába.
6. Az 5-2. lépés a .csv fájlokat hozza létre, amelyek az ügyfél-kapcsolati alkalmazásban lévő vevők és kapcsolattartók elsődleges címének frissítéséhez szükségesek.
7. 6-1–6-2. lépés: importálja a számlákat, és lépjen kapcsolatba az elsődleges címekkel a vevői együttműködés alkalmazásában.

## <a name="troubleshooting"></a>Hibaelhárítás

1. Ha a folyamat sikertelen, futtassa újra az adatgyárt. Kezdés a sikertelen tevékenységtől.
2. Az adat üzemben előállított egyes fájlok adatellenőrzésre használhatók.
3. Az adat gyára .csv fájlokon alapul. Ezért ha egy mezőértékben vessző szerepel, akkor az is lehet, hogy az eredményhez vezet. Minden vesszőt el kell távolítania a mezőértékekből.
4. A **Figyelés** lap a feldolgozott lépésekről és adatokról nyújt tájékoztatást. A hibakereséshez válasszon egy lépést.

    ![Figyelés lap.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>További tudnivalók a sablonról

A sablonnal kapcsolatos további tudnivalókat [lásd a Megjegyzések az Azure adatstára sablonhoz beolvasott fájlban](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).

