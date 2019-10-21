---
title: Vállalat fogalma a Common Data Service szolgáltatásban
description: Ez a témakör az vállalatadatok integrációját ismerteti a Finance and Operations és a Common Data Service között.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: aa4d54fd7b3ab407751ad6ca1032d742c23eed41
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184531"
---
## <a name="company-concept-in-common-data-service"></a>Vállalat fogalma a Common Data Service szolgáltatásban

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

A Finance and Operations alkalmazásban a *vállalat* koncepciója egyszerre jogi fogalom és üzleti fogalom. Mindemellett adatok biztonsági és láthatósági határa is. A felhasználók mindig egyetlen vállalat kontextusában dolgoznak, és az adatok nagy részét vállalat szerint van kezelve.

A Common Data Service nem rendelkezik ezzel egyenértékű koncepcióval. A legközelebbi koncepció a *részleg*, amely elsősorban biztonsági és láthatósági határ a felhasználói adatok számára. Ez a fogalom nem rendelkezik ugyanazokkal a jogi vagy üzleti vonatkozásokkal, mint a vállalat koncepciója.

Mivel a részleg és a vállalat nem egyenértékű fogalmak, nem lehetséges egy-az-egyhez (1:1) leképzés kényszerítése hozzájuk a Common Data Service integráció céljából. Mivel azonban a felhasználóknak alapértelmezés szerint meg kell tudniuk tekinteni ugyanazokat a rekordokat az alkamazásban és a Common Data Service magoldásokban, a Microsoft egy új entitást vezetett be a Common Data Service megoldásban, amelynek neve cdm\_Company. Ez az entitás egyenértékű a Vállalat entitással az alkalmazásban. Annak garantálására, hogy a rekordok láthatósága alapértelmezetten megegyezzen az alkalmazás és a Common Data Service között, a következő beállításokat javasoljuk a Common Data Service adatai számára:

+ Minden egyes kettős írási lehetőséget engedélyező Finance and Operations Vállalati rekordhoz legyen létrehozva egy társított CDM\_Company rekord.
+ Egy cdm\_Company rekord létrehozásakor és a kettős írás engedélyezésekor egy alapértelmezett részleg jön létre ugyanazzal a névvel. Bár a részleghez automatikusan létrejön egy alapértelmezett csoport, a részleg nincs használatban.
+ Olyan különálló tulajdonoscsapat jön létre, amelynek neve azonos. Ez is hozzá van rendelve a részleghez.
+ Alapértelmezés szerint az alkalmazásban létrehozott, és a Common Data Service szolgáltatásban duplán írt rekordok tulajdonosa a hozzárendelt részleghez kapcsolódó „DW Owner” csoport.

A következő ábrán egy példa látható az ilyen típusú adatbeállításra a Common Data Service megoldásban.

![Adatok beállítása a Common Data Service megoldásban](media/dual-write-company-1.png)

Ezen konfigurációnak az következtében az USMF vállalathoz kapcsolódó minden rekord egy olyan csapat tulajdonában lesz, amely a be Common Data Service USMF részlegéhez van csatolva. Emiatt azok a felhasználók, akik a részleghez egy részlegszintű láthatóságra beállított biztonsági szerepkörön keresztül férnek hozzá, most már láthatják ezeket a bejegyzéseket. A következő példa bemutatja, hogyan használhatók a csapatok ezen rekordok helyes elérésére.

+ Az „Értékesítési menedzser” szerepkört a "„USMF Sales” csoport tagjaihoz rendelték.
+ Azok a felhasználók, akik rendelkeznek az „Értékesítési menedzser” szerepkörrel, hozzáférhetnek minden olyan partnerbejegyzéshez, amelyek ugyanannak a részlegnek a tagjai, amelynek ők is.
+ Az „USMF Sales” csapat s kapcsolva van az USMF üzleti egységhez, amely korábban említettünk.
+ Ezért az „USMF Sales” csapat tagjai láthatnak a „USMF DW” felhasználói által birtokolt bármely olyan fiókot, amely a Finance and Operations USMF vállalati entitásából származik.

![Hogyan használhatók a csapatok](media/dual-write-company-2.png)

Ahogy az előző ábrán is látható, ez a 1:1 leképezés az üzleti egység, a vállalat és a csapat között csak egy kiindulási pont. Ebben a példában egy új „Európa” nevű részleg manuálisan lett létrehozva a Common Data Service szolgáltatásban mint DEMF és ESMF szülője. Ez az új gyökérszintű részleg nem kapcsolódik kettős íráshoz. Ugyanakkor használható arra, hogy az „EUR Sales” csapat hozzáférhessen a partneradatokhoz a DEMF és az ESMF rekordokban is, azáltal, hogy az adatok láthatóságát **Szülő/gyermek részleg** értékre állítják a társított biztosági szerepkörben.

Egy utolsó témában ismertetjük, hogyan határozza meg a lettős írás, hogy melyik tulajdonoshoz rendelje hozzá a rekordokat. Ezt a viselkedés az **Alapértelmezett tulajdonoscsoport** mező szabályozza a cdm\_Vállalat rekordban. Ha egy cdm\_Vállalat rekordhoz a kettős írás engedélyezve van, egy beépülő modul automatikusan létrehozza a hozzárendelt üzleti egységet és a tulajdonos csoportot (ha még nem létezik), és beállítja az **Alapértelmezett tulajdonosi csapat** mezőt. Az adminisztrátor megváltoztathatja ezt a mezőt egy másik értékre. Azonban az adminisztrátor nem törölheti ezt a mezőt, amíg az entitiás engedélyezve van kettős íráshoz.

![Alapértelmezett tulajdonosi csoport mező](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Cég adatcsíkozása és rendszerindítás

A Common Data Service-integráció vállalati azonosító segítségével létre a vállalatok paritását az adatcsíkozáshoz. Amint az alábbi ábrán látható, minden vállalatspecifikus entitás ki lesz bővítve úgy, hogy egy több-az-egyhez (N:1) kapcsolata lesz a CDM\_Companí entitással.

![N:1 kapcsolat a vállalatspecifikus entitás és a cdm_Company entitás között](media/dual-write-bootstrapping.png)

+ A rekordok esetében a vállalat hozzáadása és mentése után az érték írásvédett lesz. Ezért a felhasználóknak meg kell győződniük arról, hogy a megfelelő vállalatot választják ki.
+ Csak a vállalati adatokat tartalmazó rekordok alkalmasak az alkalmazás és a Common Data Service közötti kettős írásra.
+ Meglévő Common Data Service adatokhoz egy adminisztrátor által kezelt bootstrapping-élmény is hamarosan elérhető lesz.
