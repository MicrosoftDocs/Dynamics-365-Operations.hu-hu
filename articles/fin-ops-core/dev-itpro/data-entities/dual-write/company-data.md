---
title: Vállalat fogalma a Common Data Service szolgáltatásban
description: Ez a témakör a vállalati adatok integrációját ismerteti a Finance and Operations és a Common Data Service között.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/04/2020
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
ms.openlocfilehash: 444bfc1698a206ca34e67f742df63431a3b02649
ms.sourcegitcommit: 7da8811f1a7db858efb76edb0bdf857a47d07600
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/27/2020
ms.locfileid: "3728413"
---
# <a name="company-concept-in-common-data-service"></a>Vállalat fogalma a Common Data Service szolgáltatásban

[!include [banner](../../includes/banner.md)]


A Finance and Operations alkalmazásban a *vállalat* koncepciója egyszerre jogi fogalom és üzleti fogalom. Mindemellett adatok biztonsági és láthatósági határa is. A felhasználók mindig egyetlen vállalat kontextusában dolgoznak, és az adatok nagy részét vállalat szerint van kezelve.

A Common Data Service nem rendelkezik ezzel egyenértékű koncepcióval. A legközelebbi koncepció a *részleg*, amely elsősorban biztonsági és láthatósági határ a felhasználói adatok számára. Ez a fogalom nem rendelkezik ugyanazokkal a jogi vagy üzleti vonatkozásokkal, mint a vállalat koncepciója.

Mivel a részleg és a vállalat nem egyenértékű fogalmak, nem lehetséges egy-az-egyhez (1:1) leképzés kényszerítése hozzájuk a Common Data Service integráció céljából. Mivel azonban a felhasználóknak alapértelmezés szerint meg kell tudniuk tekinteni ugyanazokat a rekordokat az alkamazásban és a Common Data Service magoldásokban, a Microsoft egy új entitást vezetett be a Common Data Service megoldásban, amelynek neve cdm\_Company. Ez az entitás egyenértékű a Vállalat entitással az alkalmazásban. Annak garantálására, hogy a rekordok láthatósága alapértelmezetten megegyezzen az alkalmazás és a Common Data Service között, a következő beállításokat javasoljuk a Common Data Service adatai számára:

+ Minden egyes kettős írási lehetőséget engedélyező Finance and Operations Vállalati rekordhoz legyen létrehozva egy társított cdm\_Company rekord.
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

> [!div class="mx-imgBorder"]
![Alapértelmezett tulajdonosi csoport mező](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Cég adatcsíkozása és rendszerindítás

A Common Data Service-integráció vállalati azonosító segítségével létre a vállalatok paritását az adatcsíkozáshoz. Amint az alábbi ábrán látható, minden vállalatspecifikus entitás ki lesz bővítve úgy, hogy egy több-az-egyhez (N:1) kapcsolata lesz a CDM\_Companí entitással.

> [!div class="mx-imgBorder"]
![N:1 kapcsolat a vállalatspecifikus entitás és a cdm_Company entitás között](media/dual-write-bootstrapping.png)

+ A rekordok esetében a vállalat hozzáadása és mentése után az érték írásvédett lesz. Ezért a felhasználóknak meg kell győződniük arról, hogy a megfelelő vállalatot választják ki.
+ Csak a vállalati adatokat tartalmazó rekordok alkalmasak az alkalmazás és a Common Data Service közötti kettős írásra.
+ Meglévő Common Data Service adatokhoz egy adminisztrátor által kezelt bootstrapping-élmény is hamarosan elérhető lesz.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Vállalat nevének automatikusan történő kitöltése az ügyfélkapcsolati alkalmazásokban

Számos módja van annak, hogy a vállalat nevét az ügyfélkapcsolati alkalmazásokban automatikusan kitöltsék.

+ Ha Ön rendszergazda, akkor az alapértelmezett vállalat beállítható úgy, hogy megnyitja a **Speciális beállítások > Rendszer > Biztonság > Felhasználók** menüpontot. Nyissa meg a **Felhasználó** űrlapot, és a **Szervezet adatai** szakaszban adja állíts be az **Alapértelmezett vállalat használata az űrlapokon** értékét.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Alapértelmezett vállalat beállítása a szervezet adatai szakaszhoz.":::

+ Ha **Írás** jogosultsággal rendelkezik a **SystemUser** entitáshoz az **Üzleti egység** szintjén, akkor bármilyen űrlapon módosíthatja az alapértelmezett vállalatot, ha a **Vállalat** legördülő menüből kiválasztja a vállalatot.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="A vállalat nevének módosítása egy új partneren.":::

+ Ha egynél több vállalat adataihoz rendelkezik **Írás** hozzáféréssel, akkor egy másik vállalathoz tartozó rekord kiválasztásával is módosíthatja az alapértelmezett vállalatot.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="A rekord kiválasztása megváltoztatja az alapértelmezett vállalatot.":::

+ Ha Ön rendszerkonfiguráló vagy egy rendszergazda, és a vállalat adatait egy egyéni űrlapon szeretné automatikusan kitölteni, akkor használhatja az [űrlapesemények](https://docs.microsoft.com/powerapps/developer/model-driven-apps/clientapi/events-forms-grids) lehetőséget. Adjon hozzá JavaScript-hivatkozást az **msdyn_/DefaultCompany.js** elemhez, és használja a következő eseményeket. Használhatja az összes beépített űrlapot is, például a **Partner** űrlapot.

    + **OnLoad** esemény az űrlaphoz: Állítsa be a **defaultCompany** mezőt.
    + **OnChange** esemény a **Vállalat** mezőhöz: Állítsa be az **updateDefaultCompany** mezőt.

## <a name="apply-filtering-based-on-the-company-context"></a>Szűrés alkalmazása a vállalat kontextusa alapján

Ha azt szeretné, hogy az egyéni űrlapokon vagy egyéni keresési mezőkben megadott vállalati környezet alapján történjen a szűrés, nyissa meg az űrlapot, és használja a **Kapcsolódó rekordok szűrése** szakaszt a vállalati szűrő alkalmazásához. Ezt minden olyan keresési mező esetében be kell állítania, amelyhez szűrés szükséges a mögöttes vállalat alapján egy adott rekodnál. A beállítás a következő ábrán látható a **Partnerhez** jelenik meg.

:::image type="content" source="media/apply-company-context.png" alt-text="Vállalati környezet alkalmazása":::

