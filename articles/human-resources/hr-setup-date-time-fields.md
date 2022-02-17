---
title: Dátum és Idő mezők ismertetése
description: Ez a témakör bemutatja, hogy mire számíthat a Microsoft Dátum és Idő mezőinek használatakor Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7c81155f0c5150af44982f224c8eca2026a78ee7
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8060889"
---
# <a name="understand-date-and-time-fields"></a>Dátum és Idő mezők ismertetése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



**Dátum és idő** mezők a Microsoft alapvető fogalmai Dynamics 365 Human Resources. Fontos, hogy megértse, hogyan kell vele dolgozni **Dátum és idő** adatok oldalakon, be Dataverse és külső forrásokból.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>A Dátum és a Dátum és az idő mező adattípusai különbségeinek megértése

**Dátum és idő** mezők időzóna-információkat tartalmaznak, míg **Dátum** mezők nem. **Dátum** mezők ugyanazt az információt mutatják bármely helyen. Amikor megad egy dátumot a **Dátum** mezőbe ugyanaz a dátum kerül beírásra az adatbázisba.

Amikor adatok jelennek meg a **Dátum és idő** mezőben a dátum és az idő a felhasználó időzónája alapján módosul, amelyet a kiválasztott **Felhasználói beállítások** oldal (**Gyakori \> Beállít \> Felhasználói beállítások**). Előfordulhat, hogy a mezőbe beírt dátum és idő nem egyezik meg az adatbázisba írt adatokkal.

[![Felhasználói beállítások oldal.](./media/Useroptionsform.png)](./media/Useroptionsform.png)

## <a name="understanding-date-and-time-fields-on-pages"></a>A Dátum és Idő mezők megértése az oldalakon 

A **Dátum és idő** mezőben a képernyőn megjelenő adatok nem egyeznek meg az adatbázisban tárolt adatokkal, ha a felhasználó időzónája nem az univerzális világidő (UTC) szerint van állítva. A **Dátum és idő** mezők adatait mindig UTC-ben tárolja a program.

[![Munkavállalói oldal UTC.](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>A Dátum és Idő mezők működés az adatbázisban 

Amikor a **Dátum és idő** érték kerül az adatbázisba, az adatok UTC-ként kerülnek tárolásra. Ezért a felhasználók bármelyiket láthatják **Dátum és idő** a felhasználói beállításokban meghatározott időzónához viszonyított adatok.
 
A fenti példában a kezdési időpont egy időpont, nem pedig egy adott dátum. Ha módosítja a bejelentkezett felhasználó időzónáját a GMT + 12:00 értékről GMT UTC értékre, akkor ugyanaz a rekord 04/30/2019 12:00:00 értéket mutat 05/01/2019 12:00:00 időpont helyett.

Az alábbi példában a 000724 alkalmazott foglalkoztatása egy időben válik aktívvá, időzónától függetlenül. Az alkalmazott aktív lesz 2019. 04. 30-án a GMT-időzónában, amely ugyanaz, mint a 2019. 05. 01. a GMT + 12:00 időzónában. Mindkettő ugyanarra az idő pontra hivatkozik, és nem egy adott dátumra. 

[![Munkavállalói oldal GMT.](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Dátum-és időadatok az adatkezelési keretrendszerben, Excel programban, Dataverse és Power BI szolgáltatásokban 

Az adatkezelési keretrendszer (DMF), az Excel bővítmény,Dataverse, és Power BI A jelentések mind úgy vannak kialakítva, hogy közvetlenül az adatbázis szintjén kommunikáljanak az adatokkal. Mivel a felhasználó időzónájában nincs ügyfél a **Dátum és idő** adatok helyesbítésére, az összes **Dátum és idő** érték UTC-ben van, ami helytelen feltételezésekhez vezethet az adatok beírása vagy megtekintése során.
 
Mikor **Dátum és idő** az adatok DMF, Excel, ill Dataverse, az adatbázis azt feltételezi, hogy UTC-ben van. Ha azonban az adatokat megtekintő felhasználók felhasználói időzónája nem UTC-re van állítva, akkor az elküldi **Dátum és idő** érték nem a várt módon jelenik meg, és a felhasználók összezavarodhatnak. 
 
Ugyanaz a dolog történik meg visszafelé az adatok exportálásakor. Az exportált DMF-entitás **Dátum és idő** adatai eltérhetnek attól, ami a Dynamics-ügyfélben látható. 
 
Ha a DMF-hez hasonló külső forrásokat használ az adatok szerkesztéséhez vagy létrehozásához, fontos szem előtt tartani, hogy a **Dátum és idő** értékek alapértelmezetten UTC-nek vannak tekintve a felhasználó számítógépének időzónájától vagy az aktuális felhasználói időzóna beállításaitól függetlenül. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Példák ugyanarra a rekordra, amely a különböző terméktartományoknak vannak megjelenítve. 

**Az Emberi erőforrások időzónája UTC értékre van állítva**

[![A dolgozói oldal UTC-re van állítva.](./media/worker-form3.png)](./media/worker-form3.png)

**Az Emberi erőforrások időzónája GMT +12:00 értékre van állítva** 

[![A dolgozói oldal GMT-re van állítva.](./media/worker-form4.png)](./media/worker-form4.png)

**Excel-OData-n keresztül**

[![Excel-OData-n keresztül.](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**DMF-előkészítés**

[![DMF-előkészítés.](./media/DMFStaging.png)](./media/DMFStaging.png)

**DMF-exportálás**

[![DMF-export.](./media/DMFExport.png)](./media/DMFExport.png)

**Excel Dataverse szolgáltatáson keresztül**

[![Excel Dataverse szolgáltatáson keresztül.](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Lásd még

[Dátum- és időadatok](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[A felhasználó preferált időzónái](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
