---
title: Első lépések az Elektronikus számlázásbővítménnyel
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Elektronikus számlázásbővítménnyel kapcsolatos első lépéseket a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokban.
author: gionoder
manager: AnnBe
ms.date: 10/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 7b2a3aae43d42060c7fcd9e1ea3db814fc5d8f22
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039846"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Első lépések az Elektronikus számlázásbővítménnyel

[!include [banner](../includes/banner.md)]

Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Elektronikus számlázásbővítménnyel kapcsolatos első lépéseket. Első lépésként végigvezeti a Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Services (RCS), és Dynamics 365 Finance konfigurációs lépésein. Ezt követően leírja a dokumentumok szolgáltatáson keresztül történő elküldésének folyamatát a Dynamics 365 Finance vagy Dynamics 365 Supply Chain Management használatával. Azt is megtudhatja, hogyan értelmezze a beküldési naplókat.

## <a name="availability"></a>Elérhetőség

Az Elektronikus számlázásbővítmény kezdetben több országban is elérhető. A bővítmény támogatja az elektronikus számlák létrehozását, és a következő üzleti dokumentumok beküldését:

| Ország/régió  | Üzleti dokumentum                          |
|-----------------|--------------------------------------------|
| Ausztria         | Értékesítési és projektszámlák                 |
| Belgium         | Értékesítési és projektszámlák                 |
| Brazília          | 55-ös modellű elektronikus pénzügyi bizonylat (NF-e) |
| Dánia         | Értékesítési és projektszámlák                 |
| Észtország         | Értékesítési és projektszámlák                 |
| Finnország         | Értékesítési és projektszámlák                 |
| Franciaország          | Értékesítési és projektszámlák                 |
| Németország         | Értékesítési és projektszámlák                 |
| Olaszország           | Értékesítési és projektszámlák                 |
| Mexikó          | CFDI-számla                               |
| Hollandia     | Értékesítési és projektszámlák                 |
| Norvégia          | Értékesítési és projektszámlák                 |
| Spanyolország           | Értékesítési és projektszámlák                 |
| Európa          | PEPPOL Értékesítési és projektszámlák          |
    
## <a name="licensing"></a>Licenckezelés

Az Elektronikus számlázásbővítmény az aktuális licenccel együtt használható. Nincs szükség további licencekre a szolgáltatás használatához.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt teljesítené az ebben a témakörben ismertetett lépéseket, a következő előfeltételekkel kell rendelkeznie:

