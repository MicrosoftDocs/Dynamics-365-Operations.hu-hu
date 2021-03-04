---
title: Nyomtatható FTI-űrlapok generálása
description: Ez a témakör bemutatja a Microsoft Office dokumentumként nyomtatható szabadszöveges számla (FTI)-űrlapok generálását az Elektronikus jelentéskészítés (ER) keretrendszer segítségével.
author: NickSelin
manager: AnnBe
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 168cef1b5f5d48cb739b08fa395c1bcd62089494
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686729"
---
# <a name="generate-printable-fti-forms"></a>Nyomtatható FTI-űrlapok generálása

[!include[banner](../includes/banner.md)]

Microsoft Office dokumentumként nyomtatható szabadszöveges számla (FTI)-űrlapok generálása az Elektronikus jelentéskészítés (ER) keretrendszer segítségével. Ez a témakör a saját a konfigurációk felépítésével, valamint a rendelkezésre álló konfigurációs sablonok részleteivel kapcsolatosan nyújt tájékoztatást.

## <a name="overview"></a>Áttekintés

A nyomtatható FTI űrlapok generálása a Microsoft SQL Server Reporting Services (SSRS) segítségével képességen túl immár használhatja az ER-keretrendszert is A nyomtatható FTI-űrlapokat Microsoft Office Excel és Word programban is kezelheti. Módosíthatja az elrendezést, az adatáramlást és a formázást, hogy megfeleljenek az igényekhez, a kód módosítása nélkül.

> [!NOTE]
> Ha egy meglévő ER konfiguráció áttekintésével szeretné megkezdeni, a nyomtatható FTI-űrlapok megoldást nyissa meg közvetlenül az **ER konfigurációk letöltése nyomtatható FTI űrlapok generálásához** szakaszt a témakör későbbi részében.

## <a name="create-customized-configurations-for-fti-printable-forms"></a>Egyéni konfigurációk létrehozása a nyomtatható FTI-űrlapokhoz
A nyomtatható FTI-űrlapokhoz tartozó testreszabott megoldás részeként létre kell hoznia egy ER konfigurációkészletet.

### <a name="configure-the-er-data-model"></a>Az ER-adatmodell konfigurálása
Az alkalmazásnek tartalmaznia kell egy ER adatokmodell-konfigurációt, mely tartalmaz egy adatmodellt, amely leírja a vevő számlázási üzleti területét. Követelmény, hogy az adatmodell neve **CustomersInvoicing** legyen. Az ER adatmodellekkel tervezésével kapcsolatos további tudnivalókat lásd: [ER – Tartomány-specifikus adatmodell tervezése](tasks/er-design-domain-specific-data-model-2016-11.md).

### <a name="configure-the-er-model-mapping"></a>Az ER modell-leképezés konfigurálása
Az alkalmazásnak tartalmaznia kell az ER modell-leképezést a CustomersInvoicing adatmodellhez. A modell-leképezés lehet egy ER adatmodell-konfigurációjának vagy egy ER modell-leképezés konfiguráció. Azomban a modell-leképezés a gyökérszíntű leírójának neve **FreeTextInvoice** kell legyen.

A leképezésnek tartalmaznia kell a következő adatforrásokat:

- Adatforrás típusa: **Tábla rekordjai**

    - Az adatforrás kötelező elnevezése **CustInvoiceJour**.
    - A CustInvoiceJour alkalmazás táblára kell mutatnia.
    - Arra szolgál, hogy futási időben átadja a nyomtatásra kiválasztott számlák listáját az alkalmazásból az ER modell-leképezéshez

- Adatforrástípus: **Objektum**

    - Az adatforrás kötelező elnevezése **PrintMgmtPrintSettingDetail**.
    - A **PrintMgmtPrintSettingDetail** alkalmazásosztályra kell mutatnia.
    - Futási időben szolgál, hogy átadja a nyomtatókezelő beállítások alkalmazás – ER modell-leképezés részleteit a futó ER-formátumnak

