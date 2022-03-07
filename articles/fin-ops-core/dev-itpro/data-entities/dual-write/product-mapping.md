---
title: Egységes termékélmény
description: Ez a témakör a termékadatok integrációját ismerteti a Finance and Operations alkalmazás és a Dataverse között.
author: t-benebo
ms.date: 12/12/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a2f4aeefe5fe7698d9dfaf80619102f2b753e52b
ms.sourcegitcommit: 8592c661b41f9cef8b7ef2863a3b97bf49a4e6f9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/26/2021
ms.locfileid: "7423447"
---
# <a name="unified-product-experience"></a>Egységes terméktapasztalat

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ha egy üzleti ökoszisztéma olyan Dynamics 365-alkalmazásokból áll, mint a Finance, a Supply Chain Management vagy a Sales, akkor a vállalkozások ezeket az alkalmazásokat használják a termék adatainak forrásaként. Ennek az az oka, hogy ezek az alkalmazások megbízható termék-infrastruktúrát biztosítanak, kiegészítve a kifinomult árképzési koncepciókkal és az aktuális készlet pontos adataival. Azok a vállalkozások, amelyek külső termékéletciklus-kezelő (PLM) rendszert használnak a termék adatainak lekéréséhez, a termékeket becsatornázhatják a Finance and Operations-alkalmazásokból más Dynamics 365-alkalmazásokba. Az egységes termékélmény az integrált termékadat-modellt elérhetővé teszi a Dataverse szolgáltatásban, így az alkalmazás minden felhasználója (beleértve a Power Platform-felhasználókat is) igénybe veheti Finance and Operations-alkalmazáskból származó részletes termékadatokat.

Itt a termék adatmodellje a Sales megoldásból.

![Adatmodell CE-termékekhez.](media/dual-write-product-4.jpg)

Itt a termék adatmodellje a Finance and Operations-alkalmazásokból.

![Adatmodell a Finance and Operations termékeihez.](media/dual-write-products-5.jpg)

Ez a két termékadat-modell integrálva lett a Dataverse szolgáltatásba az alábbiakban látható módon.

![Adatmodell a Dynamics 365 alkalmazások termékeihez.](media/dual-write-products-6.jpg)

A termékekhez kapcsolódó kettős írású táblaleképezések csak egyirányú, csaknem valós idejű adatátvitelre vannak tervezve a Finance and Operations-alkalmazások és a Dataverse között. A termék-infrastruktúra azonban nyitott, hogy szükség esetén kétirányú lehessen. Noha személyre szabható, ez azonban az Ön felelőssége; a Microsoft nem javasolja ezt a megközelítést.

## <a name="templates"></a>Sablonok

A termékinformációk tartalmazzák a termékhez és a termék meghatározásához kapcsolódó összes információt, például a termékdimenziókat, illetve a nyomon követési és tárolási dimenziókat. A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott táblaleképezések gyűjteményét.

