---
title: Frissítés a fél és globális címjegyzék modelljére
description: Ez a témakör azt ismerteti, hogyan lehet kettős írású adatot frissíteni a partner és a globális címjegyzék modellel.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 579a7d19ee7196d3242c78bd9915df24ec479c31
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8060485"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Frissítés a fél és globális címjegyzék modelljére

[!include [banner](../../includes/banner.md)]



A [Microsoft Azure Data Factory sablonok](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema) segít frissíteni a következő meglévő adatokat kettős írással a fél és a globális címjegyzék modelljére: adatok a **fiók**, **lépni**, és **Eladó** táblázatok, postai és elektronikus címek.

A következő három Data Factory-sablon áll rendelkezésre. Segítenek a Finance and Operations és az ügyfélelköteleződési alkalmazásokból származó adatok egyeztetésében.

- **[Party sablon](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json) (Adatok frissítése kétírásos Party-GAB schema/arm_template.json-ra)** – Ez a sablon segít a frissítésben **Buli** és **Kapcsolatba lépni** adatokhoz, amelyekhez kapcsolódnak **fiók**, **lépni**, és **Eladó** adat.
- **[Fél postai cím sablon](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json) (Adatok frissítése kétírásos Party-GAB sémára/Frissítés Party Postacímre – GAB/arm_template.json)** – Ez a sablon segít a hozzárendelt postacímek frissítésében **fiók**, **lépni**, és **Eladó** adat.
- **[Fél elektronikus cím sablon](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json) (Adatok frissítése kétírásos Party-GAB sémára/Frissítés Party Electronic Address-re – GAB/arm_template.json)** – Ez a sablon segít a címhez társított elektronikus címek frissítésében **fiók**, **lépni**, és **Eladó** adat.

A folyamat végén a következő vesszővel elválasztott értékek (.csv) fájlok jönnek létre.

| Fájlnév | Alkalmazás célja |
|---|---|
| FONewParty.csv | Ez a fájl segít új létrehozásában **Buli** rekordokat a Finance and Operations alkalmazásban. |
| ImportFONewPostalAddressLocation.csv | Ez a fájl segít új létrehozásában **Postacím Hely** rekordokat a Finance and Operations alkalmazásban. |
| ImportFONewPartyPostalAddress.csv | Ez a fájl segít új létrehozásában **Party Postacím** rekordokat a Finance and Operations alkalmazásban. |
| ImportFONewPostalAddress.csv | Ez a fájl segít új létrehozásában **Postázási cím** rekordokat a Finance and Operations alkalmazásban. |
| ImportFONewElectronicAddress.csv | Ez a fájl segít új létrehozásában **Elektronikus cím** rekordokat a Finance and Operations alkalmazásban. |

Ez a témakör a Data Factory-sablonok használatát és az adatok frissítését ismerteti. Ha nincsenek testreszabásai, használhatja a sablonokat úgy, ahogy vannak. Ha azonban testreszabásai vannak a **fiók**, **lépni**, és **Eladó** adatokat, módosítania kell a sablonokat a témakörben leírtak szerint.

> [!IMPORTANT]
> A Party postacímének és a Party elektronikus címsablonjainak futtatására speciális utasítások vonatkoznak. Először a Party-sablont, majd a Party-postacím-sablont, majd a Party elektronikus címsablont kell futtatnia. Minden sablon külön adatgyárban történő importálásra készült.

## <a name="prerequisites"></a>Előfeltételek

A következő előfeltételeknek kell teljesülniük, mielőtt frissítené a párt és a globális címjegyzék modelljét:

