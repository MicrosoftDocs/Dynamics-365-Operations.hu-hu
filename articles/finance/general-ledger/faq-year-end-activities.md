---
title: Év végi tevékenységek – GYIK
description: Ez a témakör az év végi zárással kapcsolatos tevékenységek terén nyújt segítséget.
author: kweekley
ms.date: 01/25/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1b7606314b9cf7050a565822b5b9e23beb0cb4978b20e88596c5002d918cfcd9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725074"
---
# <a name="year-end-activities-faq"></a>Év végi tevékenységek – GYIK 

[!include [banner](../includes/banner.md)]

Ez a témakör az év végi zárással kapcsolatos tevékenységek terén nyújt segítséget. Ez a témakör elsősorban a főkönyvhöz és a kötelezettségekhez kapcsolódó év végi zárási feladatokkal foglalkozik.

## <a name="general-ledger-how-do-i-know-that-were-running-year-end-close-and-not-undoing-year-end-close"></a>Főkönyv: Hogyan tudok megbizonyosodni róla, hogy elvégezzük, és nem visszavonjuk az év végi zárást?
Több szervezetet is láttunk már, amely az év végi zárás lefuttatása helyett véletlenül visszavonta a zárást. Ha az év végi zárás művelete rendkívül gyorsan lefut, vagy az év végi zárás nem hoz létre nyitó egyenlegeket, ellenőrizze az **Előző zárás visszavonása** beállítást az **Év végi zárás** menüben (**Főkönyv > Időszak lezárása > Év végi zárás > Pénzügyi zárás futtatása**). 

[![Az év végi zárás futtatása és az év végi zárás visszavonása.](./media/faq-2020-yr-end-01.png)](./media/faq-2020-yr-end-01.png)

Ha az **Előző zárás visszavonása** beállításnál az **Igen** érték szerepel, a rendszer vissza fogja vonni az előző év végi zárást. A visszavonás futtatásakor a program a záró és nyitó egyenlegekhez kapcsolódó összes bejegyzést törli, mintha az év végi zárást még nem futtatták volna le. A program a bizonylatokat is törli. A program nem indítja el automatikusan újra az év végi zárást. A folyamatot Önnek kell újraindítania. Ügyeljen rá, hogy az **Előző zárás visszavonása** lehetőségnél a **Nem** érték legyen beállítva. 

> [!NOTE]
> A lezárás alatt álló évnél opcionálisan létrejön a záró egyenleg bejegyzése. Ez csak akkor történik meg, ha a **Záró tranzakciók létrehozása átvezetés közben** főkönyvi paraméter az **Igen** értékre van állítva. A nyitó egyenleg bejegyzését a program mindig létrehozza, mert ez a következő év nyitó egyenlege.  
 
## <a name="general-ledger-what-is-the-difference-between-undo-and-delete-gl-parameter-for-year-end-close"></a>Főkönyv: Az év végi zárást tekintve mi a különbség a Visszavonás és a Törlés főkönyvi paraméterek között?
Talán nem minden felhasználó számára egyértelmű, hogy mi a különbség az **Előző zárás visszavonása** paraméter (amely az **Év végi zárás** párbeszédpanelen található) és az **Évzáró tranzakciók törlése átvezetés közben** főkönyvi paraméter között (**Főkönyv > Időszak zárása > Év végi zárás > Pénzügyi zárás futtatása**).  

[![A Visszavonás és a Törlés főkönyvi paraméterek közötti különbség az év végi zárásnál.](./media/faq-2020-yr-end-02.png)](./media/faq-2020-yr-end-02.png)

Ha az év végi zárási folyamat futtatása közben szeretné törölni az összes záró és nyitó egyenleggel kapcsolatos bejegyzést, a párbeszédpanel legördülő menüjéből válassza az **Előző zárás visszavonása** lehetőséget. Így olyan lesz, mintha az év végi zárást még nem futtatták volna le. A program a bizonylatokat is törli. A program nem indítja el automatikusan újra az év végi zárást. Az év végi zárás futtatásához a felhasználók ismét el kell indítania a folyamatot. Ebben az esetben módosítsa az **Előző zárás visszavonása** beállítást a **Nem** értékre (**Főkönyv > Főkönyv beállítása > Főkönyvi paraméterek**). 

[![Főkönyvi paraméterek beállítása.](./media/faq-2020-yr-end-03.png)](./media/faq-2020-yr-end-03.png)