- Hozzáférés az LCS-számlájához.
- Egy LCS telepítési projekttel, amely a Finance vagy Supply Chain Management legalább 10.0.13-es verziójával rendelkezik.
- Hozzáférés az RCS-számlájához.
- Kapcsolja be a Globalizációs funkciót az RCS-fiókjához a **Funkciókezelő** modulban. További információért lásd a [Kapcsolódás Regulatory Configuration Services (RCS) szolgáltatáshoz – Globalizációs funkciók](rcs-globalization-feature.md) részt
- Hozzon létre egy kulcstartó-erőforrást és egy tárfiókot az Azure szolgáltatásban. További információért lásd az [Azure tárfiók és kulcstartó létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőséget.

## <a name="overview"></a>Áttekintés

A következő ábra bemutatja azt az öt fő lépést, amelyet ebben a témakörben el fog végezni.

![Az ebben a témakörben szereplő öt lépés áttekintése](media/e-invoicing-services-get-started-overview-5-steps.png)

1. **Azure-erőforrások beállítása:** Az Azure tárterület konfigurálása, és a digitális tanúsítványok feltöltése az Azure Key Vault szolgáltatásba.
2. **LCS beállítása:** Bővítmény telepítése a mikroszolgáltatásokhoz.
3. **RCS beállítása:** A környezet, a felhasználói hozzáférés és az e-számlázási funkciók beállítása.
4. **Vevő beállítása:** Állítsa be a kapcsolatot a vevő és az Elektronikus számlázásbővítmény között, majd kapcsolja ki az elektronikus dokumentumoknál a válaszok küldéséhez és fogadásához használt régi funkciókat.
5. **Számlák beküldése:** Elektronikus dokumentumok beküldése az Elektronikus számlázásbővítményen keresztül, valamint válaszok fogadása.

> [!NOTE]
> Az ebben a témakörben szereplő néhány konfigurációs lépés közös, illetve ország/régió-agnosztikus. Az ország-/régióspecifikus lépések és beállítási eljárások leírása az ország-/régióspecifikus témakörökben olvashatók.

## <a name="lcs-setup"></a>LCS beállítása

1. Jelentkezzen be a LCS-fiók.
2. Válassza ki az **Előzetes funkció kezelése** csempét, és a **Nyilvános előnézeti funkciók** mezőcsoportban válassza ki a **BusinessDocumentSubmission** elemet.
3. Jelölje be az **Előnézeti funkció engedélyezve** mezőt.
4. Válassza ki az LCS-telepítési projektet. A projektnek a kiválasztás előtt működőképesnek kell lennie.
5. A **Környezetbővítmények** gyorslapon válassza az **Új bővítmény telepítése** lehetőséget.
6. Válassza az **Üzleti dokumentum küldése** lehetőséget.
7. A **Bővítmény beállítása** párbeszédpanel **AAD-alkalmazásazonosító** mezőjébe írja ezt: **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Ez egy rögzített érték.
8. Az **AAD-bérlőazonosító** mezőbe írja be az Azure előfizetési fiókja azonosítóját.

    ![A bővítmény párbeszédpanelének beállítása az LCS-ben](media/e-invoicing-services-get-started-lcs-addin-setup.png)

9. Jelölje be a jelölőnégyzetet az Általános Szerződési Feltételek elfogadásához.
10. Válassza a **Telepítés** parancsot.

## <a name="rcs-setup"></a>RCS beállítása

Az RCS beállítása során a következő feladatokat kell elvégeznie:

1. Állítsa be a kulcstartót az RCS-ben.
2. Az RCS-integráció beállítása az Elektronikus számlázásbővítmény kiszolgálóval.
3. Elektronikus számlázásbővítményi környezet létrehozása a szervezet számára.

### <a name="set-up-the-key-vault-in-rcs"></a>Állítsa be a kulcstartót az RCS-ben

1. Jelentkezzen be a RCS-fiókba.
2. Nyissa meg a **Globalizációs funkciók** munkaterületet, a **Környezetek** szakaszban válassza az **e-számlázás** csempét.
3. Válassza a **Szolgáltatáskörnyezetek** lehetőséget.

    ![A Szolgáltatáskörnyezetek lehetőség kiválasztása](media/e-invoicing-services-get-started-select-service-environments.png)

> [!NOTE]
> A **Csatlakoztatott alkalmazások** lehetőség biztosítja az Elektronikus számlázásbővítmény automatikus konfigurálási hozzáférést a Finance vagy Supply Management szolgáltatásban, az RCS-n keresztül. Jelenleg azonban ez a funkció még fejlesztés alatt áll.

4. A Műveleti ablaktáblán válassza a **Key Vault-paraméterek** elemet.

    ![Key Vault-paraméter kiválasztása](media/e-invoicing-services-get-started-select-key-vault-parameters.png)

5. Jelölje be a Műveleti ablaktáblán az **Új** lehetőséget a kulcstartó létrehozásához.
6. A **Key Vault-URI** mezőbe írja be annak a kulcstartó erőforrás **DNS-név** attribútumának értékét, amelyet az Azure szolgáltatásban konfigurált. A **DNS-név** értékének megtalálásával kapcsolatos további tudnivalókat lásd az [Azure tárfiók és Key Vault létrehozása](e-invoicing-create-azure-storage-account-key-vault.md) lehetőségben.

    ![Key Vault URI-mező](media/e-invoicing-services-get-started-enter-key-vault-uri.png)

7. A **Tanúsítványok** gyorsfülön válassza ki a **Hozzáadás** parancsot az összes olyan digitális tanúsítvány nevének és a kulcstartóban lévő titkok megadásához, amely megbízható kapcsolatot igényel. A **Típus** oszlopban beállíthatja, hogy tanúsítványról vagy titokról van-e szó. Mindkét értékhalmazt az Azure szolgáltatásban lévő kulcstároló-erőforráson belül konfigurálják.

    ![Tanúsítványok hozzáadása](media/e-invoicing-services-get-started-add-digital-certificates.png)

8. Ha az ország-/régióspecifikus számlához egy tanúsítványlánc szükséges a digitális aláírás alkalmazásához, akkor válassza a Műveleti ablaktábla **Tanúsítványlánc** elemét, majd adja meg a láncot alkotó tanúsítványok vagy kulcstartó-titkokat.

### <a name="set-up-the-rcs-integration-with-the-electronic-invoicing-add-on-server"></a>Az RCS-integráció beállítása az Elektronikus számlázásbővítmény kiszolgálóval

1. A **Globalizációs funkciók** munkaterületen, a **Kapcsolódó beállítások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** hivatkozást.
2. Válassza ki a **Kattintson ide a Lifecycle Services szolgáltatáshoz való kapcsolódáshoz** lehetőséget. Ha nem szeretne az LCS-hez csatlakozni, válassza a **Mégsem** lehetőséget.
3. Az **e-számlázási szolgáltatások** fülön, a **Szolgáltatási végpont URI** mezőben írja be a rendelkezésre álló földrajzi területeknek megfelelő értéket: `https://businessdocumentsubmission.us.operations365.dynamics.com/` vagy `https://businessdocumentsubmission.eu.operations365.dynamics.com/`.
4. Az **Alkalmazásazonosító** mezőben erősítse meg, hogy az azonosító jelenik meg **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Ez egy rögzített érték.
5. Az **LCS-környezet azonosítója** mezőbe írja be az LCS előfizetési fiókja azonosítóját.

![Elektronikus számlázásbővítény paramétereinek megadása](media/e-invoicing-services-get-started-enter-e-invoicing-parameters.png)

### <a name="add-an-electronic-invoicing-add-on-environment"></a>Az Elektronikus számlázásbővítmény környezet hozzáadása

Az elektronikus számlázásbővítményhez különböző környezeteket hozhat létre, például a Dev, teszt vagy a működési környezeteket.

1. Nyissa meg a **Globalizációs funkciók** munkaterületet, a **Környezetek** szakaszban válassza az **e-számlázás** csempét.
2. Válassza ki az **Új** lehetőséget egy környezet létrehozásához.
3. A **Tárterület SAS-token fiók** mezőbe írja be annak a kulcstartó titoknak a nevét, amelyet az RCS kulcstartóban konfigurált.

    ![Tárterület SAS-token fiókmező](media/e-invoicing-services-get-started-enter-sas-token-secret.png)

4. A **Felhasználók** gyorslapon válassza az **Új** lehetőséget, ha hozzáférést szeretne adni a felhasználóknak ehhez a környezethez.

    ![Szolgáltatási felhasználók hozzáadása](media/e-invoicing-services-get-started-enter-service-users.png)

5. A Művelet ablaktáblán válassza a **Közzététel** lehetőséget a környezet Elektronikus számlázásbővítmény-kiszolgálóra történő közzétételéhez.

    ![Közzététel gomb](media/e-invoicing-services-get-started-publish-service-environment.png)

### <a name="e-invoicing-feature-setup"></a>E-számlázási funkció beállítása

„Az e-számlázás funkció” annak az erőforrásnak az általános neve, amely az Elektronikus számlázási bővítmény kiszolgáló felhasználásához van konfigurálva és közzétéve. Az e-számlázási funkció beállítása többek között az elektronikus jelentés (ER) konfigurációs formátumok használatát egyesíti úgy, hogy konfigurálható export -és importfájlokat hozzanak létre, valamint elősegítsék a műveletek és műveletfolyamatok használatát, illetve lehetővé teszi a szükséges konfigurálható szabályok létrehozását a kérelmek küldéséhez, a válaszok importálásához és a válasz tartalmának elemzéséhez.

A számla- és műveletsorok eltérései miatt az e-számlázási funkció ország-/régió-függő beállítás.

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Elektronikus számlázásbővítmény integráció beállítása a Finance vagy Supply Chain Management szolgáltatásban 

A beállítás közben a következő műveleteket fogja végrehajtani:

1. Nyitott tesztelt funkció
2. Kapcsolja be az Elektronikus számlázásbővítmény integráció funkciót, amely lehetővé teszi a Finance szolgáltatással való integrációt.
3. Az URL beállítása az Elektronikus számlázásbővítmény végponttal.
4. Importálja azokat az ER-konfigurációkat, amelyek kapcsolódnak az ország-/régióspecifikus e-számlázási funkcióhoz.
5. A megfelelő ország-/régióspecifikus e-számlázási funkció bekapcsolása.
6. Importálja az ER-konfigurációkat, és állítsa be azokat a választípusokat, amelyeknél a beküldési folyamat eredményeképpen szükség van az ország-/régióspecifikus számlázási dokumentumok frissítésére.

### <a name="open-flighted-feature"></a>Nyitott tesztelt funkció
Az Elektronikus számlaintegráció funkció engedélyezve van a tesztelésen keresztül. A tesztelés egy olyan fogalom, amely lehetővé teszi, hogy a funkció alapértelmezetten BE vagy KI legyen kapcsolva. A következő lépésekkel engedélyezheti a nem működési környezetben való tesztelésre kiadást. 

1. Hajtsa végre a következő SQL-parancsot:

    ILLESSZE BE A SYSFLIGHTING (JÁRATNÉV, ENGEDÉLYEZETT) ÉRTÉKEKBE ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    ILLESSZE BE A SYSFLIGHTING (JÁRATNÉV, ENGEDÉLYEZETT) ÉRTÉKEKBE ('ElectronicInvoicingServiceIntegrationFeature', 1)
    
2. A fenti módosítást követően futtasson egy IISReset parancsot az összes AOS-kiszolgálón

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Az Elektronikus számlázásbővítmény integráció funkció bekapcsolása

1. Jelentkezzen be a Finance vagy Supply Chain Management szolgáltatásba.
2. A **Funkciókezelés** munkaterületen keressen rá az új **Konfigurálható elektronikus számlázásbővítmény integrációja** funkcióra. Ha a funkció még nem jelenik meg a Funkciókezelés oldalon, futtassa a **Frissítések keresése** funkciót
3. Válassza ki a bekapcsolni kívánt funkciót, majd a részletek ablaktáblán válassza az **Engedélyezés most** lehetőséget.

### <a name="set-up-the-service-endpoint-url"></a>A szolgáltatásvégpont URL-címének beállítása

1. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
2. A **Beküldési szolgáltatás** lap **Szolgáltatásvégpont URL** mezőbe írja be ezt: `https://businessdocumentsubmission.us.operations365.dynamics.com/`.
3. A **Környezet** mezőbe írja be annak az Elektronikus számlázásbővítmény környezetnek a nevét, amelyet az RCS beállítása során hozott létre.

![Szolgáltatásparaméterek megadása](media/e-invoicing-services-get-started-enter-service-endpoint.png)

### <a name="import-the-er-configurations"></a>Az ER-konfigurációk importálása

Ha engedélyezni szeretné az üzleti adatok gyűjtését és küldését az elektronikus számlázásbővítményhez, akkor importálnia kell a használni kívánt ország-/régióspecifikus e-számlázási funkcióhoz kapcsolódó ER adatmodellt, és az adatmodell konfigurációját.

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** csempét. Győződjön meg róla, hogy ez a konfigurációszolgáltató **Aktív** értékre van állítva. A szolgáltatók **Aktív** értékre állításával kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11) elemet.
3. Válassza ki a **Tárházak** lehetőséget.
4. Válassza ki a **Globális erőforrás** , majd a **Megnyitás** lehetőséget.
5. A **Kapcsolódás a Lifecycle Services** párbeszédpanelben válassza a **Kattintson ide a Lifecycle Service szolgáltatáshoz való kapcsolódáshoz** elemet.
6. Attól függően, hogy melyik országban vagy régióban szeretné használni az e-számlázást, importálnia kell a megfelelő adatmodellt, az adatmodell-leképezést és a formátumokat. Az importálni kívánt ER-konfigurációkkal kapcsolatos tudnivalókat lásd az „Első lépések az Elektronikus számlázásbővítménnyel” című témakört.
7. Importálja a **Vevői számla kontextusmodellje** lehetőséget. Ez a modell további paramétereket tartalmaz, amelyek többek között az üzleti adatok benyújtásakor az Elektronikus számlázásbővítményhez használt, Finance szolgáltatásban található környezetet írják le.

