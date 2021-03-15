---
title: Első lépések a brazil elektronikus számlázásbővítménnyel
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Első lépéseket a brazil elektronikus számlázásbővítmény Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásban való használatát.
author: gionoder
manager: AnnBe
ms.date: 09/04/2020
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
ms.openlocfilehash: 0320bd1d9e93cc30ed75f28e387ac2ec8dbfc226
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962834"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Első lépések a brazil elektronikus számlázásbővítménnyel 

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Előfordulhat, hogy a Brazil elektronikus számlázásbővítmény jelenleg nem támogatja a Microsoft Dynamics 365 Finance vagy Dynamics 365 Supply Chain Management szolgáltatásba épített pénzügyi bizonylatintegrációban elérhető összes funkciót.

Ez a témakör olyan információkat tartalmaz, amelyek bemutatják a brazil elektronikus számlázásbővítménnyel kapcsolatos első lépéseket. Végigvezeti a Regulatory Configuration Services (RCS), illetve a Finance és Supply Chain Management szolgáltatásban található ország-függő konfigurációs lépéseken. Ezenkívül végigvezeti az NF-e pénzügyi bizonylat (55-ös modellű elektronikus pénzügyi bizonylat) szolgáltatáson keresztüli beküldési folyamatán, és bemutatja, hogyan lehet ellenőrizni a feldolgozási eredmények és pénzügyi bizonylatok állapotát.

## <a name="prerequisites"></a>Előfeltételek

A témakör lépéseinek végrehajtása előtt végre kell hajtania az [Első lépések az Elektronikus számlázásbővítménnyel](e-invoicing-get-started.md) részben található lépéseket.

## <a name="rcs-setup"></a>RCS beállítása

Az RCS beállítása során a következő feladatokat kell elvégeznie:

1. Az e-számlázási funkció importálása az NF-e pénzügyi bizonylatokhoz.
2. Ellenőrizze az NF-e pénzügyi bizonylatok engedélyezéséhez szükséges fájlformátumokat.
3. Tekintse át a jóváhagyott NF-e érvénytelenítési kérelmezéséhez szükséges fájlformátumokat.
4. Konfigurálja az NF-e pénzügyi bizonylatok engedélyezéséhez szükséges eseményt.
5. Konfigurálja a jóváhagyott NF-e érvénytelenítési kérelmezéséhez szükséges eseményt.
6. Rendelje hozzá az e-számlázási funkciót egy Elektronikus számlázásbővítmény környezethez.
7. Tegye közzé az e-számlázási funkciót.

> [!NOTE]
> „Az e-számlázás funkció” annak az erőforrásnak az általános neve, amely az Elektronikus számlázási bővítmény kiszolgáló felhasználásához van konfigurálva és közzétéve. Az e-számlázási funkció beállítása többek között az elektronikus jelentés (ER) konfigurációs formátumok használatát egyesíti úgy, hogy konfigurálható export- és importfájlokat hozzanak létre, valamint elősegítsék a műveletek és műveletfolyamatok használatát, illetve lehetővé teszi a szükséges konfigurálható szabályok létrehozását a kérelmek küldéséhez, a válaszok importálásához és a válasz tartalmának elemzéséhez.

## <a name="import-the-e-invoicing-feature"></a>Az e-számlázási funkció importálása

1. Jelentkezzen be a RCS-fiókba
2. Nyissa meg a **Globalizációs funkciók** munkaterületet, a **Funkciók** szakaszban válassza az **e-számlázás** csempét.
3. Az **e-számlázási funkciók** oldalon jelölje be az **Importálás** lehetőséget az NF-e pénzügyi bizonylat e-számlák funkció Globális adattárból történő importálásához.

    ![Importálás gomb](media/e-Invoicing-services-get-started-BRA-Select-Import-e-Invoicing-feature.png)

4. Válassza ki az NF-e pénzügyi bizonylat funkciót, majd válassza az **Importálás** lehetőséget.

    ![Az NF-e funkció importálása](media/e-Invoicing-services-get-started-BRA-Select-Import-NF-e-feature.png)

### <a name="create-a-new-version-of-the-nf-e-fiscal-document-feature"></a>Az NF-e pénzügyi bizonylat funkció új verziójának létrehozása

- Az **e-számlázási funkciók** oldal **Verziók** lapján válassza az **Új** lehetőséget.

![Új e-számlázási funkcióverzió hozzáadása](media/e-Invoicing-services-get-started-BRA-Select-New-e-Invoicing-feature-version.png)

