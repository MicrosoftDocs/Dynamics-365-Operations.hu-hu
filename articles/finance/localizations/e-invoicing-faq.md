---
title: Elektronikus számlázás GYIK
description: Ez a témakör az elektronikus számlázással kapcsolatos gyakori kérdéseket tartalmazza.
author: gionoder
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 2d4e7c79c83b9d60469c2b87a7b9120e0d4c13a695badfb2254a85cee629c933
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770512"
---
# <a name="electronic-invoicing-faq"></a>Elektronikus számlázás – GYIK

[!include [banner](../includes/banner.md)]

Ez a témakör az elektronikus számlázási szolgáltatással kapcsolatos gyakori kérdésekre adott válaszokat tartalmazza. Az elektronikus számlázás kibővíti a Dynamics 365 Finance, Dynamics 365 Supply Chain Management és Dynamics 365 Project Operations meglévő elektronikus számlázási képességeit. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>Mi fontos az elektronikus számlázással kapcsolatban, és miért fontos ez az én szervezetemnek?

A működési összetettség és a kockázat egyre erősebb mivel a szervezetek globálisan növekednek, és bővítik a jelenlétüket több régióban. A megfelelés fenntartása és a gyakran változó szabályozáshoz való igazodás egyre nagyobb kihívást jelent, és különösen fontos a számlázásnál. A számlázás hagyományosan drága, és gyakran hibák forrása, mivel a vállalatok papírdokumentumokra és munkaintenzív folyamatokra támaszkodnak.  

A szervezetek megkezdték a papíralapú számlákról való átállást, hogy csökkentsék a költségeket, és fel kell gyorsítsak a végpontok számának feldolgozását, és felgyorsítsák a teljes folyamatot. Az adózás digitalizációjának a egyik fő összetevője az elektronikus számlázás lesz a kormányok részéről. Azáltal, hogy a szervezeteknek digitálisan be kell nyújtaniuk a valós idejű adóinformációkat az adóhatóságok számára, a kormányok minimálisra csökkenthetik az adóelkerülést és -manipulációt és visszaszoríthatják a csalásokat. 

A világ a papírmentes dokumentumfeldolgozásra vált, és az elektronikus számlázás bevezetése nélkül a vevők a megfelelési problémákkal, a szükségtelen költségekkel és a versenytársaktól való lemaradással néznek szembe. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>A Finance, a Supply Chain Management és a Project Operations nem tartalmaz már elektronikus számlázási funkciókat? Milyen értéket ad ez nekem, mint ügyfélnek? 

Az elektronikus számlázás kiterjeszti a Finance, a Supply Chain Management és a Project Operations modulokban meglévő elektronikus számlázási lehetőségeket. Ez a funkció egyszerűbbé teszi a legújabb elektronikus számlázási szabályok betartását, és az elektronikus számlafeldolgozás és -adatcsere során egységes élményt nyújt a különböző földrajzi helyeken. Az elektronikus számlázási képességek számos előnyt nyújtanak, többek között: 

   - Ország-/régióspecifikus követelmények gyorsabb és egyszerűbb elfogadása.
   - Az e-számlázási megoldás implementációk standardizációja. 
   - Továbbfejlesztett elektronikus számlafeldolgozás nyomon követhetőség.  
   - Egyszerűbb karbantartás és megfelelés a változó jogi követelmények és a helyi üzleti gyakorlatoknak. 
   - Egyszerűsített megoldáscsomagolás.
   - Nagy mennyiségű benyújtott dokumentum skálázásának képessége, ami gyorsabb átfutást tesz lehetővé.
   - A megoldások megoszthatóak más vállalatokkal.

## <a name="does-electronic-invoicing-service-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>Az elektronikus számlázási szolgáltatás támogatja a helyszíni számlázást a Finance, a Supply Chain Management és a Project Operations modulokban? 

Az aktuális platform nem tesz lehetővé a helyszíni verzió használatát, és a jövőben sem tervezzük ennek támogatását.

## <a name="does-electronic-invoicing-service-interface-with-the-vendor-import-automation-feature"></a>Az Elektronikus számlázási szolgáltatás együttműködik a szállítói importálás automatizálás funkcióval?

