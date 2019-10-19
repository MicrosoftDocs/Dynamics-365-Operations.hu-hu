---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. február 27.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 02/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f175c6e60cf87c7dcbde0eaf35357130fa035712
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023999"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-27-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. február 27.)

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2163 buildre vonatkoznak

### <a name="add-a-custom-fields-menu-item-to-system-administration"></a>Egyéni mezők menüelem hozzáadása a Rendszerfelügyelethez

Navigálás az **Egyéni mezők** menühöz hozzá lett adva a **Rendszerfelügyelet** munkaterülethez.

### <a name="hide-the-import-and-create-options-for-new-mobile-applications"></a>Az importálás és létrehozás lehetőségek elrejtése új mobilalkalmazásokhoz

Új mobilalkalmazások jelenleg nem hozhatók létre a Talent alkalmazásban. Az új mobilélmények létrehozásának lehetősége el lett távolítva a **Mobilalkalmazás** menüből.

### <a name="variable-compensation-award-dmf-entity"></a>Változó kompenzációs jutalom (DMF-entitás)

Ebben a verzióban a **Változó kompenzációs jutalom** adatkezelési keretrendszer(DMF) entitás már exportálható.

### <a name="uk-addresses-appear-in-the-personnel-management-analytics-page-as-swiss-addresses"></a>Az Egyesült Királyságra vonatkozó svájci címként jelennek meg a személyzet kezelése analitikai oldalon

Ebben a verzióban a címek város szerint jelennek meg. Ebben a verzióban javítva lettek problémák, ahol vizualizációk helytelenül jelíntették meg az alkalmazott helyét.

### <a name="the-workforce-power-bi-report-shows-an-error-when-a-workers-seniority-date-is-on-leap-day"></a>A Munkaerő Power BI jelentés hibát jelez, amikor az dolgozó szolgálati idejének dátuma szökőnap

A javítás a Microsoft Power BI-ben , hogy figyelembe vegye a február 29-re eső szolgálatiidő-dátumokat.

### <a name="employee-fixed-compensation-employee-variable-awards-employee-variable-plans-enrollments-allow-for-custom-fields"></a>Alkalmazott fix kompenzációja, Alkalmazott változó jutalmak, Alkalmazott változó tervek (jogosultságok) esetében egyéni mezők is lehetségesek

Egyéni mezők adhatók hozzá az Alkalmazott fix kompenzációja, Alkalmazott változó jutalmak, Alkalmazott változó tervek (jogosultságok) esetében. Mostantól több információt követhet nyomon az alkalmazott fix és változó kompenzációs tervekhez, alapértelmezés szerint elérhető információkon túl. Egyéni mezők megadhatók és frissíthetők a felhasználói felületen vagy a rendelkezésre álló entitásokon keresztül.

### <a name="other-miscellaneous-bug-fixes"></a>Egyéb vegyes hibajavítások

Ebben a verzióban számos kisebb hibajavítás is található.

## <a name="coming-soon"></a>Hamarosan

### <a name="advanced-compensation-security-fixed-and-variable"></a>Haladó kompenzációs biztonsági (Fix és változó)

Számos vállalatnál a kompenzációkért és juttatásokért felelős vezetők előfordulhat, hogy csak a bizonyos kompenzációs rekordokhoz férnek hozzá. Ezeket a rekordok a vezetőkhöz és regionális alkalmazottak hoz tartozhatnak. Ez a módosítás lehetővé teszi az Emberi erőforrások osztály (HR) számára a kompenzációs tervek kezelését és karbantartását a szervezet különböző alkalmazottcsoportjaihoz. A biztonsági szerepkörök, amelyek hozzárendelhetők fix és változó kompenzációs tervekhez, határozzák meg a hozzáférést ezekhez a tervekhez és a hozzájuk kapcsolódó alkalmazotti adatokhoz (például fizetési adatok és a bónuszrekordok). Csak a kulcsfontosságú szerepkörök, amelyek rendelkeznek a meghatározott hozzáféréssel tudnak kompenzációt feldolgozni azokhoz az alkalmazottakhoz.

### <a name="platform-update-24-for-finance-and-operations"></a>Platform update 24 a Finance and Operations szolgáltatáshoz

További információért a Microsoft Dynamics 365 Finance and Operations 24-es platformfrissítéséről (2019.március ) lásd: [Előzetes funkciók a Finance and Operations Platform Update 24 (2019. márciusi) verziójában](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).

### <a name="make-employee-fixed-compensation-available-for-future-position-assignments"></a>Az alkalmazott fix kompenzációja elérhetők jövőbeli beosztás-hozzárendelésekhez

Jellemző, hogy az alkalmazottak, akik a szervezethez csatlakoznak jövőbeni kezdési dátummal rendelkeznek. Ez a módosítás lehetővé teszi fix kompenzáció meghatározását jövőbeni beosztás-hozzárendelésekkel rendelkező alkalmazottakhoz.

## <a name="known-issues"></a>Ismert problémák