### <a name="update-the-configuration-version"></a>A konfigurációverzió frissítése

1. Az **e-számlázási funkciók** oldal **Konfigurációk** lapján válassza ki a **Hozzáadás** vagy a **Törlés** lehetőséget a konfigurációverziók (ER-fájlformátum-konfigurációk) kezeléséhez.

    ![E-számlázás funkciókonfigurációk kezelése](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-configurations.png)

    - Amikor létrehozza NF-e pénzügyi bizonylat funkció új verzióját, az összes konfigurációverzió (ER-fájlformátumok) öröklődik a legújabb verzióból.
    - Az NF-e pénzügyi bizonylat engedélyezésre való beküldéséhez a következő konfigurációverziók szükségesek:

        - NFe beküldésének exportálási formátuma
        - NFe-válaszüzenet importálása
        - NFe-hibanapló importálása

    - Az NF-e érvénytelenítésre való beküldéséhez a következő konfigurációverzió szükséges:

        - NFe érvényesítésének exportálási formátuma

2. A listáról válassza ki a kívánt konfigurációverziót, majd a **Szerkesztés** vagy **Nézet** elemet kijelölve nyissa meg a **Formátumtervező** oldalt, amelyen szerkesztheti és megtekintheti a konfigurációt.

    ![A Formátumtervező lap megnyitása](media/e-Invoicing-services-get-started-BRA-Configuration-ER-fomat-designer.png)

3. Az ER-formátum fájlkonfiguráció szerkesztéséhez vagy megtekintéséhez használja a **Formátumtervező** lapot. További információ: [Elektronikus dokumentum-konfigurációk létrehozása](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Formátumtervező oldal](media/e-Invoicing-services-get-started-BRA-ER-Format-designer.png)

### <a name="manage-the-e-invoicing-feature-setups"></a>Kezelje az e-számlázás funkció beállításait

- Az **e-számlázási funkciók** oldal **Beállítások** lapján válassza a **Hozzáadás** vagy **Törlés** parancsot az e-számlázási funkciók beállításainak (azaz NF-e-események) kezeléséhez.

![Az e-számlázás funkció beállításainak kezelése](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-setup.png)

Ha egy másik e-számlázási funkcióból származó, az NF-e pénzügyi bizonylat funkció új verzióját hozza létre, akkor az összes funkcióbeállítás (NF-e-események) a legújabb verzióból öröklődnek.

Az NF-e pénzügyi bizonylatok engedélyezésre való beküldéséhez a **Beküldés** funkcióbeállítás szükséges.

Az NF-e érvénytelenítésre való beküldéséhez az **Érvénytelenítés** funkcióbeállítás szükséges.

#### <a name="configure-the-submit-feature-setup"></a>A Beküldési funkcióbeállítás konfigurálása

1. Az **e-számlázási funkciók** oldal **Beállítások** lapjának **Funkcióbeállítás** oszlopában válassza ki az **Beküldés** lehetőséget.
2. Válassza ki a **Szerkesztés** opciót.

    ![E-számlázási funkcióbeállítás szerkesztése](media/e-Invoicing-services-get-started-BRA-Edit-e-Invoicing-feature-setup.png)

3. A **Funkcióverzió beállítása** oldalon válassza ki a **Műveletek** lapot a műveletek listájának kezeléséhez.

    ![Műveletek lap](media/e-Invoicing-services-get-started-BRA-Select-Actions.png)

4. Ellenőrizze az NF-e engedélyezéséhez szükséges műveleteket.

    | Műveletazonosító | Művelet neve                  | Művelet leírása                                                |
    |-----------|------------------------------|-------------------------------------------------------------------|
    | 1         | Dokumentum átalakítása           | NF-e XML-fájl létrehozása beküldéshez.                          |
    | 2         | Dokumentum aláírása                | Digitális tanúsítvány alkalmazása az XML-fájlon.                    |
    | 3         | Brazil SEFAZ-szolgáltatás hívása | Az aláírt XML-fájl beküldése a webszolgáltatásoknak, engedélyezés céljából. |
    | 4         | Folyamatválasz             | Webszolgáltatás válaszának megszerzése.                                     |
    | 5         | Dokumentum átalakítása           | Elemezze a válaszként kapott fájltípus tartalmát.     |
    | 6         | Dokumentum átalakítása           | A beküldés állapotának lekérdezéséhez hozzon létre egy XML-fájlt.    |
    | 7         | Brazil SEFAZ-szolgáltatás hívása | A beküldési állapotot kérő XML-fájl beküldése.          |
    | 8         | Folyamatválasz             | Webszolgáltatás válaszának megszerzése.                                     |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>A SEFAZ webszolgáltatások URL-címének beállítása 

