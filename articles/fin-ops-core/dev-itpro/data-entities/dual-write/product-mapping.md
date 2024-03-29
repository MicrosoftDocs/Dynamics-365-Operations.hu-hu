---
title: Egységesített terméktapasztalat
description: Ez a témakör leírja a termékadatok integrálását a pénzügyek és a műveleti alkalmazások és a Dataverse.
author: t-benebo
ms.date: 06/23/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 89ef56510ec971ef97fc9eb5c80768527abf5f88
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288922"
---
# <a name="unified-product-experience"></a>Egységesített terméktapasztalat

[!include [banner](../../includes/banner.md)]



Ha egy üzleti ökoszisztéma olyan Dynamics 365-alkalmazásokból áll, mint a Finance, a Supply Chain Management vagy a Sales, akkor a vállalkozások ezeket az alkalmazásokat használják a termék adatainak forrásaként. Ennek az az oka, hogy ezek az alkalmazások megbízható termék-infrastruktúrát biztosítanak, kiegészítve a kifinomult árképzési koncepciókkal és az aktuális készlet pontos adataival. Azok a vállalatok, amelyek külső Termék lifecycle Management (PLM) rendszert használják a termékadatok forrásának végrehajtásához, a termékeket a pénzügyi és műveleti alkalmazásokból más Dynamics 365-alkalmazásokba csatornázzák. Az egyesített Dataverse terméktel kapcsolatos tapasztalat miatt az integrált termékadatmodellből minden alkalmazás-felhasználó, így Power Platform a felhasználók is kihasználhatják a pénzügyi alkalmazásokból és műveleti alkalmazásokból származó,gazdag termékadatokat.

Itt a termék adatmodellje a Sales megoldásból.

![Adatmodell CE-termékekhez.](media/dual-write-product-4.jpg)

Ez a pénzügyi és műveleti alkalmazásokból származó termékadatmodell.

![Adatmodell a pénzügyek és műveletek termékeihez.](media/dual-write-products-5.jpg)

Ez a két termékadat-modell integrálva lett a Dataverse szolgáltatásba az alábbiakban látható módon.

![Adatmodell a Dynamics 365 alkalmazások termékeihez.](media/dual-write-products-6.jpg)

A termékek két írásos táblatérképét úgy tervezték, hogy az adatokat csak egy időben, a pénzügy- és műveleti alkalmazásoktól a következőbe valós időben, csak úgy áramlási módra tervezték Dataverse. A termék-infrastruktúra azonban nyitott, hogy szükség esetén kétirányú lehessen. Noha személyre szabható, ez azonban az Ön felelőssége; a Microsoft nem javasolja ezt a megközelítést.

## <a name="templates"></a>Sablonok

A termékinformációk tartalmazzák a termékhez és a termék meghatározásához kapcsolódó összes információt, például a termékdimenziókat, illetve a nyomon követési és tárolási dimenziókat. A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott táblaleképezések gyűjteményét.