### <a name="turn-on-countryregion-specific-e-invoicing-features"></a><a name="region-specific"></a>Az ország-/régióspecifikus e-számlázási funkciók bekapcsolása

Ha be kívánja kapcsolni az ország-/régióspecifikus e-számlázási funkciókat, hogy azok működjenek az Elektronikus számlázásbővítménnyel, akkor minden olyan jogi személynél be kell kapcsolni a funkciót, amelyben használni szeretné. Ezt követően a régi elektronikus számlázási integrációt már nem lehet használni, és az új elektronikus számlázásbővítményhez való integráció be lesz kapcsolva.

1. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
2. A **Funkciók** lap ország-/régióspecifikus e-számlázási funkcióhoz kapcsolódó funkció sorában jelölje ki az **Engedélyezett** oszlopban lévő jelölőnégyzetet. Az azzal kapcsolatos tudnivalókat, hogy melyik funkciót kapcsolja be, lásd az „Első lépések az Elektronikus számlázásbővítménnyel” című témakört.

![Az e-számlázás funkció bekapcsolása](media/e-invoicing-services-get-started-enable-invoicing-feature.png)

> [!NOTE]
> Ha több olyan jogi személy van, aki a különböző országokban vagy régiókban van beállítva, akkor az egyes jogi személyekhez be lehet kapcsolni az ország-/régióspecifikus e-számlázási funkciókat.