1. A **Funkcióverzió beállítása** oldal **Műveletek** lapjának **Műveletek** gyorslapján válassza a **Brazil SEFAZ szolgáltatás hívása** (műveletazonosító: **3**) lehetőséget.
2. A **Paraméterek** gyorslap **URL-cím paramétere** mezőjébe írja be a SEFAZ webszolgáltatás URL-címét az NF-e beküldéséhez.
3. Válassza a **Műveletek** gyorslap **Brazil SEFAZ szolgáltatás hívása** (műveletazonosító: **7**) lehetőséget.
4. A **Paraméterek** gyorslap **URL-cím paramétere** mezőjébe írja be a SEFAZ webszolgáltatás URL-címét az NF-e beküldéséhez.

#### <a name="configure-the-cancellation-feature-setup"></a>Az Érvénytelenítési funkcióbeállítás konfigurálása

1. Az **e-számlázási funkciók** oldal **Beállítások** lapjának **Funkcióbeállítás** oszlopában válassza ki az **Érvénytelenítés** lehetőséget.
2. Válassza ki a **Szerkesztés** opciót.
3. A **Funkcióverzió beállítása** oldalon válassza ki a **Műveletek** lapot a műveletek listájának kezeléséhez.
4. Tekintse át a jóváhagyott NF-e érvénytelenítési kérelmezéséhez szükséges műveleteket.

    | Műveletazonosító | Művelet neve                  | Művelet leírása                                               |
    |-----------|------------------------------|------------------------------------------------------------------|
    | 1         | Dokumentum átalakítása           | Az NF-e érvényelenítési XML-fájl létrehozása beküldéshez.            |
    | 2         | Dokumentum aláírása                | Digitális tanúsítvány alkalmazása az XML-fájlon.                   |
    | 3         | Brazil SEFAZ-szolgáltatás hívása | Az aláírt XML-fájl beküldése a webszolgáltatásoknak, érvénytelenítés céljából. |
    | 4         | Folyamatválasz             | Webszolgáltatás válaszának megszerzése.                                    |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>A SEFAZ webszolgáltatások URL-címének beállítása

1. A **Funkcióverzió beállítása** oldal **Műveletek** lapjának **Műveletek** gyorslapján válassza a **Brazil SEFAZ szolgáltatás hívása** (műveletazonosító: **3**) lehetőséget.
2. A **Paraméterek** gyorslap **URL-cím paramétere** mezőjébe írja be a SEFAZ webszolgáltatás URL-címét az engedélyezett NF-e érvénytelenítéséhez.

### <a name="make-an-e-invoicing-environment-available-and-assign-a-draft-version"></a>E-számlázási környezet elérhetővé tétele és a Piszkozat verzió hozzárendelése

1. Az **e-számlázási funkciók** oldal **Környezetek** lapján válassza az **Engedélyezés** lehetőséget.
2. A **Környezet** mezőben válassza ki a környezetet.
3. A **Hatálybalépés dátuma** mezőben válassza ki azt a dátumot, amikortól a környezetnek hatályossá kell válnia.
4. Válassza az **Engedélyezés** lehetőséget.

![E-számlázási környezet engedélyezése](media/e-Invoicing-services-get-started-BRA-Enable-e-Invoicing-environment.png)

### <a name="change-the-status-to-completed"></a>Az állapot módosítása Befejezett értékre

1. Az **e-számlázási funkciók** oldal **Verziók** lapján válassza ki a **Piszkozat** állapotú e-számlázási funkció verzióját.
2. Válassza az **Állapot módosítása \>Teljes** lehetőséget.

### <a name="change-the-status-to-publish"></a>Az állapot módosítása Közzétett értékre

1. Az **e-számlázási funkciók** oldal **Verziók** lapján válassza ki a **Befejezett** állapotú e-számlázási funkció verzióját.
2. Válassza az **Állapot módosítása \> Közzétett** lehetőséget.