Nem. Erre a felületre tervek vannak, de ennek nincs időterve. Ha meg van tervezve, a dátumok a [Kiadási tervekben](/dynamics365/release-plans/) lesznek bejelentve.

## <a name="how-does-electronic-invoicing-service-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>Hogyan kezeli az Elektronikus számlázási szolgáltatás az elektronikus számlához csatolt fájlmellékleteket? Szükség van SharePoint-kiszolgálóra a PDF-fájlok XML-fájlba történő beágyazásához?

Az elektronikus számlához csatolt fájlok egy xml-elembe beágyazott bináris adatként vannak kezelve. A PDF-fájlok beágyazásához nem szükséges SharePoint-kiszolgáló, de a mellékletet a Finance, a Supply Chain Management és a Project Operations dokumentumkezelő rendszerben kell tárolni.

## <a name="is-electronic-invoicing-service-available-according-to-the-regulations-of-my-countryregion"></a>Az elektronikus számlázási szolgáltatás a saját országom/régióm szabályozásának megfelelően érhető el?

Az elektronikus számlázási szolgáltatás olyan mikroszolgáltatási platform, amely globálisan elérhető lesz.

A Microsoft azt tervezi, hogy közzéteszi az elektronikus számlaformátumokat és integrációkat a Microsoft által funkcionálisan honosított országokhoz. További információt az [Elektronikus számlázási szolgáltatások elérhetősége](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features) rész tartalmaz.

Ha az ön országának/régiójának elektronikus számlázási formátuma nem szerepel a listán, a platform célja, hogy a jövőben támogassa ezt a forgatókönyvet. Továbbra is élvezheti az elektronikus számlázás konfigurációs lehetőségeit, és saját maga konfigurálhatja az elektronikus számlázási formátumot, vagy dolgozhat egy partnerrel/ISV-vel, hogy a szervezete számára konfigurálják.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>A Dynamics 365 for Regulatory Services egy olyan új modul, mint a Human Resources vagy a Project Operations, amely a Finance vagy a Supply Chain Management modulhoz van társítva? Vannak ennek extra költsége?

A Dynamics 365 for Regulatory Services (RCS) egy felhőszolgáltatás a globalizációs erőforrások konfigurálására. Az RCS minden Finaince, Supply Chain Management és Project Operations licenctulajdonos számára ingyenes.

Az RCS-regisztrációhoz látogasson el a <https://marketing.configure.global.dynamics.com/> oldalra.

További információért lásd a [Kapcsolódás a Regulatory Configuration Services (RCS) szolgáltatáshoz – Globalizációs funkciók](rcs-globalization-feature.md) részt.

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing-service-or-just-turn-it-on-in-feature-management"></a>Regisztrálnom kell az elektronikus számlázási szolgáltatáshoz, vagy csak be kell kapcsolnom a Szolgáltatáskezelésben?

Ha Finance, Supply Chain Management és Project Operations licenccel rendelkezik, tekintse meg az [Első lépések az Elektronikus számlázás bővítményszolgáltatás adminisztrációjával](e-invoicing-get-started-service-administration.md) részt a feliratkozáshoz az elektronikus számlázásra.

## <a name="does-electronic-invoicing-service-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>Működik az elektronikus számlázási szolgáltatás az 1. szintű virtuális gépekkel? Mi a minimálisan szükséges környezet?

