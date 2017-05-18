---
title: "Költségkezelés konfigurálása"
description: "Ez a cikk ismerteti azokat a szempontokat, amelyeket a tervezési folyamat során – a Költséggazdálkodás Microsoft Dynamics AX rendszerben történő konfigurálása előtt – figyelembe kell venni, valamint az ekkor meghozandó döntéseket. A Költséggazdálkodás területén többek között fizetési módokkal, utazásigénylésekkel, költségjelentésekkel és irányelvekkel kapcsolatos információkat tárolhat."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 447ba56a279a29392b00119730c3594fa4ea80f6
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="configure-expense-management"></a>Költségkezelés konfigurálása

[!include[banner](../includes/banner.md)]


Ez a cikk ismerteti azokat a szempontokat, amelyeket a tervezési folyamat során – a Költséggazdálkodás Microsoft Dynamics AX rendszerben történő konfigurálása előtt – figyelembe kell venni, valamint az ekkor meghozandó döntéseket. A Költséggazdálkodás területén többek között fizetési módokkal, utazásigénylésekkel, költségjelentésekkel és irányelvekkel kapcsolatos információkat tárolhat. 

Mivel a Költséggazdálkodási konfiguráció tervezése során meghozott számos döntés az Ön szervezetének hierarchiáján, illetve annak pénzügyi struktúráján alapszik, így szükséges átolvasnia ezen területek tervezési dokumentumait is.

## <a name="intercompany-expenses"></a>Vállalatközi költségek
Ha engedélyezi a vállalatközi költségeket, úgy azt teszi lehetővé, hogy a jogi személyek és az alkalmazottak költségeket szenvedjenek el, illetve kifizetéseket vegyenek kézhez más, az Ön szervezetén belüli jogi személyektől. Vegyük például azt az esetet, hogy az A jogi személy alkalmazottja elvégez egy projektet a B jogi személynél. Ha engedélyezve vannak a vállalatközi költségek, akkor az alkalmazott tud a B jogi személy által fizetendő munkaidő-nyilvántartást nyújtani be. Ha az Ön szervezetéhez csak egy jogi személy tartozik, akkor nem szükséges engedélyeznie a vállalatközi költségeket. **Döntés:** Szeretné engedélyezni a vállalatközi költségeket?

## <a name="financial-management"></a>Pénzgazdálkodás
A költséggazdálkodás szorosan kapcsolódik szervezete pénzgazdálkodásához. A költséggazdálkodásra vonatkozó konfigurációk jelentős része a szervezete pénzügyei kapcsán már korábban meghozott döntéseken alapul. Az alábbi szakaszok azokat a különféle területeket mutatják be, melyek tervezést és döntéshozatalt igényelnek, a szervezete pénzügyi döntései, illetve a vezető testület útmutatása alapján.

### <a name="per-diems"></a>Napidíjak

Meg kell adnia a szervezete által biztosított alkalmazotti napidíjakat. Mivel a napidíjak jellemzően olyan költségek fedezésére szolgálnak, mint az étkezés, a szállás és más járulékos költségek, tud létrehozni a szervezete által térített napidíjakra vonatkozó szabályokat. A napidíj alapja a dátum, az utazási helyszín, vagy a kettő kombinációja lehet. Napidíjszabályt létrehozásakor be tudja állítani, hogy a napidíj egy részét visszatartsa a rendszer, ha a dolgozó ingyenes étkezésben vagy egyéb szolgáltatásban részesül. Emellett tud megadni napidíjszinteket is, melyek a dolgozó útjára alkalmazható napidíjjal érintett órák minimális és maximális számát szabályozzák. **Döntések:**

