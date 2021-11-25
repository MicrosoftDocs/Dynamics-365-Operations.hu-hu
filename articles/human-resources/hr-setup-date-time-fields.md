---
title: Dátum és Idő mezők ismertetése
description: Ez a témakör bemutatja, hogy mi várható a Microsoft Dátum és idő mezőinek használatakor Dynamics 365 Human Resources.
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
ms.openlocfilehash: 06c783c1e4a2961f1445909ea03d557c0985064e
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728589"
---
# <a name="understand-date-and-time-fields"></a>Dátum és Idő mezők ismertetése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

**A Dátum és** idő mezők a Microsoft alapvető alapfogalmai Dynamics 365 Human Resources. Fontos, hogy jobban megértsük, hogyan kell dolgozni a lapokon, a külső forrásokban és a lapokon található dátum- és **·** Dataverse időadatokon.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>A Dátum és a Dátum és az idő mező adattípusai különbségeinek megértése

**A Dátum és** idő mezők időzónaadatokat tartalmaznak, míg a Dátum mezők **·** nincsenek. **A** dátummezők minden helyen ugyanazt az információt mutatják. Ha dátumot ad meg egy Dátum mezőben, akkor az adatbázisba ugyanez a **dátum lesz** írva.

Ha egy Dátum és idő mezőben adatok jelennek meg, akkor a program a felhasználónak a Felhasználói beállítások lapon kiválasztott időzónája (Általános beállítási felhasználói beállítások) alapján módosítja a dátumot és az **·** **·** **\>\>** időt. Lehet, hogy a mezőben beírt dátum- és időinformációk nem egye meg, mint az adatbázisba írt adatok.

[![ Felhasználói beállítások lap.](./media/Useroptionsform.png)](./media/Useroptionsform.png)

## <a name="understanding-date-and-time-fields-on-pages"></a>A lapokon található Dátum és idő mezők ismertetése 

A **Dátum és idő** mezőben a képernyőn megjelenő adatok nem egyeznek meg az adatbázisban tárolt adatokkal, ha a felhasználó időzónája nem az univerzális világidő (UTC) szerint van állítva. A **Dátum és idő** mezők adatait mindig UTC-ben tárolja a program.

[![ Dolgozói oldal UTC-formátuma](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>A Dátum és Idő mezők működés az adatbázisban 

Ha egy dátum- és időértéket írnak az adatbázisba, akkor a rendszer UTC-formátumban tárolja **·** az adatokat. A felhasználók tehát a felhasználói beállításaikban megadott időzónához képest bármilyen dátum- és időadatokat **·** láthatnak.
 
A fenti példában a kezdési időpont egy időpont, nem pedig egy adott dátum. Ha módosítja a bejelentkezett felhasználó időzónáját a GMT + 12:00 értékről GMT UTC értékre, akkor ugyanaz a rekord 04/30/2019 12:00:00 értéket mutat 05/01/2019 12:00:00 időpont helyett.

Az alábbi példában az 000724 alkalmazott foglalkoztatása időzónától függetlenül egyidejűleg aktívvá válik. Az alkalmazott aktív lesz 04. 30-án a GMT-időzónában, amely ugyanaz, mint a 05. 01. a GMT + 12:00 időzónában. Mindkettő ugyanarra az idő pontra hivatkozik, és nem egy adott dátumra. 

[![ Dolgozó lapja, GMT.](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Dátum-és időadatok az adatkezelési keretrendszerben, Excel programban, Dataverse és Power BI szolgáltatásokban 

Az adatkezelési keretrendszer (DMF), Excel-bővítmények és jelentések mind úgy vannak kialakítva, hogy közvetlenül az adatbázis szintjén kommunikálnak az Dataverse Power BI adatokkal. Mivel a felhasználó időzónájában nincs ügyfél a **Dátum és idő** adatok helyesbítésére, az összes **Dátum és idő** érték UTC-ben van, ami helytelen feltételezésekhez vezethet az adatok beírása vagy megtekintése során.
 
Amikor **a dátum- és időadatokat** DMF, Excel vagy az adatbázis feltételezi, hogy az adatok UTC-időben Dataverse vannak. Ha azonban az adatokat megtekintő felhasználók felhasználói időzónája nem UTC-értékre van állítva, akkor a beküldött dátum- és időérték nem fog a vártnak megfelelően megjelenni, és előfordulhat, hogy a felhasználók **·** össze vannak állítva. 
 
Ugyanaz a dolog történik meg visszafelé az adatok exportálásakor. Az exportált DMF-entitás **Dátum és idő** adatai eltérhetnek attól, ami a Dynamics-ügyfélben látható. 
 
Ha a DMF-hez hasonló külső forrásokat használ az adatok szerkesztéséhez vagy létrehozásához, fontos szem előtt tartani, hogy a **Dátum és idő** értékek alapértelmezetten UTC-nek vannak tekintve a felhasználó számítógépének időzónájától vagy az aktuális felhasználói időzóna beállításaitól függetlenül. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Példák ugyanarra a rekordra, amely a különböző terméktartományoknak vannak megjelenítve. 

**Az Emberi erőforrások időzónája UTC értékre van állítva**

[![ A dolgozói lap UTC-formátumra van állítva.](./media/worker-form3.png)](./media/worker-form3.png)

**Az Emberi erőforrások időzónája GMT +12:00 értékre van állítva** 

[![ A dolgozói lap a GMT-be van állítva.](./media/worker-form4.png)](./media/worker-form4.png)

**Excel-OData-n keresztül**

[![ Excel-OData-n keresztül.](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**DMF-előkészítés**

[![ DMF-előkészítés.](./media/DMFStaging.png)](./media/DMFStaging.png)

**DMF-exportálás**

[![ DMF-export.](./media/DMFExport.png)](./media/DMFExport.png)

**Excel Dataverse szolgáltatáson keresztül**

[![ Excel Dataverse szolgáltatáson keresztül.](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Lásd még

[Dátum- és időadatok](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[A felhasználó preferált időzónái](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