Az alkalmazás a ER keretrendszerrel történő integrációja részleteit megtalálhatók az **ERPrintMgmtReportFormatSubscriber** osztályban (ER alkalmazáscsomag integrációs modell), az alkalmazás a forráskódjában.

Az ER modell-leképezések felépítésével kapcsolatos további tudnivalókat lásd: [ER modell-leképezések definiálása és adatforrások kiválasztása hozzájuk](tasks/er-define-model-mapping-select-data-sources-2016-11.md).

### <a name="configure-the-er-format"></a>ER-fromátum konfigurálása
Az alkalmazáspéldányának rendelkeznie kell ER-formátumkonfigurációval, melyek az FTI-űrlapok generálásához lesznek használva. 

> [!NOTE]
> Erre a formátumkonfigurációt létre kell hozni a CustomersInvoicing adatmodellhez, és azt modell-leképezést kell használnia, melynek gyökérleírója **FreeTextInvoice**.

Az ER-formátumok beállításával kapcsolatos további tudnivalókat lásd: [ER – Formátumkonfiguráció létrehozása (2016. november)](tasks/er-format-configuration-2016-11.md). Az ER formátumok tervezésével kapcsolatos további információkért, hogy azok OpenXML-formátumú jelentéseket generáljanak lásd: [ER – Konfiguráció tervezése jelentések létrehozásához OPENXML formátumban (2016. november)](tasks/er-design-reports-openxml-2016-11.md).

## <a name="configure-print-management"></a>A nyomtatókezelés konfigurálása
Az FTI-űrlapok létrehozásához ER keretrendszer használatával ugyanúgy rendelheti hozzá az ER-formátumokat, ahogy az SSRS-jelentések jelentéseket. Az ER-formátum társításához az összes Kinnlevőségek FTI-hez, válassza **Kinnlévőségek** \> **Beállítás** \> **Képernyők** \> **Képernyő beállítása** \> **Általános** \> **Nyomtatás kezelése** \> **Szabadszöveges számla** \> **Eredeti** lehetőséget. ER-formátum társításához egy adott vevőhöz vagy számlához kövesse az alábbi lépéseket.

1. Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.
2. Válassza ki az FTI-t, melyet társít az ER-formátummal, és nyissa meg a **Nyomtatáskezelési beállítások** oldalt.
3. A Számlák feldolgozási körének meghatározásához válasszon dokumentumszintet.
4. Válassza ki az ER formátumot a megadott dokumentumszinthez.

![Nyomtatáskezelési beállítások](media/FTIbyGER-PMSetting.png)

> [!NOTE]
> Az ER formátumok, melyek a **FreeTextInvoice** gyökérszintű leíróját használják a **CustomersInvoicing** adatmodellnek megjelennek a **Jelentésformátum keresése** mezőt a kijelölt formátumhoz.

## <a name="generate-fti-forms"></a>FTI-űrlapok létrehozása
Az FTI-űrlapok az ER keretrendszerben lesznek generálva ugyanúgy, mint az SSRS-jelentések.

FTI-űrlapok létrehozására választhat számlákat tartomány alapján vagy kiválasztással. 

![Számlakiválasztás](media/FTIbyGER-InvoiceSelection.png)

![Számlaelőnézet](media/FTIbyGER-InvoiceExcelPreview.png)

Ha ilyen módon nyomtat FTI-űrlapokat ER formátumok használatával, az alapértelmezett ER fájlcélok használatosak. A cél nem módosítható. Az ER-formátumokhoz tartozó ER-célok beállításával kapcsolatos további tudnivalókat lásd: [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md).

Generálhat FTI-űrlapokat akkor is, ha FTI-t tesz közzé a **Számla nyomtatása** bekapcsolásával, és a **Nyomtatáskezelés céljának használata** kikapcsolásával.

> [!NOTE]
> Ha ilyen módon nyomtat FTI-űrlapokat ER formátumok használatával, az alapértelmezett ER fájlcélok használatosak. Ha a cél már konfigurálva van az alapértelmezett cél futásidőben módosítható. Ha módosítani szeretné a célt, a következő biztonsági jogosultsággal kell rendelkeznie:
>
> - **Név:** ERFormatDestinationRuntimeMaintain
> - **Címke:** Elektronikus jelentéskészítési formátum céljának karbantartása futásidőben