-   Az első és utolsó napra érvényes alapértelmezett napidíjszabályok:
    -   Mi az az alkalmazott által benyújtott minimális napi óraszám, amelyre már jár a napidíj?
    -   Vonatkozik-e bármilyen levonás az első és utolsó napra járó étkezési díj összegére? Ha igen, akkor mekkora a levonás százalékos aránya?
    -   Vonatkozik-e bármilyen levonás az első és utolsó napra járó szállásdíj összegére? Ha igen, akkor mekkora a levonás százalékos aránya?
    -   Vonatkozik-e bármilyen levonás az első és utolsó napra járó egyéb költségtérítés összegére? Ha igen, akkor mekkora a levonás százalékos aránya?
-   Alapértelmezett napidíjszabályok:
    -   Vonatkozik-e bármilyen, az egyes étkezésekre vonatkozó százalékos levonás, például ingyenes étkezések esetén? Ha igen, akkor mekkora az egyes étkezésekre vonatkozó levonás százalékos aránya?
    -   Az étkezési levonás kiszámítása naponta, utanként vagy a napi étkezések darabszáma alapján történjen-e?
    -   A napidíj összegeket a hagyományos módon, vagy mindig felfelé kerekítse a rendszer?
    -   A napidíjak kiszámítása 24 órás időszak, vagy naptári napok alapján történjen-e?
-   Helyszínfüggő napidíjszabályok:
    -   A helyszín befolyásolja-e a napidíjösszegeket, illetve mely helyszínek érintettek?
    -   Amennyiben a helyszín befolyásolja a napidíjösszegeket, úgy az alábbiak kapcsán milyen százalékos összeg van érvényben az egyes helyszíneken:
        -   étkezés
        -   szállás
        -   egyéb költségek

### <a name="expense-management-journals-and-accounts"></a>Költséggazdálkodási naplók és számlák

A költséggazdálkodás több napló és számla használatát teszi szükségessé. El kell például döntenie, hogy ugyanazt a számlát használja-e a készpénzelőlegekhez, illetve a vitatott hitelkártya tételekhez? **Döntések:**

-   Melyik főkönyvi naplóba történik a jóváhagyott költségjelentések feladása?
-   Melyik számlát használja a készpénzelőlegekhez?
-   Azonnal sor kerül-e a készpénzelőlegek feladására?

### <a name="payment-methods"></a>Kifizetési módok

Ha engedélyezi az alkalmazottak részére a vállalati költségek kiegyenlítését, úgy meg kell adnia, hogy melyek az alkalmazottak részére engedélyezett fizetési módok. Lehetővé teheti például az alkalmazottak részére a készpénz vagy a vállalati hitelkártya használatát. De engedélyezheti az alkalmazottak személyes hitelkártyáinak használatát, illetve az összeg utólagos megtérítését is. Minden engedélyezett fizetési mód kapcsán el kell döntenie az alábbiakat. **Döntések:**

-   Melyek az engedélyezett fizetési módok?
-   Ki viseli a fizetési módhoz kapcsolódó költségeket?
-   Van-e ellenszámlatípus? Ha igen, milyen?
-   Ha van ellenszámla, melyik az?
-   Hitelkártyás fizetési mód esetén ez a fizetési mód csak importált tranzakciók esetén legyen alkalmazható?

### <a name="expense-categories-and-shared-categories"></a>Költség- és megosztott kategóriák

Amikor egy alkalmazott költségjelentést hoz létre, minden abban rögzített költséget társítani kell egy költségkategóriával. A költségkategóriákat a rendszer a szervezetén belül működő jogi személyek által használt megosztott kategóriákból eredezteti. Ezek a kategóriák, a szervezeti beállítások függvényében, a Projektvezetés és könyvelés modullal is megoszthatók. Határozza meg a szervezeti beállításai, illetve a végrehajtásért felelős csapat útmutatása alapján, hogy költséggazdálkodásban meghatározott kategóriákat csak a költségek kapcsán, vagy a Projektek és Költségek modul között megosztva kívánja-e használni? Kérjük, vegye figyelembe, hogy ezek a kategóriák a Projekt és a Költség, illetőleg a Projekt és a Termelés modul között oszthatók meg, de a Költség és a Termelés modul között nem. Az egyes költségkategóriák kapcsán az alábbi döntéseket kell meghoznia. **Döntések:**