Az elektronikus számlázási szolgáltatással való integrációhoz legalább egy 2. szintű virtuális gépre van szükség a Finance vagy Supply Chain Management hosztolásához. A környezet tervezésével kapcsolatos további tudnivalókat lásd: [Környezet tervezése](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-service-have-a-test-mode-for-testing-invoice-submission"></a>Rendelkezik-e az elektronikus számlázási szolgáltatás tesztmóddal a számlabenyújtás tesztelésére?

Ez konfigurációval érhető el. A számlaküldés teszteléséhez felhasználói elfogadási teszt (UAT) környezetből kapcsolódhat a Finance vagy a Supply Chain Management alkalmazáshoz, és küldhet be tesztszámlákat. Az elektronikus számlázás támogatja a teszt digitális tanúsítványok konfigurálást, és a digitális jóváhagyást igénylő e-számlák esetében az adóhatóság által közzétett teszt webszolgáltatások URL-jét.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Van-e dokumentáció a gyári országspecifikus elektronikus számlázási funkciókról?

Igen. Az elektronikus számlázási funkciók elérhetőségéről és a támogatott formátumokról lásd [Elektronikus számlázási szolgáltatások elérhetősége](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

## <a name="does-the-electronic-invoicing-service-allow-a-legal-entity-in-finance-or-supply-chain-management-that-is-configured-for-a-specific-country-to-consume-electronic-invoicing-features-from-different-countryregions"></a>Engedélyez az elektronikus számlázási szolgáltatás egy olyan jogi személyt a Finance vagy Supply Chain Management modulban, aki egy adott országhoz van konfigurálva, hogy különböző országokból/régiókból származó elektronikus számlázási funkciókat használjon?

Igen. Az elektronikus számlázási funkciók az üzleti dokumentumok benyújtásának feldolgozásához is igénybe vehetőek – a jogi személy országától függetlenül –, amennyiben a következő igaz:

   - A létrehozott üzleti dokumentum a megfelelő dokumentummodell-leképezést használja.
   - Az üzleti dokumentum és az elektronikus számlázási funkcióban beállított alkalmazhatósági szabályoknál egyezés van.

## <a name="does-the-electronic-invoicing-service-use-the-same-configuration-and-design-experience-provided-by-the-electronic-reporting-module-in-finance-and-supply-chain-management"></a>Az elektronikus számlázási szolgáltatás ugyanazt a konfigurációt és tervezési élményt használja, amelyet a Finance és Supply Chain Management elektronikus jelentési modulja biztosít? 

Igen. A Finance és Supply Chain Management modul elektronikus jelentéskészítés (ER) moduljában használt tervezőeszközök az adatmodell-leképezések és fájlformátum-konfigurációk létrehozására és konfigurálására használhatók. Ezek a tervezői eszközök a Regulatory Configuration Services (RCS) modulban is használhatók az e-számlázási funkciók konfigurációjában használt adatmodell-leképezések, és fájlformátum-konfigurációk létrehozására és konfigurálására.

## <a name="can-the-applicability-rules-be-extended-and-configured-so-that-they-arent-tied-to-any-specific-parameter-such-as-a-legal-entity"></a>Kiterjeszthetőek és konfigurálhatók az alkalmazhatósági szabályok annak érdekében, hogy ne kötődjenek konkrét paraméterekhez, például jogi személyhez?

Igen. Az alkalmazhatósági szabályok teljesen konfigurálhatók. Hozzáadhat és eltávolíthat záradékokat, build logikai műveleteket, valamint csoportosítási és csoportbontási záradékokat. További információ: [Alkalmazhatósági szabályok](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#applicability-rules).

## <a name="does-the-electronic-invoicing-service-support-adding-other-er-format-configurations-to-generate-other-types-of-documents-does-it-support-sending-the-documents-electronically-to-customers-such-as-a-delivery-note"></a>Az elektronikus számlázási szolgáltatás támogatja más ER-formátumkonfigurációk hozzáadását más típusú dokumentumok létrehozása során? Támogatja a dokumentumok, például a szállítólevél vevőknek történő elektronikus küldését?

Más ER formátumkonfigurációk segítségével előállíthatja a kívánt kimeneti fájlokat. Az ER-formátum konfigurációjának azonban ugyanabból az ER-számlamodell-leképezésből kell származnia, mint ami a Finance vagy Supply Chain Management szolgáltatásban be van állítva az üzleti dokumentumok létrehozása érdekében. A kimeneti fájl közvetlenül a vevőnek, EDI-tranzakcióként való küldése nem támogatott az elektronikus számlázás azonnal használható művelete esetén.

## <a name="does-the-electronic-invoicing-service-support-exchanging-electronic-invoices-with-customers-does-it-support-configuring-different-invoice-formats-for-the-same-invoice"></a>Az elektronikus számlázási szolgáltatás támogatja a vevőkkel történő elektronikus számlacseréket? Támogatja ugyanannak a számlának a különböző számlaformátumba való konfigurálását?

A szállítói elektronikus számlák fogadása és importálása folyamatban van, de jelenleg nem támogatott az elektronikus számlák automatikus elküldése a vevőknek.

## <a name="does-the-electronic-invoicing-service-extend-to-support-exchanging-edi-messages-with-other-companies"></a>Az elektronikus számlázási szolgáltatás támogatja a más vállalatokkal történő EDI-üzenetek váltását?

Az elektronikus számlázási szolgáltatás első sorban azon elektronikus számlaüzenetek típusainak cseréjére összpontosít, amelyeket a jogszabályoknak való megfelelési követelmények vezérelnek. A szállítói elektronikus számlák fogadása és importálása szerepel az ütemtervben, de az elektronikus számlafájlok vevőknek történő küldése jelenleg nem érhetőek el azonnal, kivéve, ha az elektronikus számla vevőnek történő küldése jogszabályi előírás.

## <a name="does-the-electronic-invoicing-service-support-importing-or-merging-customizations-made-in-the-er-format-configurations-from-the-legacy-electronic-invoicing-feature"></a>Az elektronikus számlázási szolgáltatás támogatja az örökölt elektronikus számlázás funkcióból az ER-formátum-konfigurációkban készített testreszabások importálását vagy egyesítéset?

Az ER-formátum-konfigurációk újrafelhasználhatók az elektronikus számlázási szolgáltatásban. Az ER-formátum konfigurációjának azonban ugyanabból az ER-számlamodell-leképezésből kell származnia, mint amit az elektronikus számlázási funkcióval való használatra terveztek, és ami a Finance vagy Supply Chain Management szolgáltatásban be van állítva az üzleti dokumentumok létrehozása érdekében.

## <a name="does-the-electronic-invoicing-service-support-issuing-electronic-invoices-from-custom-made-tables-if-so-how-do-you-create-the-er-data-model-configurations-for-these-new-tables-and-entities"></a>Az elektronikus számlázási szolgáltatás támogatja az egyedi táblákból történő elektronikus számlakiállításokat? Ha igen, hogyan hozza létre az ER adatmodell-konfigurációkat ezekhez az új táblákhoz és entitásokhoz?

Igen. Ehhez azonban szükség van a számlamodell leképezésére és a szükséges hivatkozások egyéni táblákhoz való hozzáadására, illetve a bonyolultságtól függően az új számlamodell-leképezés létrehozására.

## <a name="does-the-electronic-invoicing-service-support-different-web-service-endpoints"></a>Az elektronikus számlázási szolgáltatás támogatja a különböző webszolgáltatás-végpontokat?

Az elektronikus számlázás támogatja a különböző webszolgáltatások végpontjait. Konfigurálható integrációt használhat a REST webszolgáltatásokkal vagy számos paraméterezett országspecifikus webszolgáltatás-integrációkkal is. Ugyanazokhoz a webszolgáltatásokhoz és API-khoz különböző végpontokat lehet konfigurálni a különböző konfigurációverziók használatával. További információért lásd: [Műveletenkénti paraméterek listája](e-invoicing-setup.md#list-of-parameters-by-action).

## <a name="is-electronic-invoicing-integrated-with-the-various-invoice-operators-apis-from-the-nordic-countries-or-should-that-be-handled-on-a-case-by-case-basis"></a>Az Elektronikus számlázás modul integrálva van a különféle számlaműveletek API-aival az északi országban, vagy csak eseti alapon kell kezelni?

A Microsoft az elektronikus számlázási funkciók segítségével folyamatosan kiterjeszti a funkcionális fedezetet az azonnal elérhető integrációk biztosításához. A támogatott formátumokkal és integrációkkal kapcsolatos további tudnivalókat lásd: [Az elektronikus számlázási funkciók elérhetősége](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Ha nem találta meg a keresett választ, küldje el kérdését a termékfejlesztési csapatnak a következő címre: <D365EInvoicePreview@microsoft.com>. Vagy felvesszük Önnel a kapcsolatot, vagy javítjuk a GYIK lefedettségét.
