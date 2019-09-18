---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. március 26.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 03/26/2019
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
ms.search.validFrom: 2019-03-26
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 24070d1efa3299c378d7a4a328531817a598d272
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741567"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-26-2019"></a>Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. március 26.)

[!include [banner](includes/banner.md)]

Ez a témakör a Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="enhancements-to-interview-scheduling"></a>Interjúk ütemezésével kapcsolatos fejlesztések
A következő fejlesztéseket érhetők el az interjúk ütemezése terén.

- Az állás felvételi vezetője vagy toborzója úgy is dönthet, hogy emlékeztetetőt indít el az interjúkészítő számára a visszajelzés küldésére. A társított e-mail sablon az emlékeztetőhöz konfigurálható is.
- Interjú összegzésének megosztása során a jelentkezővel, miközben az interjú ütemezője elrejtheti az interjúztatók nevét, illetve sorokat is elrejthet az interjú összegző nézetéből.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

### <a name="embedded-images-in-activities"></a>Beágyazott képek tevékenységekben
Mostantól közvetlenül is beágyazhat képeket tevékenységekbe. Nem csak az internetről képek másolása és beillesztése lehetéséges, hanem a helyi fájlrendszerből is feltölthet képeket. A tevékenység mérete 1 MB-ra korlátozódik. Ha a kép túl nagy, méretezze át, és próbálja újból feltölteni.

[![Hozzárendelés](./media/embedimages.png)](./media/embedimages.png)

Ebben a verzióban kisebb hibajavítások találhatók a Dynamics 365 Talent: Onboard alkalmazáshoz.

## <a name="changes-in-core-hr"></a>A Core HR módosításai
**Build 8.1.2210**

### <a name="custom-field-support-available-for-select-entities-in-common-data-service"></a>Egyéni mező támogatása is elérhető bizonyos entitásokhoz a Common Data Service megoldásban 

A következő Common Data Service entitások mostantól támogatják a Dynamics 365 for Talent alkalmazásban létrehozott ügyfélmezőket:

- Dolgozó
- Etnikum
- Veteránállapot
- Nyelvkód
- Beosztás
- Feladattípus
- Beosztás
- Beosztás
- Beosztás típusa
 
### <a name="employment-history-not-displayed-chronologically"></a>Alkalmazási előzmények nem időrendi sorrendben jelennek meg
Ezzel a módosítással, a foglalkoztatási előzmények lap az alkalmazotti rekordokat időrendben jeleníti meg, függetlenül a vállalattól. Rendezési beállítások segítségével vállalat szerint is rendezhet.

### <a name="fixed-compensation-plans-dont-appear-when-restricting-user-by-company-in-security"></a>A Fix kompenzációs konstrukciók nem jelennek meg, korlátozva van a felhasználó vállalati biztonság szerint.
Ebben a kiadásban a fix kompenzációs konstrukciók nem jelennek meg, ha a felhasználók korlátozva vannak a felhasználó vállalati biztonság szerint. Az összes biztonsági beállítás figyelembe van véve, és fix konstrukció jelennek meg azokhoz a vállalatokhoz, amelyekhez a felhasználó elérési engedéllyel rendelkezik. 

### <a name="cant-delete-job-records-using-open-in-excel-option-in-talent"></a>Nem lehet törölni a feladatrekordokat a Megnyitás Excelben lehetőséggel a Talentben
Ebben a verzióban, eltávolíthat feladatrekordokat a **Megnyitása Excelben** lehetőség használatával a Dynamics 365 for Talent alkalmazásban.

### <a name="upgrade-to-common-data-service"></a>Frissítés Common Data Service megoldásra
A Common Data Service frissítés határideje gyorsan közeledik. Jelentkezzen be annak meghatározásához, hogy kell-e az adatbázist frissíteni kell PowerApps felügyeleti központba. Határidőkkel és frissítéséhez szükségesek további lépésekkel kapcsolatos tudnivalókat lásd: [Frissítés a Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds) megoldásra.

## <a name="in-preview"></a>Előnézetben

Előnézeti funkciók engedélyezésével kapcsolatos további tudnivalókat lásd: [Talent – előnézeti funkciók elérése](./access-preview-feature.md).

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Okkódok megadásának engedélyezése a szabadságtípusoknál
A szervezeteknek kiegészítő információkra lehet szüksége a szabadságkérelmekkel kapcsolatosan. Ezen információk megszerzése érdekében az alkalmazottaknak okkódot kell megadniuk szabadságkérelmükhöz. Ebben a verzióban, megadhat okkódokat egy adott távolléttípushoz, és engedélyezheti az alkalmazottak számára okkód választását szabadságkérelmükhöz.

### <a name="configure-reason-codes-to-be-required-when-submitting-time-off-for-certain-leave-types"></a>Okkódokat konfigurálása ,hogy azok kötelezők legyenek bizonyos távollétkérelmek leadásakor.
Előfordulhat, hogy a szervezetek okkódok megadását kérik, bizonyos távolléttípusokhoz, amikor a munkavállalók távolléti kérelmet nyújtanak be. Ez az ország/régió követelményei vagy vállalati irányelvek alapján lehet szükséges. Ebben a verzióban lehetővé vált, hogy aHR megadja mely Szabadságtípusokhoz kötelező okkód megadása. Ez meg lesz követelve, amikor az alkalmazottak távollétkérelmet nyújtanak be, ha a távoléthez okkód szükséges.

## <a name="coming-soon"></a>Hamarosan

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Haladó kompenzációs biztonsági (fix és változó)
Számos vállalatnál a kompenzációkért és juttatásokért felelős vezetők előfordulhat, hogy csak a bizonyos kompenzációs rekordokhoz férnek hozzá. Ezek a vezetőkhöz és regionális alkalmazottak hoz tartozhatnak. Ez a módosítás lehetővé teszi a HR számára kompenzációs tervek kezelését és karbantartását a szervezet különböző alkalmazottcsoportjaihoz. A fix és változó kompenzációs tervek, amelyeket hozzárendelhet biztonsági szerepkörökhöz, határozzák meg a hozzáférést ezekhez a tervekhez és a hozzájuk kapcsolódó alkalmazotti adatokhoz, például fizetés és bónuszrekordok. Csak a hozzáférést kapott szerepkörök dolgozhatnak fel kompenzációt ezekhez a munkavállalókhoz.

###  <a name="email-support-for-alerts"></a>E-mailek támogatása figyelmeztetésekhez
A 25-ös platformfrissítéssel a felhasználók létrehozhatnak figyelmeztetési szabályokat, amely automatikusan értesítő e-maileket kézbesítenek, a kapcsolattartóknak, ha egy esemény kezdeményezi azt. 

### <a name="duplicate-employee-checks-user-interface-changes"></a>Duplikált alkalmazottak ellenőrzése: Felhasználói felület módosítása
Ez a módosítással az ismétlődések észleli a program, amikor névmezőket ad meg, és egy állapot jelenik meg a talált ismétlődések számával. A hivatkozás kiválasztásával megnyithat egy új lapot, hogy megállapítsa, hogy használja-e az észlelt egyezést. Az adatbevitel megzavarása elkerülése érdekében az ismétlődéseket tartalmazó űrlap nem nyílik meg automatikusan.
