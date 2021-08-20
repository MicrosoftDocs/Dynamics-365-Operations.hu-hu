---
title: Vállalat fogalma a Dataverse szolgáltatásban
description: Ez a témakör a vállalati adatok integrációját ismerteti a Finance and Operations és a Dataverse között.
author: RamaKrishnamoorthy
ms.date: 08/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 46e5edb61da7539b51c2678c69238c9df9c85043dfc71903e1633843a3071d4d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748376"
---
# <a name="company-concept-in-dataverse"></a>Vállalat fogalma a Dataverse szolgáltatásban

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


A Finance and Operations alkalmazásban a *vállalat* koncepciója egyszerre jogi fogalom és üzleti fogalom. Mindemellett adatok biztonsági és láthatósági határa is. A felhasználók mindig egyetlen vállalat kontextusában dolgoznak, és az adatok nagy részét vállalat szerint van kezelve.

A Dataverse nem rendelkezik ezzel egyenértékű koncepcióval. A legközelebbi koncepció a *részleg*, amely elsősorban biztonsági és láthatósági határ a felhasználói adatok számára. Ez a fogalom nem rendelkezik ugyanazokkal a jogi vagy üzleti vonatkozásokkal, mint a vállalat koncepciója.

Mivel a részleg és a vállalat nem egyenértékű fogalmak, nem lehetséges egy-az-egyhez (1:1) leképzés kényszerítése hozzájuk a Dataverse integráció céljából. Mivel azonban a felhasználóknak alapértelmezés szerint meg kell tudniuk tekinteni ugyanazokat a sorokat az alkamazásban és a Dataverse megoldásokban, a Microsoft egy új táblát vezetett be a Dataverse megoldásban, amelynek neve cdm\_Company. Ez a tábla egyenértékű a Vállalat táblával az alkalmazásban. Annak garantálására, hogy a sorok láthatósága alapértelmezetten megegyezzen az alkalmazás és a Dataverse között, a következő beállításokat javasoljuk a Dataverse adatai számára:

+ Minden egyes kettős írási lehetőséget engedélyező Finance and Operations Vállalati sorhoz legyen létrehozva egy társított cdm\_Company sor.
+ Egy cdm\_Company sor létrehozásakor és a kettős írás engedélyezésekor egy alapértelmezett részleg jön létre ugyanazzal a névvel. Bár a részleghez automatikusan létrejön egy alapértelmezett csoport, a részleg nincs használatban.
+ Olyan különálló tulajdonoscsapat jön létre, amelynek neve azonos. Ez is hozzá van rendelve a részleghez.
+ Alapértelmezés szerint az alkalmazásban létrehozott, és a Dataverse szolgáltatásban duplán írt sorok tulajdonosa a hozzárendelt részleghez kapcsolódó „DW Owner” csoport.

A következő ábrán egy példa látható az ilyen típusú adatbeállításra a Dataverse megoldásban.

![Adatok beállítása a Dataverse megoldásban.](media/dual-write-company-1.png)

Ezen konfigurációnak az következtében az USMF vállalathoz kapcsolódó minden sor egy olyan csapat tulajdonában lesz, amely a be Dataverse USMF részlegéhez van csatolva. Emiatt azok a felhasználók, akik a részleghez egy részlegszintű láthatóságra beállított biztonsági szerepkörön keresztül férnek hozzá, most már láthatják ezeket a sorokat. A következő példa bemutatja, hogyan használhatók a csapatok ezen sorok helyes elérésére.

+ Az „Értékesítési menedzser” szerepkört a "„USMF Sales” csoport tagjaihoz rendelték.
+ Azok a felhasználók, akik rendelkeznek az „Értékesítési menedzser” szerepkörrel, hozzáférhetnek minden olyan partnersorhoz, amelyek ugyanannak a részlegnek a tagjai, amelynek ők is.
+ Az „USMF Sales” csapat s kapcsolva van az USMF üzleti egységhez, amely korábban említettünk.
+ Ezért az „USMF Sales” csapat tagjai láthatnak a „USMF DW” felhasználói által birtokolt bármely olyan fiókot, amely a Finance and Operations USMF vállalati táblából származik.

![Hogyan használhatók a csapatok.](media/dual-write-company-2.png)

Ahogy az előző ábrán is látható, ez a 1:1 leképezés az üzleti egység, a vállalat és a csapat között csak egy kiindulási pont. Ebben a példában egy új „Európa” nevű részleg manuálisan lett létrehozva a Dataverse szolgáltatásban mint DEMF és ESMF szülője. Ez az új gyökérszintű részleg nem kapcsolódik kettős íráshoz. Ugyanakkor használható arra, hogy az „EUR Sales” csapat hozzáférhessen a partneradatokhoz a DEMF és az ESMF rekordokban is, azáltal, hogy az adatok láthatóságát **Szülő/gyermek részleg** értékre állítják a társított biztosági szerepkörben.