![Elektronikus jelentéskészítés célja](media/FTIbyGER-ERFileDestinationSetting.png)

![Elektronikus jelentéskészítési formátum célja](media/FTIbyGER-ERFileDestinationUsage.png)

Az ER keretrendszer jelenleg támogatja a következő helyeket a létrehozott dokumentumokhoz:

- **Letöltött fájl** – A generált űrlapok letöltésekként vannak felajánlva, hogy a böngésző segítségével menthesse azokat.
- **Képernyő** – A Microsoft 365 Excel szolgál a létrehozott FTI-űrlapok megtekintésére Excel formátumban.
- **SharePoint-mappa** – A generált űrlapokat a Dokumentumkezelő keretrendszer beállításai alapján tárolja .
- **Alkalmazásarchívum** –A generált űrlapokvégrehajtási naplóbejegyzések mellékleteként vannak tárolva a Microsoft Azure Storage szolgáltatásban.
- **E-mail**– A generált űrlapok e-mail-mellékleteként lesznek küldve.

> [!NOTE]
> A FTI űrlapokat amelyek közvetlenül vannak generálva nem küldheti közvetlenül a nyomtatóra , mert a Dynamics nyomtatóirányítási ügynököt használó közvetlen nyomtatás jelenleg nem támogatott.

## <a name="download-sample-er-configurations-to-generate-printable-fti-forms"></a>Töltse le a minta ER konfigurációk nyomtatható FTI űrlapok generálásához
Minta ER konfigurációkat tölthet le, melyeket sablonként használhat FTI megoldásában. A konfigurációk a Microsoft Dynamics Lifecycle Services (LCS) Megosztott eszközök könyvtárában vannak tárolva. A konfigurációk tartalma:

- A **Vevői számlázási modell** konfigurációja tartalmazza a szükséges adatmodellt és a modell-leképezést.
- A **Vevői FTI jelentés** (GER) konfigurációja tartalmazza a mintaformátumot.

> [!NOTE]
> Ezek a konfigurációk minták, amelyek elősegíti a különböző esetek tisztázását. Ilyen konfigurációk jövője az értékelés eredményétől és a kapott visszajelzésektől függ.

### <a name="features-that-are-implemented-in-the-sample-er-format"></a>Minta ER formátumban megvalósított funkciók
Minta ER formátum konfigurációjában egy Excel-fájl használatos sablonként az FTI űrlapok létrehozásához.

![Formátumtervező](media/FTIbyGER-ERFormat.png)

Ez minta ER formátum jelenleg FTI űrlapok létrehozásához a következő funkciókat támogatja:

- FTI-űrlapok a feladott eredeti számlákhoz és a még fel nem adott eredeti számlákhoz jönnek létre. A javított számlák és jóváírások nem támogatottak.
- FTI űrlapok a számla nyelvén jönnek létre. Az értékek és dátumok formátuma a generált képernyőkön az ügyfél területi beállításain alapul.
- A létrehozott számlák adatok elérhetetlenségével kapcsolatos értesítést, ha nincsenek sorok a feldolgozott számlákon.
- Létrehozott számlafejlécek azon a papírformátumon alapulnak, amely az FTI űrlaphoz ki van választva a **Kinnlevőségek paraméterei** oldalon. Vállalat adatai csak akkor jelennek meg a létrehozott számlaképernyő fejlécében, ha a papírformátum üres.
- A létrehozott számlaképernyőkön megjelennek a vállalati és a vevői adómentességi számok, ha a megfelelő beállítás ki lett választva az FTI űrlap **Kinnlevőségek paraméterek** oldalán.
- A létrehozott számlasorok és számlaösszegek szakaszok a számla alapértelmezett pénzügyi részleteit mutatják a számla regisztrációs pénznemében.
- A létrehozott számla összegeinek szakasz megjelenítheti a pénzügyi részleteket euró pénznemben és a számla regisztrációs pénznemben ha az **Összeg nyomtatása az eurót képviselő pénznemben** beállítás engedélyezve van a **Kinnlevőségek paraméterei** oldalon.
- A létrehozott számlaképernyők megjelenítenek minden elérhető számlamegjegyzést a **Kinnlevőségek paraméterei** oldal beállításai alapján. A megjegyzések megjelennek a teljes számlához és az egyes számlasorokhoz is.
- Létrehozott számlaképernyők tartalmaznak megjegyzéseket a vevői FTI űrlapokhoz ás a feldolgozási számlanyelvhez ha konfigurálva lettek az AR képernyőjegyzetek listában.
- A Nyomtatókezelési beállításoktól függően, a létrehozott számlák egyéni láblécszöveget tartalmaznak, ha az konfigurálva lett a számlanyelvhez, az ER-formátumhoz és a FTI dokumentumhatókörhöz.
- A létrehozott számlaképernyők összegek szakasza tartalmaz minden elérhető készpénzfizetési engedéllyel kapcsolatos információt.
- A létrehozott számlaképernyők fizetési ütemezés szakasza minden rendelkezésre álló fizetés ütemezi részletet tartalmaz.
- A létrehozott számlaképernyők haszonkulcs szakasza tartalmazza az összes rendelkezésre álló költségtranzakciót.
- A létrehozott számlaképernyők tartalmazzák az áfa adatait az **Áfa meghatározása** beállítás szerint a **Kinnlevőségek paraméterei** lapon. Ebben a szakaszban az adó részleteinek megjelenítése lehetséges csak a számla pénznemében vagy számla regisztrációs pénznemében és a vállalat könyvelési pénznemében egyszerre.
- A létrehozott számlaképernyők megjelenítik a terhelési értesítések részleteit. Ha például megjelenítik, amennyiben a fizetés módjához tartozik kötelező beszedési megbízási felhatalmazás azonosítás, mely ki volt választva a számlához, ha a feldolgozási számla euró pénznemben volt regisztrálva és a számlához meg van adva a beszedési megbízási felhatalmazás azonosítója.
- Az előállított számlák megjelenítenek minden részletes előlegadatot a feladott számlákhoz.
- Létrehozott számlaképernyőket e-mail mellékleteként lehet elküldeni egy számlaügyfélnek. A megfelelő ER fájlcélt a használt ER formátumhoz kell beállítani.

### <a name="countryregion-specific-features"></a>Ország-/régiófüggő jellemzők 
A következő ország-/ területspecifikus funkciók érhetők el a minta ER-formátumban, hogy megmutassák, hogyan lehet kezelni a specifikus követelményeket az ER-konfigurációkban.

#### <a name="norway"></a>Norvégia
A Vállalati nyilvántartás feltétel megjelenik a létrehozott számlaképernyő fejlécében ha a számla egy jogi személyhez van feldolgozva a következő módon:

- Az ország/régió összefüggés Norvégiához használatban van.
- A **Foretaksregisteret nyomtatása** paraméter aktív az értékesítési bizonylatokban.

#### <a name="spain"></a>Spanyolország
A **Különleges rendszer készpénzkönyvelési módszerhez** feltétel megjelenik a létrehozott számlaképernyő fejlécében ha a számla egy jogi személyhez van feldolgozva a következő módon:

- Az ország/régió összefüggés Spanyolországhoz használatban van.
- A Különleges rendszer készpénzkönyvelési módszermez engedélyezve van a számla feldolgozási dátumánál

Ha a Készpénzfizetési engedmény részletei, például a készpénzfizetési engedmény összege és a számlasor nettó összege elérhetők, ha azok megjelennek a létrehozott számlaképernyő számlaösszeg részében, amikor egy jogi személyhez lett feldolgozva, aki a következő módon van beállítva:

- Az ország/régió összefüggés Spanyolországhoz használatban van.
- A **Számlán alkalmazott készpénzfizetési engedmény** van kapcsolva a számlabeállításnál (**Főkönyvi paraméterek** \> **Áfa** szakasz).

#### <a name="italy"></a>Olaszország
Az áruengedmény jelet tartalmazzák a létrehozott számla számlasorai, amikor az egy jogi személyhez van feldolgozva amely az ország/régió környezet Olaszországhoz használatával van konfigurálva.

#### <a name="finland"></a>Finnország
A létrehozott számlaképernyőn kívül Zsíróátutalási bizonylatok hozhatók létre a következőképpen:

- Jogi személyhez, mely Finnországhoz tartozó ország/régió összefüggést használ és van legalább egy bankszámla **Zsírószámlaként** és **Bank vonalkódjaként** van megjelölve. 
- Egy számla, amely be van jelölve, hogy szükséges a **finn** kapcsolódó fizetési melléklethez.

![Zsíróátutalási bizonylat](media/FTIbyGER-GiroSlip.PNG)

> [!NOTE]
> Minta ER formátum konfigurálva lett, hogy opcionálisan generálja a Zsíróalapú átutalási bizonylatokat külön munkalapon.

> [!NOTE]
> Előbb telepítenie kell a betűtípust, amellyel a helyi számítógépen vonalkódelőállítása történi, ahol a létrehozott számla előnézete meg lesz jelenítve Excel-formátumban.

### <a name="use-the-sample-er-format-to-configure-email-destinations"></a>A minta ER formátumot használja az e-mail célok beállításához
A minta ER formátum következő elemeit használja az e-mail célok beállításához:

- A vevő kapcsolattartójának e-mail-címe elérhető következő ER kifejezéssel: **model.InvoiceBase.Contact.ElectronicMail**.
- A következő ER kifejezés keresztül elérhető az e-mail tárgya: **Emailing.TxtToUse.Subject**.
- A következő ER kifejezésen keresztül elérhető az e-mail törzse: **Emailing.TxtToUse.Body**.

![Cél beállításai](media/FTIbyGER-ERFileDestinationSettingEmail.png)

Az e-mail tárgyának és törzsének meghatározása a minta ER-formátumban történik. A nyelv a formátum címkéitől függ. Ez az alapértelmezett szöveg lesz használva, ha egy egyéni szervezeti e-mail-sablon lett hozzáadva, amelynek az előre definiált **ERFTITMP** azonosítója nincs hozzáadva .

> [!NOTE]
> A **ERFTITMP** e-mail-sablon azonosítójának definiálása ER minta formátumban történik. Szükség szerint módosítható az új ER formátumban, hogy ebből a minta formátumból jöjjön létre .

Ha a szervezet e-mail-sablont, amelynek az előre definiált **ERFTITMP** azonosító hozzá van adva a jogi személyhez, melyhez feldolgozza a számlát, az e-mail tárgyának és szövegének sablonja lesz használva az e-mail generálásához. 

![Szervezeti e-mail sablonok](media/FTIbyGER-EmailTemplate.png)

![E-mail sablon feltöltése](media/FTIbyGER-EmailTemplateBody.png)

Az **Emailing.TxtToUse.Subject** ER kifejezés a minta ER formátumban úgy van beállítva, hogy a(z) %1 helyőrző minden előfordulását lecseréli a feldolgozási számla azonosítójára.

Az **Emailing.TxtToUse.Body** kifejezés a minta formátumban a helyőrzők alábbiak szerinti cserélésére van beállítva:

- "%1" a vevő kapcsolattartó személyére lesz cserélve.
- "%2" helyére kerül a vállalat neve.
- "%3" helyére kerül az ügyfél neve.
- "%4" a vállalat kapcsolattartó személyére lesz cserélve.
- "%5" a vállalat kapcsolattartó személyének beosztására lesz cserélve.
- "%6" a vállalat kapcsolattartó személyének e-mail-címére lesz cserélve.

![E-mail-cím](media/FTIbyGER-Email.PNG)

## <a name="additional-resources"></a>További erőforrások
[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]