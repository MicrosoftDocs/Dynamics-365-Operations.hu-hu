---
title: Frissítés a fél és globális címjegyzék modelljére
description: Ez a témakör azt ismerteti, hogyan lehet kettős írású adatot frissíteni a partner és a globális címjegyzék modellel.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 90ddbe704ab21d62752b581a813601e8986c2103
ms.sourcegitcommit: 180548e3c10459776cf199989d3753e0c1555912
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2021
ms.locfileid: "6112673"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Frissítés a fél és globális címjegyzék modelljére

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A [Microsoft Azure Data Factory sablon](https://aka.ms/dual-write-gab-adf) segít frissíteni a kettős írású **Fiók**, **Kapcsolattartó** és **Szállító** táblaadatokat a partneri és a globális címjegyzék modelljére. A sablon a Finance and Operations- és a Customer Engagement-alkalmazásokból származó adatokat is egyezteti. A folyamat végén a **Partner** rekordjaihoz tartozó **Partner** és **Kapcsolattartó** mezők létrejönnek, és társítva lesznek az ügyfélkapcsolati pályázatok **Számla**, **Kapcsolattartó** és **Szállító** rekordjaihoz. A rendszer .csv fájlt (`FONewParty.csv`) hoz létre, hogy új **Partner** rekordokat hozzon létre a Finance and Operations-alkalmazáson belül. Ez a témakör a Data Factory-sablon használatára és az adatok frissítésére vonatkozó útmutatást tartalmaz.

Ha nincsenek testreszabásai, a sablont használhatja úgy, ahogy van. Ha testreszabott beállításai vannak a **számlához**, a **kapcsolattartóhoz** és a **szállítóhoz**, akkor a következő útmutatásokkal kell módosítania a sablont.

> [!NOTE]
> A sablon csak a **Partner** adatait frissíti. Egy későbbi verzióban a postai és az elektronikus címek is szerepelni fognak.

## <a name="prerequisites"></a>Előfeltételek

A partneri és a globális címjegyzék modelljére való frissítéséhez a következő előfeltételek szükségesek:

+ [Azure-előfizetés](https://portal.azure.com/)
+ [Hozzáférés a sablonhoz](https://aka.ms/dual-write-gab-adf)
+ Önnek kettős írású ügyfélnek kell lennie.

## <a name="prepare-for-the-upgrade"></a>Felkészülés a frissítésre
A frissítés előkészítéséhez a következő tevékenységek szükségesek:

+ **Teljesen szinkronizálva:** Mindkét környezet teljesen szinkronizálva van a **Számla (vevő)**, a **Kapcsolattartó** és a **Szállító** esetében.
+ **Integrációs kulcsok**: a **Számla (Vevő)**, a **Kapcsolattartó** és a **Szállító** tábla az ügyfélkapcsolati alkalmazásokban a gyárilag beépített integrációs kulcsokat használja. Ha testre szabta az integrációs kulcsokat, testre kell szabni a sablont.
+ **Partnerszámszám**: a frissítésre sorra kerülő összes **Számla (Vevő)**, **Kapcsolattartó** és **Szállító** rekordnak van **partnerszáma**. A **Partnerszám** nélküli rekordokat figyelmen kívül hagyja a rendszer. Ha frissíteni szeretné ezeket a rekordokat, a frissítési folyamat kezdete előtt adjon hozzá egy **Partnerszámot**.
+ **Rendszerszünet**: A frissítési folyamat során mind a Finance and Operations-, mind a Customer Engagement-környezeteket kapcsolat nélkül módba kell vinni.
+ **Pillanatkép**: Pillanatkép készítése mind a Finance and Operations-, mind a Customer Engagement-alkalmazásokról. A pillanatképek segítségével szükség esetén visszaállíthatja az előző állapotot.

## <a name="deployment"></a>Telepítés

1. Töltse le a sablont a [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf) eszközből.

2. Jelentkezzen be ide: [Microsoft Azure](https://portal.azure.com/).

3. Hozzon létre egy [erőforráscsoportot](/azure/azure-resource-manager/management/manage-resource-groups-portal).

4. Hozzon létre egy [tárolási fiókot](/azure/storage/common/storage-account-create?tabs=azure-portal) a létrehozott erőforráscsoportban.

5. Hozzon létre egy [adat-előállítót](/azure/data-factory/quickstart-create-data-factory-portal) a fent létrehozott erőforráscsoportban.

6. Nyissa meg az adat-előállítót, és válassza a **Szerző & Monitor** csempét.

7. A **Kezelés** lapon válassza ki az **ARM-sablont**.

8. Válassza ki az **ARM-sablon importálása** lehetőséget a **Partner** sablon importálásához.

9. A sablon importálása az adat-előállítóba. Adja meg az alábbi értékeket a **projekt részleteinél** és a **példányok részleteinél**.

    Mező | Érték
    ---|---
    Előfizetés | Azure-előfizetés
    Erőforráscsoport | Adja meg ugyanazt az erőforrást, amelyhez a tárolási fiókot létrehozták.
    Régió | Adja meg a régiót.
    Gyár neve | Adja meg a gyár nevét.
    FO összekapcsolt Service_service alapkulcs | Az alkalmazás kulcsának megadása.
    Azure Blob Storage_connection karakterlánc | Azure Blob Storage kapcsolati karakterlánc.
    Dynamics Crm kapcsolt Service_password | A felhasználónévként megadott felhasználói fiók jelszava.
    FO összekapcsolt Service_properties_type Properties_url  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    FO összekapcsolt Service_properties_type Properties_tenant | Adja meg azt a bérlői információt (tartománynevet vagy bérlőazonosítót), amely alatt az alkalmazás található.
    FO összekapcsolt Service_properties_type Properties_aad Resource Id | `https://sampledynamics.sandboxoperationsdynamics.com`
    FO összekapcsolt Service_properties_type Properties_service Principal Id | Az alkalmazás ügyfélazonosítójának megadása.
    Dynamics Crm csatolt Service_properties_type Properties_username | A Dynamics 365-csatlakozáshoz használt felhasználónév.

    További tájékoztatás a következő témakörökben található: 
    
    - [Erőforrás-kezelő sablon manuális promóciója az egyes környezetek számára](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Kapcsolt szolgáltatás tulajdonságai](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Adatok másolása az Azure Data Factory segítségével](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. A telepítést követően ellenőrizze az adattárat, az adatáramlást és az adat-előállító kapcsolt szolgáltatását.

   ![Adatkészletek, adatáramlás és csatolt szolgáltatás](media/data-factory-validate.png)

11. Lépjen a **Kezelés** elemre. A **Kapcsolatok** alatt válassza a **Csatolt szolgáltatás** lehetőséget. Válassza a **DynamicsCrmLinkedService** elemet. A **Csatolt szolgáltatás szerkesztése (Dynamics CRM)** űrlapon írja be a következő értékeket.

    Mező | Érték
    ---|---
    Név | DynamicsCrmLinkedService
    Leírás | Az entitások adatainak beolvasására és a CRM-példányhoz való kapcsolódásra szolgáló kapcsolt szolgáltatások
    Csatlakozás integrációs modulon keresztül | AutoResolvelntegrationRuntime
    Telepítés típusa | Online
    Szolgáltatási URI | `https://<organization-name>.crm[x].dynamics.com`
    Hitelesítési típus | Office365
    Felhasználónév |
    Jelszó vagy Azure Key Vault | Jelszó
    Jelszó |

## <a name="run-the-template"></a>Futtassa a sablont

1. Állítsa le a következő **Számla**, **Kapcsolattartó** és **Szállító** kettős írású leképezését a Finance and Operations alkalmazás segítségével.

    + Vevők V3 .(partnerek)
    + Vevők V3(kapcsolattartók)
    + CDS kapcsolattartók V2(kapcsolattartók)
    + CDS kapcsolattartók V2(kapcsolattartók)
    + Szállító V2 (msdyn_vendors)

2. Győződjön meg róla, hogy a leképezések el vannak távolítva a `msdy_dualwriteruntimeconfig` táblából itt: Dataverse.

3. [Kettős írású fél és globális címjegyzék megoldások](https://aka.ms/dual-write-gab) telepítése innen: AppSource.

4. Ha a Finance and Operations alkalmazásban a következő táblák adatokat tartalmaznak, futtassa a **Kezdeti szinkronizálás** műveletet.

    + Üdvözlések
    + Személyes karaktertípusok
    + Udvarias levélzárás
    + Kapcsolattartó megszólításai
    + Döntéshozatali szerepkörök
    + Hűségszintek

5. A Customer Engagement alkalmazásban tiltsa le a következő beépülőmodul-lépéseket.

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

6. Az ügyfélkapcsolati alkalmazásban tiltsa le a következő munkafolyamatokat.

    + Szállítók létrehozása a Partnerek táblában
    + Szállítók létrehozása a Partnerek táblában
    + Személy típusú szállítók létrehozása a Kapcsolattartók táblában
    + Személy típusú szállítók létrehozása a Szállítók táblában
    + Szállítók frissítése a Fiókok táblában
    + Szállítók frissítése a Szállítók táblában
    + Személy típusú szállítók frissítése a Kapcsolattartók táblában
    + Személy típusú szállítók frissítése a Szállítók táblában

7. Az adat-előállítóban futtassa a sablont úgy, hogy kiválasztja a **Kiváltás most** elemet úgy, ahogy az a következő képen látható. Ez a folyamat az adatok mennyisége alapján néhány óráig is igénybe vehet.

    ![Futtatás kiváltása](media/data-factory-trigger.png)

    > [!NOTE]
    > Ha testre szabott beállításai vannak a **Számlához**, a **Kapcsolattartóhoz** és a **Szállítóhoz**, módosítania kell a sablont.

8. Importálja az új **Partner** rekordjait az Finance and Operations alkalmazásból.

    + Töltse le a `FONewParty.csv` fájlt az Azure blobtárolóból. Elérési út a következő: `partybootstrapping/output/FONewParty.csv`.
    + Konvertálja a `FONewParty.csv` fájlt Excel-fájlba, és az Excel-fájlt importálja a Finance and Operations alkalmazásba. Ha a csv import megfelelő, akkor közvetlenül importálhatja a csv fájlt. Az importálás az adatmennyiségtől függően néhány óráig is igénybe vehet. A további tudnivalókat lásd: [Adatimportálási és -exportálási feladatok áttekintése](../data-import-export-job.md).

    ![A Datavers fél rekordjainak importálása](media/data-factory-import-party.png)

9. A Customer Engagement-alkalmazásokban engedélyezze a következő beépülőmodul-lépéseket:

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

10. Ha az előző lépések során inaktiválta őket, aktiválja a következő munkafolyamatokat az ügyfélkapcsolati alkalmazásokban:

    + Szállítók létrehozása a Partnerek táblában
    + Szállítók létrehozása a Partnerek táblában
    + Személy típusú szállítók létrehozása a Kapcsolattartók táblában
    + Személy típusú szállítók létrehozása a Szállítók táblában
    + Szállítók frissítése a Fiókok táblában
    + Szállítók frissítése a Szállítók táblában
    + Személy típusú szállítók frissítése a Kapcsolattartók táblában
    + Személy típusú szállítók frissítése a Szállítók táblában

11. A **Partnerhez** kapcsolódó leképezések futtatása a [Partner és a globális címjegyzék](party-gab.md) utasításának megfelelően.

## <a name="troubleshooting"></a>Hibaelhárítás

1. A folyamat sikertelen végrehajtása esetén futtassa újra az adat-előállítót, a sikertelen tevékenységtől kezdve.
2. Egyes fájlokat az adat-előállító hoz létre, amely adatellenőrzési célokra használható.
3. Az adat-előállító vesszővel tagolt csv-fájlokon alapulva fut. Ha olyan mezőérték van, amelynél vessző van, akkor az hatással lehet az eredményre. El kell távolítania a vesszőket.
4. A **Figyelés** lapon található tájékoztatás az összes lépésről és a feldolgozott adatokról. A hibakereséshez válasszon egy lépést.

    ![Figyelés lap](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>További tudnivalók a sablonról

További információk a sablonról: [Az Azure Data Factory-sablonra vonatkozó megjegyzések, readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).