Egy utolsó témában ismertetjük, hogyan határozza meg a lettős írás, hogy melyik tulajdonoshoz rendelje hozzá a sorokat. Ezt a viselkedés az **Alapértelmezett tulajdonoscsoport** oszlop szabályozza a cdm\_Vállalat sorban. Ha egy cdm\_Vállalat sorhoz a kettős írás engedélyezve van, egy beépülő modul automatikusan létrehozza a hozzárendelt üzleti egységet és a tulajdonos csoportot (ha még nem létezik), és beállítja az **Alapértelmezett tulajdonosi csapat** oszlopot. Az adminisztrátor megváltoztathatja ezt az oszlopot egy másik értékre. Azonban az adminisztrátor nem törölheti ezt az oszlopot, amíg a tábla engedélyezve van kettős íráshoz.

> [!div class="mx-imgBorder"]
![Alapértelmezett tulajdonosi csoport oszlop.](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Cég adatcsíkozása és rendszerindítás

A Dataverse-integráció vállalati azonosító segítségével létre a vállalatok paritását az adatcsíkozáshoz. Amint az alábbi ábrán látható, minden vállalatspecifikus tábla ki lesz bővítve úgy, hogy egy több-az-egyhez (N:1) kapcsolata lesz a CDM\_Company táblával.

> [!div class="mx-imgBorder"]
![N:1 kapcsolat a vállalatspecifikus tábla és a cdm_Company tábla között.](media/dual-write-bootstrapping.png)

+ A sorok esetében a vállalat hozzáadása és mentése után az érték írásvédett lesz. Ezért a felhasználóknak meg kell győződniük arról, hogy a megfelelő vállalatot választják ki.
+ Csak a vállalati adatokat tartalmazó sorok alkalmasak az alkalmazás és a Dataverse közötti kettős írásra.
+ Meglévő Dataverse adatokhoz egy adminisztrátor által kezelt bootstrapping-élmény is hamarosan elérhető lesz.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Vállalat nevének automatikusan történő kitöltése az ügyfélkapcsolati alkalmazásokban

Számos módja van annak, hogy a vállalat nevét az ügyfélkapcsolati alkalmazásokban automatikusan kitöltsék.

+ Ha Ön rendszergazda, akkor az alapértelmezett vállalat beállítható úgy, hogy megnyitja a **Speciális beállítások > Rendszer > Biztonság > Felhasználók** menüpontot. Nyissa meg a **Felhasználó** űrlapot, és a **Szervezet adatai** szakaszban adja állíts be az **Alapértelmezett vállalat használata az űrlapokon** értékét.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Alapértelmezett vállalat beállítása a szervezet adatai szakaszhoz.":::

+ Ha **Írás** jogosultsággal rendelkezik a **SystemUser** táblához az **Üzleti egység** szintjén, akkor bármilyen űrlapon módosíthatja az alapértelmezett vállalatot, ha a **Vállalat** legördülő menüből kiválasztja a vállalatot.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="A vállalat nevének módosítása egy új partneren.":::

+ Ha egynél több vállalat adataihoz rendelkezik **Írás** hozzáféréssel, akkor egy másik vállalathoz tartozó sor kiválasztásával is módosíthatja az alapértelmezett vállalatot.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="A sor kiválasztása megváltoztatja az alapértelmezett vállalatot.":::

+ Ha Ön rendszerkonfiguráló vagy egy rendszergazda, és a vállalat adatait egy egyéni űrlapon szeretné automatikusan kitölteni, akkor használhatja az [űrlapesemények](/powerapps/developer/model-driven-apps/clientapi/events-forms-grids) lehetőséget. Adjon hozzá JavaScript-hivatkozást az **msdyn_/DefaultCompany.js** elemhez, és használja a következő eseményeket. Használhatja az összes beépített űrlapot is, például a **Partner** űrlapot.

    + **OnLoad** esemény az űrlaphoz: Állítsa be a **defaultCompany** oszlopot.
    + **OnChange** esemény a **Vállalat** oszlophoz: Állítsa be az **updateDefaultCompany** oszlopot.

## <a name="apply-filtering-based-on-the-company-context"></a>Szűrés alkalmazása a vállalat kontextusa alapján

Ha azt szeretné, hogy az egyéni űrlapokon vagy egyéni keresési oszlopokban megadott vállalati környezet alapján történjen a szűrés, nyissa meg az űrlapot, és használja a **Kapcsolódó rekordok szűrése** szakaszt a vállalati szűrő alkalmazásához. Ezt minden olyan keresési oszlop esetében be kell állítania, amelyhez szűrés szükséges a mögöttes vállalat alapján egy adott sornál. A beállítás a következő ábrán látható a **Partnerhez** jelenik meg.

:::image type="content" source="media/apply-company-context.png" alt-text="Vállalati környezet alkalmazása.":::



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]