![Az e-számlázási funkció közzététele](media/e-Invoicing-services-get-started-BRA-Publish-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Elektronikus számlázásbővítmény integráció beállítása a Finance vagy Supply Chain Management szolgáltatásban

A beállítás során a következő feladatokat kell elvégeznie:

1. Kapcsolja be a brazil NF-e szövetségi funkciót.
2. Importálja a sepcifikus ER-adatmodellt, az adatmodell-leképezést, valamint az NF-e pénzügyi bizonylathoz szükséges formátumokat.
3. Importálja az ER-konfigurációt, és állítsa be azokat a választípusokat, amelyeknél a beküldési folyamat visszaérkezése után szükség van a pénzügyi bizonylat állapotának frissítésére.

### <a name="turn-on-the-nf-e-federal-feature-for-brazil"></a>Kapcsolja be a brazil NF-e szövetségi funkciót

1. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
2. A **Funkciók** lapon válassza ki az **Engedélyezés** jelölőnégyzetet az **BR00053** funkcióhivatkozás sorában.

### <a name="import-the-er-data-model-mapping-required-for-nf-e-fiscal-documents"></a>Az NF-e pénzügyi bizonylathoz szükséges ER-adatmodell-leképezés importálása

1. Bejelentkezés a Finance szolgáltatásba.
2. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** csempét. Győződjön meg róla, hogy ez a konfigurációszolgáltató **Aktív** értékre van állítva. A szolgáltatók **Aktív** értékre állításával kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11) elemet.
3. Válassza ki a **Tárházak** lehetőséget.
4. Válassza ki a **Globális erőforrás \> Megnyitás** lehetőséget.
5. A **Pénzügyi bizonylatok leképezése** konfigurációk importálása.

### <a name="import-er-configurations-and-set-up-the-response-types-for-fiscal-documents"></a>A választípusok beállítása a pénzügyi bizonylatokhoz, illetve az ER-konfigurációk importálása

1. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációszolgáltatók** szakaszban, válassza a **Microsoft** csempét.
2. Válassza ki a **Tárházak** lehetőséget.
3. Válassza ki a **Globális erőforrás \> Megnyitás** lehetőséget.
4. Az **NF-e hibanapló importálása (BR)**, az **NF-e válaszadatok importálási formátuma (BR)**, és az **NF-e válaszüzenet importálása (BR)** importálása.
5. Menjen a **Szervezeti adminisztráció \> Beállítás \> Elektronikus dokumentumparaméterek** lehetőségre.
6. Az **Elektronikus dokument** lapon válassza a **Hozzáadás** lehetőséget.
6. A **Tábla neve** mezőben adja meg a **Pénzügyi bizonylat fejléce** értéket.
7. A **Dokumentum kontextusa** mezőben válassza a **Vevői számla kontextusmodellje – Pénzügyi bizonylat kontextusa** elemet.
8. Válassza ki a **Választípusok** lehetőséget.
9. Válassza az **Új**, majd a **Válasz típusa** mezőt, majd a **Válasz** elemet.
10. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
11. A **Modell-leképezés** mezőben válassza a **Válaszüzenet importálási formátuma – Modell-leképezés válaszüzenetből** lehetőséget.
12. Válassza a **Mentés** lehetőséget.
13. Válassza az **Új**, majd a **Válasz típusa** mezőt, majd adja meg a **Válaszadatok** elemet.
14. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
15. A **Modell-leképezés** mezőben válassza ki az **NFe-válaszadatok importálási formátuma – Válaszadatok importálása** lehetőséget.
16. Válassza a **Mentés** lehetőséget.

## <a name="electronic-invoice-processing"></a>Elektronikus számla feldolgozása

A Finance szolgáltatásban történő feldolgozás során a következő feladatokat kell elvégeznie:

1. Pénzügyi bizonylat beküldése az elektronikus számlázásbővítményen keresztül.
2. A beküldési végrehajtási naplók megtekintése, és a feldolgozás eredményeinek áttekintése.
3. Pénzügyi bizonylat érvénytelenítésének beküldése az elektronikus számlázásbővítményen keresztül.

### <a name="submit-nf-e-fiscal-documents-for-sefaz-authorization"></a>Küldje be az NF-e pénzügyi bizonylatokat a SEFAZ engedélyezéséhez 

A **Konfigurálható elektronikus számlázásbővítmény integrációja** funkció bekapcsolását követően az NF-e pénzügyi bizonylatok érvényesítésre való beküldésének régi folyamata (**NF-e exportálási/importálási folyamata**) már nem használható. Ezt felváltotta egy új, **Elektronikus dokumentumok beküldése** nevű folyamat.

