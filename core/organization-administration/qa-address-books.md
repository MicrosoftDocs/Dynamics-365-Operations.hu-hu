---
title: "Címjegyzékek"
description: 
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartyCheckDuplicate, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23601
ms.assetid: b177fa0f-ac9a-415e-9498-15438e132f60
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 7b3bed2bec4b109c6e3b557b8c3651f15f25169c
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017


---

# <a name="address-books"></a>Címjegyzékek

[!include[banner](../includes/banner.md)]




<a name="how-do-i-check-for-duplicate-records"></a>Hogyan tudom ellenőrizni, hogy vannak-e ismétlődő rekordok?
-------------------------------------

Az ismétlődő rekordok közvetlenül a **Globális címjegyzék** listaoldalon ellenőrizhetők. A Műveleti Ablaktábla **Fél** lapján található **Karbantartás** csoportban kattintson az **Ismétlődések ellenőrzése** lehetőségre. Ezután válassza ki az ismétlődések ellenőrzése kapcsán használni kívánt értékeket.

## <a name="can-i-bulk-add-or-delete-party-records-from-an-address-book"></a>A rendszer engedélyezi-e a partnerrekordok tömeges hozzáadását, illetve eltávolítását egy címjegyzékből?
Igen, lehetőségében áll több partnerrekordot adni hozzá, vagy távolítani el egy címjegyzékből.

-   Több partnerrekordok egy adott címjegyzékhez történő hozzáadásához, válassza ki a listából a kívánt partnereket a **Globális címjegyzék** listaoldalán. Ezután a Műveleti Ablaktábla **Fél** lapján található **Karbantartás** csoportban kattintson a **Felek hozzárendelése** lehetőségre. Jelölje ki azokat a címjegyzékeket, melyekbe a kiválasztott partnerrekordok kerülnek, majd kattintson az **OK** gombra. Az összes kiválasztott partnerrekord bekerül a kiválasztott címjegyzékbe.
-   Több partnerrekord egy adott címjegyzékből történő eltávolításához, válassza ki a listából a kívánt partnereket a **Globális címjegyzék** listaoldalán. Ezután a Műveleti Ablaktábla **Fél** lapján található **Karbantartás** csoportban kattintson a **Felek eltávolítása** lehetőségre. Jelölje ki azokat a címjegyzékeket, melyekből el kívánja távolítani a kiválasztott partnerrekordokat, majd kattintson az **OK** gombra. Az összes kiválasztott partnerrekord eltávolításra kerül a kiválasztott címjegyzékből.

## <a name="can-i-change-the-party-type-of-a-record-or-do-i-have-to-delete-the-old-record-and-create-a-new-one"></a>Módosítható-e a partnerrekord típusa, vagy törölnöm kell a régi rekordot, és újat hoznom létre?
Előfordulhat, hogy módosítania kell egy adott rekord típusát magánszemélyről szervezetre, vagy szervezetről magánszemélyre. Noémi például a Faktúra Kft. értékesítési csapatának tagja. Egy pécsi kereskedelmi bemutatón hat új potenciális vevővel találkozik. Noémi potenciálisvevő-rekordot hoz létre mindegyik potenciális vevőhöz. Amikor elmenti a rekordokat, akkor azokat a rendszer létrehozza a Globális címjegyzékben is. A Faktúra Kft-nél a szervezet az alapértelmezett féltípus beállítás, két potenciális vevő kapcsán azonban magánszemély típusú rekordra van szükség. Ezért Noéminek módosítania kell két potenciálisvevő-rekord féltípusát, amikor visszatér a kereskedelmi kiállításról. Egy féltípus egyik alternatíváról a másikra történő átállításához elsőként a globális címjegyzékben létre kell hoznia egy új, megfelelő típusú rekordot. Ezután társítania kell a régi partnerrekordot az újjal. Az új fél társítását követően törölje a rossz féltípusú partnerrekordot.

## <a name="how-do-i-change-the-name-or-address-of-a-party-record"></a>Hogyan tudom módosítani egy partnerrekord nevét vagy címét?
Bármikor tudja frissíteni a partnerrekordok nevét, illetve az azzal társított címeket.

-   A partnerrekord nevének frissítéséhez nyissa meg az adott partnerrekordot, majd a Műveleti Ablaktáblában kattintson a **Szerkesztés** lehetőségre. Adja meg az adott fél új nevét az **Általános** Gyorslapon, majd mentse el a rekordot.
-   A partnerrekord egy címének frissítéséhez nyissa meg az adott partnerrekordot, majd válassza ki a frissítendő címet a **Címek** Gyorslapon. Kattintson a **Szerkesztés** lehetőségre, majd végezze el a cím vagy címparaméterek szükséges módosításait a **Cím szerkesztése** oldalon.

