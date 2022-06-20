---
title: Beszerzési rendelés feladása
description: Ez a témakör a Készletfeladási profilok lap Beszerzési rendelés lapját írja le.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 0793c58b07d2c0a133e1a5bc0607483f22206b95
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849931"
---
# <a name="purchase-order-posting"></a>Beszerzési rendelés feladása

A **Készletfeladási** profilok lapon **a** Beszerzési rendelés lap használatával lehet szabályozni, hogyan adja fel a rendszer a beszerzési rendeléseket a főkönyvbe. Két fő tevékenység ad fel a főkönyvbe egy beszerzési rendelés esetén: 

- Termékbevételezés
- Számla

Ahhoz, hogy egy beszerzési rendelésen fizikai tranzakció (termékbevételezés) legyen felve a főkönyvbe, a következő jelölőnégyzeteket kell bejelölve lennie:

- A **Termékbevételezés feladása a főkönyvbe** jelölőnégyzet a Készlet **- és raktárkezelési paraméterek lapon**.
- A **Tényleges készlet és** **a Kötelezettség elhatárolása a termékbevételezéseken** **jelölőnégyzet a Cikkmodellcsoportok** lapon.

A fő számlákat a **Készletfeladási** profil lapon kell megadni a következő feladási típusokhoz:

- Beérkezett beszerzési anyagok költsége
- Beszerzési kiadás, nem számlázás
- Beszerzés, elhatárolás

Ahhoz, hogy egy beszerzési rendelés pénzügyi tranzakciója (számlája) feladható legyen a főkönyvbe, teljesülnie kell a következő feltételeknek:

- A **Pénzügyi készlet feladása jelölőnégyzetet** **be kell lennie jelölve a beszerzési rendelés sorában kiválasztott cikk Cikkmodellcsoportok** lapján.
- A fő számlákat a **Készletfeladási** profil lapon kell megadni a következő feladási típusokhoz:
  - Megvásárolt anyagok számlázott költsége
  - Termékre vonatkozó beszerzési kiadás
  - Beszerzési kiadás a költségekhez
  - Engedmény (nem kötelező)

## <a name="fixed-receipt-price-posting"></a>Rögzített bevételezési ár feladása

A rögzített **bevételezési** **·** **árat** felhasználhatja egy termék elszámolóáraként, ha a cikk cikkmodellcsoport oldalának Készletmodell mezőjében az Elszámolóár beállítást választja. A fő különbség **az**, hogy rögzített bevételezési ár használatakor a cikk aktuális önköltségi árát használja a rendszer a készletbevételezés feladásakor. A rögzített bevételezési **árhoz** nincs költség-átértékelési folyamat; pénzügyi frissítés feladása során a rendszer a feladáskor az aktuális önköltségi árat használja. Ha eltérés van a bevételezéskor és a számlán használt önköltségi ár között, az eltérés a rögzített bevételezési ár eredményszámláira lesz feladhatja.

Ha egy termékre fix bevételezési árat használ, a következőket kell beállítania:

- A Cikkmodellcsoportok **lapon** jelölje be **a Tényleges készlet feladása** és **a Rögzített bevételezési ár jelölőnégyzetet**. 
- A Készlet- **és raktárkezelési paraméterek** lapon jelölje be **a Csomagjegyzék feladása a főkönyvi modulban** jelölőnégyzetet.
- A Készletfeladási **profil** oldalon adja meg a következő feladási típusok fő számláit:
  - Rögzített bevételezési ár nyeresége
  - Rögzített bevételezési ár vesztesége
  - Rögzített bevételezési ár ellentétele