> [!NOTE]
> Mielőtt folytatná, győződjön meg róla, hogy van legalább egy vevői pénzügyi intézmény által kiállított 55-ös modellű vevői pénzügyi bizonylata. A pénzügyi bizonylatok irányát **Kimenő** értékre, illetve az állapotot **Létrehozott** értékre kell állítani. További információkért lásd a [Vevői pénzügyi bizonylat kiadása (Brazília)](https://docs.microsoft.com/dynamics365/finance/localizations/tasks/br-00038-issuing-customer-fiscal-document) lehetőséget.

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumok beküldése** lehetőségre.
2. A dokumentumok első beküldésekor mindig **Nem** értékre kell állítania a **Dokumentumok újraküldése** lehetőséget. Ha a szolgáltatáson keresztül újra kell küldenie a dokumentumot, akkor ezt a beállítást állítsa **Igen** értékre.
3. A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrő** lehetőséget a **Lekérdezés** párbeszédpanel megnyitásához, amelyen létrehozhat egy lekérdezést, hogy milyen dokumentumok legyenek kiválasztva a beküldéshez.
4. A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget.
5. A **Tábla neve** mezőben válassza a **Pénzügyi bizonylat fejléce** lehetőséget.
6. A **Származtatott tábla** mezőben válassza a **Pénzügyi bizonylat fejléce** lehetőséget.
6. A **Mező** mezőben válassza ki a **Szám** lehetőséget.
7. A **Feltételek** mezőbe írja be annak a pénzügyi bizonylatnak a számát, amelyet el kell küldeni.
8. Kattintson az **OK** gombra a **Lekérdezés** párbeszédpanel bezárásához.
8. Kattintson az **OK** gombra a kiválasztott dokumentumok elküldéséhez.

> [!NOTE]
> A dokumentum szolgáltatáson keresztüli beküldésének első kísérlete során a program rákérdez, hogy megerősíti-e a kapcsolatot az Elektronikus számlázásbővítménnyel. Válassza a **Kattintson az Elektronikus dokumentumbeküldési szolgáltatáshoz való csatlakozáshoz**.

### <a name="view-all-submission-logs"></a>Az összes beküldési napló megtekintése

A **Konfigurálható elektronikus számlázásbővítmény integráció** funkció bekapcsolása után egy új lap érhető el, amellyel nyomon követheti a dokumentum beküldési folyamatát. Ezen a lapon megtekintheti az összes beküldött dokumentum beküldési naplóját.

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.
2. A **Dokumentumtípus** mezőben válassza ki a **Pénzügyi bizonylat fejléce** lehetőséget, ha kizárólag pénzügyi bizonylatokra szeretne szűrni.
3. A Művelet ablaktáblán válassza ki a **Lekérdezések \> Beküldések részletei** lehetőséget a beküldési végrehajtási naplók részleteinek megtekintéséhez.

![A beküldési napló részleteinek megtekintése](media/e-Invoicing-services-get-started-BRA-View-Submission-log-details.png)

> [!NOTE] 
> Az NF-e pénzügyi bizonylatoknál a **Hibakód** oszlop a SEFAZ webszolgáltatások által visszaküldött visszajuttatási kódot jeleníti meg.

### <a name="view-submission-logs-through-the-fiscal-document-page"></a>Beküldési naplók megtekintése a pénzügyi bizonylat oldalon

A **Konfigurálható elektronikus számlázásbővítmény integrációja** funkció bekapcsolása után a pénzügyi bizonylat oldalon is megtekintheti a beküldési naplókat.

1. Menjen a **Főkönyv \> Lekérdezések és jelentések \> Pénzügyi bizonylatok \> Összes pénzügyi bizonylat** lehetőségre.
2. Válasszon ki egy olyan pénzügyi bizonylatot, amelyet korábban már elküldött az Elektronikus számlázásbővítményen keresztül.
3. A Művelet panel **NF-e szövetségi** lapján válassza az **Elektronikus dokumentumnapló** menüpontot.

![Beküldési naplók megtekintése a pénzügyi bizonylat oldalról](media/e-Invoicing-services-get-started-BRA-View-Submission-log-from-Fiscal-document-viewer.png)

### <a name="submit-approved-nf-e-fiscal-documents-for-sefaz-cancellation"></a>Küldje be az engedélyezett NF-e pénzügyi bizonylatokat a SEFAZ érvénytelenítéséhez

A **Konfigurálható elektronikus számlázásbővítmény integrációja** funkció bekapcsolása után már nem használható a régi folyamat az NF-e pénzügyi bizonylatok érvénytelenítésére. Egy új érvénytelenítési folyamat váltja fel, amely az **Elektronikus dokumentum beküldési naplója** lapon lesz beágyazva.

> [!NOTE]
> Győződjön meg róla, hogy az elfogadott NF-e pénzügyi bizonylatoknál futtatta a vevői pénzügyi bizonylat érvénytelenítését. További információkért lásd a [Vevői pénzügyi bizonylat érvénytelenítése (Brazília)](https://docs.microsoft.com/dynamics365/finance/localizations/latam-bra-cancel-customer-fiscal-documents) lehetőséget.

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.
2. Válassza ki a pénzügyi bizonylat, majd a **Funkciók \> Kapcsolódó beküldés küldése** funkciót.
3. Adja meg a kapcsolódó beküldés leírását, majd kattintson az **OK** gombra.

### <a name="view-cancellation-submission-logs"></a>Tekintse meg az érvénytelenítési beküldési naplókat

1. Menjen a **Szervezeti adminisztráció \> Időszakos \> Elektronikus dokumentumok \> Elektronikus dokumentumbeküldési napló** lehetőségre.
2. A **Dokumentumtípus** mezőben válassza ki a **Pénzügyi bizonylat fejléce** lehetőséget, ha kizárólag pénzügyi bizonylatokra szeretne szűrni.
3. Válassza ki a pénzügyi bizonylat, majd a Műveleti ablaktáblán válassza ki a **Lekérdezések \> Kapcsolódó beküldés** lehetőséget.

    A kapcsolódó beküldések olyan beküldések, amelyek az első fő beküldéshez kapcsolódnak. Például az adott NF-e-t engedélyező beküldés a fő beküldés. A beküldés, amely ugyanezen NF-e SEFAZ-ban történő érvénytelenítését kéri, egy kapcsolódó beküldés. Ez kizárólag azért van, mert egy olyan feladat érvénytelenítését kéri, amely egy másik beküldésen keresztül lett elvégezve.

    A **Kapcsolódó beküldések** oldal egy adott pénzügyi bizonylat összes kapcsolódó beküldésér és beküldési állapotát megjeleníti. A következő ábrán az első sor azt a beküldést jelöli, amely a pénzügyi bizonylat jóváhagyását kérte. A második sor azt a beküldést jelöli, amely érvénytelenítette az adott pénzügyi bizonylatot.

    ![Az érvénytelenítési beküldési naplók megtekintése](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log.png)

4. A Művelet ablaktáblán válassza ki a **Lekérdezések \> Beküldések részletei** lehetőséget a beküldési végrehajtási naplók részleteinek megtekintéséhez.

    ![Az érvénytelenítési beküldési napló részleteinek megtekintése](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log-details.png)

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat
A BR-00053 (NF-e szövetségi) funkció engedélyezése és használata korlátozott adatok küldését igényelheti, ideértve a szervezet adóregisztrációs azonosítóját. Ezek továbbítva lesznek az adóhatóság által kinevezett harmadik fél ügynökségekhez, az elektronikus számlák – kormányzati szervek webszolgáltatással való integrációhoz szükséges, előre meghatározott formátumban való – adott adóhatósághoz történő elküldése céljából. A rendszergazda engedélyezheti és letilthatja a BR-00053 (NF-e Federal) funkciót a **Szervezeti adminisztráció \> Beállítások \> Elektronikus dokumentumparaméterek** lehetőségre való navigálással. Válassza ki a **Funkciók** lapot, majd a BR-00053 (NF-e Federal) funkciót tartalmazó sort, és végezze el a megfelelő kijelölést. A külső rendszerekből ebbe a Dynamics 365 online szolgáltatásba importált adatok az [Adatvédelmi nyilatkozatunk](https://go.microsoft.com/fwlink/?LinkId=512132) hatálya alá tartoznak. Kérjük, hogy további tájékoztatásért olvassa el az országspecifikus funkciók dokumentációja szakaszokban található Adatvédelmi nyilatkozatot.


## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlázásbővítmény – áttekintés](e-invoicing-service-overview.md)
- [Első lépések az Elektronikus számlázásbővítménnyel](e-invoicing-get-started.md)
- [Az Elektronikus számlázásbővítmény beállítása](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]