Finance and Operations-alkalmazásoknak | Egyéb Dynamics 365 alkalmazások | Leírás
-----------------------|--------------------------------|---
[Minden termék](mapping-reference.md#138) | msdyn_globalproducts | A minden terméktábla tartalmazza a Finance and Operations-alkalmazások összes rendelkezésre álló termékét, a kiadott termékeket és a nem kiadott termékeket is.
[Kiadott CDS-egyedi termékek](mapping-reference.md#213) | Termék | A **Termék** tábla a termék meghatározására szolgáló oszlopokat tartalmazza. Tartalmazza az egyedi termékeket (termék altípusú termékeket) és a termékváltozatokat. A következő táblázat a leképezéseket mutatja be.
[Színek](mapping-reference.md#170) | msdyn\_productcolors
[Konfigurációk](mapping-reference.md#171) | msdyn\_productconfigurations
[Alapértelmezett rendelésbeállítások](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Termékkategóriák](mapping-reference.md#166) | msdyn_productcategories | A termékkategóriák mindegyike, valamint a szerkezetükkel és a jellemzőikkel kapcsolatos információk a termékkategória-táblában találhatók.
[Termékkategóriák hozzárendelései](mapping-reference.md#167) | msdyn_productcategoryassignments | Ha terméket szeretne hozzárendelni egy kategóriához, akkor a termékkategória hozzárendelési tábláját használhatja.
[Termékkategóriák hierarchiái](mapping-reference.md#168) | msdyn_productcategoryhierarchies | A termékhierarchiák használatával kategóriákat vagy termékeket csoportosíthat. A kategória-hierarchiák a Dataverse szolgáltatásban termékkategória-hierarchia tábla használatával érhetők el.
[Termékkategória-hierarchiához tartozó szerepkörök](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles | A termékhierarchiák a D365 Finance and Operations különböző szerepköreiben használhatók. Azt határozzák meg, hogy melyik kategóriát használja az egyes szerepkörökben, amelyekben a termékkategória szerepkörtáblához használatos.
[Termék alapértelmezett rendelésbeállításai V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |
[Termékdimenzió-csoportok](mapping-reference.md#173) | msdyn\_productdimensiongroups | A termékdimenzió csoportja határozza meg, hogy mely cikkdimenziók határozzák meg a terméket.
[Alaptermékszínek](mapping-reference.md#187) | msdyn_sharedproductcolors | A **Megosztott termékszín** tábla azt jelzi, hogy egy adott alapterméknek milyen színei lehetnek. Ezt a koncepciót a program a Dataverse szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
[Alaptermék-konfigurációk](mapping-reference.md#188) | msdyn_sharedproductconfigurations | A **Megosztott termékkonfiguráció** tábla azt jelzi, hogy egy adott alapterméknek milyen konfigurációi lehetnek. Ezt a koncepciót a program a Dataverse szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
[Alaptermékméretek](mapping-reference.md#190) | msdyn_sharedproductsizes | A **Megosztott termékméret** tábla azokat a méreteket jelzi, amelyekkel egy adott alaptermék rendelkezhet. Ezt a koncepciót a program a Dataverse szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
[Alaptermékstílusok](mapping-reference.md#191) | msdyn_sharedproductstyles | A **Megosztott termékstílus** tábla azt jelzi, hogy egy adott alapterméknek milyen stílusai lehetnek. Ezt a koncepciót a program a Dataverse szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
[Termékszám alapján azonosított vonalkód](mapping-reference.md#164) | msdyn\_productbarcodes | A termék vonalkódja a termékek egyedileg történő azonosítására szolgál.
[Termékspecifikus egységátváltások](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Kiadott termékek V2](mapping-reference.md#189) | msdyn\_sharedproductdetails | A **msdyn\_sharedproductdetails** tábla tartalmazza a termék meghatározására szolgáló oszlopokat a Finance and Operations alkalmazásokból, illetve ez tartalmazza a termék pénzügyi és vezetési információit.
[Méretek](mapping-reference.md#174) | msdyn\_productsizes
[Tárolásidimenzió-csoportok](mapping-reference.md#177) | msdyn_productstoragedimensiongroups | A termék tárolási dimenziócsoportja képviseli azt a módszert amelyet használnak a termék elhelyezésének definiálásához a raktárban.
[Stílusok](mapping-reference.md#178) | msdyn\_productsytles
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

Ha a kettős írás funkció engedélyezve van, a Finance and Operations modul alkalmazásai szinkronizálva lesznek a többi Dynamics 365 termékben a **Vázlat** állapotban. Az első árlistához az ügyfélkapcsolati alkalmazásban használt pénznemmel és az árlista nevének ábécé szerinti rendezésével kerülnek hozzáadásra. Más szóval a Dynamics 365 alkalmazás első árlistájához lesznek hozzáadva amely megfelel annak a jogi táblának a pénznemének, ahol a termék ki van adva a Finance and Operations-alkalmazásban. Ha a megadott pénznemhez nincs árlista, a program automatikusan létrehoz egy árlistát, és hozzárendeli a terméket.

A kettős írású beépülő modulok jelenlegi megvalósítása, amelyek az alapértelmezett árlistát társítják a Finance and Operations alkalmazáshoz társított pénznem kereséséhez, és az árlista betűrendes rendezésével megkeresik az első árlistát a vevői megállapodási alkalmazásban. Ha egy adott pénznemhez alapértelmezett árlistát szeretne beállítani, ha több árlistája van az adott pénznemnek, akkor frissítenie kell az árlista nevét olyan névre, amely a betűrendben korábbi, mint bármely más árlista ugyanarra a pénznemre. Ha nincs árlista az adott pénznemhez, akkor egy újat hoz létre.

Alapértelmezés szerint a Finance and Operations-alkalmazások termékeit szinkronizálja a rendszer a többi Dynamics 365-alkalmazással **Vázlat** állapotban. Ha azt szeretné, hogy az **Aktív** állapotú termék szinkronizálva legyen, hogy például közvetlenül tudja használni az értékesítési rendelések árajánlataiban, akkor az alábbi beállítást kell választani: a **Rendszer > Adminisztráció > Rendszeradminisztráció > Rendszerbeállítások > Sales** lapon válassza a **Termékek létrehozása az aktív állapotban = igen** értéket.

A termékek szinkronizálásakor meg kell adnia az **Értékesítési egység** mező értékét a Finance and Operations alkalmazásban, mert az kötelező mező az Értékesítésben.

A termékek Dynamics 365 Sales alkalmazásból való létrehozása nem támogatott a termékek kettős írású szinkronizálása során.

A termékek szinkronizálása a Finance and Operations-alkalmazásokból a Dataverse felé történik. Ez azt jelenti, hogy a terméktábla oszlopaiban szereplő értékek módosíthatók a Dataverse szolgáltatásban, de ha a szinkronizálást aktiválják (ha egy termékoszlop módosul a Finance and Operations-alkalmazásban), akkor ez felülírja a Dataverse értékeit.

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
[Stílusok](mapping-reference.md#178) | msdyn\_productsytles
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

Az alapértelmezett rendelési beállítások határozzák meg azt a helyet és raktárt, ahol a cikkek beszerzése és tárolása történik, illetve azt a minimális, maximális, többszörös és szokásos mennyiséget, amely felhasználásra kerül a kereskedéshez vagy a készletgazdálkodáshoz, valamint az átfutási időket, a leállító jelzőket és a rendelési ígéret módszerét. Ezek az információk a Dataverse rendszerben az alapértelmezett rendelési beállításokkal és a termékre vonatkozó alapértelmezett rendelésbeállítási entitással érhetők el. További információ az [Alapértelmezett rendelési beállítások cikkben](../../../../supply-chain/production-control/default-order-settings.md)olvasható.

Finance and Operations alkalmazások | Customer Engagement alkalmazások |
---|---
[Alapértelmezett rendelésbeállítások](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Termék alapértelmezett rendelésbeállításai V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Mértékegység és mértékegység-átváltások

A mértékegységek és a kapcsolódó átváltás a diagramon látható adatmodellben érhetők el a Dataverse szolgáltatásban.

![Adatmodell mértékegységhez.](media/dual-write-product-three.png)

A mértékegység fogalma integrálva van a Finance and Operations-alkalmazások és más Dynamics 365 alkalmazások között. A Finance and Operations-alkalmazás minden egységosztálya esetében létrejön egy olyan egységcsoport a Dynamics 365-alkalmazásban, amely az egységosztályhoz tartozó egységeket tartalmazza. Minden egységcsoporthoz egy alapértelmezett alapegység is létrejön.

Finance and Operations alkalmazások | Customer Engagement alkalmazások |
---|---
[Termékspecifikus egységátváltások](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Egységek](mapping-reference.md#219) | uoms
[Egységek átváltása](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Az egységadatok egyezésének eredeti kezdeti szinkronizálása a Finance and Operations és a Dataverse között

### <a name="initial-synchronization-of-units"></a>Egységek kezdeti szinkronizálása

Ha a kettős írás engedélyezett, a Finance and Operations rendszerből származó egységeket a rendszer szinkronizálja a többi Dynamics 365-alkalmazással. A Finance and Operations-alkalmazásokból a Dataverse szolgáltatásban szinkronizált egységcsoportok olyan jelölővel rendelkeznek, amely mutatja, hogy „Külsőleg karbantartottak”.

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Egyező egységek és egységosztályok/csoportok Finance and Operations- és más Dynamics 365-alkalmazásokból származó adatai

Fontos megjegyezni, hogy az egység integrációs kulcsa az msdyn_symbol. Ennek megfelelően az értéknek egyedinek kell lennie a Dataverse- vagy más Dynamics 365-alkalmazásokban. Mivel a többi Dynamics 365-alkalmazásban az „Egységcsoport azonosítója” és a „Név” határozza meg egy egység egyediségét, különböző eseteket kell figyelembe vennie az egységadatok Finance and Operations-alkalmazások és Dataverse közötti egyeztetése során.

A Finance and Operations-alkalmazások és más Dynamics 365-alkalmazások egyező/átfedő egységei:

+ **Az egység olyan, másik Dynamics 365-alkalmazásokban lévő egységcsoportba tartozik, amelyik megfelel a Finance and Operations-alkalmazások társított egységosztályának**. Ebben az esetben a többi Dynamics 365-alkalmazás msdyn_symbol oszlopában a Finance and Operations-alkalmazásokból származó egységszimbólumot kell megadni. Emiatt az adatok egyeztetése során az egységcsoport beállítása „Külsőleg karbantartott” lesz a többi Dynamics 365-alkalmazásban.
+ **Az egység más Dynamics 365-alkalmazások olyan egységcsoportjába tartozik, amely nem felel meg a Finance and Operations-alkalmazások társított egységosztályának (nincs egységosztály a Finance and Operations-alkalmazásokban a többi Dynamics 365-alkalmazás egységosztályához).** Ebben az esetben a msdyn_symbol mezőt véletlenszerű karakterlánccal kell kitölteni. Ügyeljen rá, hogy az értéknek egyedinek kell lennie a többi Dynamics 365-alkalmazásban.

A Finance and Operations-egységek és -egységosztályok nem léteznek más Dynamics 365-alkalmazásokban:

A kettős írás részeként a Finance and Operations-alkalmazások egységcsoportjai és a megfelelő egységek más Dynamics 365-alkalmazásokban és a Dataverse szolgáltatásban jönnek létre és szinkronizálódnak, az egységcsoportot pedig „Külsőleg karbantartottnak” állítja be a rendszer. Nincs szükség további rendszerindításra.

Más Dynamics 365-alkalmazások egységei, amelyek nem találhatók meg Finance and Operations-alkalmazásokban:

Az msdyn_symbol oszlop minden egységnél ki kell tölteni. Az egységek bármikor létrehozhatók a megfelelő egységosztályban (ha van ilyen) lévő Finance and Operations-alkalmazásokban. Ha az egységosztály nem létezik, akkor először létre kell hozni többi Dynamics 365-alkalmazás egységcsoportjával egyező egységosztályt (ügyeljen rá, hogy a Finance and Operations szolgáltatásban nem lehet egységosztályt létrehozni, csak bővítményen keresztül, ha kibővíti a felsorolást). Ezt követően létrehozhatja az egységet. Ügyeljen rá, hogy a Finance and Operations-alkalmazások egységszimbólumának az egységhez a többi Dynamics 365-alkalmazásban korábban meghatározott msdyn_symbol szimbólumnak kell lennie.

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

Ha egyedileg szeretné azonosítani a termékeket a Dynamics 365 for Finance and Operations és a Dataverse-termékek között, akkor integrációs kulcsot kell használni.
A termékek esetében a **(termékszám)** az az egyedi kulcs, amely azonosít egy terméket a Dataverse szolgáltatásban. Ez a következők összefűzésével jön létre: **(company, msdyn_productnumber)**. A **company** jelöli a jogi személyt a Finance and Operations szolgáltatásban; a **msdyn_productnumber** jelöli az adott termék termékszámát a Finance and Operations szolgáltatásban.

Egy másik Dynamics 365-alkalmazás felhasználói esetén a termék a felhasználói felületen lévő **msdyn_productnumber** értékkel azonosítható (az oszlop címkéje a **Termékszám**). A termék képernyőjén mind a vállalat, mind a msydn_productnumber látható. A (productnumber) oszlop, a termék egyedi kulcsa viszont nem jelenik meg.

Ha alkalmazásokat épít a Dataverse szolgáltatásban, akkor ügyeljen arra, hogy a **productnumber** elemet (az egyedi termékazonosító) használja integrációs kulcsként. Ne használja az **msdyn_productnumber** elemet, mert az nem egyedi.

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>A termékek kezdeti szinkronizálása, és az adatok áttelepítése a Dataverse szolgáltatásból a Finance and Operations szolgáltatásba

### <a name="initial-synchronization-of-products"></a>Termékek kezdeti szinkronizálása

Ha a kettős írás engedélyezett, a Finance and Operations alkalmazásokból származó termékeket a rendszer szinkronizálja a Dataverse szolgáltatással és a többi Customer Engagement-alkalmazással. A Dataverse szolgáltatásban és a többi Dynamics 365-alkalmazásban a kettős írás előtt kiadott alkalmazások nem frissülnek, és a rendszer nem egyezteti őket a Finance and Operations alkalmazások termékadataival.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>A Finance and Operations és más Dynamics 365-alkalmazások termékadatainak egyeztetése

Ha ugyanaz a termék szerepel (átfedő/egyező) a Finance and Operations és a Dataverse szolgáltatásban és más Dynamics 365-alkalmazásokban, akkor a kettős írás engedélyezésekor sor kerül a Finance and Operations szolgáltatásból származó termékek szinkronizálására, és az egyes termékekhez ismétlődő sorok jelennek meg a Dataverse szolgáltatásban.
Az előző helyzet elkerülése érdekében, ha más Dynamics 365-alkalmazásokban a Finance and Operations szolgáltatásban lévőkkel átfedő vagy egyező termékek vannak, akkor a kettős írást engedélyező rendszergazdának rendszerindítást kell végeznie a **Vállalat** (pl. „USMF”) és az **msdyn_productnumber** oszlopokban (például: „1234:Black:S”), mielőtt megtörténik a termékek szinkronizálása. Más szóval, a Dataverse szolgáltatásban lévő termékben található két oszlopban meg kell adni a termékszámot, valamint a Finance and Operations alkalmazásban lévő azon megfelelő vállalatot, amelyhez egyeztetni kell a terméket.

Amikor ezután megkezdődik a szinkronizálás, a Finance and Operations szolgáltatásból származó termékeket a rendszer szinkronizálja a Dataverse szolgáltatásban és a többi Dynamics 365-alkalmazásban lévő egyeztetett termékekkel. Ez egyedi termékekre és termékváltozatokra is vonatkozik.

### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>A termékadatok áttelepítése más Dynamics 365-alkalmazásokból a Finance and Operations szolgáltatásba

Ha más Dynamics 365-alkalmazások olyan termékekkel rendelkeznek, amelyek nem szerepelnek a Finance and Operations modulban, akkor a rendszergazda először használhatja az **EcoResReleasedProductCreationV2Entity** entitást az ilyen termékek Finance and Operations modulba történő importálásához. Ezután a fent ismertetett módon egyeztetheti a Finance and Operations modulból és a többi Dynamics 365-alkalmazásból származó termékadatokat.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
