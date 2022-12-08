---
title: Store Commerce alkalmazás képességei
description: Ez a cikk ismerteti azokat a funkciókat, amelyek elérhetők a Store Commerce alkalmazásban Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2022-09-30
ms.openlocfilehash: 58f2ab1f913d3629de7971c8eeb2d1821161e44f
ms.sourcegitcommit: 29d9a7573bdac004726da88a9d7b2cc9c383e9ca
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2022
ms.locfileid: "9788512"
---
# <a name="store-commerce-app-capabilities"></a>Store Commerce alkalmazás képességei

[!include [banner](includes/banner.md)]

A Store Commerce alkalmazás a pénztári tapasztalat modern felhasználói élménye Microsoft Dynamics 365 Commerce. Lehetővé teszi a vállalkozások számára, hogy tranzakciókat feldolgoztanak az üzletben, és kezelni tárolják az irodai műveleteket, például a készletet és a rendelési beszerzéseket. Az alkalmazás a vállalkozások számára is lehetővé teszi a hűségprogrammal és ügyfélkapcsolatokkal való ügyfélkapcsolatok kezelését. 

A Commerce Scale Unit (STB) segítségével működő Store Commerce alkalmazás teljes csatorna-megoldást biztosít. Például egy vevő online vásárolhat egy terméket, és felveheti azt egy közeli üzletben, ezáltal folytathatja a vásárlást a csatornák között anélkül, hogy adatvesztést volna kapnia. 

Ez a cikk áttekintést nyújt a Store Commerce alkalmazás lehetőségeiről.

