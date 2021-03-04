---
title: Dátuma és Idő mezők ismertetése
description: Annak megértése, mire számíthat, ha a Microsoft Dynamics 365 Human Resources megoldásban dátum-és időmezőket használ. Megtudhatja, hogy mire számíthat, ha az Emberi erőforrások egy űrlapján külső forrásból vagy a Common Data Service szolgáltatásból származó adatokkal dolgozik.
author: Darinkramer
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 027e46d53fd9704f5483e90409be53c1510e8cd4
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529852"
---
# <a name="understand-date-and-time-fields"></a>Dátuma és Idő mezők ismertetése

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

**A dátum és Idő** mezők alapvető fontosságúak a Dynamics 365 Human Resources megoldásban. Fontos, hogy megtanulja, hogyan dolgozzon a **Dátum és idő** adatokkal Dynamics 365 Human Resources űrlapokon, a Common Data Service szolgáltatásban és külső forrásokon.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>A Dátum és a Dátum és az idő mező adattípusai különbségeinek megértése

A **Dátum és idő** mező időzóna-információt tartalmaz, míg a **Dátum** mezők nem. A **Dátum** mezők bármilyen helyen ugyanazt az információt jelenítik meg. Amikor dátumot ír be a **Dátum** mezőbe, az Emberi erőforrások ugyanazt a dátumot írja az adatbázisba.

Amikor egy **Dátumot és idő** mezőben adatokat jeleníti meg, az Emberi erőforrások a **Felhasználói beállítások** képernyőn (**Közös > Beállítás > Felhasználói beállítások**) megadott időzóna alapján módosítja a dátumot és az időt. Előfordulhat, hogy a mezőben megadott dátum-és időadatok nem egyeznek meg az adatbázisba írt adatokkal.

[![Felhasználói beállítások képernyő](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Dátum és Idő mezők képernyőkön 

Amikor a **Dátumot és idő** mezőbe írja be az adatokat, a képernyőn megjelenő adatok nem egyeznek meg az adatbázisban tárolt adatokkal, ha a felhasználó időzónája nem az univerzális világidő (UTC) szerint van állítva. A **Dátum és idő** mezők adatait mindig UTC-ben tárolja a program.

[![Dolgozó képernyő](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>A Dátum és Idő mezők működés az adatbázisban 

Amikor az Emberi erőforrások egy **Dátumot és idő** értéket ír az adatbázisba, az adatokat a UTC-ben tárolja. Ez lehetővé teszi a felhasználók számára , hogy a felhasználói beállításaiban megadott időzónához viszonyítva jelenítsenek meg minden **Dátum és idő** adatot.
 
A fenti példában a kezdési időpont egy időpont, nem pedig egy adott dátum. Ha módosítja a bejelentkezett felhasználó időzónáját a GMT + 12:00 értékről GMT UTC értékre, akkor az imént létrehozott rekord ugyanaz a rekord, 04/30/2019 12:00:00 értéket mutat 05/01/2019 12:00:00 időpont helyett.
  
Az alábbi példában a 000724 számú alkalmazott munkaviszonya az időzónatól függetlenül aktívvá válik ugyanabban az időpontban. Az alkalmazott aktív lesz 2019. 04. 30-án a GMT-időzónában, amely ugyanaz, mint a 2019. 05. 01. a GMT + 12:00 időzónában. Mindkettő ugyanarra az idő pontra hivatkozik, és nem egy adott dátumra. 

[![Dolgozó képernyő](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a>Dátum-és időadatok az adatkezelési keretrendszerben, Excel programban, Common Data Service és Power BI szolgáltatásokban 

Az adatkezelési keretrendszer, az Excel-bővítmény, a Common Data Service és a Power BI és a jelentéskészítés mind az adatbázis szintjén, közvetlenül az adatokkal való együttműködésre szolgálnak. Mivel a felhasználó időzónájában nincs ügyfél a **Dátum és idő** adatok helyesbítésére, az összes **Dátum és idő** érték UTC-ben van, ami helytelen feltételezésekhez vezethet az adatok beírása vagy megtekintése során.  
 
A **Dátum és idő** adatok, amelyek DMF, Excel, vagy Common Data Service szolgáltatáson keresztül lettek beküldve UTC-nek vannak tekintve az adatbázisban. Ez némi zavart okozhat, ha a benyújtott **dátum-és időérték** nem a várt módon jelenik meg, mert az adatokat megjelenítő felhasználó időzónája nem UTC értékre van állítva. 
 
Ugyanaz a dolog történik meg visszafelé az adatok exportálásakor. Az exportált DMF entitás **Dátum-és idő** adatai különbözőek lehetnek attól ami a Dynamics ügyfélben látható. 
 
Ha olyan külső forrásokat használ, mint a DMF az adatok szerkesztéséhez vagy létrehozásához, akkor fontos szem előtt tartani, hogy a **Dátum-és idő** értékek alapértelmezetten UTC-nek vannak tekintve a felhasználó számítógépének időzónájától vagy az aktuális felhasználói időzóna beállításaitól függetlenül. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Példák ugyanarra a rekordra, amely a különböző terméktartományoknak vannak megjelenítve. 

**Az Emberi erőforrások időzónája UTC értékre van állítva**

[![Dolgozó képernyő](./media/worker-form3.png)](./media/worker-form3.png)

**Az Emberi erőforrások időzónája GMT +12:00 értékre van állítva** 

[![Dolgozó képernyő](./media/worker-form4.png)](./media/worker-form4.png)

**Excel-OData-n keresztül**

[![Excel-OData-n keresztül](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**DMF-előkészítés**

[![DMF-előkészítés](./media/DMFStaging.png)](./media/DMFStaging.png)

**DMF-exportálás**

[![DMF-előkészítés](./media/DMFexport.png)](./media/DMFexport.png)

**Excel Common Data Service szolgáltatáson keresztül**

[![Excel Common Data Service szolgáltatáson keresztül](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Lásd még

[Dátum- és időadatok](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[A felhasználó preferált időzónái](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]