A főkönyv **Évzáró tranzakciók törlése átvezetés közben** paramétere csak az év végi zárás futtatása során használatos (amikor az **Előző zárás visszavonása** lehetőség a **Nem** értékre van állítva), tehát a zárás visszavonásakor nem. Ha a paraméter az **Igen** értékre van állítva, a rendszer törli a záró egyenleghez és a nyitó egyenleghez kapcsolódó bejegyzéseket, és újra lefuttatja az év végi zárást. Ezt a folyamatot akkor használják, ha a szervezet egyetlen, a záró és a nyitó egyenleg bejegyzéseihez kapcsolódó könyvelési bejegyzésben szeretné feladni az összes tranzakciót, ideértve az előző év zárása óta végzett korrekciókat. 

Ha a paraméter beállítása **Nem**, a záró és a nyitó egyenleghez kapcsolódó összes bejegyzés megmarad. A program nem törli őket. Ehelyett létrejön egy új bejegyzés a nyitó és a záró egyenleghez, amely csak a változásokat, azaz az adott pénzügyi év előző év végi zárása óta feladott új tranzakciókat tartalmazza.  

> [!NOTE]
> A záró egyenleghez kapcsolódó bejegyzést a rendszer a zárás alatt álló évben hozza létre. Ez csak akkor történik meg, ha a főkönyv **Záró tranzakciók létrehozása átvezetés közben** paramétere az **Igen** értékre van állítva. A nyitó egyenleg bejegyzését a program mindig létrehozza, mert ez a következő év nyitó egyenlege. 

## <a name="general-ledger-what-can-be-changed-to-enhance-performance-of-year-end-processing"></a>Főkönyv: Milyen módosításokkal lehet javítani az év végi zárás feldolgozásának teljesítményét? 
Számos módosítás segíthet az év végi zárás teljesítményének javításában. Javasoljuk, hogy értékelje ki az itt ajánlott módosításokat, és fontolja meg, hogy megfelelőek-e az Ön szervezete számára.  

### <a name="dimension-sets"></a>Dimenziókészletek
Az év végi zárás futtatásakor a rendszernek minden dimenziókészlet egyenlegét újra kell építenie, ami közvetlenül befolyásolja a teljesítményt. Egyes szervezetek felesleges, a korábbiakban valaha használt vagy a jövőben használni tervezett dimenziókészleteket hoznak létre.  A program ezeket a szükségtelen dimenziókészleteket is újraépíti az év végi zárás során, ami meghosszabbítja a folyamatot. Alaposan értékelje ki a dimenziókészleteket, és törölje a szükségtelen elemeket.

A szükségtelen dimenziókészletek a **BudgetDimensionFocusInitializeBalance** kötegelt feladatot is befolyásolják (**Főkönyv > Számlatükör > Dimenziók > Pénzügyi dimenziókészletek**).