Finance and Operations alkalmazások | Egyéb Dynamics 365 alkalmazások | Leírás
-----------------------|--------------------------------|---
[Minden termék](mapping-reference.md#138) | msdyn_globalproducts | Az összes terméktábla tartalmazza az összes, a pénzügyi alkalmazásokban és az üzemeltetésben elérhető terméket, mind a kiadott termékeket, mind a nem kiadott termékeket.
[Kiadott CDS-egyedi termékek](mapping-reference.md#213) | Termék | A **Termék** tábla a termék meghatározására szolgáló oszlopokat tartalmazza. Tartalmazza az egyedi termékeket (termék altípusú termékeket) és a termékváltozatokat. A következő táblázat a leképezéseket mutatja be.
[Színek](mapping-reference.md#170) | msdyn\_productcolors
[Konfigurációk](mapping-reference.md#171) | msdyn\_productconfigurations
[Alapértelmezett rendelésbeállítások](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Termékkategóriák](mapping-reference.md#166) | msdyn_productcategories | A termékkategóriák mindegyike, valamint a szerkezetükkel és a jellemzőikkel kapcsolatos információk a termékkategória-táblában találhatók.
[Termékkategóriák hozzárendelései](mapping-reference.md#167) | msdyn_productcategoryassignments | Ha terméket szeretne hozzárendelni egy kategóriához, akkor a termékkategória hozzárendelési tábláját használhatja.
[Termékkategóriák hierarchiái](mapping-reference.md#168) | msdyn_productcategoryhierarchies | A termékhierarchiák használatával kategóriákat vagy termékeket csoportosíthat. A kategória-hierarchiák a Dataverse szolgáltatásban termékkategória-hierarchia tábla használatával érhetők el.
[Termékkategória-hierarchiához tartozó szerepkörök](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles | A termékhierarchiák a D365 pénzügyekben és műveletekben különböző szerepkörökhöz használhatók. Azt határozzák meg, hogy melyik kategóriát használja az egyes szerepkörökben, amelyekben a termékkategória szerepkörtáblához használatos.
[Termék alapértelmezett rendelésbeállításai V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |
[Termékdimenzió-csoportok](mapping-reference.md#173) | msdyn\_productdimensiongroups | A termékdimenzió csoportja határozza meg, hogy mely cikkdimenziók határozzák meg a terméket.
[Alaptermékszínek](mapping-reference.md#187) | msdyn_sharedproductcolors | A **Megosztott termékszín** tábla azt jelzi, hogy egy adott alapterméknek milyen színei lehetnek. Ezt a koncepciót a program a Dataverse szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
[Alaptermék-konfigurációk](mapping-reference.md#188) | msdyn_sharedproductconfigurations | A **Megosztott termékkonfiguráció** tábla azt jelzi, hogy egy adott alapterméknek milyen konfigurációi lehetnek. Ezt a koncepciót a program a Dataverse szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
[Alaptermékméretek](mapping-reference.md#190) | msdyn_sharedproductsizes | A **Megosztott termékméret** tábla azokat a méreteket jelzi, amelyekkel egy adott alaptermék rendelkezhet. Ezt a koncepciót a program a Dataverse szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
[Alaptermékstílusok](mapping-reference.md#191) | msdyn_sharedproductstyles | A **Megosztott termékstílus** tábla azt jelzi, hogy egy adott alapterméknek milyen stílusai lehetnek. Ezt a koncepciót a program a Dataverse szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
[Termékszám alapján azonosított vonalkód](mapping-reference.md#164) | msdyn\_productbarcodes | A termék vonalkódja a termékek egyedileg történő azonosítására szolgál.
[Termékspecifikus egységátváltások](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Kiadott termékek V2](mapping-reference.md#189) | msdyn\_sharedproductdetails | Az **msdyn\_ sharedproductdetails tábla** tartalmazza a termék meghatározására használt pénzügyi és műveletalkalmazások oszlopait, valamint a termék pénzügyi és felügyeleti adatait.
[Méretek](mapping-reference.md#174) | msdyn\_productsizes
[Tárolásidimenzió-csoportok](mapping-reference.md#177) | msdyn_productstoragedimensiongroups | A termék tárolási dimenziócsoportja képviseli azt a módszert amelyet használnak a termék elhelyezésének definiálásához a raktárban.
[Stílusok](mapping-reference.md#178) | msdyn\_ termékstílusok
[Nyomonkövetésidimenzió-csoportok](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups | A termék nyomon követési dimenziócsoportja a termék készletben történő nyomon követésére használt módszert jelöli.
[Egységek](mapping-reference.md#219) | uoms
[Egységek átváltása](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="integration-of-products"></a>Termékek integrálása

Ebben a modellben a termék a következő két tábla kombinációjával van ábrázolva a Dataverse: **Termék** és **msdyn\_sharedproductdetails** helyeken. Ahol az első tábla a termék definícióját tartalmazza (a termék egyedi azonosítója, a termék neve és a leírás), a második tábla a termék szintjén tárolt oszlopokat tartalmazza. Ennek a két táblának a kombinációja a terméknek a készletezési egység (SKU) fogalma alapján történő meghatározására szolgál. Minden kiadott termék adatai megjelennek az említett táblákban (Termék és Megosztott termék részletei). Az összes (kiadott és nem kiadott) termék nyomon követésére a **Globális termék** tábla szolgál.

Mivel a termék SKU-ként képviselteti magát, az egyedi termékek, alaptermékek és termékváltozatok koncepciója a következő módon rögzíthető Dataverse szolgáltatásban:

- **A termékek altípus termékkel rendelkező termékek** saját maguk által meghatározott termékek. Nem kell dimenziókat definiálni. Egy példa erre egy meghatározott könyv. Ezeknél a termékeknél egy sor jön létre a **Termék** táblában, és egy sor jön létre a **msdyn\_sharedproductdetails** táblában. Nem jön létre termékcsaládsor.
- Az **Alaptermékek** általános termékként használatosak, amelyek meghatározzák az üzleti folyamatokban történő működéséthez kapcsolódó definíciókat és szabályokat. Ezeknek a definícióknak alapján egyedei termékeket lehet létrehozni, amelyek a termék változatát jelentik. Például a póló az alaptermék, és a szín és a méret dimenzióként is megadható. A változatok adhatók ki, amelyek ezen dimenziók különböző kombinációi, például a kis kék póló vagy egy közepes zöld póló. Az integrációban egy sor jön létre változatonként a terméktáblában. Ez a sor tartalmazza a változatspecifikus adatokat, például a különböző dimenziókat. A termék általános információinak tárolása a **msdyn\_sharedproductdetails** táblában történik. (Ez az általános információ az alaptermékben található.) Az alaptermék adatait a rendszer szinkronizálja Dataverse szolgáltatásba a kiadott alaptermék létrehozásával (de a változatok megjelenése előtt).
- Az **Egyedi termékek** a termékek a termék összes altípusára és az összes termékváltozatra utalnak.

![Adatmodell termékekhez.](media/dual-write-product.png)

Ha engedélyezve van a kettős írású funkció, a pénzügyből és a műveletekből származó termékek a Vázlat állapotban lesznek szinkronizálva a többi Dynamics 365 **termékkel**. Az első árlistához az ügyfélkapcsolati alkalmazásban használt pénznemmel és az árlista nevének ábécé szerinti rendezésével kerülnek hozzáadásra. Más szóval bekerülnek a Dynamics 365 alkalmazás első árlistája listára, amely megfelel annak a jogi táblának, amely a pénzügyi és műveleti alkalmazásban ki van adva. Ha a megadott pénznemhez nincs árlista, a program automatikusan létrehoz egy árlistát, és hozzárendeli a terméket.

A kétírásos lista jelenlegi megvalósítása, amely az alapértelmezett árlistát társítja az egységhez, és megkeresi a pénzügy és a műveletek alkalmazásához rendelt pénznemet, és az árlista nevén betűrendben megkeresi az első árlistát a vevői megállapodás alkalmazásában. Ha egy adott pénznemhez alapértelmezett árlistát szeretne beállítani, ha több árlistája van az adott pénznemnek, akkor frissítenie kell az árlista nevét olyan névre, amely a betűrendben korábbi, mint bármely más árlista ugyanarra a pénznemre. Ha nincs árlista az adott pénznemhez, akkor egy újat hoz létre.

Alapértelmezés szerint a pénzügyi és műveleti alkalmazásokból származó termékek vázlat állapotban lesznek szinkronizálva a többi Dynamics 365-alkalmazással **·**. Ha azt szeretné, hogy az **Aktív** állapotú termék szinkronizálva legyen, hogy például közvetlenül tudja használni az értékesítési rendelések árajánlataiban, akkor az alábbi beállítást kell választani: a **Rendszer > Adminisztráció > Rendszeradminisztráció > Rendszerbeállítások > Sales** lapon válassza a **Termékek létrehozása az aktív állapotban = igen** értéket.

A termékek szinkronizálása során meg kell adnia egy értéket a **Pénzügy** és műveletek alkalmazásban az Értékesítési egység mezőben, mert az kötelező mező az Értékesítés mezőben.

A termékek Dynamics 365 Sales alkalmazásból való létrehozása nem támogatott a termékek kettős írású szinkronizálása során.

A termékek szinkronizálása a Pénzügy és műveletek alkalmazásból a következőbe történik:Dataverse Ez azt jelenti Dataverse, hogy a terméktábla oszlopainak értékei módosíthatók, de a szinkronizálás kiváltása esetén (amikor a termékoszlopot módosítják a pénzügyi és műveleti alkalmazásban), Dataverse ezzel felülírja az értékeket a következőben: .

Finance and Operations alkalmazások | Customer Engagement alkalmazások |
---|---
[Kiadott CDS-egyedi termékek](mapping-reference.md#213) | Termék |
[Kiadott termékek V2](mapping-reference.md#189) | msdyn_sharedproductdetails |
[Minden termék](mapping-reference.md#138) | msdyn_globalproducts |

## <a name="product-dimensions"></a>Termékdimenziók

Termékdimenziók olyan jellemzők, amelyek termékváltozat azonosítására szolgálnak. A négy termékdimenzió (szín, méret, stílus és konfiguráció) a termék változatának meghatározásához hozzá van hozzárendelve a Dataverse szolgáltatáshoz is. A következő ábra a Szín cikkdimenzió adatmodelljét mutatja be. Ugyanez a modell a méretekre, stílusokra és a konfigurációkra is érvényes.

![Adatmodell a termékdimenziókhoz.](media/dual-write-product-two.png)

Finance and Operations alkalmazások | Customer Engagement alkalmazások |
---|---
[Színek](mapping-reference.md#170) | msdyn\_productcolors
[Méretek](mapping-reference.md#174) | msdyn\_productsizes
[Stílusok](mapping-reference.md#178) | msdyn\_ termékstílusok
[Konfigurációk](mapping-reference.md#171) | msdyn\_productconfigurations

Ha egy terméknek különböző a termékdimenziói vannak (például a az alaptermék mérete és szín termékdimenziók tartoznak), akkor mindegyik különböző termék (azaz a termék variánsa) ezen termékdimenziók kombinációja. A B0001 termékszámű termék például egy extra kis méretűfekete póló, és a B0002 termékszám egy kis fekete póló. Ebben az esetben a termékdimenziók meglévő kombinációinak meghatározása történik. Például az előző példából származó póló lehet extra kicsi és fekete, kicsi és fekete, közepes és fekete, illetve nagy és fekete, de nem lehet extra nagy és fekete. Más szóval az a termékdimenziók, amelyek az alaptermékhez tartozhatnak meghatározottak, és a változatokat ezen értékek alapján lehet kiadni.

Annak érdekében, hogy nyomon követhesse a termékdimenziókat, amit egy alaptermék felvehet a következő táblák jönnek létre és lesznek leképezve a Dataverse szolgáltatásban az egyes termékdimenziókhoz. A további tudnivalókat lásd: [Termékinformációk áttekintése](../../../../supply-chain/pim/product-information.md).

Finance and Operations alkalmazások | Customer Engagement alkalmazások |
---|---
[Alaptermékszínek](mapping-reference.md#187) | msdyn_sharedproductcolors |
[Alaptermék-konfigurációk](mapping-reference.md#188) | msdyn_sharedproductconfigurations |
[Alaptermékméretek](mapping-reference.md#190) | msdyn_sharedproductsizes |
[Alaptermékstílusok](mapping-reference.md#191) | msdyn_sharedproductstyles |
[Termékszám alapján azonosított vonalkód](mapping-reference.md#164) | msdyn\_productbarcodes |

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Alapértelmezett rendelési beállítások és termékspecifikus alapértelmezett rendelési beállítások

Az alapértelmezett rendelési beállítások határozzák meg azt a helyet és raktárt, ahol a cikkek beszerzése és tárolása történik, illetve azt a minimális, maximális, többszörös és szokásos mennyiséget, amely felhasználásra kerül a kereskedéshez vagy a készletgazdálkodáshoz, valamint az átfutási időket, a leállító jelzőket és a rendelési ígéret módszerét. Ezek az információk a Dataverse rendszerben az alapértelmezett rendelési beállításokkal és a termékre vonatkozó alapértelmezett rendelésbeállítási entitással érhetők el. A funkcióval kapcsolatos további tudnivalókat az Alapértelmezett rendelési beállítások [cikk tartalmazhatja](../../../../supply-chain/production-control/default-order-settings.md).

Finance and Operations alkalmazások | Customer Engagement alkalmazások |
---|---
[Alapértelmezett rendelésbeállítások](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Termék alapértelmezett rendelésbeállításai V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Mértékegység és mértékegység-átváltások

A mértékegységek és a kapcsolódó átváltás a diagramon látható adatmodellben érhetők el a Dataverse szolgáltatásban.

![Adatmodell mértékegységhez.](media/dual-write-product-three.png)

A mértékegység koncepció integrálva van a pénzügyi és a műveleti alkalmazások és más Dynamics 365-alkalmazások között. A pénzügyi és műveleti alkalmazás minden egységosztálya számára létrejön egy egységcsoport a Dynamics 365 alkalmazásban, amely az egységosztályhoz tartozó egységeket tartalmazza. Minden egységcsoporthoz egy alapértelmezett alapegység is létrejön.

Finance and Operations alkalmazások | Customer Engagement alkalmazások |
---|---
[Termékspecifikus egységátváltások](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Egységek](mapping-reference.md#219) | uoms
[Egységek átváltása](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Az egységek adategyeztetésének kezdeti szinkronizálása a pénzügyek és a műveletek között, és Dataverse

### <a name="initial-synchronization-of-units"></a>Egységek kezdeti szinkronizálása

Ha engedélyezve van a kettős írás, a pénzügyi és műveleti alkalmazások egységei szinkronizálódnak más Dynamics 365-alkalmazásokkal. A pénzügyi és műveleti alkalmazásokból Dataverse szinkronizált egységcsoportokhoz egy jelzőkészlet van beállítva, amely azt jelzi, hogy azok "Külsőleg karbantartva".

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Egyező egységek és egységosztályok/csoportok adatai a pénzügyből és a műveletekből, valamint más Dynamics 365-alkalmazásokból

Fontos megjegyezni, hogy az egység integrációs kulcsa az msdyn_symbol. Ennek megfelelően az értéknek egyedinek kell lennie a Dataverse- vagy más Dynamics 365-alkalmazásokban. Mivel más Dynamics 365-alkalmazásokban ez az egység egyediségét meghatározó "Egységcsoport azonosítója" és "Név" pár, Dataverse különböző helyzeteket kell figyelembe venni a pénzügyi és műveleti alkalmazások és a.

A pénzügyi és műveleti alkalmazások és egyéb Dynamics 365-alkalmazások egységegyeztetése/átfedése esetén:

+ **Az egység olyan mértékegységcsoporthoz tartozik a Dynamics 365-alkalmazásokban, amelyek megfelelnek a pénzügyi és műveleti alkalmazások kapcsolódó egységosztályának**. Ebben az esetben msdyn_symbol Dynamics 365-alkalmazások oszlopát a pénzügyi és műveleti alkalmazások egységszimbólumával kell kitölteni. Emiatt az adatok egyeztetése során az egységcsoport beállítása „Külsőleg karbantartott” lesz a többi Dynamics 365-alkalmazásban.
+ **Az egység olyan mértékegységcsoporthoz tartozik a Dynamics 365-alkalmazásokban, amelyek nem felelnek meg a pénzügyi és műveletalkalmazások kapcsolódó egységosztályának (nincs meglevő egységosztály a többi Dynamics 365-alkalmazás egységosztályának pénzügyi és műveleti alkalmazásában).** Ebben az esetben a msdyn_symbol mezőt véletlenszerű karakterlánccal kell kitölteni. Ügyeljen rá, hogy az értéknek egyedinek kell lennie a többi Dynamics 365-alkalmazásban.

A más Dynamics 365-alkalmazásokban nem létező pénzügyi egységek és műveletosztályok esetén:

A pénzügyi és műveleti alkalmazásokból származó egységcsoportok kettős megírásának részeként a megfelelő egységeket más Dynamics 365-alkalmazásokban Dataverse kell létrehozni és szinkronizálni, és az egységcsoport "Külsőleg karbantartva" lesz beállítva. Nincs szükség további rendszerindításra.

A többi Dynamics 365-alkalmazás olyan egységeihez, amelyek nem léteznek a pénzügyi és műveleti alkalmazásokban:

Az msdyn_symbol oszlop minden egységnél ki kell tölteni. Az egységeket mindig létre lehet hozott a megfelelő egységosztályba tartozó pénzügyi és műveletalkalmazásokban (ha van ilyen). Ha az egységosztály nem létezik, először létre kell hozni az egységosztályt (ne feledje, hogy a másik Dynamics 365-ös alkalmazásegységcsoportnak megfelelő mértékegységcsoportot csak kiterjesztéssel lehet létrehozni a pénzügyi és műveleti alkalmazásokban egységosztályt). Ezt követően létrehozhatja az egységet. Ne feledje, hogy a pénzügyi és műveleti alkalmazásokban az egységszimbólumnak olyan szimbólumnak kell lennie, msdyn_symbol más Dynamics 365-alkalmazásokban már meg van adva az egységhez.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Termékirányelvek: dimenzió, nyomon követés és tárolás csoportjai

A termékirányelvek a termékek és a készletbeli jellemzőik meghatározására használt irányelvek halmazai. A termékdimenzió-csoport, a termékkövetési-dimenziócsoport és a tárolási dimenziócsoport a termékirányelvekként találhatók meg.

Finance and Operations alkalmazások | Customer Engagement alkalmazások |
---|---
[Termékdimenzió-csoportok](mapping-reference.md#173) | msdyn\_productdimensiongroups |
[Tárolásidimenzió-csoportok](mapping-reference.md#177) | msdyn_productstoragedimensiongroups |
[Nyomonkövetésidimenzió-csoportok](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups |

## <a name="product-hierarchies"></a>Termékhierarchiák

Finance and Operations alkalmazások | Customer Engagement alkalmazások |
---|---
[Termékkategóriák hozzárendelései](mapping-reference.md#167) | msdyn_productcategoryassignments |
[Termékkategóriák hierarchiái](mapping-reference.md#168) | msdyn_productcategoryhierarchies |
[Termékkategória-hierarchiához tartozó szerepkörök](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles |

## <a name="integration-key-for-products"></a>Termékek integrációs kulcsa

A Dynamics 365 Pénzügy Dataverse és az integrációs kulcsokban található termékek egyedi azonosítására használja a rendszer.
A termékek esetében a **(termékszám)** az az egyedi kulcs, amely azonosít egy terméket a Dataverse szolgáltatásban. Ez a következők összefűzésével jön létre: **(company, msdyn_productnumber)**. A **vállalat** jelzi a jogi **személyt a pénzügyben és a műveletekben,** msdyn_productnumber a termékszámot az adott termékhez a pénzügyben és a műveletekben.

Egy másik Dynamics 365-alkalmazás felhasználói esetén a termék a felhasználói felületen lévő **msdyn_productnumber** értékkel azonosítható (az oszlop címkéje a **Termékszám**). A termék képernyőjén mind a vállalat, mind a msydn_productnumber látható. A (productnumber) oszlop, a termék egyedi kulcsa viszont nem jelenik meg.

Ha alkalmazásokat épít a Dataverse szolgáltatásban, akkor ügyeljen arra, hogy a **productnumber** elemet (az egyedi termékazonosító) használja integrációs kulcsként. Ne használja az **msdyn_productnumber** elemet, mert az nem egyedi.

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Termékek kezdeti szinkronizálása és adatok áttelepítése a pénzügyből Dataverse és a műveletekbe

### <a name="initial-synchronization-of-products"></a>Termékek kezdeti szinkronizálása

Ha engedélyezve van a kettős írás, Dataverse a pénzügyi és műveleti alkalmazások termékei szinkronizálódnak az ügyfél-kapcsolati alkalmazásokkal és az ügyfél-kapcsolati alkalmazásokkal. A kettős Dataverse írású írású alkalmazásokban és más Dynamics 365-alkalmazásokban létrehozott termékek nem frissülnek és nem eznek a pénzügyi és műveleti alkalmazásokból származó termékadatokkal.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Termékadatok egyeztetése pénzügyből és műveletekből, valamint egyéb Dynamics 365-alkalmazásokból

Ha ugyanazok a termékek a pénzügyben, a műveletekben, valamint más Dynamics 365-alkalmazásokban is átfedik/ Dataverse egyeztetik őket, akkor a kettős írás engedélyezésekor a pénzügyek és műveletek termékeinek szinkronizálása történik, Dataverse és ugyanannál a terméknél többször jelennek meg sorok.
A korábbi **helyzet** elkerülése érdekében, ha más Dynamics 365-alkalmazások olyan termékeket tartalmaznak, amelyek átfedésben vannak a pénzügyekkel és a műveletekkel, akkor a kettős írást engedélyező rendszergazdának el kell indítania a Vállalat oszlopokat (például: "USMF") **és msdyn_productnumber (** például: "1234:Black:S") a termékek szinkronizálása előtt. Más szóval a Dataverse termék e két oszlopát meg kell egyezni a pénzügyben érintett vállalattal, valamint azokkal a műveletekkel, amelyekhez a terméket és annak termékszámát meg kell egyezni.

Ezt követően, amikor a szinkronizálás engedélyezve van és helyre kerül, Dataverse a program szinkronizálja a pénzügyek és műveletek termékeit azokkal az egyező termékekkel és más Dynamics 365-alkalmazásokkal. Ez egyedi termékekre és termékváltozatokra is vonatkozik.

### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Termékadatok áttelepítése más Dynamics 365-alkalmazásokból a pénzügybe és a műveletekbe

Ha más Dynamics 365-alkalmazások olyan termékeket tartalmaznak, amelyek nem nincsenek jelen a pénzügyben és a műveletekben, **a rendszergazda először az EcoResReleasedProductCreationV2Entity** funkcióval importálhatja ezeket a termékeket a pénzügyekbe és a műveletekbe. Másodszor, a fentiek szerint egyeznie kell a pénzügyi adatokkal és műveletekkel, valamint más Dynamics 365-alkalmazásokkal.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