-   Mi a költségkategória? Például repülőjegy, szállás vagy kilométerdíj.
-   Ez a költségkategória használható a Projektvezetés és könyvelési modulban is?
-   Mi a költségkategória?
-   Mi a költségkategóriára érvényes alapértelmezett fizetési mód?
-   Szükséges-e a kategóriába tartozó költségek részletezése?
-   Mi a költségkategóriára érvényes fő alapértelmezett számla?
-   Mi a költségcsoportra érvényes alapértelmezett cikkáfacsoportot?
-   Engedélyezett-e további fizetési mód ebben a költségkategóriában? Ha igen, melyek ezek?
-   Ebben a költségkategóriában vannak-e alkategóriák? Ha igen:
    -   Vannak-e adó-visszaigénylésre nem jogosító alkategóriák?
    -   Mi az alkategóriák cikkáfacsoportja?

    Válaszoljon az alábbi kérdésekre, ha ez a költségkategória a Projektvezetés és könyvelés modulban is felhasználásra kerül. Ellenkező esetben nincs további teendője ebben a szakaszban.
-   Melyik költségszámla használandó az alábbiak kapcsán?
    -   Költség
    -   Bérfoglalás
    -   Folyamatban lévő munka-költségérték
    -   Költség-cikk
    -   Folyamatban lévő munka-költségérték-cikk
    -   Elhatárolt veszteség
    -   Folyamatban lévő munka-elhatárolt veszteség
-   Melyik bevételszámla használandó az alábbiak kapcsán?
    -   Számlázott bevétel
    -   Elhatárolt bevétel-értékesítési érték
    -   Folyamatban lévő munka-értékesítési érték
    -   Elhatárolt bevétel-termelés
    -   Folyamatban lévő munka-termelés
    -   Elhatárolt bevétel-nyereség
    -   Folyamatban lévő munka-nyereség
    -   Elhatárolt bevétel-előfizetés
    -   Folyamatban lévő munka-előfizetés

 

### <a name="taxes"></a>Adók

A költségekhez kapcsolódó adók kapcsán meg kell adnia, hogy mit ad hozzá, illetve mit engedélyez a költségjelentésekben. **Döntések:**

-   A költségösszegek tartalmazzák az áfát?
-   Engedélyezett a költség kapcsán az adó-visszaigénylés?

Kérjük, vegye figyelembe, hogy amennyiben a főkönyv tervezése során az USA-beli áfa és adózási szabályok használata mellett döntött, melyet az **Áfára vonatkozó adózási szabályok alkalmazása** mező Igen értékének kiválasztása útján tud megtenni, úgy nem tudja engedélyezni az adó-visszaigénylést a költségek kapcsán.

## <a name="policies"></a>Szabályzatok
Tud létrehozni olyan költségjelentési irányelveket, melyek segítségével a szervezete időt és pénzt takarít meg, amikor az alkalmazottak rendezik a vállalati költségeket. Az irányelvek biztosítják, hogy az alkalmazottak betartsák a költségkertet, hogy megadjanak minden szükséges információt, illetve hogy csak a szükséges mértékű összeget költsék el. Az alábbi döntéseket kell meghoznia minden egyes, Ön által létrehozott költségjelentés irányelv és költségjelentés jóváhagyási irányelv kapcsán. **Döntések:**

-   Mi az irányelv neve?
-   Mi a költségirányelv célja?
-   Ha korábban engedélyezte a vállalatközi költségeket, úgy az irányelv a szervezet mely vállalataira vonatkozik?
-   Mikor lép életbe az irányelv?
-   Mikor jár le az irányelv?
-   Mi az irányelvszabály?
-   Mi az irányelvszabály eredménye?