### <a name="import-er-configurations-and-set-up-the-response-types-to-update-your-countryregion-specific-invoice-document"></a>Az ER-konfigurációk importálása, és a választípusok beállítása az ország-/régióspecifikus számlára vonatkozó dokumentumok frissítéséhez

Ha az elküldött számlán szereplő dokumentumnak frissítésre van szüksége, miután a kérelmet benyújtotta a kormányzati engedélyezési szolgáltatásokhoz, akkor importálnia kell egy speciális ER-adatmodellt és -konfigurációkat, hogy a számla dokumentuma vagy más további mező állapota frissíthető legyen.

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** csempét.
2. Válassza ki a **Tárházak** lehetőséget.
3. Válassza ki a **Globális erőforrás** , majd a **Megnyitás** lehetőséget.
4. A **Válaszüzenet-modell** , a **Válaszüzenet importálási formátuma** , a **Válaszüzenet-modell leképezése a célhoz** , és a **Fájl tartalmának importálási formátuma** lehetőségek importálása.
5. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
6. Az **Elektronikus dokumentum** lap **Hozzáadás** elemét kiválasztva adja meg annak a táblának a nevét, amely az adott ország-/régióspecifikus számlához kapcsolódik. Az azzal kapcsolatos tudnivalókat, hogy melyik táblaneveket válassza ki, lásd az „Első lépések az Elektronikus számlázásbővítménnyel” című témakört.
7. A választípusok konfigurálásához válassza ki a kívánt **Választípusokat**. Az azzal kapcsolatos tudnivalókat, hogy melyik táblaneveket válassza ki, lásd az „Első lépések az Elektronikus számlázásbővítménnyel” című témakört.