További tájékoztatás: Rögzített bevételezési [ár](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="purchase-charges-and-stock-variation-posting"></a>Beszerzési költségek és készlet variációs feladása

Ha a beszerzési költségeket és a készlet variációit is figyelembe veszi, tegye a következőket:

- A Számla **lap Kötelezettségek paraméterei** **·** **lapján jelölje be a Feladás költségként főkönyvi jelölőnégyzetet.**
- A beszerzésirendelés-sorban kiválasztott cikk cikkmodellcsoport-lapján jelölje be a Tényleges készlet könyvelése, a **Pénzügyi** **készlet** könyvelése és a Kötelezettség elhatárolása a termékbevételezéseken jelölőnégyzetet.**·** **·**
- A Beszerzés és **forrás paraméterei** oldalon jelölje **be a Költségek létrehozása a termékbevételezéseken** jelölőnégyzetet.
- A Készlet- **és raktárkezelési paraméterek** lapon jelölje be **a Csomagjegyzék feladása a főkönyvi modulban** jelölőnégyzetet.

A Készletfeladási **profil** lapon meg kell adni a fő számlákat a következő feladási típusokhoz:

- Beszerzési kiadás, nem számlázás
- Termékre vonatkozó beszerzési kiadás
- Készlet variációja

> [!NOTE]
> A **költségfeladás** típusa nem használható, ha a főkönyvi paraméterBen be van **jelölve a** Feladás költségként számla.

A további tudnivalókat a Költségszámla könyvelése [alapelvként való postán található meg](/supply-chain/cost-management/post-to-charge-account-accounting-principle.md).

## <a name="sample-posting-profile-configuration"></a>Minta feladási profil konfigurációja

Az alábbi táblázat példákat mutat be az alapértelmezett feladási típusokra a minta fő számlákkal és leírásokkal:

- Az **Elszámolószámla** oszlop azt jelzi, hogy a feladás elszámolószámla típusú. Egy későbbi tranzakció feladása során a program automatikusan sztornírozi az erre a számlára feladott összeget. 
- A **P/F** oszlop mutatja **, hogy tényleges feladásra P**, **pénzügyi feladásra pedig F**. 
- A **Követés** oszlop jelzi, hogy egy adott feladási típus fő számlája általában megegyezik-e egy másik feladási típussal. Az oszlopban lévő érték jelzi a feladás jellemzően használt típusát.

> [!NOTE]
> A fő számlák és a fő számlanevek csak javaslatok. Javasoljuk<!--note from editor: Via Writing Style Guide.--> A könyvelővel való munka során meghatározhatja, hogy a legjobb konfigurációt szeretné-e a vállalat igényeinek megfelelően.


| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | K/F | Kövesse | Leírás |
|--------------|---------------------|-------------------------|----------------|----------------|--------------------|----|----------|-----------|
| Megvásárolt anyagok bevételezett költsége | 140100</br>140101 | Anyagkészlet</br>Nem számlázott leszállított anyagok | Eszközök | Terhelés | Igen | P | Megvásárolt anyagok számlázott költsége | Akkor használja a beszerzési rendelés termékbevételezésének feladása esetén. A számla ellentételezése a számlázatlan beszerzési kiadás. A számlán szereplő összeget a beszerzési rendelés számlájának feladott összege sztornírozja. |
| Beszerzési kiadás, nem számlázás | 600180 | Anyagbevételezések | Költség | Terhelés | Igen | P | |Akkor használja a beszerzési rendelés termékbevételezésének feladása esetén. A bevételezéshez két bizonylat jön létre, amelyek az elszámolóár használata esetén a beszerzési ár eltérését követik nyomon. Az első bizonylaton szereplő számla ellenszámlája a Beszerzés elhatárolása. A második bizonylaton szereplő ellenszámla a kapott beszerzett anyagok beszerzési árának és a beszerzési ár különbözetszámláknak az összege. Az erre a számlára feladott összegeket a beszerzési rendelés számlájának feladott összegei sztornírozják. |
| Megvásárolt anyagok számlázott költsége | 140100 | Anyagkészlet | Eszközök | Terhelés | Nem | P  |Megvásárolt anyagok bevételezett költsége | Beszerzési rendelés számlájának feladott dátuma esetén használatos. Ennek a számlának az ellenszámlája a termék beszerzési kiadása. Ez a számla jelenti a készletet a mérlegben. A használt számla általában megegyezik az értékesítési rendelés szállított egységeinek költségével és a számlázott egységek költségével. |
| Termékre vonatkozó beszerzési kiadás | 600180 | Anyagbevételezés | Költség | Jóváírás | Nem | P  | |Beszerzési rendelés számlájának feladott dátuma esetén használatos. A számla ellenszámlája a beszerzett anyagok költsége. Ez a számla jelenti a készletet a mérlegben. |
| Rögzített bevételezési ár nyeresége (beszerzés, rögzített bevételezési ár nyeresége*) | 510310 | Beszerzési árkülönbözet | Költség | Jóváírás | Nem | P | Rögzített bevételezési ár vesztesége | Akkor használja a rendszer, amikor egy beszerzési rendelési számlát feladnak, és eltérés van a számlázott ár és a cikk alapértelmezett költsége között. Ez a számla akkor használatos, ha nagyobb a különbség. Ennek a számlának az ellenszámlája a Rögzített bevételezési ár ellenszámlája. |
| Rögzített bevételezési ár vesztesége (beszerzés, rögzített bevételezési ár vesztesége*) | 510310 | Beszerzési árkülönbözet | Költség | Terhelés | Nem | P | Rögzített bevételezési ár nyeresége | Akkor használja a rendszer, amikor egy beszerzési rendelési számlát feladnak, és eltérés van a számlázott ár és a cikk alapértelmezett költsége között. Ez a számla akkor használatos, ha kisebb a különbség. Ennek a számlának az ellenszámlája a Rögzített bevételezési ár ellenszámlája. |
| Rögzített bevételezési ár ellentétele (beszerzés, rögzített bevételezési ár ellentétele*) | 140900 | Készlet variációja | Eszközök | Mindkettő | Nem | P  | |Akkor használja a rendszer, amikor egy beszerzési rendelési számlát feladnak, és eltérés van a számlázott ár és a cikk alapértelmezett költsége között. Ez a számla a rögzített bevételezési ár eredményszámlái ellenszámlái. |
| Költség | NA | NA | NA | NA | NA | NA | NA | Ez a számla már nincs használva. Használja helyette a Készlet variációját. |
| Készlet variációja | 600170 | Készlet variációja | Költség | Jóváírás | Nem | Mindkettő | | Ez a számla akkor használatos, amikor: <ul><li>Eltérés van a termékbevételezés és a számla egységárában.</li><li>A költségek feladása a cikkre.</li><li>Közvetett költségek jelentve<!--note from editor: Edit okay?--> Hozzá lesz adva a beszerzett cikkekhez. </li><li>Ennek a számlának az ellenszámlája a beszerzési kiadás, a ki nem számlázatlan számla.</li></ul> |
| Beszerzés, elhatárolás | 200140 | Elhatárolt beszerzések | Kötelezettség | Jóváírás | Y | P | |Akkor használja a rendszer, amikor egy beszerzési rendelés termékbevételezését feladja, és engedélyezve van a beszerzési összegek elhatárolása. |
| Elhatárolt áfa a nyugtán | 250500 | Elhatárolt áfa | Kötelezettség | Jóváírás | Y | Mindkettő  | |Ezt a számlát akkor **használja** **a** rendszer, amikor a Tényleges adó feladása beállítást választja a Készlet- és raktárkezelési paraméterek között, és van egy adóval megrendelt beszerzési rendelése. Az összeg feladása a beszerzési rendelés fizikai frissítése (termékbevételezés) után történik, és a pénzügyi feladáskor sztornírozható a beszerzési rendelés (számla). |
| Tárgyi eszköz bevételezése (tárgyi eszköz terhelése*) | 180100 | Materiális tárgyi eszközök | Eszközök | Terhelés | N | Mindkettő | Mindkettő | Ez a számla akkor használatos, amikor a tárgyi eszközök beszerzésirendelés-sorában kiválasztja a lehetőséget. A beszerzési rendelés integrálása úgy van beállítva, hogy a termékbevételezés vagy -számla esetén beszerezzék a tárgyi eszközt. A tárgyi eszközök beszerzési rendelésének integrációjával kapcsolatos további tudnivalókat a Beszerzés révén [szerezheti meg](/fixed-assets/acquire-assets-procurement). |
| Beszerzési kiadás a költségekhez | 618900 | Vegyes költségek | Költség | Terhelés | N | Mindkettő | |Akkor használja a rendszer, amikor olyan beszerzési rendelés termékbevételezését vagy számláját feladásra használja, ahol a cikkek nincsenek raktáron, vagy beszerzési kategóriát használ. |
| Előleg | 132190 | Előre fizetett költség | Eszközök | Terhelés | N | Mindkettő | | Előlegszámla beszerzési rendelésen történő feldolgozásához használatos. |


\* A zárójelben **látható értékek a Bizonylattranzakciók lap Feladástípus** **mezőjében használt értéket jelentik**. A Feladás típusa az **Általános** lap Bizonylattranzakciók **lapján** **található**.

## <a name="fixed-asset-posting-with-purchase-orders"></a>Tárgyi eszköz feladása beszerzési rendelésekkel

Ha a Tárgyi eszközök modult használja, és azt tervezi, hogy beszerzési rendeléseken keresztül vásárol tárgyi eszközöket, **·** **·** **akkor be kell állítania a Tárgyi eszköz bevételezésének feladási típusát a Készletfeladási profil lap Beszerzési rendelés** lapján.**·** A további tudnivalókat a Tárgyi eszközök [integrációja](/fixed-assets/fixed-asset-integration.md)[, valamint az Eszközök létrehozása és a Kötelezettségek eszközbeszerzése oldalon szerezheti meg](/fixed-assets/tasks/create-acquire-assets-accounts-payable.md).

## <a name="prepayment-purchase-order-invoice-posting"></a>Előleg beszerzési rendelési számlájának feladása

Ha a beszerzési rendelésekhez az Előlegszámla szolgáltatást tervezi használni, **·** **·** **akkor** az előleg feladási típusát ki kell választani a Készletfeladási profil oldalÁnak Beszerzési rendelés lapján.**·** További tájékoztatás: Előlegszámlák [és Előlegek](/accounts-payable/prepayments-invoices-vs-prepayments.md).

## <a name="purchase-requisition-and-purchase-order-confirmation-posting"></a>Beszerzési igénylés és beszerzési rendelés visszaigazolásának feladása

A beszerzési igényléseket és a beszerzési rendelések visszaigazolását úgy is be lehet állítani, hogy előzetes kötelezettségvállalásokat és kötelezettségvállalásokat adjanak fel a főkönyvbe. Ezeket a feladásokat egy feladásdefiníció vezérli. További tájékoztatás a beszerzési rendelés [kötelezettségvállalási információinál található](/dynamicsax-2012/appuser-itpro/about-purchase-order-encumbrances).

## <a name="procurement-category-posting"></a>Beszerzési kategória feladása

A készletfeladás beállításának alternatívájaként beállíthatja az összes cikkre, cikkcsoportra vagy egyetlen cikkre vonatkozó beállításokat, kategóriákat állíthat be, és a beszerzési kategóriák szerinti főkönyvi feladást szabályozhatja. A kategóriák beállításával [és](#sample-posting-profile-configuration) termékekhez való hozzárendelésével kapcsolatos további tudnivalókat a cikk korábbi példafeladási profiljának konfigurációjában talál.

Ha beszerzési rendelésekkel vagy szállítói számlákkal használ kategóriákat, **akkor a kategóriahierarchiát hozzá kell rendelni a Beszerzési kategóriahierarchia** **típushoz a Kategóriahierarchia szerepkör-hozzárendelések** lapon.

### <a name="vendor-invoices-with-procurement-categories"></a>Beszerzési kategóriákhoz tartozó szállítói számlák

Ha a szervezet beszerzési rendeléseket használ egyes beszerzésekért, más beszerzésekért nem, a nem beszerzési rendelésekkel kapcsolatos számlákat többféle módon fel lehet feldolgozni. Ebbe beletartozik a **naplók használata a Kötelezettségek** **vagy** a Függőben lévő szállítói számlák lap alapján, amely a beszerzési rendelések számláit generálja. Nem beszerzési rendeléshez kapcsolódó számlákhoz tartozó számlák létrehozásakor beszerzési kategóriákat kell létrehoznia mindegyik költségtípushoz. A kategóriát a megfelelő költségszámlához kell leképezni a Készletfeladási **profilok lapon**.

A kategóriák pontos száma attól függ, hogy hány költségszámlát használ a számlák feladására. Minden fő számlához, amely a nem beszerzési rendelési számlákat költségként könyveli, legalább egy beszerzési kategóriára szüksége lesz. Egy fő számlához több kategória is használható. Ez hasznos lehet a használhatóság, a kereshetőség és a használatbanlott költségek típusainak jelentésére.

### <a name="benefits-of-using-procurement-categories-for-vendor-invoices"></a>A beszerzési kategóriák használatának előnyei szállítói számlákhoz

Néhány, a szállítói számlákhoz tartozó beszerzési kategória használatának előnyei a következők:

- Egységes felhasználói felület: Ha beszerzési kategóriákat konfigurál minden nem beszerzési rendeléshez kapcsolódó költséghez, **akkor** a felhasználók a Függőben lévő szállítói számlák lapon használhatja a számlázási folyamatot.
- Jobb jelentési tapasztalat: Amikor beszerzési kategóriákat konfigurál minden cikkhez és minden nem beszerzési rendeléshez kapcsolódó költséghez, a beszerzési ráfordítási jelentés szállító, kategória stb. szerint elemzi a kiadásokat.
- Konzisztens **munkafolyamat:** Amikor a Függőben lévő szállítói számlák segítségével feldolgoz minden számlát, egyetlen munkafolyamat használatával egy egységes munkafolyamatot és jóváhagyási folyamatot hozhat létre.

## <a name="consignment-inventory-posting"></a>Bizományosi készlet feladása

A bizományosi készlet ugyanazt a főkönyvi feladást használja, mint a többi beszerzett cikk. A kulcskülönbség az, hogy a készlet be érkezik, és a főkönyvi tranzakciókat nem rögzíti a rendszer. Ha a tulajdonosváltási **napló** feladása során a tulajdonost át kell ruházni a szervezetre, a cikk költségének rögzítésére bizonylat jön létre. További tájékoztatás: Bizományos [beállítása](/supply-chain/inventory/consignment.md).