[![Pénzügyi dimenziókészletek.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Év végi zárásra vonatkozó sablon konfigurálása
Az év végi zárásra vonatkozó sablon segítségével a szervezetek kiválaszthatják a pénzügyidimenzió-szintet, amelyet az eredményegyenlegek mérleg szerinti egyenlegbe való átviteléhez szeretnének használni. A beállítások segítségével a szervezetek kezelhetik a részletes pénzügyi dimenziókat (**Az összes lezárása**), amikor az egyenlegeket átviszik a mérleg szerinti eredménybe, vagy ha úgy döntenek, hogy az összegeket egyetlen dimenzióértékben szeretnék összegezni (**Egyetlen lezárása**). Ezt minden pénzügyi dimenziónál meg lehet határozni. A beállításokkal kapcsolatos további információkért lásd az [Év végi zárás](year-end-close.md) című témakört.

A teljesítmény javítása érdekében javasoljuk, hogy értékelje ki a szervezet igényeit, és ha lehetséges, zárjon le a lehető legtöbb dimenziót az **Egyetlen lezárása** év végi lehetőséggel. Ha egyetlen dimenzióértékre (amely üres érték is lehet) végez lezárást, a rendszer kevésbé részletes számításokat végez az eredmény-zárószámla bejegyzései egyenlegének meghatározásakor.

### <a name="10013-update-or-later"></a>10.0.13-as és újabb verziók
Ha a szervezet legutóbbi év végi zárása óta a 10.0.13-as vagy újabb verzióra frissített, a [kivonat második verziójának implementálása](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/verify-hash-function-changes-after-update-to-dynamics-365-finance-2020-release-wave-2) miatt az év végi zárási folyamat több időt vehet igénybe. (A *kivonat* olyan mezőket jelent, amelyeket a program más sztringmezőkből számított ki. A kivonat GUID-értékét kiszámító API-t a biztonság fokozása érdekében frissítettük.) Az év végi zárási folyamat felgyorsítása érdekében javasoljuk, hogy az év végi zárás futtatása előtt építse újra a dimenziókészletek egyenlegét. Ha a 10.0.13-as frissítés után már újraépítette a dimenziókészletek egyenlegét, nem szükséges újra elvégeznie az újraépítési folyamatot.
 
## <a name="general-ledger--what-does-the-period-close--year-end-close-do"></a>Főkönyv – Mi történik az Időszak lezárása – Év végi zárás lehetőség használatakor?
 
[![Időszaki lezárása, év végi zárás.](./media/faq-2020-yr-end-05.png)](./media/faq-2020-yr-end-05.png)

### <a name="performance-improvements-for-rebuilding-financial-dimension-sets-new-feature"></a>Teljesítménnyel kapcsolatos fejlesztések a pénzügyi dimenziókészletek újraépítéséhez (új funkció)
A 10.0.16-os verzióban bevezetett új funkció javítja az év végi zárási és konszolidálási folyamatok teljesítményét. A funkció neve: Teljesítménnyel kapcsolatos fejlesztések a pénzügyi dimenziókészletek újraépítéséhez. Ez a funkció módosítja a dimenziókészletek újraépítésének módját, amelyeket így csak egy adott időkeretben lehet újraépíteni. A korábbi verziókban a program az összes dátumhoz újraépítette a dimenziókészleteket. Ha például a 2020-as évet zárja, a rendszer csak a 2020-as pénzügyi évhez tartozó tranzakciók egyenlegeit építi újra. Ha például a 2020. november 1. és 2020. november 30. közötti dátumtartományban futtat konszolidációt, a rendszer csak az erre a dátumtartományra vonatkozó egyenlegeket építi újra.

Mivel ez a funkció kompatibilitástörő változásnak számít, a **Funkciókezelés** munkaterület segítségével kell engedélyeznie.
 
[![Év végi zárás.](./media/faq-2020-yr-end-06.png)](./media/faq-2020-yr-end-06.png)

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2020"></a>Kötelezettségek: Milyen módosításokat vezettek be 2020-ban az 1099-es év végi jelentés támogatásához?

2020-ban két új szabályozási funkciót adtunk hozzá az 1099-es űrlaphoz kapcsolódó év végi módosításokhoz. Az elsőt év közben adtuk ki kötelező funkcióként: **A 2020-as 1099-NEC és az 1099-MISC űrlapok módosítása**. Célja, hogy a 2020-as évre vonatkozó 1099-es tranzakciós adatok nyomon követhetők legyenek az új 1099-NEC űrlapon. Ez a funkció hozzáadta a programhoz az új 1099-NEC támogatásához szükséges 1099-es mezőket, és frissítette az 1099-MISC mezőket. Ez az 1099-es mező adataihoz tartozó szállítóirekord-adatokat is frissítette. 

A második szabályozói funkció, **A 2020-as adótörvényhez módosított 1099-es nyilatkozat** a következő módosításokat tartalmazza.

- 1099-OID – Az adóhatóság folyamatosan használhatóvá alakította az űrlapot.
   - Nyomtatáskor a jelentési év 3. és 4. számjegyét ki kell tölteni. Használja a **Jelentési év** mező 3. és 4. számjegyét az **1099-es adó nyomtatási beállításai** alapján. 

- 1099-NEC – Új űrlap a 2020-as évre. Ez az űrlap rögzíti a nem alkalmazotti kompenzációt. 

-   1099-MISC – Az 1099-NEC űrlap bevezetése miatt az adóhatóság módosította az 1099-MISC űrlapot, és átalakította a bizonyos bevételek jelentésére szolgáló a mezők számozását.
Az alábbiakban láthatja a jövedelemjelentésekkel és az űrlap mezőinek számozásával kapcsolatos módosításokat.
   - A fizető a 7. mezőben 5 000 $ vagy nagyobb értékben (jelölőnégyzet) végzett közvetlen értékesítést adott meg.
   - A terménybiztosítási bevételeket a 9. mezőben lehet rögzíteni.
   - A bruttó ügyvédi bevételek a 10. mezőbe kerültek.
   - A 409A szakasznak megfelelő halasztásokat a 12. mező rögzíti.
   - A nem minősített halasztott kompenzációs bevételeket a 14. mező rögzíti.
   - A 15., 16. és 17. mező rögzíti az államadó-előleget, az államazonosító-számot és az államban megszerzett jövedelem összegét.

- 2020-ban az 1099-DIV és az 1099-INT nem módosult.

- Elektronikus benyújtás – A formátum módosult, hogy igazodjon az új NEC űrlaphoz, valamint a fent ismertetett MISC mező módosításaihoz. Az elektronikus benyújtáshoz kapcsolódó specifikus információkat az [adóhatóság 1220-as kiadványában](https://www.irs.gov/pub/irs-pdf/p1220.pdf) találja meg.

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Kötelezettségek: 1099 – Hogyan módosítom az 1099-es űrlap mezőértékeit, valamint az olyan szállítók értékeit, amely az év során nem követte az 1099-es adatokat?
Az „1099 frissítése” funkció (**Kötelezettségek > Szállítók > Minden szállító > Szállító kiválasztása > Szállító fül a menüszalagon > 1099 frissítése**) segítségével áttekintheti a korábban kifizetett számlatranzakciókat, hogy megfelelően újból hozzárendelhesse az 1099-es adatokat az **Adó – 1099** fülön megadott beállítások alapján (lásd a **Szállító** oldalon).

## <a name="can-i-run-the-update-1099-for-all-my-vendors-at-once"></a>Futtathatom az „1099 frissítése” funkciót az összes szállítónál egyszerre?
Nem. A „1099 frissítése” rutint egyszerre csak egy szállítón lehet lefuttatni. Ha szervezeténél szükség lenne erre a lehetőségre, szavazzon a [Batch Process for Update of Vendor's 1099 Data](https://experience.dynamics.com/ideas/idea/?ideaid=5493d608-350e-eb11-b5d9-0003ff68ded8) (A szállítók 1099-es adatainak kötegelt frissítése) nevű ötletre.

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-vs-update-all-in-the-update-1099-utility"></a>Kötelezettségek: 1099 – „A meglévő 1099-es összegek újraszámítása” és az „Összes frissítése” lehetőség összehasonlítása az „1099 frissítése” segédprogramban.
**A meglévő 1099-es összegek újraszámítása** jelölőnégyzet a teljes kifizetett értékre állítja vissza az 1099-es összeget, amennyiben az **Összes frissítése** jelölőnégyzettel együtt használják. 

[![1099-es adótranzakciók: a frissítési rutin futtatása előtt.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

**A meglévő 1099-es összegek újraszámítása** jelölőnégyzet csak akkor használható, ha a számlán részleges 1099-es értékek szerepelnek, vagy ha az 1099-es adóűrlapon módosították. Ha például a számla értéke 1000,00 $, de a felhasználó manuálisan megadja az űrlapon az 500,00 $ értéket az 1099-es funkciónál.

[![1099-es adótranzakciók: Az Összes frissítése és A meglévő 1099-es összegek újraszámítása lehetőségek megjelölése.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Ha ezt kifizetik, az 500,00 $ lesz a kifizetett 1099-es összeg. Ha lefuttatja az újraszámítási rutint, a rendszer 1000,00 $-re módosítja az 1099-es összeget, amely a teljes kifizetett összeg.

[![1099-es adótranzakciók: Az 1099-es rutin futtatása után.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Kötelezettségek: 1099 – Az 1099-es tranzakciók manuális létrehozása
Előfordulhat, hogy egy szervezetnek manuálisan kell létrehoznia azokat az 1099-es tranzakciókat, amelyek nincsenek számlához társítva. Manuálisan is hozzáadhat 1099-es tranzakciókat, amelyhez a **Kötelezettségek > Időszakos feladatok > Adó - 1099 > Szállítói kiegyenlítések az 1099-es jelentéshez** menüpontot használhatja. Válassza a **Manuális 1099-es tranzakciók** gombot. 

A manuálisan létrehozott 1099-es tranzakciók nem frissülnek az **Összes frissítése** folyamattal, sem **A meglévő 1099-es összegek újraszámítása** folyamattal az **1099-es frissítés** segédprogramban.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Kötelezettségek: 1099 – Támogatja a Dynamics 365 Finance az 1096-os űrlapot? 

A Dynamics 365 Finance nem nyomtatja ki az 1096-os éves összesítés és az egyesült államokbeli információküldés átvitele űrlapot.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Kötelezettségek: 1099 – Vannak olyan új funkciók, amelyek támogatják az állami szektor számára az 1099-es jelentéseket? 
A program az állami szektor számára készült új funkcióval, az **1099-es adatok frissítése fő számla szerint** funkcióval bővült, amelyet a **Funkciókezelés** munkaterületen lehet engedélyezni. Ezzel a funkcióval a fő számla alapján lehet társítani a szállító 1099-es értékeit a könyvelési felosztásban, nem pedig a szállítói rekordon található alapértelmezett számla alapján.

További információkért lásd: [Szállítók beállítása az 1099-es kimutatáshoz](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