## <a name="can-i-merge-two-or-more-party-records-into-one-record"></a>Tudok-e két vagy több partnerrekordot egy rekordban egyesíteni?
Bizonyos esetekben szükség lehet két vagy több partnerrekord egyetlen rekordban történő egyesítésére. Ez akkor fordulhat elő, ha szándékosan vagy véletlenül egy vagy több ismétlődő rekordot hoz létre. Partnerrekordok egyesítése esetén ki kell választania, hogy melyik rekordot szeretné megtartani. A további rekordokból származó információkat a rendszer ezzel a rekorddal egyesíti. Tegyük fel, például, hogy azt veszi észre, hogy a Faktúra Kft. adatait három partnerrekord tartalmazza: az A, B és C jelű. Úgy határoz, hogy az A jelűt fogja megtartani. Így a B és C jelű partnerrekordokban tárolt adatok az A jelűben kerülnek egyesítésre. Bizonyos esetekben nincs lehetőség a partnerrekordok egyesítésére:

-   Nem lehet egyesíteni az azonos félszerepkörhöz, például egyazon jogi személyhez tartozó vevőhöz vagy szállítóhoz társított partnerrekordokat. Vegyük például azt az esetet, hogy az A jelű fél társítva van egy, az 123 jogi személyhez tartozó vevőhöz, a B jelű fél pedig társítva van egy, az 123 jogi személyhez tartozó másik vevőhöz. Ezek a partnerrekordok nem egyesíthetők, mivel az egyesített partnerrekord több, egyazon jogi személyhez tartozó vevőhöz lenne társítva, ami nem engedélyezett. A rekordokat azonban egyesíthetők, ha a B jelű fél egy, az 123 jogi személyhez tartozó szállítóhoz, vagy egy másik jogi személyhez tartozó vevőhöz van társítva.
-   Nem egyesíthetők az egyazon jogi személyhez vagy üzemi egységhez tartozó belsőfél-szervezetrekordok.

## <a name="should-i-create-a-party-record-in-the-global-address-book-or-in-another-place-such-as-the-customer-or-vendor-page"></a>A globális címjegyzékben, vagy egy másik helyen, például a vevő vagy szállító lapon érdemes létrehoznom a címjegyzék-bejegyzést?
A felek rekordjait a globális címjegyzékben vagy a megfelelő entitáslapon adhatja meg. Amikor egy rekordot az egyik helyen hozzáad, az minden esetben hozzáadásra kerül a másik helyen is. Ha például partnerrekordot ad hozzá egy vevőhöz a globális címjegyzékben, úgy az a rekord a **Vevő** oldalon is hozzáadásra kerül . Hasonlóképpen, ha a **Vevő** oldalon ad hozzá partnerrekordot, úgy az a globális címjegyzékben is hozzáadásra kerül. Az irányelvek segítségével tudja eldönteni, hogy hol hozza létre az új partnerrekordokat:

-   **Új partnerrekord létrehozása, amikor nem ismeri az entitástípust** – Ha partnerrekordot kell létrehoznia, de nem ismeri a az entitástípust (például nem tudja, hogy az entitás vevő-e vagy lehetőség), akkor a rekordot célszerű a globális címjegyzékben hozni létre. Az entitástípust később is ki tudja választani.
-   **Új partnerrekord létrehozása, amikor ismeri az entitástípust** – Ha ismeri a fél entitástípusát, akkor a rekordot célszerű az adott típusra vonatkozó oldalon hozni létre. Vevőre vonatkozó rekordot például a **Vevő** oldalon. Ha a megfelelő entitástípus segítségével hoz létre és ment rekordot, úgy a rekord automatikusan létrehozásra kerül a globális címjegyzékben is.

## <a name="can-i-translate-address-information-for-party-records"></a>Le lehet fordítani a partnerrekordok címadatait?
A címadatok fordítását be tudja úgy állítani, hogy az adatok az Ön felhasználói nyelvén (a rendszernyelven) jelenjenek meg a Microsoft Dynamics 365 for Finance and Operations rendszerben, de más nyelven az olyan dokumentumokban, mint például egy értékesítési rendelés. Az országok és régiók nevei, illetve címzési célok és névsorozatok kapcsán tud megadni fordításokat. Ha például az Ön rendszernyelve a dán, tud értékesítési rendelést hozni létre egy franciaországi vevő részére. Ebben az esetben a programban tudja dán nyelven megjeleníteni a vevőrekordot, a nyomtatott értékesítési rendelésen azonban franciául tüntetni fel a címadatokat. A fordítások beállításakor a listában szereplő minden cikkhez kell megadnia fordítást. Azok a cikkek, melyekhez nem ad meg fordítás, a rendszernyelven jelennek meg. Ha például az Ön rendszernyelve a dán, tud dokumentumot küldeni egy spanyolországi vevő részére. Ha nem adott meg spanyol (ESP) fordításokat a címadatok kapcsán, úgy ezek az adatok dán nyelven jelennek meg, mind a programban, mind a bizonylaton.