![Választípusok beállítása](media/e-invoicing-services-get-started-set-up-response-types.png)

## <a name="e-invoicing-feature-names-by-country"></a>országonkénti e-számlázási funkciónevek 
A következő tábla olyan más e-számlázási szolgáltatásokat ír le, amelyek az elektronikus jelentések globális adattárából tölthetők le az elektronikus számlák létrehozásához.
A RCS-ben letöltheti a táblában felsorolt e-számlázási funkciókat, az ER-konfigurációkat, valamint a rendelkezésre álló e-számlázási szolgáltatások beállításait.
A Finance szolgáltatásban engedélyezheti a kapcsolódó szolgáltatások hivatkozásait az **Elektronikus dokumentumparaméterek** lapon, hogy elektronikus számlákat adhasson ki ezen országoknak. További tájékoztatásért olvassa el a témakör korábbi [Az ország-/régióspecifikus e-számlázási funkciók bekapcsolása](#region-specific) részét.

| Funkció neve                      | Leírás                                 | Elektronikus jelentéskészítés-konfigurációk                                                                                                  | Beállítások                                                                                                                                                         | Ország/régió  | Funkcióra mutató hivatkozás      |
|-----------------------------------|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|------------------------|
| Osztrák elektronikus számlák (AT) | Értékesítési és projektszámlák Ausztria számára      | - OIOUBL Értékesítési számla <br>- OIOUBL Projektszámla <br>- OIOUBL Értékesítési jóváírás <br>- OIOUBL Projektjóváírás | - Értékesítési számla létrehozása (AT) <br>- Projektszámla létrehozása (AT) <br>- Értékesítési jóváírás létrehozása (AT) <br>- Projektjóváírás létrehozása (AT)         | Ausztria         | EUR-00023              |
| Belga elektronikus számla (BE)   | Értékesítési és projektszámlák Belgium számára      | - UBL Értékesítési számla BE <br>- UBL Projektszámla BE <br>- UBL Projektjóváírás BE <br>- UBL Értékesítési jóváírás BE | - Értékesítési számla létrehozása (BE)<br>- Projektszámla létrehozása (BE) <br>- Értékesítési jóváírás létrehozása (BE) <br>- Projektjóváírás létrehozása (BE)         | Belgium         | EUR-00023              |
| Dán elektronikus számla (DK)    | Értékesítési és projektszámlák Dánia számára      | - OIOUBL Értékesítési számla <br>- OIOUBL Projektszámla <br>- OIOUBL Értékesítési jóváírás <br>- OIOUBL Projektjóváírás | - Értékesítési számla létrehozása (DK) <br>- Projektszámla létrehozása (DK) <br>- Értékesítési jóváírás létrehozása (DK)<br>- Projektjóváírás létrehozása (DK)         | Dánia         | EUR-00023<br> DK-00001 |
| Holland elektronikus számla (NL)     | Értékesítési és projektszámlák Hollandia számára  | - UBL Értékesítési számla NL <br>- UBL Projektszámla NL <br>- UBL Értékesítési jóváírás NL <br>- UBL Projektjóváírás NL | - Értékesítési számla létrehozása (NL) <br> - Projektszámla létrehozása (NL) <br> - Értékesítési jóváírás létrehozása (NL) <br>- Projektjóváírás létrehozása (NL)          | Hollandia | EUR-00023              |
| Észt elektronikus számla (EE)  | Értékesítési és projektszámlák Észtország számára      | - Értékesítési számla (EE) <br> - Projektszámla (EE)                                                                     | - Értékesítési számla létrehozása (EE) <br>- Projektszámla létrehozása (EE)                                                                                           | Észtország         | EUR-00023              |
| Finn elektronikus számla (FI)   | Értékesítési és projektszámlák Finnország számára      | - Értékesítési számla (FI) <br>- Projektszámla létrehozása (FI)                                                          | - Értékesítési számla létrehozása (FI) <br>- Projektszámla létrehozása (FI)                                                                                           | Finnország         | EUR-00023              |
| Francia elektronikus számla (FR)    | Értékesítési és projektszámlák Franciaország számára    | - UBL Értékesítési számla (FR) <br> - UBL Projektszámla FR <br> - UBL Értékesítési jóváírás FR <br>- UBL Projektjóváírás FR | - Értékesítési számla létrehozása (FR) <br> - Projektszámla létrehozása (FR) <br>- Értékesítési jóváírás létrehozása (FR) <br>- Projektjóváírás létrehozása (FR)         | Franciaország          | EUR-00023              |
| Német elektronikus számla (DE)    | Értékesítési és projektszámlák Németország számára      |- Értékesítési számla (DE) <br> - Projektszámla <DE>                                                                     | - Értékesítési számla létrehozása (DE) <br>- Projektszámla létrehozása (DE)                                                                                           | Németország         | EUR-00023              |
| Norvég elektronikus számla (NO) | Értékesítési és projektszámlák Norvégia számára       | - OIOUBL Értékesítési számla <br>- OIOUBL Projektszámla <br>- OIOUBL Értékesítési jóváírás <br>- OIOUBL Projektjóváírás | - Értékesítési számla létrehozása (NO) <br>- Projektszámla létrehozása (NO) <br>- Értékesítési jóváírás létrehozása (NO) <br>- Projektjóváírás létrehozása (NO)          | Norvégia          | EUR-00023<br> NO-00010 |
| Spanyol elektronikus számla (ES)   | Értékesítési és projektszámlák Spanyolország számára        | - Értékesítési számla (ES) <br>- Projektszámla (ES)                                                                     | - Értékesítési számla létrehozása (ES) <br>- Projektszámla létrehozása (ES)                                                                                           | Spanyolország           | EUR-00023 <br>ES-00025 |
| Olasz elektronikus számla (IT)   | Értékesítési és projektszámlák Olaszország számára        | - (Előzetes verzió) Értékesítési számla (IT) <br> - Projektszámla (IT)                                                           | - Értékesítési számla <br> - Projektszámla                                                                                                                           | Olaszország           | EUR-00023 <br>IT-00036 |
| PEPPOL elektronikus számla         | PEPPOL Értékesítési és projektszámla létrehozása | - PEPPOL Értékesítési számla <br>- PEPPOL Projektszámla <br>- PEPPOL Értékesítési jóváírás <br> - PEPPOL Projektjóváírás | - PEPPOL Értékesítési számla létrehozása <br>- PEPPOL Projektszámla létrehozása <br>- PEPPOL Értékesítési jóváírás létrehozása <br>- PEPPOL Projektjóváírás létrehozása |                 | EUR-00023              |


## <a name="electronic-invoice-processing-in-finance-and-supply-chain-management"></a>Elektronikus számla feldolgozása a Finance és Supply Chain Management szolgáltatásokban

A feldolgozás során a következő feladatokat kell elvégeznie:

1. Üzleti dokumentum (számla) elküldése az elektronikus számlázásbővítményen keresztül.
2. A beküldési végrehajtási naplók megtekintése.

### <a name="submit-business-documents"></a>Üzleti dokumentumok beküldése

A rendszeres beküldési folyamat során a program kétirányú kommunikációt folytat a vevő és az Elektronikus számlázásbővítmény között. Az elektronikus dokumentumok elküldése során két fő feladat megvalósítása a cél:

1. Minden olyan elektronikus dokumentum elküldése, amely függőben van a Finance szolgáltatásban, illetve amelyeknek megfelel az állapota az elküldéshez és a kiválasztási feltételek teljesítéséhez.
2. A korábban elküldött elektronikus dokumentumokra adott elektronikus számlázásbővítmény válaszát importálja a Finance szolgáltatásba. Az importálás után a rendszer elemzi a válaszokat, és azoknak megfelelően frissíti az üzleti dokumentumok állapotát.

Üzleti dokumentumokat akár manuálisan, akár az ütemezés követelményei alapján is be lehet küldeni.

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumok beküldése** lehetőségre.
2. A dokumentumok első beküldésekor mindig **Nem** értékre kell állítania a **Dokumentumok újraküldése** lehetőséget. Ha a szolgáltatáson keresztül újra kell küldenie a dokumentumot, akkor ezt a beállítást állítsa **Igen** értékre.
3. A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrő** lehetőséget a **Lekérdezés** párbeszédpanel megnyitásához, amelyen létrehozhat egy lekérdezést, hogy milyen dokumentumok legyenek kiválasztva a beküldéshez.

![Elektronikus dokumentumok beküldése párbeszédpanel](media/e-invoicing-services-get-started-submission-form.png)

### <a name="filter-query"></a>Lekérdezés szűrése

1. A **Tartomány** lapon lévő **Lekérdezés** párbeszédpanelbe írja be a szűrési feltételeket a **Tábla** , **Származtatott tábl** , **Mező** , és **Feltételek** mezőket.
2. Válassza a **Hozzáadás** lehetőséget, hogy a szükségnek megfelelően, minél több további feltételt hozzá tudjon adni az üzleti dokumentumokhoz.

    ![Beküldési szűrési feltételek beállítása](media/e-invoicing-services-get-started-set-up-submission-filter-criteria.png)

3. Kattintson az **OK** gombra a **Lekérdezés** párbeszédpanel bezárásához.
4. Kattintson az **OK** gombra a kiválasztott üzleti dokumentumok Elektronikus számlázásbővítményhez való beküldéséhez.

    > [!NOTE]
    > A dokumentum szolgáltatáson keresztüli beküldésének első kísérlete során a program rákérdez, hogy megerősíti-e a kapcsolatot az Elektronikus számlázásbővítménnyel. Válassza a **Kattintson az Elektronikus dokumentumbeküldési szolgáltatáshoz való csatlakozáshoz**.
    >
    > ![Csatlakozzon az Elektronikus dokumentumbeküldési szolgáltatás üzenetablakához](media/e-invoicing-services-get-started-dialog-form-connect-e-Invoicing-services.png)
    >
    > Ha a kapcsolat sikeres, akkor egy visszaigazoló üzenet jelenik meg.
    >
    > ![Az elektronikus számlázásbővítménnyel való kapcsolat megerősítése](media/e-invoicing-services-get-started-confirmation-connection-e-invoicing-services.png)

5. Zárja be a párbeszédpanelt.

> [!NOTE]
> Minden egyes beküldés után a Műveletközpont jeleníti meg a beküldött dokumentumok számát.
>
> ![Műveletközpont üzenetek](media/e-invoicing-services-get-started-view-action-center-messages.png)

### <a name="submission-by-batch"></a>Beküldés köteg szerint

A dokumentumok manuális elküldése helyett automatizálhatja a küldési folyamatot, és a háttérben futtathatja azt a kötegelt végrehajtás konfigurált gyakorisága alapján.

1. Az **Elektronikus dokumentumok beküldése** párbeszédablakban, a **Futtatás a háttérben** gyorslapon állítsa a **Kötegelt feldolgozás** beállítást **Igen** értékre.
2. Az **Ismétlődés** lapon konfigurálja a kötegelt feldolgozási gyakoriságot.

![Köteg szerinti beküldés beállítása](media/e-invoicing-services-get-started-set-up-submission-batch.png)

### <a name="view-all-submission-logs"></a>Az összes beküldési napló megtekintése

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.
2. A **Dokumentumtípus** mezőben válassza ki a szűrni kívánt dokumentumtípust.

    ![A dokumentumtípus kiválasztása a beküldési naplók megtekintéséhez](media/e-invoicing-services-get-started-select-document-type-for-viewing-submission-log.png)

    > [!IMPORTANT]
    > A **Beküldési állapot** oszlopban látható érték a beküldési folyamat befejezéséhez kapcsolódó állapotot jelöli. Azt jelzi, hogy az RCS konfigurált műveletek áramlása véget értaz elektronikus dokumentum jóváhagyása vagy elutasítása nélkül. A **Beküldési állapot oszlopában** lévő érték nem felel meg a beküldött dokumentum állapotának. Megtekintheti az elküldött dokumentum állapotát (azt, hogy a dokumentum jóváhagyása vagy elutasítása megtörtént) a beküldési napló részleteiben lévő **Műveletfeldolgozási napló** gyorslap további témakörben leírtak szerint.

3. A Műveleti ablaktáblán kattintson a **Lekérdezések \> Beküldési részletek** megjelenítése elemre.
4. A beküldési napló részleteinek megtekintése.

    ![A beküldési napló részletei](media/e-invoicing-services-get-started-view-submission-log-form.png)

A beküldési naplóban megjelenő eredmények attól függnek, hogy az e-számlázási funkció hogyan lett beállítva az RCS-ben. A beállítástól függetlenül azonban a beérkezési naplónak három gyorslapja van:

- **Műveletek feldolgozása** – Ez a gyorslap azon végrehajtási naplót mutatja meg, amely az RCS-ben beállított funkcióverzióban konfigurált műveletekhez tartozik. Az **Állapot** oszlop azt jelzi, hogy a művelet futtatása sikeres volt-e.
- **Műveletfájlok** – Ez a gyorslap a műveletek végrehajtása során létrehozott közbenső fájlokat jeleníti meg. A fájl letöltéséhez és tartalmának megtekintéséhez válassza a **Megtekintés** lehetőséget.
- **Műveletnapló feldolgozása** – Ez a gyorslap az Elektronikus számlázásbővítmény és a cél webszolgáltatás közötti kommunikáció eredményeit jeleníti meg. Azt is bemutatja, hogy mit küldött vissza a webszolgáltatásból-feldolgozás.

## <a name="related-topics"></a>Kapcsolódó témakörök

- [Elektronikus számlázásbővítmény – áttekintés](e-invoicing-service-overview.md)
- [Első lépések a brazil Elektronikus számlázásbővítménnyel](e-invoicing-bra-get-started.md)
- [Első lépések a mexikói Elektronikus számlázásbővítménnyel](e-invoicing-mex-get-started.md)
- [Első lépések az olasz Elektronikus számlázásbővítménnyel](e-invoicing-ita-get-started.md)
- [Az Elektronikus számlázásbővítmény beállítása](e-invoicing-setup.md)