## <a name="platform"></a>Platform

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Csatorna | Dynamics 365 Commerce Olyan átfogó csatorna-megoldást kínál, amely egységesíti a háttérirodai, az áruházi, a hívásközponti és a digitális tapasztalatokat. | [Áttekintés](index.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/dynamics-365-commerce-overview-november-2-2020) |
| Nem központosított Commerce | A Commerce Scale Unit a fej nélküli kereskedelmi motornak ad állomást. A fej nélküli kereskedelmi motor a commerce üzleti logika központi pontjaként szolgál, és egy teljes csatorna-megoldást nyújt. | <p>[Architektúra – áttekintés](commerce-architecture.md)</p><p>[Fej nélküli architektúra](dev-itpro/retail-server-architecture.md)</p> | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-commerce-architecture-overview-december-4-2020) |
| Commerce headquarters | A Commerce Headquarters olyan háttér-funkciókat kínál, amelyek lehetővé teszik a termékek, alkalmazottak, üzleti folyamatok, árképzés és más, a vállalat számára szükséges funkciók konfigurálást. | [Architektúra – áttekintés](commerce-architecture.md) | |
| Pénztár (POS) | A Store Commerce alkalmazás a pénztári tapasztalat. Dynamics 365 Commerce Funkciógazdag és átfogó POS-funkciókat nyújt, amelyek az értékesítési munkatársaknak, pénztárosoknak és vezetőknek nyújtanak jobb ügyfélszolgálatot. Ezenkívül számos telepítési lehetőséget kínál a kiskereskedők számára, javítja a teljesítményt, és jobb életciklus-kezelési (ALM) lehetőségeket nyújt az alkalmazásoknak. | [Store Commerce alkalmazás](dev-itpro/store-commerce.md) | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/modernize-the-dynamics-365-commerce-in-store-technology-using-the-new-store-commerce-app-march-30-2022)</p><p>[Videó](https://youtu.be/7B332XH_zfs)</p><p>[Áttelepítés az MPOS rendszerből a Store Commerce alkalmazásba](dev-itpro/pos-extension/migrate-mpos-store-commerce.md)</p> |
| Felhőbeli telepítés | A Commerce Scale Units több példánya telepíthető rakományelosztás és földrajzi távolság miatt. | [Felhőbeli telepítés](../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md) | |
| A létesítményben telepítettek | A helyi üzleti adatok telepítésével a Commerce ügyfelek több tulajdonost és vezetést kaphatnak a Dynamics 365 környezetekben. | [Helyszíni telepítés](../fin-ops-core/dev-itpro/deployment/deploy-retail-onprem.md) | |

## <a name="device-management"></a>Eszközkezelés

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Több űrlaptényező | A Store Commerce alkalmazás több eszközképernyő tényezőjére is használható, például számítógépekre, táblagépekre és mobileszközökre. A látható felhasználói felület lehetővé teszi az elrendezés automatikus átméretezését és a képernyő méretének megfelelő beállítását. | [Vizuális konfigurációk](pos-screen-layouts.md) |  |
| Több platformon keresztül | A Store Commerce alkalmazás a weben, a Windows rendszerben, az iOS-en és a platformokon is támogatott Android . | [Platformok](dev-itpro/hybridapp.md) | |
| Márka | A képernyőtervező segítségével testreszabhatja a képernyő-elrendezéseket, hogy megfeleljen az üzleti követelményeknek. Ezen kívül témákat, elrendezéseket, színeket és képeket lehet létrehozni az alkalmazotti szerepkörök alapján, majd megoszthatók a felhasználók között a márka konzisztenciája és a használat könnyebbsége érdekében. | [Vizuális konfigurációk](pos-screen-layouts.md) | [Videó](https://www.youtube.com/watch?v=ldqCw2wf5fY) |
| Topológia | A különböző üzleten belüli topológiák a hálózati elérhetőségtől függően támogatottak. | <p>[Topológia](dev-itpro/retail-modern-pos-architecture.md)</p><p>[Infographic](dev-itpro/retail-in-store-topology.md)</p> | |
| Több eszköz kezelése | A Commerce Headquarters segítségével egyszerűen több eszköz kezelhető az üzletek között. | [Aktiválás](set-up-activation-accounts-validate-devices-hq.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/commerce-mass-deployment-with-sccm-system-center-configuration-manager-october-6-2022) |

## <a name="employee-management"></a>Alkalmazottak kezelése

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Bejelentkezés | Az üzlet minden alkalmazottja külön bejelentkezést kaphat. A bejelentkezés típusa lehet felhasználónév, vonalkód, mágnescsík-olvasó (MSR), biometrikus adatok és Azure Active Directory (Azure AD). | <p>[Azure AD](aad-pos-logon.md)</p><p>[Kiterjesztett bejelentkezés](extended-logon.md)</p> | |
| Engedélyek | Az alkalmazottak különféle engedélyszinteket támogatnak, például a rendelések létrehozására és a rendelések szerkesztésére vonatkozó engedélyeket. | [Engedélyek](tasks/create-pos-permission-groups.md) | |
| Idő- és jelenlétkezelés | A jelenlét az Idő óra funkcióval kezelhető. A jelenléti adatokat az alkalmazás segítségével lehet a bérszámfejtésbe Dynamics 365 Human Resources feldolgozni. | [Időgazdálkodás](retail-time-attendance.md) | |
| Értékesítési jutalék | Az értékesítéseket az üzletkötő nyomon követheti jutalékok és más ösztönzők kiszámítása érdekében. | [Jutalék](pos-sales-groups-track-commissions.md) | |

## <a name="merchandising"></a>Árusítás

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Szortiment kezelése | Az árusítási vezetők kiválogatják a termékeket, hogy egy adott csatornában és adott időszakban rendelkezésre állnak értékesítésre. | [Szortimentek](assortments.md) | |
| Katalógusok | Az árusítási vezetők a katalógusokat kezelhetik, és azonosítják azokat a termékeket, amelyek katalógusspecifikus árakat kínálnak. | [Katalógusok](/dynamicsax-2012/appuser-itpro/about-retail-product-catalogs) | |
| Termék- és kategóriakezelés | A Commerce Headquarters üzletvezetői létrehozhatnak változatokkal, attribútumokkal, mértékegységekkel stb. kapcsolatos termékeket. Kategóriahierarchiát is meghatároznak a termékek rendszerezése érdekében. | [Termék](retail-hierarchies.md) | |
| Csomagok | Az árusítási vezetők csoportba csoportosítják a termékeket, hogy csomagként vagy csomagként eladják őket. | [Csomagok](/dynamicsax-2012/appuser-itpro/about-setting-up-retail-product-kits) | |
| Infókódok | Infókódok használatával rákérdezhet a pénztárosra, hogy adja meg az adatokat a POS különböző műveletei során, például cikkértékesítés, cikk-visszaadás vagy vevőválasztás során. | [Infókódok](/dynamicsax-2012/appuser-itpro/about-info-codes-retail) | |
| Csatolt cikkek | A csatolt cikkek segítségével lehet értékeket értékesítani, amikor egy cikket hozzáadnak a tranzakcióhoz. | [Csatolt cikkek](/dynamicsax-2012/appuser-itpro/set-up-products-for-cross-selling-and-up-selling) | |
| Garanciák | A kiterjesztett garanciák termékekkel együtt értékesíthatók. | [Garancia](extended-warranty.md) | |
| Címkenyomtatás | Címkéket lehet generálni, amelyek termékadatokat, például kötegszámot, sorozatszámot és lejárati dátumot tartalmaznak. | [Címkenyomtatás](/dynamicsax-2012/appuser-itpro/create-and-print-labels-overview) | |

## <a name="assisted-selling"></a>Értékesítő

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Termékek tallózása | Termékek tallózása kategória szerint. | [Termékhierarchia](retail-hierarchies.md) | |
| Termékkeresés | A termékek keresése név szerint, a keresés finomítása a termékattribútumok, például a márka, az ár és az anyag alapján. Ezt a funkciót az Azure Keresési szolgáltatás használja. | [Felhőalapú keresés](cloud-powered-search-overview.md) | |
| Termékadatok lap | A részletes termékekkel kapcsolatos lapok képekkel, leírással, termékattribútumokkal és ajánlott termékekkel kapcsolatosak lehetnek. Az ajánlásokhoz az Ajánlások szolgáltatás szolgál. | | |
| Termék összehasonlítása | Több termék összehasonlítása, és súgó a vevőknek a választásban és a termékek tranzakcióhoz való hozzáadásában. | | |
| Folyosó folyosója | A készlet egyszerű keresni a többi üzletben, és rendelések létrehozása. | [Keresés a készletben](pos-inventory-lookup-operation.md) | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |
| Ajánlatok | Az Ajánlások szolgáltatás segítségével értékesítsen és értékesítsen több terméket. Ez a szolgáltatás szabadalmazott technológia segítségével tesz javaslatot a beszerzési trendekre, valamint az újonnan érkezett, hasonló megjelenésre és bestsételre vonatkozó jellemzők alapján. Ezek az ajánlások a termék részletei lapokon, **a** Vevő adatai lapon és **a Tranzakciók lapon érhetők** el. | [Ajánlatok](product-recommendations.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-recommendations-march-2-2021) |

## <a name="customer-relationship"></a>Ügyfélkapcsolat

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Ügyfélkezelés | Vevői számlák létrehozása, szerkesztése és kezelése. A vevőszámlák aszinkron módban kezelhetők a valós idejű feldolgozás elkerülése érdekében. | [Kezelése](customer-mgmt-stores.md) | |
| Vevőattribútumok | A Vevőattribútumok keretrendszer lehetővé teszi további vevői kapcsolódó adatoknak az üzleti követelmények alapján való rögzített beállítását. | [Attribútumok](dev-itpro/customer-attributes.md) | |
| Vevő részletes adatai lap | A részletes vevői adatokat tartalmazó lap minden csatornában részletesen beszerzi a vevők közötti kommunikáció részleteit. Az ilyen műveletek közé tartoznak a beszerzések, a kívánságlisták és a hűségpontok. | | |
| Felhőalapú vevőkeresés | Vevők keresése név, telefonszám, e-mail cím, hűségkártya, cím stb. szerint. | [Felhőalapú keresés](pos-search-improvements.md#customer-search) | |
| Hűség és jutalmak | Az ügyfelek hűségprogramokhoz csatlakozhatnak, és hűségpontokat szerezhetnek és válthatnak be a különböző csatornákon keresztül. | [Hűség](set-up-customer-loyalty-program.md) | [Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5c2wW) |
| Ügyfélkör | A kulcs vevők kezelése ügyfélkönyv használatával, és a vevőprofilban végzett tevékenységek és megjegyzések nyomon követése. Dynamics 365 Customer Insights integrációval az alkalmazottak a következő legjobb műveletre vonatkozó adatokat kapják meg az egyes vevők számára. | [Ügyfélkör](clienteling-overview.md#activities-and-notes) | [Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSP) |

## <a name="pricing-and-discounts"></a>Árképzés és engedmények

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Kereskedelmi megállapodások | Az árképzési vezetők a kereskedelmi megállapodások segítségével speciális árakat határozhatnak meg, amelyek meghatározott vevőknek szóló hosszú távú ügyleteken alapulnak. | [Árképzés](price-management.md)| [Videó](https://www.youtube.com/watch?v=r2VD8IxHesM) |
| Értékesítési szerződések | Az árképzési vezetők az értékesítési megállapodások segítségével szerződésen alapuló árakat határozhatnak meg a vállalat közötti (B2B) kereskedelmi helyzetekben. | [Árképzés](price-management.md) | |
| Ármódosítások | Az árképzési vezetők az árkorrekciók segítségével hozhatják létre, követhetik nyomon és kezelhetik a termékeik árkorrekcióit. | [Ármódosítások](price-adjustments-discounts.md) | |
| Engedmények | Az árvezetők többféle kedvezménytípust állíthatnak be különböző promóciók futtatásához. Ilyen engedmények lehetnek egyszerű engedmények, mennyiségi engedmények, küszöbérték-engedmények, kombinációs engedmények, fizetőeszköz-alapú engedmények és szállítási engedmények. | [Engedmények](retail-discounts-overview.md) | |
| Utalványok | Az árképzési vezetők utalványkódokat vagy vonalkódokat állíthatnak be, engedményekhez csatolják őket, és elosztják a vevőknek. Az értékesítési munkatársak utalványokat adhatnak hozzá az értékesítési tranzakciókhoz, illetve eltávolítják azokat. | [Utalványok](coupons.md) | |
| Árcsoportok | Az árvezetők az árcsoport segítségével definiálhat környezetfüggő árakat a csatornák, katalógusok, tagságok vagy hűségprogramok alapján. | [Árképzés](price-management.md) | |
| Elérhető promóciók | Az értékesítési munkatársak egyszerűen meg lehet keresni az üzletben elérhető termékek promócióit, a tranzakcióhoz hozzáadott termékeket stb. | [Árképzési funkciók](pos-pricing-functions.md) | |
| Árellenőrzések | Az értékesítési munkatársak gyorsan ellenőrizhetik az üzletben lévő termékek aktív eladási árát. | [Árképzési funkciók](pos-pricing-functions.md) | |
| Ár felülírásai | A szükséges engedélyekkel rendelkező értékesítési munkatársak felülbírálhatják a rendszer által konfigurált vagy számított árakat. | [Árképzési funkciók](pos-pricing-functions.md) | |
| Manuális engedmények | A szükséges engedélyekkel rendelkező értékesítési munkatársak manuális engedményeket alkalmazhatnak az értékesítési tranzakciókra vagy értékesítési sorokra. | [Árképzési funkciók](pos-pricing-functions.md) | |

## <a name="electronic-payments"></a>Elektronikus kifizetések

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Jóváírás és terhelés | A Store Commerce alkalmazás a nagyobb hitelkártyás és bankkártyás fizetéseket támogatja az Adyen fizetési átjárón és a PayPal rendszeren keresztüli rendelésteljesítésen keresztül. A Payments SDK szoftverfejlesztői készlet lehetővé teszi külső átjáró kapcsolatok létesítét, amelyet független szoftverszállítói (ISV) integrációk támogatnak. | <p>[Adyen](dev-itpro/adyen-connector.md?tabs=10-0-23)</p><p>[Paypal](paypal.md)</p><p>[Kifizetések](payment-methods.md)</p> | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-configuration-february-9-2021)</p><p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-overview-processing-february-4-2021)</p> |
| Digitális digitális támogatás | A Store Commerce alkalmazás digitális fizetési módokon keresztül támogatja a kifizetéseket, amelyek nem használják a bankazonosító szám (BIN) tartományokat, mint a hagyományos hitel- és bankkártyák. A kifizetési módok digitális kifizetésre (például Adyenre) leképezve is megfeleltetve. | [Pénztárca](wallets.md) | |
| Ajándékutalvány támogatása | Bankazonosító szám: Dynamics 365 ajándékutalvány, tárolt érték megoldások (IVS) és Givex ajándékutalványok. Az ajándékutalványok megrendelésben válthatók be és válthatók be. | [Ajándékutalványok](dev-itpro/gift-card.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/d365-commerce-internal-gift-cards-november-16-2021) |
| Csalás elleni védelem | Dynamics 365 Fraud Protection A <a0/<a0/<a2/aki segít a csalást akadályozó tevékenységek megakadályozásában, és azonosítani tudja azokat a helyeket, ahol a csalást nem lehet azonosítani. | [Csalás elleni védelem](dev-itpro/dfp.md) | [Videó](https://www.youtube.com/watch?v=j_1nEiq3LfM) |

## <a name="taxes-and-charges"></a>Adók és költségek

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Adók | A Store Commerce alkalmazás számos közvetett adótípust támogat, így az áfát, az áfakulcsot, az áruk és szolgáltatások adóját (GST), az egység alapú díjakat és az adóelőlegeket. | [Adók](/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json) | |
| Költségek | A költségek a sor szintjén, a fejléc szintjén konfigurálhatók automatikus költségekként, csatornák szerint stb. | [Költségek](omni-auto-charges.md) | |

## <a name="order-processing-and-fulfillment"></a>Rendelés feldolgozása és teljesítése

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Rendelés létrehozása | Rendelést lehet létrehozni a szállításhoz vagy egy közeli üzletben való felvételhez. A felvételhez időidők is rendelkezésre állnak. | [Áttekintés](customer-orders-overview.md) | |
| Rendelés módosítása | A rendelés módosítható, visszaadható, visszavonható stb. | <p>[Mégse](customer-orders-overview.md#cancel-a-customer-order)</p><p>[Visszáruk](pos-returns.md)</p> | |
| Keresése | Rendelések keresése és szűrése rendelésspecifikus információk alapján. | [Keresése](enhancedorderrecall.md) | |
| Rendelésattribútumok | A Rendelésattribútum keretrendszer lehetővé teszi további rendelésekkel kapcsolatos információknak az üzleti követelmények alapján való rögzített beállítását. | [Attribútumok](dev-itpro/order-attributes.md) | |
| Közvetlen kiszállítás | A cikkeket megjelölheti a szállító a vevő címére történő közvetlen kiszállításra. A közvetlen kiszállítás más néven közvetlen kiszállítás. | [Közvetlen kiszállítás](/dynamics365/supply-chain/sales-marketing/tasks/ship-orders-direct-deliveries) | |
| Árajánlat | Az üzlet alkalmazottai árajánlatokat hozhatnak létre a vevők számára, és megadhatnak egy speciális árat, manuális engedményeket és ajánlat-érvényességi dátumot. | [Árajánlat](/dynamics365/supply-chain/sales-marketing/tasks/create-edit-sales-quotations) | |
| Teljesítés | Az üzletek kitárolt, csomagolt és szállíthat rendeléseket. A szállításra kész csomagokhoz csomagjegyzéket lehet hozzáadni. | [Teljesítés](order-fulfillment-overview.md) | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-supporting-buy-online-pickup-in-store-curbside-with-dynamics-365-commerce-pos-february-3-2021)</p> <p>[Videó](https://www.microsoft.com/videoplayer/embed/RE5bRXE)</p>|
| Felosztott rendeléskezelés | A Store Commerce alkalmazás intelligens rendelésteljesítési optimalizálást támogat, ahol az üzleti stratégiák az üzlet jellege, a vevő típusa, a rendelés eredete és a rendelés szállítási módja alapján konfigurálhatók. | [DOM](dom.md) | [Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5bRYl)|

## <a name="inventory-management"></a>Készletgazdálkodás

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Központi elosztás | A rendelkezésre álló készlet elosztásának racionalizálása az elosztási központból több üzletbe vagy raktárba. | [Központi elosztás](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Áttárolás | A készlet felosztásának racionalizálása a bejövő beszerzési rendeléseken több üzletbe vagy raktárba. | [Áttárolás](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Bejövő készlet | Készlet fogadása a szállítótól beszerzési rendelésen keresztül vagy másik raktárból átrendelt rendelésen keresztül. Bejövő beszerzési rendelés vagy átátviteli rendelési kérelem létrehozása. | [Bejövő](pos-inbound-inventory-operation.md) | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p>  <p>[Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p>|
| Kimenő készlet | Készlet másik raktárba történő szállításának átrakodása rendelésen keresztül, és kimenő átátviteli rendelési kérelem létrehozása. | [Kimenő](pos-outbound-inventory-operation.md) | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p>  <p>[Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |
| Keresés a készletben | Az üzletekben és raktárakban található termékek aktuális készletének ellenőrzése, és az ígérethez rendelkezésre álló készlet jövőbeli dátumok ellenőrzése. | [Keresés a készletben](pos-inventory-lookup-operation.md) | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |
| Készlethelyesbítés | Módosítsa a készletet az üzlet raktárában, illetve a raktárból, hogy megfeleljen az adott üzleti követelményeknek értékesítés, bevételezés és újraszámlálás nélkül. | [Készlethelyesbítés](work-with-store-inventory.md) | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p>|
| Leltárok | A tényleges készlet leltározása és a rendszer könyvelési készletének beállítása, hogy megfeleljen neki. | [Leltár](work-with-store-inventory.md) | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)<p> |
| Készletmozgás | Készlet áthelyezése az üzlet helyei között. | [Mozgatás](work-with-store-inventory.md) | <p>[Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Videó](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |

## <a name="financials"></a>Pénzügyek

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Készpénzgazdálkodás | A Store Commerce alkalmazás támogatja az üzletben található készpénz és más meghatározott ajánlatok kezelését. A továbbfejlesztett készpénzkezelési funkciókhoz ezenkívül engedélyezhető az üzlet műszakegyeztetése is. | [Készpénz](cash-mgmt.md) | |
| Pénzügyi kimutatások és egyeztetés | Az áruházak készpénzes és tranzakciós tranzakcióit a kimutatásfeladási folyamatokkal rögzíti a Commerce Headquarters. | [Kimutatások](retail-statements.md) | |
| Bevételi és kiadási tranzakciók | A pénztári készpénztranzakciók feldolgozása az üzletben, és a nem hagyományos módon meg nem felelő bevételek, például az elvesztett és talált pénz, a kávézóból származó bevételből való részesedés és a tisztítási szolgáltatások nyilvántartása. | [Kimutatások](retail-statements.md) | |
| Számlakifizetések | Számlák ellenében történő kifizetések rögzítése | [Számla](payinvoice.md) | |

## <a name="employee-productivity"></a>Alkalmazott termelékenysége

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Feladatkezelés | Feladatlisták és feladatok létrehozása, és hozzárendelése az üzletekhez és az alkalmazottakhoz. A feladatok állapotának követése az üzletekben. Problémamentesen integrálható a Microsoft Teams szolgáltatásokkal. | <p>[Feladatkezelés](task-mgmt-overview.md)</p><p>[Microsoft Teams](commerce-teams-integration.md)</p> | [Videó](https://www.youtube.com/watch?v=ES1whB4C2lU) |

## <a name="hardware-and-peripherals"></a>Hardverek és perifériák

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Perifériák csatlakoztatása | A perifériás eszközök (nyomtatók, pénztárfiókok, beolvasók és fizetési eszközök) csatlakoztatása a POS-terminálhoz. | [Perifériák](retail-peripherals-overview.md) ||
| Share perifériák | A nyugtanyomtatók, pénztárfiókok és fizetési eszközök több terminál között is megoszthatók, ha megosztott hardverállomáshoz kapcsolják őket. | <p>[Hardverállomás](retail-peripherals-overview.md) ||
| POS és perifériás szimulátor | A perifériás szimulátor lehetővé teszi olyan helyzetek tesztelését, amelyekhez általában fizikai POS perifériás eszközökre van szükség. Emellett tartalmaz egy POS-szimulátort is, amely a fizikai perifériás eszközök kompatibilitásának tesztelésére használható, a POS-ügyfél telepítése nélkül. | [Szimulátor](dev-itpro/retail-peripheral-simulator.md) | |

## <a name="receipts"></a>Bevételezések

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Nyugták nyomtatása | A különféle típusú nyugták, például az értékesítési nyugták, a hitelkártyás nyugták, az ajándékutalványok és a számlák alapértelmezés szerint kinyomtathatók, vagy a pénztáros jóváhagyása után a fizetésnél. A naplóból újra is nyomtathatók. | [Nyomtatás](receipt-templates-printing.md) | |
| E-mail nyugták | A nyugtákat a pénztárból e-mailben lehet küldeni a kijelentkezés befejezése után. | [E-mail-cím](email-receipts.md) | |
| Bevételezések tervezése | Az üzletbevételezéseket testre lehet szabni, hogy a kiskereskedőnek és a tranzakciótípusnak megfelelő adatokat és elrendezéseket mutassanak. A nyugtákat ki is lehet terjeszteni úgy, hogy a kiskereskedő számára szükséges egyéni adatokat mutassanak. | [Tervezés](receipt-templates-printing.md) | |

## <a name="offline-support"></a>Offline támogatás

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Zökkenőmentes offline | A problémamentes offline módban akkor is folytathatja a tranzakciót, ha az internetkapcsolat korlátozott vagy nem áll rendelkezésre. Az adat kizárásával csökkentheti az offline adatbázisok adatméretét, és maximális teljesítményt nyújt. | [Nem elérhető](pos-operations.md) | |
| Teljesítmény alapú váltás | Váltás offline módra, ha teljesítménycsökkenés észlelhető. | [Nem elérhető](dev-itpro/implementation-considerations-offline.md) | [Videó](https://youtu.be/sQU-2pgHToI) |
| Offline irányítópult | Az **Offline állapot** vezérlőpulton látható az egyes eszközök offline állapota, hibái és adatai. Emiatt könnyen kezelhető számos eszköz állapota. | [Nem elérhető](dev-itpro/implementation-considerations-offline.md) | [Videó](https://youtu.be/sQU-2pgHToI)|

## <a name="extensibility"></a>Bővíthetőség

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Commerce headquarters | A Commerce Headquarters megoldásai az üzleti folyamatok hozzáadásával és módosításával szabhatók testre. A Commerce Headquarters metaadatok és kódvezérelt bővítménymodellek használatát támogatja az egyéni funkciók hozzáadásához. A külső megoldásokba egyszerűen integrálható. | [Áttekintés](dev-itpro/extend-customer-cdx-package.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-unlock-the-power-of-dynamics-365-commerce-commerce-extensibility-overview-february-23-2021) |
| Fej nélküli kereskedelem | A extensible Can-channel API keretrendszer az üzleti logika testreszabásához és hozzáadásához használható. Olyan API-k, amelyekhez kérelemkezelők, valamint előzetes és utáni eseményindító kiterjesztési mintázatok is vannak. | [CSU](dev-itpro/retail-server-customer-consumer-api.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Commerce SDK | A Commerce SDK szoftverfejlesztői készlet tartalmazza a funkciók kiterjesztéséhez vagy testreszabásához szükséges kódot, kódmintákat, Dynamics 365 Commerce sablonokat és eszközöket. Az SDK a bővítmény-összetevőktől függően különböző tárárakban (tárárakban) történik. | [SDK](dev-itpro/retail-sdk/sdk-github.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Pénztár | A Store Commerce alkalmazás a Commerce SDK POS-bővítményének funkcióját használva önállóan is kiterjeszthető. A keretrendszer támogatja a felhasználói felület, a munkafolyamatok és az üzleti logika testreszabását. | [POS](dev-itpro/pos-extension/pos-extension-overview.md) | [Tech tech tech (tech, tech)](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |

## <a name="reporting"></a>Jelentéskészítés

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Értékesítési jelentések | Az értékesítési jelentések munkatárs, pénztárgép, fizetéstípus, visszaküldés, termék stb. szerint az üzletvezetők számára érhetők el. A vezetők megtekinthetik ezeket a jelentéseket, és felhasználhatja őket a jutalékok felosztására és a termék trendjeinek azonosítására. | | |

## <a name="diagnostics"></a>Diagnosztika

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Üzemeltetési információk | Az üzletben minősített szolgáltatás állapotának megbízhatósága és a teljesítménymetrikák elérhetők a vevő előfizetésében Application Insights . Speciális riasztási és figyelési funkciók érhetők el. | | |
| Állapot-ellenőrzés | A POS-hoz csatlakoztatott perifériák elérhetősége az állapotellenőrzési művelet futtatásával ellenőrizhető. Ezután javítani és ellenőrizni lehet az egyes perifériás problémákat. | [Állapot-ellenőrzés](pos-healthcheck.md) | [Videó](https://www.youtube.com/watch?v=RfPDNmnqYvY) |

## <a name="globalization"></a>Globalizáció

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Többpiacos támogatás | A mezőn túl a piacspecifikus funkciók, például a pénzügyi integráció, a GST, a speciális számlázás és az előlegek is támogatottak. Ez a képesség számos európai piacra, Amerikai Egyesült Államokra, Oroszországra, Ázsiare, Szaúd-Arábia stb. | [Globalizáció](localizations/fiscal-integration-for-retail-channel.md) | |

## <a name="compliance"></a>Megfelelés

| Képesség | Leírás | Dokumentáció | Kiegészítő tartalom |
|---|---|---|---|
| Microsoft-szabványok | A Store Commerce alkalmazás megfelel a Microsoft biztonsági, adatvédelmi, kisegítő lehetőségekkel kapcsolatos szabványait, az általános adatvédelmi szabályozást (GDR), az Európai Unió (EU) adathatárát stb. | | |