+ Biztosan van egy [Azure-előfizetés](https://portal.azure.com/).
+ Hozzá kell férnie [a sablonokat](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
+ Önnek kettős írású ügyfélnek kell lennie.

## <a name="prepare-for-the-upgrade"></a>Felkészülés a frissítésre

A frissítéshez a következő előkészületek szükségesek:

+ **Teljes szinkronizálás:** Mind a Pénzügyi és üzemeltetési környezet, mind az ügyfél-elköteleződési környezet teljesen szinkronizált állapotban van **Fiók (ügyfél)**, **lépni**, és **Eladó** táblázatok.
+ **Integrációs kulcsok:** A **Fiók (ügyfél)**, **lépni**, és **Eladó** Az ügyfél-elköteleződési alkalmazásokban lévő táblázatok a kész integrációs kulcsokat használják. Ha testre szabta az integrációs kulcsokat, testre kell szabni a sablont.
+ **Pártszám:** Minden **Fiók (ügyfél)**, **lépni**, és **Eladó** a frissítendő rekordoknak van pártszámuk. A rendszer figyelmen kívül hagyja azokat a rekordokat, amelyek nem rendelkeznek pártszámmal. Ha frissíteni szeretné ezeket a rekordokat, a frissítési folyamat megkezdése előtt adjon hozzá egy pártszámot.
+ **Rendszerkimaradás:** A frissítési folyamat során mind a pénzügyi, mind a műveleti környezetet, mind az ügyfélkapcsolati környezetet offline állapotba kell hoznia.
+ **Pillanatkép:** Készítsen pillanatképet mind a Pénzügyi, mind az Operations alkalmazásokról, mind az ügyfélkapcsolati alkalmazásokról. Ezután a pillanatképek segítségével szükség esetén visszaállíthatja az előző állapotot.

## <a name="deployment"></a>Telepítés

1. Töltse le a sablonokat a Dynamics-365-FastTrack-Implementation-Assets [webhelyről](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
2. Jelentkezzen be az [Azure portálra](https://portal.azure.com/).
3. Hozzon létre egy [erőforráscsoportot](/azure/azure-resource-manager/management/manage-resource-groups-portal).
4. Hozzon létre egy [tárolási fiókot](/azure/storage/common/storage-account-create?tabs=azure-portal) a létrehozott erőforráscsoportban.
5. Hozzon létre egy adatgyárat [a](/azure/data-factory/quickstart-create-data-factory-portal) létrehozott erőforráscsoportban.
6. Nyissa meg az adatgyárat, és válassza a **Szerző és Figyelő** csempét.
7. A **Kezelés** lapon válassza ki az **ARM-sablont**.
8. Válassza az ARM-sablon **importálása lehetőséget** a **félsablon** importálásához.
9. A sablon importálása az adat-előállítóba. Adja meg az alábbi értékeket a **projekt részleteinél** és a **példányok részleteinél**.

    | Mező | Érték |
    |---|---|
    | Előfizetés | Az Azure-előfizetés |
    | Erőforráscsoport | Adja meg ugyanazt az erőforrást, amely alatt a Tárfiók létrejön. |
    | Régió | A régió |
    | Gyár neve | A gyár neve |
    | FO összekapcsolt Service_service alapkulcs | Az alkalmazás kulcsa |
    | Azure Blob Storage_connection karakterlánc | Az Azure Blob Storage-kapcsolat karakterlánca |
    | Dynamics Crm kapcsolt Service_password | A felhasználónévként megadott felhasználói fiók jelszava |
    | FO összekapcsolt Service_properties_type Properties_url | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | FO összekapcsolt Service_properties_type Properties_tenant | Információk (tartománynév vagy bérlői azonosító) arról a bérlőről, amely alatt az alkalmazás található |
    | FO összekapcsolt Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | FO összekapcsolt Service_properties_type Properties_service Principal Id | Az alkalmazás ügyfélazonosítója |
    | Dynamics Crm csatolt Service_properties_type Properties_username | A Dynamics 365-höz való csatlakozáshoz használt felhasználónév |

    További információért tekintse át az alábbi témaköröket:

    - [Erőforrás-kezelő sablon manuális promóciója az egyes környezetek számára](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Kapcsolt szolgáltatás tulajdonságai](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Adatok másolása az Azure Data Factory segítségével](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. A telepítést követően ellenőrizze az adattárat, az adatáramlást és az adat-előállító kapcsolt szolgáltatását.

    ![Adatkészletek, adatáramlás és csatolt szolgáltatás.](media/data-factory-validate.png)

11. Menj a Manage-hez **·**. A **Kapcsolatok** alatt válassza a **Csatolt szolgáltatás** lehetőséget. Ezután válassza a DynamicsCrmLinkedService **lehetőséget**. **A Csatolt szolgáltatás (Dynamics CRM) szerkesztése párbeszédpanelen** adja meg a következő értékeket.

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

## <a name="prepare-to-run-the-data-factory-templates"></a>Felkészülés a Data Factory sablonok futtatására

Ez a szakasz azt a beállítást ismerteti, amely a fél postai címének és a fél elektronikus cím adatfeldolgozó sablonjának futtatása előtt szükséges.

### <a name="setup-to-run-the-party-postal-address-template"></a>A Fél postai címsablonjának futtatása

1. Jelentkezzen be az ügyfélkapcsolati alkalmazásokba, és lépjen a **Beállítások** \> **személyre szabási beállításaira.** Ezután az **Általános** lapon konfigurálja a rendszer rendszergazdai fiókjának időzóna-beállítását. Az időzónának koordinált univerzális időben (UTC) kell lennie ahhoz, hogy frissítse a pénzügyi és üzemeltetési alkalmazások postai címeinek "érvényes" és "érvényes" dátumát.

    ![A rendszeradminisztrátor-fiók időzónájának beállítása.](media/ADF-1.png)

2. A Data Factory Kezelés lapján, a **Globális** paraméterek **csoportban** hozza létre a következő globális paramétert.

    | Szám | Név | Típus | Érték |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | karakterlánc | Ez a paraméter előtagként egy sorszámot fűz az újonnan létrehozott postai címekhez. Ügyeljen arra, hogy olyan karakterláncot biztosítson, amely nem ütközik a pénzügyi és üzemeltetési alkalmazások és az ügyfélkapcsolati alkalmazások postai címeivel. Használja **például az ADF-PAD-- parancsot**. |

    ![PostalAddressIdPrefix globális paraméter a Kezelés lapon.](media/ADF-2.png)

3. Ha befejezte, válassza az Összes **közzététele lehetőséget**.

    ![Tegye közzé az összes gombot.](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>A fél elektronikus címsablonjának futtatására vonatkozó beállítás

1. A Data Factory kezelés lapján, a **Globális** paraméterek **csoportban** hozza létre a következő globális paramétereket.

    | Szám | Név | Típus | Érték |
    |---|---|---|---|
    | 1 | IsFOSource | Bool | Ez a paraméter határozza meg, hogy ütközés esetén mely elsődleges rendszercímek váltódnak fel. Ha az **érték igaz**, a Pénzügyi és műveleti alkalmazások elsődleges címei helyettesítik az ügyfélkapcsolati alkalmazások elsődleges címeit. Ha az **érték hamis**, az ügyfélkapcsolati alkalmazások elsődleges címei helyettesítik a Pénzügyi és műveleti alkalmazások elsődleges címeit. |
    | 2 | ElectronicAddressIdPrefix | karakterlánc | Ez a paraméter előtagként egy sorozatszámot fűz az újonnan létrehozott elektronikus címekhez. Ügyeljen arra, hogy olyan karakterláncot biztosítson, amely nem ütközik az elektronikus címekkel a Pénzügyi és műveleti alkalmazásokban és az ügyfélkapcsolati alkalmazásokban. Használja **például az ADF-EAD-et**. |

    ![IsFOSource és ElectronicAddressIdPrefix globális paramétereket hoztak létre a Kezelés lapon.](media/ADF-4.png)

2. Ha befejezte, válassza az Összes **közzététele lehetőséget**.

## <a name="run-the-templates"></a>A sablonok futtatása

1. Állítsa le a Következő **Partner**-, **Partner**- és **Szállítói** kettős írási térképeket, amelyek a Pénzügy és műveletek alkalmazást használják:

    + Vevők V3 .(partnerek)
    + Vevők V3(kapcsolattartók)
    + CDS kapcsolattartók V2(kapcsolattartók)
    + CDS kapcsolattartók V2(kapcsolattartók)
    + Szállító V2 (msdyn_vendors)

2. Győződjön meg arról, hogy a térképek el vannak távolítva a **msdy_dualwriteruntimeconfig** táblából a .Dataverse
3. [Kettős írású fél és globális címjegyzék megoldások](https://aka.ms/dual-write-gab) telepítése innen: AppSource.
4. A Pénzügy és műveletek alkalmazásban futtassa a Kezdeti szinkronizálást **a** következő táblákhoz, ha azok adatokat tartalmaznak:

    + Üdvözlések
    + Személyes karaktertípusok
    + Udvarias levélzárás
    + Kapcsolattartó megszólításai
    + Döntéshozatali szerepkörök
    + Hűségszintek

5. Az ügyfélkapcsolati alkalmazásban tiltsa le a következő beépülő modul lépéseit:

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

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: Customeraddress létrehozása

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: A customeraddress frissítése

        + Törlés

            + Microsoft.Dynamics.GABExtended.Plugins.DeleteCustomerAddress: A customeraddress törlése

    + msdyn_partypostaladdress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: msdyn_partypostaladdress létrehozása
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: létrehozása msdyn_partypostaladdress

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: msdyn_partypostaladdress frissítése
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: A msdyn_partypostaladdress frissítése

    + msdyn_postaladdress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: msdyn_postaladdress létrehozása
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: Msdyn_postaladdress létrehozása
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: msdyn_postaladdress létrehozása

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: A msdyn_postaladdress frissítése
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: A msdyn_postaladdress frissítése

    + msdyn_partyelectronicaddress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: msdyn_partyelectronicaddress létrehozása

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: A msdyn_partyelectronicaddress frissítése

        + Törlés

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: Msdyn_partyelectronicaddress törlése

6. Az ügyfélkapcsolati alkalmazásban tiltsa le a következő munkafolyamatokat.

    + Szállítók létrehozása a Partnerek táblában
    + Szállítók létrehozása a Partnerek táblában
    + Személy típusú szállítók létrehozása a Kapcsolattartók táblában
    + Személy típusú szállítók létrehozása a Szállítók táblában
    + Szállítók frissítése a Fiókok táblában
    + Szállítók frissítése a Szállítók táblában
    + Személy típusú szállítók frissítése a Kapcsolattartók táblában
    + Személy típusú szállítók frissítése a Szállítók táblában

7. Az adatgyárban futtassa a sablont **úgy, hogy az eseményindító most** lehetőséget választja az alábbi ábrán látható módon. Ez a folyamat az adatmennyiségtől függően néhány órát is igénybe vehet.

    ![A sablon futtatása.](media/data-factory-trigger.png)

    > [!NOTE]
    > Ha a Partner **,** a Partner **és** a **Szállító** testreszabásával rendelkezik, módosítania kell a sablont.

8. Importálja az új **félrekordokat** a Finance and Operations alkalmazásba.

    1. Töltse le a **FONewParty.csv** fájlt az Azure Blob Storage-ból. Az elérési út a **partybootstrapping/output/FONewParty.csv**.
    2. Konvertálja a **FONewParty.csv** fájlt Excel-fájllá, és importálja az Excel-fájlt a Finance and Operations alkalmazásba. Alternatív megoldásként, ha a CSV importálás működik az Ön számára, közvetlenül importálhatja a .csv fájlt. Ez a lépés az adatmennyiségtől függően néhány órát is igénybe vehet. A további tudnivalókat lásd: [Adatimportálási és -exportálási feladatok áttekintése](../data-import-export-job.md).

    ![A pártrekordok importálása Dataverse.](media/data-factory-import-party.png)

9. Az adatgyárban futtassa a fél postai címét és a fél elektronikus címsablonjait, egymás után.

    + A fél postai címsablonja az ügyfélkapcsolati alkalmazás összes postai címrekordját feljavasztja, és társítja őket a megfelelő **Partner**-, **Kapcsolattartó**- és **Szállítói** rekordokhoz. Három .csv fájlt is létrehoz: ImportFONewPostalAddressLocation.csv, ImportFONewPartyPostalAddress.csv és ImportFONewPostalAddress.csv.
    + A fél elektronikus címsablon az ügyfélkapcsolati alkalmazás összes elektronikus címét feljavasztja, és társítja őket a megfelelő **Fiók**-, **Kapcsolattartó**- és **Szállítói** rekordokhoz. Egy .csv fájlt is létrehoz: ImportFONewElectronicAddress.csv.

    ![A fél postai címének és a fél elektronikus címsablonjainak futtatása.](media/ADF-7.png)

10. A Pénzügy és műveletek alkalmazás ezen adatokkal való frissítéséhez a .csv fájlokat Excel-munkafüzetté kell konvertálnia, és [importálnia kell a Finance and Operations alkalmazásba](/data-entities/data-import-export-job). Alternatív megoldásként, ha a CSV importálása működik az Ön számára, közvetlenül importálhatja a .csv fájlokat. Ez a lépés a kötettől függően néhány órát is igénybe vehet.

    ![Sikeres importálás.](media/ADF-8.png)

11. Az ügyfélkapcsolati alkalmazásban engedélyezze a következő beépülő modul lépéseit:

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

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: msdyn_partypostaladdress létrehozása
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: létrehozása msdyn_partypostaladdress

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: msdyn_partypostaladdress frissítése
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: A msdyn_partypostaladdress frissítése

    + msdyn_postaladdress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: msdyn_postaladdress létrehozása
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: Msdyn_postaladdress létrehozása
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: msdyn_postaladdress létrehozása

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: A msdyn_postaladdress frissítése
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: A msdyn_postaladdress frissítése
 
    + msdyn_partyelectronicaddress

        + Létrehozás

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: msdyn_partyelectronicaddress létrehozása

        + Frissítés

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: A msdyn_partyelectronicaddress frissítése

        + Törlés

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: Msdyn_partyelectronicaddress törlése

12. Az ügyfélkapcsolati alkalmazásban aktiválja a következő munkafolyamatokat, ha korábban inaktiválta őket:

    + Szállítók létrehozása a Partnerek táblában
    + Szállítók létrehozása a Partnerek táblában
    + Személy típusú szállítók létrehozása a Kapcsolattartók táblában
    + Személy típusú szállítók létrehozása a Szállítók táblában
    + Szállítók frissítése a Fiókok táblában
    + Szállítók frissítése a Szállítók táblában
    + Személy típusú szállítók frissítése a Kapcsolattartók táblában
    + Személy típusú szállítók frissítése a Szállítók táblában

13. Futtassa a pártrekordokkal **kapcsolatos térképeket a** fél- és globális címjegyzékben [leírtak](party-gab.md) szerint.

## <a name="explanation-of-the-data-factory-templates"></a>Az Adatgyár sablonok magyarázata

Ez a szakasz végigvezeti az egyes Data Factory-sablonok lépésein.

### <a name="steps-in-the-party-template"></a>A pártsablon lépései

1. Az 1–6. lépés azonosítja azokat a vállalatokat, amelyek engedélyezve vannak a kettős íráshoz, és szűrő záradékot készít számukra.
2. A 7-1–7-9. lépés beolvassa az adatokat mind a Finance and Operations alkalmazásból, mind az ügyfélkapcsolati alkalmazásból, és frissíti az adatokat.
3. A 8–9. lépés összehasonlítja a Partner **,** Kapcsolattartó **és** Szállító **rekordjainak számát** a Finance and Operations alkalmazás és az ügyfélkapcsolati alkalmazás között. Minden olyan rekord, amely nem rendelkezik pártszámmal, kimarad.
4. A 10. lépés két .csv fájlt hoz létre az ügyfélkapcsolati alkalmazásban és a Pénzügy és műveletek alkalmazásban létrehozandó partirekordokhoz.

    - **FOCDSParty.csv** – Ez a fájl mindkét rendszer összes félrekordját tartalmazza, függetlenül attól, hogy a vállalat engedélyezve van-e a kettős íráshoz.
    - **FONewParty.csv** – Ez a fájl a félrekordok egy részét tartalmazza, amely Dataverse ismeri (például a **Prospect** típusú fiókokat).

5. A 11. lépés létrehozza a feleket az ügyfélkapcsolati alkalmazásban.
6. A 12. lépés lekéri a felek globálisan egyedi azonosítóit (GUID-okat) az ügyfélkapcsolati alkalmazásból, és szakaszosra rendezi őket, hogy a következő lépésekben társíthatók legyenek a Partner **-,** Kapcsolattartó **- és** Szállítói **rekordokhoz**.
7. A 13. lépés társítja a **Partner**-, **Kapcsolattartó**- és **Szállítói** rekordokat a parti GUID-okkal.
8. A 14-1–14–3. lépéssel frissítjük a **partner**-, **kapcsolattartói** és **szállítói** rekordokat az ügyfélkapcsolati alkalmazásban a parti GUID-okkal.
9. A 15-1–15-3 lépés előkészíti **a Kapcsolat a fél** számára rekordokat a Partner **-,** Kapcsolattartó **- és** Szállítói **rekordokhoz**.
10. A 16-1–16-7 lépés beolvassa a hivatkozási adatokat, például a megszólításokat és a személyes karaktertípusokat, és társítja azokat a Kapcsolattartó fél **rekordjaihoz**.
11. A 17. lépés egyesíti a **Partner** **, Kapcsolattartó** és **Szállító** rekordok kapcsolattartó félhez **rekordjait**.
12. A 18. lépés importálja a **Partner fél számára** rekordokat az ügyfélkapcsolati alkalmazásba.

### <a name="steps-in-the-party-postal-address-template"></a>A fél postai címsablonjának lépései

1. Az 1-1–1–10 lépés lekéri az adatokat mind a Finance and Operations alkalmazásból, mind az ügyfélkapcsolati alkalmazásból, és az adatokat frissítésre rendezi.
2. A 2. lépés denormalizálja a postai címadatokat a Finance and Operations alkalmazásban a postacím és a fél postacímének összekapcsolásával.
3. A 3. lépés eltávolítja és egyesíti a fiók-, kapcsolatfelvételi és szállítói címadatokat az ügyfél-elköteleződés alkalmazásból.
4. A 4. lépés .csv-fájlokat hoz létre a Finance and Operations alkalmazáshoz új címadatok létrehozásához, amelyek fiók-, kapcsolattartó- és szállítói címeken alapulnak.
5. Az 5-1. lépés .csv-fájlokat hoz létre az ügyfél-elköteleződési alkalmazáshoz az összes címadat létrehozásához, mind a Finance and Operations, mind az ügyfél-elköteleződési alkalmazás alapján.
6. Az 5-2. lépés a .csv fájlokat Finance and Operations importálási formátumba konvertálja kézi importáláshoz.

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. A 6. lépés importálja a postacím-gyűjtési adatokat az ügyfél-elköteleződési alkalmazásba.
8. A 7. lépés lekéri a postacím-gyűjtési adatokat az ügyfél-elköteleződési alkalmazásból.
9. A 8. lépés létrehozza az ügyfélcímadatokat, és hozzárendeli a postai címgyűjtési azonosítót.
10. 9-1-től 9-2-ig lépések Társult felek és postai címek gyűjtési azonosítói postai címekkel és felek postai címeivel.
11. A 10-1-től 10-3-ig terjedő lépések importálják az ügyfelek címeit, postai címeit és felek postai címeit az ügyfél-elköteleződés alkalmazásba.

### <a name="steps-in-the-party-electronic-address-template"></a>A Party elektronikus címsablon lépései

1. Az 1-1-től 1-5-ig lépések lekérik az adatokat mind a Finance and Operations, mind az ügyfél-elköteleződés alkalmazásból, és ezeket az adatokat frissítik.
2. A 2. lépés összevonja az elektronikus címeket az ügyfél-elköteleződési alkalmazásban a fiók-, kapcsolattartó- és szállítói entitásoktól.
3. A 3. lépés egyesíti az elsődleges elektronikus címadatokat az ügyfél-elköteleződési alkalmazásból és a Finance and Operations alkalmazásból.
4. A 4. lépés .csv fájlokat hoz létre.

    - Hozzon létre új elektronikus címadatokat a Finance and Operations alkalmazáshoz a fiók-, kapcsolattartási és szállítói címek alapján.
    - Hozzon létre új elektronikus címadatokat az ügyfél-elköteleződési alkalmazáshoz a Finance and Operations alkalmazásban található elektronikus cím, fiók, kapcsolattartási és szállítói cím alapján.

5. Az 5-1. lépés elektronikus címeket importál az ügyfél-elköteleződési alkalmazásba.
6. Az 5-2. lépés .csv-fájlokat hoz létre a fiókok és kapcsolattartók elsődleges címeinek frissítéséhez az ügyfél-elköteleződés alkalmazásban.
7. A 6-1–6-2 lépések importálják a fiókokat és az elsődleges kapcsolatfelvételi címeket az ügyfél-elköteleződés alkalmazásba.

## <a name="troubleshooting"></a>Hibaelhárítás

1. Ha a folyamat sikertelen, futtassa újra az adatgyárat. Kezdje a sikertelen tevékenységből.
2. Egyes, az adatgyár által generált fájlok felhasználhatók az adatok ellenőrzésére.
3. Az adatgyár .csv fájlok alapján fut. Ezért, ha bármely mezőértékben vessző szerepel, az zavarhatja az eredményeket. A mezőértékekből minden vesszőt el kell távolítania.
4. A **Monitoring** lap információkat tartalmaz az összes feldolgozott lépésről és adatról. A hibakereséshez válasszon egy lépést.

    ![Figyelés lap.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>További tudnivalók a sablonról

A sablonnal kapcsolatos további információkért lásd: [Megjegyzések az Azure Data Factory sablon readme-hez](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).