### <a name="changes-to-the-core-hr-integration-template-talent-common-data-service-to-finance"></a>A Core HR integrációs sablon változtatásai (Talent Common Data Service és Finance között)
A Core HR-hez tartozó sablon „speciális lekérdezési sablonná” lett frissítve. Ezért alapértelmezés szerint a speciális lekérdezési lesz elérhető az ezen sablon segítségével létrehozott projektekhez. Ezenkívül, bármely alapértelmezett leképezési funkció csak a speciális lekérdezési szerkesztőben lesz látható. (Az alapértelmezett leképezés funkciók mint „FN” jelennek meg a leképezésekben.)

Leképezési hibákkal kapcsolatos további tudnivalókat lásd: [Újdonságok és változások a Dynamics 365 Talent: Core HR rendszerben (2018. december 14.)](https://docs.microsoft.com/dynamics365/unified-operations/talent/whats-new-talent-december-14).

Az új sablon használatához hozzon létre egy új projektet, és válassza ki az új Talent integrációs sablont.

A meglévő sablon frissítéséhez, kövesse az alábbi lépéseket.

1. A következő leképezések frissítése:

    - **Munkabeosztások munkákhoz:** Távolítsa el ezt a leképezést.
    - **Munkabeosztások munkákhoz Szülő munkahozzárendelés** Távolítsa el ezt a leképezést.
    - **Munkabeosztások Alapbeosztásokhoz:** Adjon hozzá új leképezést a **Munkabeosztások** Common Data Service entitáshoz az **Alapbeosztás** Finance and Operations entitáshoz. Helyezze át a sorozat 7 pozíciójába.

        [![Feladatbeosztások Alapbeosztásokhoz leképezése](./media/CDS-Mapping1.png)](./media/CDS-Mapping1.png)

    - **Munkabeosztások a Beosztásrészletekhez:** Adjon hozzá új leképezést a **Munkabeosztások** Common Data Service entitáshoz a **Beosztásrészletek** Finance and Operations entitáshoz. Helyezze át a sorozat 8 pozíciójába.

        [![Feladatbeosztások Beosztásrészletekhez leképezése](./media/CDS-Mapping2.png)](./media/CDS-Mapping2.png)

    - **Munkabeosztások a Beosztásidőtartamokhoz:** Adjon hozzá új leképezést a **Munkabeosztások** Common Data Service entitáshoz a **Beosztásidőtartamok** Finance and Operations entitáshoz.

        [![Feladatbeosztások Beosztásidőtartamokhoz leképezése](./media/CDS-Mapping3.png)](./media/CDS-Mapping3.png)

    - **Munkabeosztások a Beosztáshierarchiákhoz:** Adjon hozzá új leképezést a **Munkabeosztások** Common Data Service entitáshoz a **Beosztáshierarchiák** Finance and Operations entitáshoz. Válassza **Speciális lekérdezés** lehetőséget, hogy a speciális lekérdezést elérhetővé tegye a projekt számára.

       [![Speciális lekérdezés gomb](./media/CDS-Advanced-Query.png)](./media/CDS-Advanced-Query.png)

2. Adja hozzá a következő leképezéseket:
    
    [![Hozzárendelés](./media/CDS-Mapping4.png)](./media/CDS-Mapping4.png)

    1. cdm_jobpositionnumber cdm_jobspositionnumb... = POSITIONID cdm_parentjobpositionid.cdm-jobpositionnumb... = PARENTPOSITIONID cdm_validfrom cdm_validfrom = VALIDFROM cdm_validto cdm_validto = VALIDTO
       
    2. Válassza ki a **Speciális lekérdezési és szűrés** hivatkozást a **Keresés** mező mellett.  

    3. Keresse meg a **cdm_parentjobpositionid.cdm_jobpositionnumber** oszlopot, és válassza ki a jobb oldalán, a lefelé nyíl gombot.

    4. A megjelenő párbeszédpanelen jelölje be az **Üres eltávolítása** lehetőséget.

    5. Válassza az **Oszlop hozzáadása \> Feltételes oszlop hozzáadása** lehetőséget, hogy hozzáadja az alapértelmezett értékátalakítást a HIERARCHYTYPENAME elemhez.

        [![Feltételes oszlop hozzáadása parancs](./media/Add-column.png)](./media/Add-column.png)

    6. A **Feltételes oszlop hozzáadása** párbeszédpanelen adja meg a **HIERARCHYTYPENAME** értéket az új oszlop nevének.
    7. A **Ha** részében a feltételnek, jelölje ki bármlyik mezőt, használja az **egyenlő** lehetőséget kapcsolatnak, és adjon meg bármilyen értéket. Az ***Akkor** és **Máskülönben** részeiben a feltételnek, adja meg a szükséges alapértelmezett értéket. Ebben az esetben adja meg **Sor** elemet mindkét résznél.

        [![Feltételes oszlop hozzáadása párbeszédpanel](./media/Add-conditional-column.png)](./media/Add-conditional-column.png)

    8. Válassza az **OK** lehetőséget a **Speciális lekérdezési és szűrés** párbeszédpanel bezárásához.
    9. A **Leképezési feladat** oldalon, jelölje be az új oszlopot egy másik leképezés forrásaként a HIERARCHYTYPENAME elemhez.

        [![Hozzárendelés](./media/CDS-Mapping5.png)](./media/CDS-Mapping5.png)
