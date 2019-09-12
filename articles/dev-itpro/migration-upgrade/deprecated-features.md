---
title: Eltávolított vagy elavult funkciók
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve.
author: sericks007
manager: AnnBe
ms.date: 08/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4aad4f2cf42b72256b5c4727bfd145d16af033ed
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867101"
---
# <a name="removed-or-deprecated-features"></a>Eltávolított vagy elavult szolgáltatások

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva vagy elavultak a Dynamics 365 for Finance and Operations szolgáltatásban.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!NOTE]
> A Dynamics 365 for Finance and Operations 2017. júliusi kiadása a 8-as platformfrissítéssel verziótól kezdve minden eltávolított és elavult szolgáltatás esetében feltüntetjük a telepítések típusát. Az ebben a témakörben említett korábbi kiadások kivétel nélkül csak a felhőtelepítést támogatták.

> A Finance and Operations objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations egyes verzióiban.

## <a name="dynamics-365-for-finance-and-operations-1005-with-platform-update-29"></a>Dynamics 365 for Finance and Operations 10.0.5 és 29-as platformfrissítés

> [!IMPORTANT]
> A Dynamics 365 for Finance and Operations 10.0.5 29-ös platformfrissítéssel a megcélzott felhasználók számára elérhető egy előzetes kiadás részeként. A tartalom és a funkciók megváltozhatnak. Az előzetes kiadásokkal kapcsolatban további információkat a [Szolgáltatásfrissítések elérhetősége](../../fin-and-ops/get-started/public-preview-releases.md) oldalon találhat.

### <a name="us-payroll-tax-updates"></a>USA bérszámfejtési adófrissítések

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Kivezetjük az adófrissítéseket az amerikai bérszámfejtés funkcióhoz, mivel keveset volt használva, és továbbfejlesztett funkciók érhetők el a most kínált stratégiai integrációkban.  |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Bérlista |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavul : 2021. október 1-jén, azt tervezzük, hogy már nem nyújtunk adófrissítéseket az amerikai bérszámfejtés ügyfeleknek. A funkcionalitás megmarad a termékben, de a fejlesztések többé nem tartják naprakészen a funkcionalitást, és minden termékhibát eseti alapon fognak értékelni. További információ: [Adófrissítések kivezetése az amerikai bérszámfejtés funkcióhoz a Microsoft Dynamics 365 for Finance and Operations](https://aka.ms/financepayrollfaq) megoldásban. |


### <a name="data-management-staging-clean-up"></a>Az adatkezelés előkészítési megtisztítása
|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Nem felel meg az időszakos törlés ütemezéséhez szükséges alapkövetelményeknek. |
| **Felváltotta másik szolgáltatás?**   | Igen, a Munkaelőzmények törlése funkció lett hozzáadva a használati esetek kezelésére. |
| **Érintett területek**         | Adatkezelés |
| **Telepítési beállítás**              | Összes  |
| **Állapot**                         | Elavult: A funkció eltávolításának célként meghatározott időkerete 2020 decembere. |

## <a name="dynamics-365-for-finance-and-operations-1004-with-platform-update-28"></a>Dynamics 365 for Finance and Operations 10.0.4 és 28-as platformfrissítés

### <a name="france-fec-accounting-data-export-in-xml"></a>FEC Könyvelési adatok exportálása XML-formátumban, Franciaország

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A TXT formátumra cserélve a **Francia FEC könyvvizsgálati fájl** a **Főkönyv** \> **Ismétlődő feladatok** \> **Adatok exportálása** pontban érhető el.
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Főkönyv |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult. A funkció eltávolításának céljaként megjelölt időkeret 2020. július. |


### <a name="legacy-navigation-bar"></a>Korábbi navigációs sáv

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Fejléc igazítása más Dynamics és Office termékekkel. A további tudnivalókat lásd: [A frissített navigációs sáv mostantól igazodik az Office fejléchez](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-finance-operations/updatednavbar)
| **Felváltotta másik szolgáltatás?**   | A Platform update 24-től kezdve bevezetésre került egy újratervezett navigációs sáv, amelyen keresés is található. |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2020 áprilisában a korábbi navigációs sáv már nem lesz elérhető. Eddig a pontig a vevők a korábbi navigációs sávra az **Ügyfélteljesítmény beállításai** lapon térhetnek vissza. |


## <a name="dynamics-365-for-finance-and-operations-1002-with-platform-update-26"></a>Dynamics 365 for Finance and Operations 10.0.2 és 26-as platformfrissítés


### <a name="legacy-default-action-behavior"></a>Örökölt alapértelmezett művelet viselkedése

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az rácsokban végzett alapértelmezett műveletek örökölt viselkedése azt eredményezheti, hogy az egyik, alapértelmezett művelet hivatkozását tartalmazó, rácsoszlopok után szereplő váratlan oszlop átrendezése történik személyre szabáson keresztül. Az új beragadó alapértelmezett művelet funkció ennek javítására használatos. További részletekért lásd: [Alapértelmezett beragadó műveletek rácsokban](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/sticky-default-action). |
| **Felváltotta másik szolgáltatás?**   | A 21-es platformfrissítéstől kezdődően bevezettük az „alapértelmezett beragadó műveletek” funkciót. A funkciót az **Ügyfélteljesítmény beállításai** oldalon lehet engedélyezni. |
| **Érintett területek**         | Rácsok a webes ügyfélnél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2020. áprilistól kezdődően az alapértelmezett beragadó műveletek lesznek az alapértelmezett műveletek, és nem áll majd rendelkezésre olyan mechanizmus, amellyel vissza lehet térni az örökölt viselkedésre. |

### <a name="legacy-is-one-of-filtering-experience"></a>Örökölt „egyike a következőknek” szűrési élmény

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az „egyike a következőknek” szűrési gyakorlatot a 22-es platformfrissítésben átterveztük, mivel a jövőben ez lesz az egyetlen „egyike a következőknek” szűrési gyakorlat. |
| **Felváltotta másik szolgáltatás?**   | A 22-es platformfrissítéstől kezdődően a továbbfejlesztett „egyike a következőknek” szűrési gyakorlat elérhetővé vált az **Ügyfélteljesítmény beállításai** oldalon. További információért lásd: [Optimalizált „egyike a következőknek” szűrési élmény](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering). |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2020. áprilistól kezdődően a továbbfejlesztett „egyike a következőknek” gyakorlat lesz az alapértelmezett viselkedés, és nem áll majd rendelkezésre olyan mechanizmus, amellyel vissza lehet térni az örökölt viselkedésre. |

### <a name="parameter-to-enable-sales-orders-with-multiple-project-contract-funding-sources"></a>Paraméter, amellyel engedélyezhetők a több projektszerződéses finanszírozási forrással rendelkező értékesítési rendelések
Támogatja a projektalapú értékesítési rendelések létrehozását, ahol a projekszerződéseknél több finanszírozási forrás is engedélyezve van a **Projektvezetési paraméterek** beállítás **Több finanszírozási forrással rendelkező projekthez tartozó értékesítési rendelések engedélyezése** értékével. Alapértelmezés szerint ez a paraméter nincs engedélyezve. 

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A funkciót a rendszer mindig engedélyezi a paraméter eltávolítása után. |
| **Felváltotta másik szolgáltatás?**   | Szám A funkció, amely támogatja a projektalapú értékesítési rendelkéseket, amelyek több finanszírozási forrással rendelkeznek, mindig engedélyezve lesz.   |
| **Érintett területek**         |A **Több finanszírozási forrással rendelkező projektekhez tartozó értékesítési rendelések engedélyezése** paraméter el lesz távolítva. Paraméter eltávolításakor a következő metódusok módosulnak: **ctrlSalesOrderTable** metódus a **ProjStatusType** osztályban, az **ellenőrzés** metódus a **ProjId** mezőre vonatkozóan, és a **futtatás** metódus a **SalescreateOrder** képernyőn. A kövektező metódusok elavulnak a paraméter eltávolításakor: **IsSalesOrderAllowedForMultipleFundingSources** a **ProjTable** táblafájlban, a **IsAllowSalesOrdersForMultipleFundingSourcesParamEnabled** metódus a **ProjTable** táblafájlban, az **AllowSalesOrdersForMultipleFundingSources** adatmező a **ProjParameters** képernyőn és a **ProjParameterEntity** fájlokban, az **IsAssociatedToMultipleFundingSourcesContract** privát metódus a**ProjTable** táblafájlban. |
| **Telepítési beállítás**              | Összes  |
| **Állapot**                         | Az elavulást a 2020. áprilisi kiadási hullámra tervezzük. |

### <a name="legacy-workflow-reports-for-tracking-and-instance-status"></a>Örökölt munkafolyamat-jelentések nyomon követéshez és példányállapothoz

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A nyomon követéshez és példányállapothoz használt örökölt munkafolyamat-jelentések elavulnak, mivel már nem hivatkoznak rájuk a navigációból. A jelentések nevei a következők: WorkflowWorkflowInstanceByStatusReport és WorkflowWorkflowTrackingReport. |
| **Felváltotta másik szolgáltatás?**   | Ehelyett a munkafolyamat-előzmények képernyő használható. |
| **Érintett területek**         | Webes ügyfél |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A funkció eltávolításának célként meghatározott időkerete 2020 áprilisa. |

## <a name="dynamics-365-for-finance-and-operations-1001-with-platform-update-25"></a>Dynamics 365 for Finance and Operations 10.0.1 és 25-as platformfrissítés

### <a name="deprecated-apis-and-potential-breaking-changes"></a>Elavult API-k és a lehetséges kompatibilitástörlő változások


#### <a name="deriving-from-internal-classes-is-deprecated"></a>A belső osztályok történő származtatás elavult.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A 25-ös platformfrissítés előtt létre lehetett hozni egy osztályt vagy táblát, amely egy belső osztályból/táblából származik, amelyik egy másik csomagban/modulban van definiálva. Ez nem egy biztonságos programozási gyakorlat. A 25-ös platformfrissítéstől kezdve a fordító figyelmeztetést jelenít meg. |
| **Felváltotta másik szolgáltatás?**   | A 26-os platformfrissítésben a fordítói figyelmeztetése hibaüzenetre lesz módosítva. Ez a módosítás visszafelé kompatibilis futásidőben, ami azt jelenti, hogy, hogy a 25-ös platformfrissítés vagy az újabb verziók telepíthetők bármely teszt- vagy a termelési környezetben, anélkül, hogy szükséges lenne egyéni kód módosítására. Ez a változtatás csak a fejlesztési és fordítási időt érinti.|
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A 26-os platformfrissítésben a figyelmeztetés fordítói hibaüzenetre lesz módosítva. |

#### <a name="overriding-internal-methods-is-deprecated"></a>A belső módszerek felülbírálása elavult

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A 25-ös platformfrissítés előtt lehetséges volt felülbírálni egy belső metódust egy származtatott osztályban, amelyik egy másik csomagban/modulban van definiálva. Ez nem egy biztonságos programozási gyakorlat. A 25-ös platformfrissítéstől kezdve a fordító figyelmeztetést jelenít meg. |
| **Felváltotta másik szolgáltatás?**   | A 26-os platformfrissítésben a figyelmeztetése fordítási hibaüzenetre lesz módosítva. Ez a módosítás visszafelé kompatibilis futásidőben, ami azt jelenti, hogy, hogy a 25-ös platformfrissítés vagy az újabb verziók telepíthetők bármely teszt- vagy a termelési környezetben, anélkül, hogy szükséges lenne egyéni kód módosítására. Ez a változtatás csak a fejlesztési és fordítási időt érinti. |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A 26-os platformfrissítésben a figyelmeztetés fordítói hibaüzenetre lesz módosítva. |

## <a name="dynamics-365-for-finance-and-operations-1000-with-platform-update-24"></a>Dynamics 365 for Finance and Operations 10.0.0 és 24-as platformfrissítés

### <a name="renaming-released-products"></a>Kiadott termékek átnevezése 
|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ha egy kiadott termék ItemId értékének módosítására használja az **Elsődleges kulcs átnevezése** funkciót, akkor csak a közvetlen idegenkulcs-hivatkozásokat frissíti a rendszer. A kiadott termékre vonatkozó bármilyen egyéb hivatkozás (például a termelési rendelések) megtartják a régi ItemId értéket. Ennek eredményeképpen előfordulhat, hogy inkonzisztens adatok jönnek létre, amelyek idővel blokkolják az üzleti folyamatokat. |
| **Felváltotta másik szolgáltatás?**   | Szám |
| **Érintett területek**         | Termékinformációk kezelése |
| **Telepítési beállítás**              | Összes  |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Finance and Operations 10.0.0-es verzió és platform update 24 után. Kivételes esetekben, például egy kiadott termék elsődleges kulcsának egy korábbi átnevezéséből történő helyreállításhoz a Microsofttól kérheti, hogy ideiglenesen szüntesse meg ezt a korlátozást a kiadott termékek elsődleges kulcsának átnevezése során. |


## <a name="dynamics-365-for-finance-and-operations-813-with-platform-update-23"></a>Dynamics 365 for Finance and Operations 8.1.3 és 23-as platformfrissítés

### <a name="sql-server-reporting-services-reportviewer-control"></a>Az SQL Server Reporting Services ReportViewer vezérlője
Az ügyfelek használhatják az **Exportálás** művelet, amelyet a beágyazott SQL Server Reporting Services (SSRS) Report Viewer vezérlője biztosít a Finance and Operations alkalmazások által létrehozott dokumentumok letöltése céljából. Ez a HTML-alapú megjelenítése a jelentésnek la dokumentum nem oldalakra bontott előnézetét kínálja a dokumentumnak

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A HTML-alapú előnézeti tapasztalat nem oldalakra bontott jellege **nem** biztosítja a Finance and Operations rendszerrel készített végső dokumentumok hitelességét Amennyiben teljes mértékben elfogadják, hogy a PDF az üzleti dokumentumok szabványos formátuma, a felhasználók élvezhetik a modern megtekintési élmény által nyújtott előnyöket, amelyek az alkalmazásjelentések létrehozásakor megnövelt teljesítményt nyújtanak. |
| **Felváltotta másik szolgáltatás?**   | Innentől a PDF-dokumentum lesz az alapértelmezett formátum a Finance and Operations jelentéseihez.   |
| **Érintett területek**         | Ez a módosítás **nem** befolyásolja, azon ügyfélszituációkat ahol jelentések elektronikus úton elosztottak vagy közvetlenül nyomtatókra küldik azokat.    |
| **Telepítési beállítás**              | Összes  |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. A funkció, amellyel automatikusan megtekinthető a pályázati jelentések előnézete egy beágyazott PDF-megtekintő segítségével, a tervek szerint a 2019. májusi platformfrissítésben lesz elérhető. |

### <a name="client-kpi-controls"></a>Ügyfél KPI-vezérlők
A beágyazott fő teljesítménymutatók (KPI) modellezhetők a Visual Studio rendszerben egy fejlesztő által és a végfelhasználó tovább testreszabhatja azokat.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A KPI-k meghatározásához használt natív ügyfélvezérlők alacsony szintű megértést várnak el az ügyféltől, és a fejlesztők adhatják hozzá a követhető mutatókat. |
| **Felváltotta másik szolgáltatás?**   | PowerBI.com szolgáltatás világszínvonalú eszközöket kínál KPI-k kezeléséhez és meghatározásához külső forrásból származó adatok alapján.  Egy közelgő kiadásban tervezzük PowerBI.com-on tárolt megoldások beágyazását az alkalmazások munkaterületeire   |
| **Érintett területek**         | Ez a frissítés megakadályozza, hogy a fejlesztők új KPI-vezérlők vezessenek be a Visual Studio tervezőjében.    |
| **Telepítési beállítás**              | Összes  |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="deprecated-apis-and-future-breaking-changes"></a>Elavult API-k és jövőbeni kompatibilitástörlő változások

#### <a name="field-groups-containing-invalid-field-references"></a>Érvénytelen mező hivatkozásokat tartalmazó mezőcsoportok

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Lehetőséges, hogy a táblák metaadatdefiníciói érvénytelen mezőhivatkozásokat tartalmazó mezőcsoportokat tartlmaznak. A probléma jelenleg a *fordítói figyelmeztetés* kategóriába tartozik, és nem *hiba*, tehát, hogy a telepíthető csomag létrehozása és a telepítés végrehajtható a probléma kijavítása nélkül. Telepítés esetén ez hibákat okozhat futásidőben a pénzügyi jelentésekben és az SQL Server Reporting Services (SSRS) szolgálatásokban. A probléma megoldásához:<br><br>1. Távolítsa el az érvénytelen mezőhivatkozást a tábla a mezőcsoport-definíciójából.<br><br>2. Fordítsa újra.<br><br>3. Győződjön meg arról, hogy minden hiba vagy figyelmeztetés javítva lett. |
| **Felváltotta másik szolgáltatás?**   | A jövőben ez a fordítói figyelmeztetés hibaüzenetre lesz módosítva.  |
| **Érintett területek**         | Visual Studio fejlesztőeszközök. |
| **Telepítési beállítás**              | Mind. |
| **Állapot**                         | Elavult: A figyelmeztetés fordítási hiba lesz a jövőben. Jelenleg a 30-as platformfrissítés van megcélozva. |

#### <a name="complete-list"></a>Teljes lista
Az elavulás alatt álló API-k teljes listáját lásd: [Módszerek és metaadat-elemek elavulása](deprecation-deletion-apis.md).

## <a name="dynamics-365-for-finance-and-operations-81-with-platform-update-20"></a>Dynamics 365 for Finance and Operations 8.1 és 20-as platformfrissítés

### <a name="batch-transfer-rules-for-subledger-journal-account-entries"></a>Kötegelt átviteli szabályok analitikus naplószámla bejegyzéseihez
A szinkron átmozgatási módot megszüntetjük a főkönyvi paramétereknél.  A módnál csak az aszinkron és az ütemezett köteg marad mind átmozgatási lehetőség. További információért lásd: [Főkönyvi paraméterek – Kötegelt átmozgatás szabályai](https://community.dynamics.com/365/financeandoperations/b/financials/archive/2019/03/15/general-ledger-parameters-batch-transfer-rules) blogot.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A szinkron beállítást a rendszer teljesítményére gyakorolt hatás miatt szüntetjük meg. |
| **Felváltotta másik szolgáltatás?**   | A szinkron helyett az aszinkron és az ütemezett köteg beállítás használható.   |
| **Érintett területek**         | Főkönyv, Kötelezettségek, Kinnlevőségek, Beszerzés, Költség    |
| **Telepítési beállítás**              | Összes  |
| **Állapot**                         | Elavult: A funkció eltávolításának cél időkerete a 10.0-s verzió.|

### <a name="electronic-reporting-for-russia"></a>Elektronikus jelentéskészítés Oroszország esetében
Funkció a bevallások .txt és .xml fájlformátumainak konfigurálásához. 

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Helyére az elektronikus jelentéskészítés kerül. |
| **Felváltotta másik szolgáltatás?**   | Igen. |
| **Érintett területek**         | Főkönyv |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Finance and Operations 8.1-es verzió és platform update 20 után. |

### <a name="financial-reports-generator-for-russia"></a>Pénzügyi jelentéskészítő Oroszország számára
Eszköz az adatgyűjtemény elszámolás és adókimutatások céljából való beállításához, valamint annak érdekében, hogy XLS és DOC kimutatássablonokba exportálhassa az adatokat. Funkcionális részek: Adatok exportálása XLS és DOC jelentéssablonokba, lekérdezések, a rögzített kellékek eltávolításra kerülnek. 

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az eltávolított részek helyére az elektronikus jelentések kerülnek. |
| **Felváltotta másik szolgáltatás?**   | Igen. A pénzügyi kimutatások beállításának kezelőfelülete használandó az adatgyűjtemény-szabályok főkönyvi számlál és adónyilvántartások általi beállítására. Adatok exportálása különböző fájltípusokba; a rögzített elemek és a lekérdezésszerű adatgyűjtési szabályok konfigurálása az elektronikus jelentésekben történik. |
| **Érintett területek**         | Főkönyv. |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Finance and Operations 8.1-es verzió és platform update 20 után. |

### <a name="integration-with-external-providers-for-sending-electronic-reporting-through-communication-channels-for-russia"></a>Külső szolgáltatók integrálása elektronikus jelentések kommunikációs csatornákon keresztül való küldéséhez Oroszország esetében
A deklaráció elektronikus fájljait exportáló funkció, amely az exportálást egy mappába végzi, hogy továbbküldhesse az adatokat az elektronikus jelentések hivatalos szolgáltatóinak, akik visszaadják az állapotot.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Helyére az elektronikus üzenetek konfigurálható funkciója kerül. |
| **Felváltotta másik szolgáltatás?**   | Igen.  |
| **Érintett területek**         | Főkönyv, Adó |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Finance and Operations 8.1-es verzió és platform update 20 után. |


### <a name="profit-tax-register-wizard"></a>Nyereségadó-jegyzék varázsló
Ez a funkció az új nyereségadó-jegyzékekhez tartozó sablonok létrehozásához használatos. A funkció X++ objektumokat hoz létre az új jegyzékekhez, amelyeket utána sablonként létre lehez hozni, ha a megfelelő kalkulációs logikát hozzáadják.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A funkció nem kompatibilis a Dynamics 365 for Finance and Operations bővíthetőségi modellel. |
| **Felváltotta másik szolgáltatás?**   | Szám |
| **Érintett területek**         | Adó |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Finance and Operations 8.1-es verzió és platform update 20 után. |


## <a name="dynamics-365-for-finance-and-operations-80-with-platform-update-15"></a>Dynamics 365 for Finance and Operations 8.0 és platform update 15
Nincsenek funkciók eltávolítva vagy elavulttá nyilvánítva ebben a kiadásban. A 15-ös platformfrissítés halmozott és tartalmazza a 13-as platformfrissítés, a 14-es platformfrissítés a 15-ös platformfrissítés új vagy módosított szolgáltatásait.

## <a name="dynamics-365-for-finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>Dynamics 365 for Finance and Operations, Enterprise edition 7.3 és platform update 12

### <a name="personalized-product-recommendations"></a>Személyre szabott termékajánlatok 
2018. február 15-től a kiskereskedők már nem jeleníthetnek meg személyre szabott termékjavaslatok a pénztári (POS) eszközökön. További információ: [Személyre szabott termékajánlatok áttekintése](../../retail/personalized-product-recommendations.md).  

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A termékajánló szolgáltatás jelenlegi verzióját eltávolítjuk, mivel ezt a funkciót jobb algoritmussal és újabb kiskereskedelmi orientált képességekkel újratervezzük.  |
| **Felváltotta másik szolgáltatás?**   | Szám 2018 tavaszától azonban a funkció újbóli bevezetését tervezzük annak érdekében, hogy kihasználhassunk egy új ajánlási szolgáltatást.   |
| **Érintett területek**         | Személyre szabott termékajánlások a POS felületén.                                                    |
| **Telepítési beállítás**              | Mind                                                                                      |
| **Állapot**                         |Eltávolítva 2018. február 15-én. Ez befolyásolja a Dynamics 365 for Operations 1611-es és újabb verzióit futtató ügyfeleket.  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>Elektronikus jelentéskészítési (ER) funkciók listájának kibővítése
A lehetőség az ER kifejezésszerkesztőben használandó egyéni funkciók bevezetésére (további tájékoztatás: [Elektronikus jelentéskészítési funkciók listájának kibővítése](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md)) már nem támogatott. Az ER API-kon végrehajtott módosítások következtében az ER Kifejezésszerkesztő beépített függvényeit meghívó API belsővé vált, és többé nem lehet kiterjeszteni.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Kódzárolási kezdeményezés  |
| **Felváltotta másik szolgáltatás?**   | Egyik sem. Amikor csak új beépített függvényre van szükség, új bővítési kérelmet kell benyújtani az ER-keretrendszer csapatnak.<br><br>Ideiglenes megoldásként, amíg az ER-csapat fejleszti a kért függvényt, a szükséges logika egy egyéni alkalmazásosztály metódusaként is programozható. Ez a metódus egy ER kifejezésben érhető el a hozzáadott ER adatforrás tulajdonságaként az **Application\Class** típusnak, amely az egyéni alkalmazásosztályra hivatkozik.  |
| **Érintett területek**         | Elektronikus jelentéskészítési keretrendszer                                                      |
| **Telepítési beállítás**              | Összes                                                                                      |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Finance and Operations, Enterprise edition 7.3 után.    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>Készlet a cikkcsoport és készlet a készletdimenzió korosítási jelentései szerint

Ezt a két jelentést már nem támogatja a Finance and Operations. Ehelyett a **Készletkorosítási** jelentés használható a felhasználói élmény fokozása érdekében.

|   |  |
|--------------|-----------------------|
| **Megszűnés oka**       | Máshol már meglévő funkció  |
| **Felváltotta másik szolgáltatás?** | Igen. A két jelentést leváltotta a **Készletkorosítási** jelentés.     |
| **Érintett területek**       | Készletkezelés, költségkezelés        |
| **Telepítési beállítás**        | Mind|
| **Állapot**                       | Elavult: A két jelentés menüpontjai el lettek távolítva a 7.3 verzióban. A jelentések kódja azonban a termékben marad. A terv szerint valamelyik jövőbeli programverzióban eltávolítjuk a kódot. |

### <a name="power-bi-content-packs-available-on-appsource"></a>Power BI tartalom csomagok elérhetők az AppSource felületén
A **Költségkezelés**, **Pénzügyi teljesítmény** és **Retail Channel Performance** tartalomcsomagok, amelyek elérhetők a [Microsoft AppSource](https://appsource.microsoft.com) webhelyen, a Microsoft Power BI termékfrissítései miatt elavulttá válnak. A rendszerfelügyeleti képernyők, amelyeknek a segítségével ezeket a tartalmi csomagokat telepítették a PowerBI.com webhelyre, szintén elavultak a Finance and Operations megoldásban.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Microsoft Power BI termékfrissítései. |
| **Felváltotta másik szolgáltatás?**   | A **Költségkezelés**, **Pénzügyi teljesítmény** és **Retail Channel Performance** tartalomcsomagok, amelyek elérhetők a [AppSource](https://appsource.microsoft.com) webhelyen, olyan analitikus alkalmazásokra cserélődnek le, amelyek az adatbázis szintjén tesznek lehetővé megoldásintegrációt. Az analitikai alkalmazásokkal kapcsolatos további tudnivalókat lásd: [Beágyazott Power BI-munkaterületek](../../dev-itpro/analytics/embed-power-bi-workspaces.md).    |
| **Érintett területek**         | Költségkezelés, pénzügy és kiskereskedelem                                                                                               |
| **Telepítési beállítás**              | Csak felhő (A PowerBI.com webhellyel való integráció nem támogatott a helyszíni telepítések esetében.)                                                                                                            |
| **Állapot**                         | Elavult: A funkció eltávolításának cél időkerete 2018 2. negyedéve.    |

### <a name="standard-ui-in-data-management-workspace"></a>Normál kezelőfelület az adatkezelési munkaterületen

A normál adatkezelési kezelőfelület a régebbi kezelőfelület, amely a felhasználók számára alapértelmezetten jelenik meg, amikor megnyitják az adatok kezelése munkaterületet.

|   |  |
|------------------|-------------------------|
| **Elavulás/eltávolítás oka** | Befektetünk az új felhasználói élmény nyújtásában az új felhasználói felület segítségével.             |
| **Felváltotta másik szolgáltatás?**   | Az új felhasználói felület neve *Bővített nézet*, és a régi felhasználói felületet váltja le.            |
| **Érintett területek**         | Adatkezelési munkaterület                                                     |
| **Telepítési beállítás**              | Mind                                                                           |
| **Állapot**                         | Elavult: A funkció eltávolításának cél időkerete 2018 2. negyedéve. |

### <a name="excise-sales-tax-service-tax-for-india"></a>Fogyasztási adó, áfa, szolgáltatási adó India esetében

Ezeket az adókat már magában foglalja az indiai GST.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Elavulás vagy eltávolítás oka**       | Ezeket az adókat már magában foglalja az indiai GST.                          |
| **Felváltotta másik szolgáltatás?**            | Indiai GST                                                              |
| **Érintett területek**                  | Adó                                                                     |
| **Telepítési beállítás**                       | Minden modul                                                   |
| **Állapot**                                  | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |    

### <a name="file-validation-utility-fvu-for-india"></a>Fájlellenőrzési segédprogram (FVU) India esetében

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Elavulás vagy eltávolítás oka**       | Vevői használat hiánya.                                                  |
| **Felváltotta másik szolgáltatás?**            | Nincs                                                                      |
| **Érintett területek**                  | Indiai adóelőleg                                                  |
| **Telepítési beállítás**                       | Minden modul                                                                    |
| **Állapot**                                  | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |        

### <a name="tdstcs-certificate-for-india"></a>TDS/TCS-tanúsítvány India esetében

A felhasználók a kormányzati portálról tölthetik le.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Elavulás vagy eltávolítás oka**       | Vevői használat hiánya.                                                  |
| **Felváltotta másik szolgáltatás?**            | Nincs                                                                      |
| **Érintett területek**                  | Indiai adóelőleg                                                  |
| **Telepítési beállítás**                       | Minden modul                                                                   |
| **Állapot**                                  | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>Exportálási/importálási (EXIM) ösztönző rendszer India esetében


|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Elavulás vagy eltávolítás oka**       | Vevői használat hiánya.                                                  |
| **Felváltotta másik szolgáltatás?**            | Nincs                                                                      |
| **Érintett területek**                  | Importálás és exportálás                                                       |
| **Telepítési beállítás**                       | Minden modul                                                                    |
| **Állapot**                                  | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>Személyre szabott termékajánlatok 
2018. február 15-től a kiskereskedők már nem jeleníthetnek meg személyre szabott termékjavaslatok a pénztári (POS) eszközökön. További információ: [Személyre szabott termékajánlatok áttekintése](../../retail/personalized-product-recommendations.md).  

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A termékajánló szolgáltatás jelenlegi verzióját eltávolítjuk, mivel ezt a funkciót jobb algoritmussal és újabb kiskereskedelmi orientált képességekkel újratervezzük.  |
| **Felváltotta másik szolgáltatás?**   | Szám 2018 tavaszától azonban a funkció újbóli bevezetését tervezzük annak érdekében, hogy kihasználhassunk egy új ajánlási szolgáltatást.   |
| **Érintett területek**         | Személyre szabott termékajánlások a POS felületén.                                                    |
| **Telepítési beállítás**              | Mind                                                                                      |
| **Állapot**                         |Eltávolítva 2018. február 15-én. Ez befolyásolja a Dynamics 365 for Retail 7.2-es és újabb verzióit futtató ügyfeleket. |


## <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Dynamics 365 for Finance and Operations, Enterprise edition 2017 júliusi verzió és platform update 8

### <a name="currency-conversion-for-accounting-and-reporting-currencies"></a>Pénznemátváltás könyvelési és jelentési pénznemek esetén

A pénznemátváltást könyvelési és jelentési pénznem esetén az euró bevezetésekor vezettük be.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Korlátozott felhasználás és a Jogi személy másolása funkció bevezetése a helyettesítésére.      |
| **Felváltotta másik szolgáltatás?**   | Nem, de bevezettük a Jogi személy másolása és a Konfigurációk funkciókat, hogy megkönnyítsük az olyan vállalatokhoz való áthelyezést, amelyeknél változnak az alapkövetelmények. |
| **Érintett területek**         | Pénzgazdálkodás     |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |


### <a name="warehouse-mobile-devices-portal"></a>Raktári mobileszközportál

A Raktári mobileszközportál (Warehouse mobile devices portal – WMDP) egy különálló összetevő volt a helyszíni saját telepítésekhez. Ezt az összetevőt már nem támogatja a Finance and Operations. A WMDP funkció helyére egy natív alkalmazás lépett, amely javítja a felhasználói élményt.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Máshol már meglévő funkció.       |
| **Felváltotta másik szolgáltatás?**   | Igen. Ezt a funkciót felváltotta a Finance and Operations – Raktárkezelés funkció. A beállítással és előfeltételekkel kapcsolatban további tudnivalókat a [Microsoft Dynamics 365 for Finance and Operations – Raktárkezelés telepítése és konfigurálása](../../supply-chain/warehousing/install-configure-warehousing-app.md) című részben talál. |
| **Érintett területek**         | Raktárkezelés, szállításkezelés     |
| **Telepítési beállítás**              | A Raktári mobileszközportál (Warehouse mobile devices portal – WMDP) egy különálló összetevő volt a helyszíni saját telepítésekhez.               |
| **Állapot**                         | Elavult: A funkció eltávolításának cél időkerete 2019 4. negyedéve.   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Továbbfejlesztett banki egyeztetési szabály kézi egyeztetéshez

Az egyeztetési munkalapon a dokumentumok kézi egyeztetéséhez egy egyeztetési szabályt használtak.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Korlátozott felhasználás.                                                                         |
| **Felváltotta másik szolgáltatás?**   | Szám Az oszlopszűrési lehetőségeket kell használni az egyeztetendő dokumentumok keresésére. |
| **Érintett területek**         | Készpénz- és bankkezelés                                                               |
| **Telepítési beállítás**              | Összes                                                                                    |
| **Állapot**                         | Eltávolítva 2017 júliusában.                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>Dynamics 365 for Operations 1611 és platform update 3

### <a name="aeb-payment-formats-for-spain"></a>Spanyol AEB fizetési formátumok

A Consejo Superior Bancario fizetési formátumok átutalási fájlok bankhoz történő küldésére voltak használatosak vevői és szállítói kifizetések esetén. Ezen formátumok tartalmát az Asociación Española de Banca határozta meg. A következőket fedi le: Cuaderno 19, 32, 58, 34.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                                  |
| **Felváltotta másik szolgáltatás?**   | Igen, az ISO20022 átutalási és beszedési formátumok Spanyolország esetében |
| **Érintett területek**         | Kötelezettség és kinnlevőség                                    |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.           |

### <a name="bank-payments-transfer-for-lithuania"></a>Banki átutalásos kifizetések Litvánia esetében

A banki átutalásos kifizetések létrehozása és nyomtatása a fizetési átutalás (LT) exportformátumban történt Litvánia vonatkozásában. A litván piac 2005-ben kezdte el a LITAS egységesített elektronikus bankrendszert használni.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Litvánia esetében     |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>BBS Direkte Remittering fizetési formátumok Norvégia esetében

A BBS Direkte Remittering fizetési formátumok a következőket tartalmazzák: vevői fizetés beszedésének exportálása (beszedési megbízás) és a válaszüzenet importálása.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.  |
| **Felváltotta másik szolgáltatás?**   | A Norvégiában rendelkezésre álló, AvtaleGiro vevői fizetési formátum használható beszedési megbízási üzenetek létrehozására. A visszaigazoló üzenetek importálása a jövőbeli kiadásokban kerül bevezetésre. |
| **Érintett területek**         | Kötelezettség és kinnlevőség   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>Számlatükör eszköz Spanyolország esetében

Ez az eszköz akkor használatos, ha a számlatükör esetében jelentős változtatásokra van szükség Spanyolországban. A felhasználók importálhatják az új számlatükröt Microsoft Excel- vagy szöveges formátumban, valamint importálhatják a pénzügyi kimutatásokat is.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Korlátozott felhasználás                                                  |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                             |
| **Érintett területek**         | Főkönyv                                                 |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="dom80-payment-format-for-belgium"></a>Belga Dom80 fizetési formátum

Hagyományos fizetési formátum fizetés beszedéséhez (beszedési megbízási).

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                          |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO 20022 beszedési megbízási fizetési formátum Belgium esetében.         |
| **Érintett területek**         | Kinnlevőségek                                            |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="dtaezag-payment-formats-for-switzerland"></a>DTA/EZAG fizetési formátumok Svájc esetében

A DTA/EZAG formátumok az ESR rendszer integrált részét alkotják, mert rendelkezhetnek hivatkozási számmal. Mivel a hivatkozási számok nem kötelezők, ezért bármilyen szállítói fizetés feldolgozható ezen formátumok használatával. Ezeket a formátumokat olyan vállalatok használják, amelyeknek a „Postfinance”-től eltérő helyen van bankszámlája.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Svájc esetében   |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>EDIFACT-DIRDEB fizetési formátum Ausztria esetében.

EDIFACT-DIRDEB fizetési formátum fizetés beszedéséhez (beszedési megbízás).

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                          |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO 20022 beszedési megbízási fizetési formátum Ausztria esetében         |
| **Érintett területek**         | Kinnlevőségek                                            |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="edivat-for-belgium"></a>EDIVAT Belgium esetében

EDIVAT a biztonságos levelezésen keresztüli elektronikus nyilatkozat elavult belga szabványa. A Microsoft Dynamics AX 2012 megtartja a csak olvasható megoldást annak érdekében, hogy a régebbi adatokhoz hozzá lehessen férni.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez a funkció már nincs használatban.                           |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                             |
| **Érintett területek**         | Főkönyv                                                 |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>eGiro EDIFACT CREMUL fizetési importformátum Norvégia esetében

Az eGiro az ENSZ EDIFACT CREMUL (Multiple Credit Advice Message) nemzetközi szabványon alapszik, amely a vevői kifizetések automatikus feladásához használatos. A Microsoft Dynamics AX alkalmazásban az eGiro vevői fizetési importformátumként van megvalósítva.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                                                     |
| **Felváltotta másik szolgáltatás?**   | Szám A formátum helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| **Érintett területek**         | Kinnlevőségek                                                                       |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                            |

### <a name="external-inventory-for-poland"></a>Külső készlet Lengyelország esetében

Szállítótól beszerzés nélkül, értékesítésre átvett áruk bizonylata. A külső készleten kezelt áruk, amelyek a normál készletet nem érintik, és automatikusan eladhatóak, majd később megvásárolhatók. Ez a folyamat tényleges készletmozgást hoz létre.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Másik szolgáltatás váltotta fel                                    |
| **Felváltotta másik szolgáltatás?**   | Igen, a bejövő szállítmány alapfunkciója                |
| **Érintett területek**         | Kötelezettségek, készletkezelés                         |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="financial-reports-generator-for-eastern-europe"></a>Pénzügyi beszámolók létrehozása Kelet-Európa esetében

Egy eszköz szolgál a könyvelési és adójelentések adatgyűjtésének beállításához és az adatok XLS vagy DOC jelentéssablonba való exportálásához

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Korlátozott felhasználás                                                                            |
| **Felváltotta másik szolgáltatás?**   | Szám Az eszközt elektronikus jelentési konfigurációk fogják leváltani a jövőbeli kiadásokban. |
| **Érintett területek**         | Főkönyv                                                                           |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Vevői kifizetési tranzakciók importálása Finnország esetében

Kiválaszthat egy olyan importálási formátumot a finn fizetésekhez, amely a vevői kifizetési tranzakciókat importálja egy bank által biztosított külső fájlból.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                                                     |
| **Felváltotta másik szolgáltatás?**   | Szám A formátum helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| **Érintett területek**         | Kinnlevőségek                                                                       |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>A Finnországra vonatkozó fizetési tranzakciók importálása a főkönyvi naplóba

Finnországra vonatkozó, specifikus formátum, amellyel könyvelési tranzakciók importálhatóak a főkönyvbe.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                                                     |
| **Felváltotta másik szolgáltatás?**   | Szám A formátum helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| **Érintett területek**         | Kinnlevőségek                                                                       |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integráció az Isabel-hez szinkronizált (CIS) rendszerekkel Belgium esetében

Az Isabel az elektronikus banki ügyintézés európai rendszere, Belgiumban de facto szabványnak minősül.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az Isabel-klienssel való integráció már nincs forgalomban.   |
| **Felváltotta másik szolgáltatás?**   | Szám A már nem használt fizetési formátumok helyébe ISO20022 átutalási fizetési formátum lépett Belgium esetében. |
| **Érintett területek**         | Kötelezettségek     |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>A számlatükör és a számviteli szabályok módosulása Spanyolország esetében

Ez a funkció a számlatükör és a számviteli szabályok változásaihoz használatos Spanyolországban esetében. Leképezi a számlákat, hogy segítsen a régi számlatükröt az új számlatükörré alakítani, és összehasonlítja az előző pénzügyi évet az új pénzügyi évvel még akkor is, ha azokhoz eltérő számlaszámokat rendeltek.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Korlátozott felhasználás                                                  |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                             |
| **Érintett területek**         | Főkönyv                                                 |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Pagamento Fornittori szállítói fizetési formátum

Hagyományos olasz fizetési formátum átutalásokhoz.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátum már nem használható.                          |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Olaszország esetében         |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="payment-export-formats-for-estonia"></a>Kifizetésexportálás formátuma Észtország esetében

Banki fizetés exportálása a Telehansa és Teleservice formátumot használja.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Észtország esetében       |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="payment-file-archive-for-norway"></a>Fizetési fájlarchívum Norvégia esetében

Amikor fizetési fájlok jönnek létre, a fájlarchívum automatikusan archivál minden létrehozott fájlt, még akkor is fájlokat korábban írták vagy olvasták.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Másik szolgáltatás váltotta fel                                        |
| **Felváltotta másik szolgáltatás?**   | Igen. Elektronikus jelentéskészítési archivált feladatok                            |
| **Érintett területek**         | Kötelezettségek, kinnlevőségek, a szervezet felügyelete |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.     |

### <a name="payment-import-formats-for-estonia"></a>Kifizetésimportálás formátuma Észtország esetében

Banki fizetés importálása a TeleTeenus formátumot használja.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                                                    |
| **Felváltotta másik szolgáltatás?**   | Szám A formátumok helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| **Érintett területek**         | Kinnlevőségek                                                                        |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                             |

### <a name="payroll-information-in-human-resources"></a>Bérlistaadatok az Emberi Erőforrásokban

Emberi Erőforrások Bérlistaadatai

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezt a funkciót az alapvető Bérlista és az Emberi Erőforrások lapokok váltotta fel.  |
| **Felváltotta másik szolgáltatás?**   | A **Juttatások** és a **Bevételek** oldalakon, valamint az egyéb kapcsolódó, korábban az amerikai Bérszámfejtésben levő oldalakon újrakonfigurálást végeztünk, így ezek most az Emberi erőforrások alapkonfiguráció részei, ezért a külső bérlisták feldolgozását segítik. Ez a funkció a **Humán Erőforrások 1** \> **Bérlista**-konfigurációs kulcs használatával érhető el. |
| **Érintett területek**         | Emberi Erőforrások, Bérlista   |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Operations 1611 verziójától kezdve.    |

### <a name="performance-management-goal-workflow"></a>Teljesítménymenedzsment, célok munkafolyamata

A teljesítménymenedzsment a célok kezelését tartalmazza, és integrálja a teljeseítményellenőrzést.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A teljesítménymenedzsment át lett tervezve, és a célok oldalainak száma csökkent a folyamat egyszerűsítése érdekében.                 |
| **Felváltotta másik szolgáltatás?**   | Szám A célok láthatók a vezetők számára az Vezetők önkiszolgáló portálján; ezeket a vezető módosíthatja és megtekintheti. |
| **Érintett területek**         | Emberierőforrás-menedzselés       |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Operations 1611 verziójától kezdve.    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>PostGirot és a Postgirot Utland fizetési formátumok Svédország esetében

PostGirot és a Postgirot Utland fizetési formátumok Svédország esetében.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Svédország esetében        |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="radio-frequency-identifier"></a>Rádiófrekvenciás azonosító

A rádiófrekvenciás azonosítás (Radio Frequency Identification – RFID) egy olyan adatgyűjtési technológia, amely az azonosítási adatok tárolásához elektronikus címkéket használ, az azonosítási adatok beolvasásához pedig nem közvetlen rálátású olvasót.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony vevői használat és korlátozott szolgáltatáskészlet.   |
| **Felváltotta másik szolgáltatás?**   | Nincs                                              |
| **Érintett területek**         | Készletgazdálkodás                            |
| **Állapot**                         | Eltávolítva az Dynamics 365 for Operations 1611-es verziójától kezdve. |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Állami számlák számozására vonatkozó jelentés Lettország esetében

A lett jogszabályok szigorú szabályokat írnak elő az értékesítési számlák számozására vonatkozóan. A funkciók segítségével egyedi számokat lehet az értékesítési számlákhoz rendelni, a felhasználó vagy felhasználói csoport alapján. Ezután lehet létrehozni egy jelentést vagy egy XML-fájlt. A felhasznált számlaszámokról jelentést is lehet nyomtatni.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az állami számlák számozását már nem kell fenntartani. A felhasznált számlaszámokra vonatkozó jelentésre már nincs szükség. |
| **Felváltotta másik szolgáltatás?**   | Nincs       |
| **Érintett területek**         | Kinnlevőségek    |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Valamely vállalat vezetője és főkönyvelője nevének beállítása Litvánia esetében

A vállalat vezetőjének és főkönyvelőjének nevét a vállalati adatok között lehet megadni, és fel lehet használni különböző, helyi nyomtatott jelentésekben.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Másik szolgáltatás váltotta fel                                     |
| **Felváltotta másik szolgáltatás?**   | Igen, a tisztviselők beállítása ugyanerre a célra használható.   |
| **Érintett területek**         | Kötelezettségek, Kinnlevőségek, Készpénz- és bankkezelés |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |

### <a name="shipping-carrier-interface"></a>Szállítmányozói felületek

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Máshol már meglévő funkció   |
| **Felváltotta másik szolgáltatás?**   | A szállításkezelés részlegesen lecserélte |
| **Érintett területek**         | Értékesítés és marketing, Készletkezelés  |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Operations 1611 verziójától kezdve.  |

### <a name="telepay-payment-formats-for-norway"></a>TelePay fizetési formátumok Norvégia esetében

TelePay fizetési formátumok közé tartozik a szállítói fizetés exportálása (átutalás) és a vevői kifizetési gyűjtemény (beszedési megbízás).

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                                                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum és AvtaleGiro vevői kifizetési formátum Norvégia esetében |
| **Érintett területek**         | Kötelezettség és kinnlevőség                                                          |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>Szállítói fizetésexportálási formátumok Finnország esetében

Finnországban két formátum érhető el fizetések exportálásához. LM02 (FI) belföldi fizetésekhez használható, az LUM2 (FI) pedig külföldi fizetésekhez.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fizetési formátumok már nem használhatók.                        |
| **Felváltotta másik szolgáltatás?**   | Igen, ISO20022 átutalási fizetési formátum Finnország esetében       |
| **Érintett területek**         | Kötelezettségek                                               |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="warehouse-management-ii"></a>Raktárkezelés II

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A korábban a **Készletkezelés** modulban elérhető Raktárkezelés II megoldás (WMS II) ugyanazokkal a funkciókkal rendelkezik, mint a Microsoft Dynamics AX 2012 R3 verzióban kiadott **Raktárkezelés** modul.                                                                         |
| **Felváltotta másik szolgáltatás?**   | Az AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 és Dynamics AX 2012 R3 CU9 verziókban kiadott **Raktárkezelés** modul váltja fel a Raktárkezelés II szolgáltatást. Az új modul több speciális funkcióval és rugalmasabb raktárkezelési folyamatokkal rendelkezik, mint a Raktárkezelés II funkció. |
| **Érintett területek**         | Készletkezelés, értékesítés és marketing, beszerzés és forrás   |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Operations 1611 verziójától kezdve.    |

### <a name="worker-reminders-in-human-resources"></a>Dolgozói emlékeztetők az Emberi Erőforrásokban

Emberi Erőforrások Bérlistaadatai

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony használat                                                           |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                                  |
| **Érintett területek**         | Emberi erőforrások                                                     |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Operations 1611 verziójától kezdve |

### <a name="workflow-for-creating-goals"></a>Célok létrehozásának munkafolyamata

A munkavállalók céljai létrehozásának kezelésére vonatkozó munkafolyamat a számos olyan munkafolyamat egyike, amely rendelkezésre állt a teljesítménykezelési folyamat koordinálásának elősegítésére.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A teljesítménykezelést teljesen újraterveztük a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban.     |
| **Felváltotta másik szolgáltatás?**   | Az átalakított teljesítménymendzsment funkciója segítségével jobban lehet felügyelni a célok tartalmát, az előrehaladás nyomon követéséhez használt méréseket és a kiegészítő dokumentumok csatolását. A célok sablonként tárolhatók, és ezután újra felhasználhatók. Ezen funkció segítségével gyorsabban beállíthatók további célok az alkalmazottak számára. |
| **Érintett területek**         | Emberierőforrás-menedzselés                 |
| **Állapot**                         | Eltávolítva a Dynamics 365 for Operations 1611 verziójától kezdve. |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Szállítói számla módosításainak érvénytelenítésére vonatkozó képesség

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Teljesítménynövekedés.        |
| **Felváltotta másik szolgáltatás?**   | Nincs                             |
| **Érintett területek**         | Kötelezettségek               |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve. |

### <a name="aif-axd-and-axbc-integrations"></a>AIF, AxD és AxBC integrációja

Az Alkalmazásintegrációs keretrendszerben (AIF-ben) adatok cserélhetőek ki külső rendszerekkel, szolgáltatásként kitett üzleti logikán keresztül. A Dynamics AX dokumentumokon és .NET Business Connector-on (AxBC) alapuló szolgáltatásokat tartalmaz. Dokumentumok XML használatával hozhatóak létre. Az XML által tartalmazott fejlécadatok hozzáadásával *üzenet* hozható létre, amely a Dynamics AX rendszerbe vagy rendszerből átvihető. Dokumentumok például az értékesítési rendelések és a beszerzési rendelések. Azonban szinte minden entitást (például vevőt) képviselhet dokumentum. A dokumentumokon alapuló szolgáltatások az **Axd \<Document\>** osztályokat használják.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az AIF és az AxD-k architektúráját nem sikerült felhőszolgáltatáshoz méretezni. A tömeges importálás során teljesítményproblémák léptek fel.                                        |
| **Felváltotta másik szolgáltatás?**   | Ezt a szolgáltatást felváltotta az Adatimportálási és -exportálási keretrendszer, amely támogatja az ismétlődő tömeges importálást/exportálást. AxBC esetén a tényleges táblák használatát javasoljuk. |
| **Érintett területek**         | AxD-k, AxBC-k és AIF   |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.   |

### <a name="billing-code-rate-scripts"></a>Számlázási kód díjalap parancsfájljai

Számlázási parancsfájlok számlázási kódokhoz tartozó számlázási díjak kiszámításához használatosak. Ezekhez a parancsfájlokhoz egyéni fejlesztés volt szükséges C# vagy Visual Basic programozási nyelvben. A Dynamics AX aktuális verziójában a **Számlázási kód díjalap parancsfájljai** nem támogatottak.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az egyéni C# vagy Visual Basic parancsfájlok támogatása nem elérhető a Dynamics AX 7.0-s verzióban. |
| **Felváltotta másik szolgáltatás?**   | Nem                                                                                      |
| **Érintett területek**         | Állami szektor, kinnlevőségek                                    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.                                                          |

### <a name="boms-without-bom-versions"></a>Anyagjegyzékek Anyagjegyzék-verziók nélkül

Korábban az **Anyagjegyzék-verziók** konfigurációs kulcs letiltásakor, az anyagjegyzék-verziók (BOM) minden képernyőn rejtett állapotba kerültek, és a rendszer kötelezővé tette a kiadott termékek és anyagjegyzékek közti 1:1 arányú kapcsolatot. A Dynamics AX jelenlegi verziójában az **Anyagjegyzék-verziók** konfigurációs kulcsot nem lehet letiltani.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Anyagjegyzék-verziók konfigurációs kulcsokkal való vezérlése nem méretezhető felhő környezetre. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                                                      |
| **Érintett területek**         | Termékinformációk kezelése, Készletkezelés                                    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.                                                          |

### <a name="brazilian-bordero"></a>Brazil borderó

Egyedi fizetési mód brazil vállalatok esetében

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Brazil borderó fizetési mód támogatása már nem része a brazil honosításnak |
| **Felváltotta másik szolgáltatás?**   | Nincs   |
| **Érintett területek**         | Kötelezettségek   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="brazilian-sintegra-statement"></a>Brazil Sintegra kivonat

Szövetségi adókimutatás az ICMS adó esetében

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez a kimutatás már nem alkalmazható néhány brazil államban. |
| **Felváltotta másik szolgáltatás?**   | Szám A felhasználók általános elektronikus jelentési eszközt használhatnak a kimutatás beállításához, ha arra bizonyos helyzetekben szükség van. |
| **Érintett területek**         | Pénzügyi könyvek    |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Brazil SCAN készenléti mód az NF-e esetében

A (SCAN) készenléti környezet a Nota Fiscal eletrônica (NF-e) állapotának előállítására, exportálására és importálására szolgál, amikor nem érhető el a Secretaria da Fazenda (SEFAZ) környezet.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez a készenléti módszer már nem alkalmazható minden brazil államban |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                                          |
| **Érintett területek**         | Kinnlevőségek                                                         |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.              |

### <a name="business-analyzer"></a>Business Analyzer

Ez a mobilalkalmazás lehetővé teszi a felhasználók számára a kulcsfontosságú üzleti mutatók áttekintését.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezt a szolgáltatást egy másik szolgáltatás váltotta fel.   |
| **Felváltotta másik szolgáltatás?**   | A Microsoft Power BI Pénzügyi teljesítményfigyelő tartalmi csomagja magába foglalja a Business Analyzer alkalmazásban korábban elérhető kulcsfontosságú üzleti mutatókat. |
| **Érintett területek**         | Főkönyv      |
| **Állapot**                         | Elavult: Az üzleti elemző elavult.    |

### <a name="business-statistics"></a>Üzleti statisztikák

Üzleti statisztikai lekérdezések beállítása, amelyek segítségével elemezhető a szervezet teljesítménye.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Üzleti intelligencia (BI) elavult megközelítése, alacsony vevői használat és a korlátozott szolgáltatási kör. |
| **Felváltotta másik szolgáltatás?**   | Új Üzleti Intelligencia megoldások a Dynamics AX jelenlegi verziójában                                      |
| **Érintett területek**         | Beszerzés és forrás, Kötelezettségek, Értékesítés és marketing, Kinnlevőségek         |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>A Számla-jóváhagyási naplóban található Dokumentum dátumának módosítása funkció

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony használat                                                               |
| **Felváltotta másik szolgáltatás?**   | Igen. A feladott szállítói tranzakció dokumentumdátuma módosítható. |
| **Érintett területek**         | Kötelezettségek                                                        |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>A holland ClieOp03 fizetési formátum

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A formátum már nem alkalmazható Hollandiában, mivel azt felváltotta a SEPA funkció. |
| **Felváltotta másik szolgáltatás?**   | SEPA exportkifizetések  |
| **Érintett területek**         | Minden modul     |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |

### <a name="compliance-center"></a>Megfelelési Központ

A Megfelelési Központ egy Enterprise Portal webhely volt, amely a Sarbanes-Oxley törvénnyel kapcsolatos megfelelési kezdeményezések dokumentációs követelményeinek kezelésére szolgált.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Vevői használat hiánya. A Microsoft SharePoint magában foglalja ugyanazt a képességet, ami korábban a Megfelelési Központban volt elérhető. |
| **Felváltotta másik szolgáltatás?**   | Nincs   |
| **Érintett területek**         | Megfelelés és belső ellenőrzés  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.    |

### <a name="connector-for-microsoft-dynamics"></a>Csatlakozó a Microsoft Dynamics szolgáltatáshoz

Ezzel az eszközzel integrálták a Microsoft Dynamics CRM rendszerből származó kulcsadatokat a Microsoft Dynamics ERP alkalmazásokba.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezt a szolgáltatást egy másik szolgáltatás váltotta fel. |
| **Felváltotta másik szolgáltatás?**   | Common Data Service                                      |
| **Érintett területek**         | Csatlakozó a Microsoft Dynamics szolgáltatáshoz                         |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Tárolóegység és a készleten lévő több dimenzió

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Máshol már meglévő funkció |
| **Felváltotta másik szolgáltatás?**   | Igen. Az AX 2012 óta, ezt a funkciót az összesített kötegrendelések szolgáltatáskészlet váltotta fel. Ez a szolgáltatáskészlet tartalmazza az egyesített készletnézetet. |
| **Érintett területek**         | Termékinformációk kezelése, Gyártásvezérlés, Készletkezelés, Értékesítés és marketing  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve. |

### <a name="cue-group-metadata"></a>Kötegcsoport-metaadatok

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Kötegcsoportok használatával korábban egy vagy több Köteget lehetett megjeleníteni az Adatterületen. A feltöltés korlátozottsága mellett teljesítményproblémák is felléptek, mivel egy szülőűrlapon történő rekordváltoztatás a Kötegcsoport minden egyes Kötegéhez létrehozott egy lekérdezést. |
| **Felváltotta másik szolgáltatás?**   | Nincs      |
| **Érintett területek**         | Minden modul    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.  |

### <a name="cue-metadata"></a>Köteg-metaadatok

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A köteg-metaadatok információk számlálására vagy összesítésére korlátozódtak.    |
| **Felváltotta másik szolgáltatás?**   | Annak érdekében, hogy a modellezéshez nagyobb rugalmasságot biztosítsunk, bevezettük a csempe-metaadatokat. Modellezhet például aktuális számlálókat, navigációt, valamint fő teljesítménymutatókat (KPI-ket). A Köteg-metaadatokat közvetlenül helyettesítik a Csempeszámláló metaadatai. |
| **Érintett területek**         | Minden modul           |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve      |

### <a name="danish-check-format"></a>Dán csekkformátum

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A dán csekkformátum elrendezésének támogatása megszűnt, a jelentést eltávolítottuk a dán honosításból. |
| **Felváltotta másik szolgáltatás?**   | Nincs    |
| **Érintett területek**         | Minden modul    |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |

### <a name="data-partitions"></a>Adatpartíciók

Az adatpartíciók az adatok logikus elkülönítését biztosítják a Microsoft Dynamics AX adatbázisában.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az adatpartíciókat a Microsoft Dynamics AX 2012 R2 változatában vezették be adatok elkülönítéséhez. Általános esetben a vállalat leányvállalatokkal rendelkezik, és egy leányvállalat adatait nem láthatja egy másik leányvállalat, annak ellenére, hogy mindkét leányvállalatot azonos informatikai részleg kezeli. Azonban további parancsfájlok és kezelési többletköltség voltak szükségesek új partíciók létrehozására és azok adatokkal való feltöltésére, és a partíció adatainak biztonsági mentésére. A felhőben, ahol hozzáférésünk van platformhoz mint szolgáltatáshoz (PaaS), adatbázis-szolgáltatáshoz (Microsoft Azure SQL Database), sokkal hatékonyabb az adatbázist elkülönítési tárolóként használni, mint a elkülönítést végezni a programon belül. Függetlenül attól, hogy adatpartíció szükségesek leányvállalatoknak, több bérlőnek vagy csak mérlegelésre, úgy véljük, hogy az esetek jobban kezelhetők több Finance and Operations példánnyal. |
| **Felváltotta másik szolgáltatás?**   | Az adatpartíciókat használó vevőknek a Finance and Operations több példányát kell használniuk, ha az adatbázis szintű elkülönítése kritikus fontosságú.    |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.  |


### <a name="database-and-file-share-storage-for-attachments"></a>Adatbázis és fájlmegosztás tárolása a mellékletek számára

A Microsoft Dynamics AX 2012 lehetővé tette a mellékletek tárolását az adatbázisban és a fájlmegosztásokban. Ezek a lehetőségek a továbbiakban nem támogatottak.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A fájlmegosztással történő tárolás a továbbiakban már nem támogatott, mert a felhőalapú tárolási környezet nem tud kommunikálni a helyi fájlmegosztásokkal. Az adatbázia-alapú tárolás helyére az Azure Blob-tárolás lépett. Az Azure Blob-tárolás megegyezik az adatbázisban való tárolással, mivel a dokumentumok elérése csak a Dynamics 365 for Finance and Operations ügyfélképernyőkön keresztül történhet. Ez a megoldás azzal a plusz előnnyel jár, hogy olyan tárhelyet kínál, amely nem befolyásolja negatívan az adatbázis teljesítményét. A Blob-tárolás a dokumentumkezelés alapértelmezett tárolási mechanizmusa, és azonnal működik. |
| **Felváltotta másik szolgáltatás?**   | Az adatbázia-alapú tárolás helyére az Azure Blob-tárolás lépett.   |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.   |

### <a name="delimitation"></a>Elválasztás

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A funkció hasznossága nem mutatható ki. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                     |
| **Érintett területek**         | Munkaidő és jelenlét                    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.         |

### <a name="desktop-client"></a>Asztali ügyfél

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Dynamics AX ügyfél felhasználói felületét a több platformon és eszközön való jobb felhasználhatóság érdekében újraterveztük.                      |
| **Felváltotta másik szolgáltatás?**   | Az új webes ügyfél az asztali képernyő metaadatain és programozási modelljén alapul, amelyeket egy multimédiás webes platform szolgáltatása érdekében módosítottunk. |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.   |

### <a name="direct-database-connection"></a>Közvetlen adatbázis-kapcsolat

A Dynamics AX 2012 R3 rendszerben a Retail Modern POS az Enterprise POS rendszerhez hasonló módon, közvetlenül tudott kapcsolódni a csatorna-adatbázishoz. Ez ráadás volt a Retail Modern POS Retail Server kiszolgálón keresztüli kommunikációjához használt szokásos kommunikációs módja mellett.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A közvetlen adatbázis-kapcsolathoz alacsonyabb szintű biztonsági protokollok voltak szükségesek, és elsődleges használati célja a legmagasabb szintű teljesítmény elérése volt. A Finance and Operations teljesítménybeli és biztonsági fejlesztései következtében ez a funkció több problémát okoz, mint amennyit megold. |
| **Felváltotta másik szolgáltatás?**   | Szám Jelenleg csak a szabványos Retail Server által biztosított kommunikáció támogatott.  |
| **Érintett területek**         | Csatorna-adatbázis/Retail Modern POS   |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.  |

### <a name="dutch-swift-mt940"></a>Holland SWIFT MT940

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A honosított funkció helyett már az általános funkció használatos.                    |
| **Felváltotta másik szolgáltatás?**   | Igen, ezt a funkciót a Továbbfejlesztett banki egyeztetés funkció váltotta fel. |
| **Érintett területek**         | Minden modul                                                                              |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL, Németország)

Ez a funkció az eXtensible Business Reporting Language (XBRL) kimenetet biztosítja, amely kifejezetten a német eBilanz rendszertan részére lett szánva.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Vevői használat hiánya.  |
| **Felváltotta másik szolgáltatás?**   | Ezt a szolgáltatást nem váltotta fel másik, azonban számos speciális, széles körű XBRL funkciókat magában foglaló XBRL csomag érthető el a német piac számára. |
| **Érintett területek**         | Management Reporter      |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.  |

### <a name="enterprise-portal-client"></a>Enterprise Portal-ügyfél

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Egy együgyfeles platform biztosított.  |
| **Felváltotta másik szolgáltatás?**   | Az új webes ügyfél az asztali képernyő metaadatain és programozási modelljén alapul, amelyeket egy multimédiás webes platform szolgáltatása érdekében módosítottunk. |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.   |

### <a name="environmental-sustainability"></a>Környezeti fenntarthatóság

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony vevői használat és korlátozott szolgáltatáskészlet.  |
| **Felváltotta másik szolgáltatás?**   | Nincs              |
| **Érintett területek**         | Megfelelés és belső ellenőrzés, Kötelezettségek  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve. |

### <a name="form-activex-and-managed-host-controls"></a>ActiveX és Felügyelt Állomás vezérlők

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az ActiveX és Felügyelt Állomás vezérlők a már megszűnt asztali ügyfélen alapulnak. |
| **Felváltotta másik szolgáltatás?**   | A bővíthető vezérlési keretrendszer támogatja új, HTML-, CSS- és JavaScript-alapú vezérlések kiépítését, továbbá Microsoft Visual Studio Tooling környezetben elsőrangú vezérlő. |
| **Érintett területek**         | Minden modul     |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.       |

### <a name="generate-prenotes-by-using-a-batch"></a>Ellenőrző tranzakciók létrehozása a köteg használatával

Előjegyzés létrehozás nem lehetséges köteg használatával, azonban a felhasználó által továbbra is végrehajtható.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Nem létezik olyan képernyő, amely a köteg használatával létrehozott előjegyzési fájl tárolására és megjelenítésére alkalmas lenne. |
| **Felváltotta másik szolgáltatás?**   | Előjegyzések továbbra is létrehozhatók, ekkor a fájl mentésének helyét a felhasználó állíthatja be.   |
| **Érintett területek**         | Kötelezettségek, Kinnlevőségek, Készpénz- és bankkezelés  |
| **Állapot**                         | Eltávolítva az AX 7.0-es verziójától kezdve.    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Német DTAUS kifizetési export és számlakivonat-import (összegek és tranzakciók)

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A formátum már nem alkalmazható Németországban, mivel azt felváltotta a SEPA funkció.                    |
| **Felváltotta másik szolgáltatás?**   | Igen, ez a funkció le lett cserélve a SEPA kifizetési export és a továbbfejlesztett banki egyeztetés funkciókra a számlakivontok importálásához. |
| **Érintett területek**         | Minden modul  |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="german-dtazv-payment-format"></a>Német DTAZV fizetési formátum

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A formátum már nem alkalmazható Németországban, mivel azt felváltotta a SEPA funkció. |
| **Felváltotta másik szolgáltatás?**   | SEPA exportkifizetések    |
| **Érintett területek**         | Minden modul   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.    |

### <a name="german-mt940-import"></a>Német MT940 importálása

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A honosított funkció helyett már az általános funkció használatos.                    |
| **Felváltotta másik szolgáltatás?**   | Igen, ezt a funkciót a Továbbfejlesztett banki egyeztetés funkció váltotta fel. |
| **Érintett területek**         | Minden modul                                                                              |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.                           |

### <a name="german-xml-eu-sales-list"></a>Német XML-formátumú EU Értékesítési lista

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Német EU Értékesítési Lista jelentés XML-formátuma, már nem támogatott. Csak az ELMA5 szövegfájl formátumban lehet a Német Adóhivatal számára jelenteni az EU értékesítési lista jelentést. |
| **Felváltotta másik szolgáltatás?**   | Nincs         |
| **Érintett területek**         | Adó        |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.   |

### <a name="gl-ssrs-reports"></a>GL SSRS-jelentések

A következő menüpontokat tartalmazó jelentések eltávolításra kerültek: **Összegző főkönyvi kivonat**, **Részletes főkönyvi kivonat**, **Számlatükör**, **Könyvvizsgálati ellenőrzés**, **Egyenlegek** és **Egyenleglista**.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Microsoft SQL Server Reporting Services (SSRS) pénzügyi jelentéseket felváltották a Management Reporter funkciói és az alapértelmezett jelentések. |
| **Felváltotta másik szolgáltatás?**   | Management Reporter (a Dynamics AX jelenlegi verziójában **Pénzügyi jelentéskészítés** megjelöléssel)    |
| **Érintett területek**         | Főkönyv   |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.   |

### <a name="infopart-and-formpart-metadata"></a>InfoPart és FormPart metaadatai

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az InfoPart és FormPart metaadatok két különböző ügyfél számára engedélyezték Adatterületek létrehozását. |
| **Felváltotta másik szolgáltatás?**   | Fejlesztés után az InfoPart metaadatokat, amelyek egy egyszerűsített képernyődefiníciót adtak meg, Képernyővé alakítottuk. Fejlesztés után a FormPart metaadatokat, amelyek egy Képernyőre hivatkoztak, közvetlenebb hivatkozással váltottuk fel. |
| **Érintett területek**         | Minden modul    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.        |

### <a name="main-account-list-page"></a>Fő számla listaoldal

A jogi személy számláinak listája és kapcsolódó egyenleginformációk

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Az egyenleginformációk elérhetőek a **Főkönyvi kivonat** listaoldalon, számla és dimenzió szerint.  |
| **Felváltotta másik szolgáltatás?**   | A **Fő számlák** ugyanazt a számlalistát tartalmazza, amit korábban a **Fő számla** listaoldal. A **Fő számlák** rácsnézetével egy még kisebb, rácsszerű megjelenítés is elérhető. |
| **Érintett területek**         | Főkönyv      |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Malajziai és szingapúri banki pénzforgalmi jelentés

Ez a szolgáltatás olyan pénzforgalmi jelentés nyomtatását tette lehetővé a felhasználó számára, amelyen megjelentek a kiválasztott bankszámlák megadott dátumtartományához kapcsolódó tranzakciók, illetve a pénzbeáramlások és a pénzkiáramlások részletei.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ugyanezek az adatok a Banki tranzakció lekérdezéséből is beszerezhetőek. |
| **Felváltotta másik szolgáltatás?**   | A Banki tranzakció lekérdezése                                            |
| **Érintett területek**         | Készpénz- és bankkezelés                                                |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz.          |

### <a name="mexican-cfd-electronic-invoice"></a>Mexikói CFD elektronikus számla

Ez a funkció lehetővé tette a CFD módszerrel történő mexikói elektronikus számlák létrehozását, abban az esetben ha vállalat írja alá a számlát, valamint kérvényezi a kapcsolódó állami engedélyeket. Ez a szolgáltatás egy olyan havi jelentést is magában foglal, amely a periódusban kiadott összes elektronikus számlát tartalmazza.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A módszer már nem alkalmazható. Az adóhatóságok beszüntettették az elektronikus számlák CFD módszerrel való létrehozását. Ennek helyét a CFDI (Comprobante Fiscal Digital a través de Internet) módszer vette át, amelynek megfelelően egy külső szolgáltató (PAC) ír alá. A havi jelentést eltávolítottuk, a felhasználók egy lekérdezési lehetőség segítségével kérhetnek le előzménytranzakciókat. |
| **Felváltotta másik szolgáltatás?**   | Nincs    |
| **Érintett területek**         | Kinnlevőségek, Projekt   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="mexico-realized-and-unrealized-vat"></a>Mexikói realizált és nem realizált áfa

A Microsoft Dynamics AX 2012 a nem realizált áfát a Mexikó-specifikus nem realizált adó funkció használatával kezelte.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Máshol már meglévő funkció  |
| **Felváltotta másik szolgáltatás?**   | Igen, ezt a funkciót felváltotta az alapból biztosított standard feltételes áfa funkció. |
| **Érintett területek**         | Adó   |
| **Állapot**                         | Elavult: Az eltávolítási dátum nem lett beállítva ehhez a szolgáltatáshoz. |

### <a name="microsoft-outlook-integration"></a>Microsoft Outlook-integráció


|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ezt a szolgáltatást a Microsoft Exchange Server integrációja váltotta fel. |
| **Felváltotta másik szolgáltatás?**   | Igen                                                                            |
| **Érintett területek**         | Értékesítés és marketing                                                            |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Készlet- és raktárkezelési naplók személyes zárolása

A készlet- és raktárnaplók már nem támogatják naplók megjelölését egy kiválasztott felhasználó személyes tartalmaként. A naplók zárolásának folyamata csak felhasználócsoportok személyes tartalmaként, illetve szerkesztés alatt támogatott.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A funkció hasznossága nem mutatható ki. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                     |
| **Érintett területek**         | Készletgazdálkodás                   |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.         |

### <a name="product-builder"></a>Termékszerkesztő

A Termékszerkesztő használatával korábban értékesítési rendelésekből, beszerzési rendelésekből, termelési rendelésekből, értékesítési ajánlatokból projektajánlatokból vagy cikkszükségletekből származó cikkek dinamikus konfigurálására volt lehetőség. Egy modellezési változókkal rendelkező termékmodell alapján a felhasználó ki tudta választani a vevői követelményeknek megfelelő értékeket, valamint létre tudott hozni egy egyedi, anyagjegyzékkel és útvonallal rendelkező termékváltozatot.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Termékszerkesztő a végfelhasználók számára X++ kódot jelenített meg, a Dynamics AX jelenlegi verziójában nem támogatott. Az átfedő, nagy terjedelmű kódbázisok ismétlődő karbantartásainak elkerülése érdekében eltávolításra került.  |
| **Felváltotta másik szolgáltatás?**   | Igen. A megszorításon alapuló konfiguráció a Dynamics AX 2012 verzióban jelent meg, és már akkor megtörtént annak a bejelentése, hogy a Termékszerkesztő a későbbi verziókban elavulttá válik. A megszorításon alapuló konfigurációs technológia van kiválasztva az alaptermékekhez a konfiguráció engedélyezéséhez. További tudnivalókért lásd: [Termékkonfigurációs modell felépítése](../../supply-chain/pim/build-product-configuration-model.md). |
| **Érintett területek**         | Termékinformációk kezelése, Értékesítés és marketing  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.      |

### <a name="production-floor-app"></a>Termelési üzem alkalmazás
Ez az alkalmazás a Windows 8.1 RT és Windows 8.1 Pro rendszereket futtató táblagépekhez való.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A webalapú kliensre való váltásnak köszönhetően a natív Dynamics AX 7.0 kliensen keresztül is végrehajtható hasonló funkció. A Feladatkártya eszköze olyan termelési üzem felhasználói felületet biztosít, amely érintőképernyők és táblagép formátumú tényezőkre is optimalizálva van. |
| **Felváltotta másik szolgáltatás?**   | Igen. A Feladatkártya eszköze a Dynamics AX 7.0 natív része.                                                                           |
| **Érintett területek**         | Gyártásvezérlés                                                |
| **Állapot**                         | Elavult: A Microsoft Store-ból való eltávolítás dátuma még nem került meghatározásra ehhez a funkcióhoz.                                                |


### <a name="rename-product-dimension"></a>Termékdimenzió átnevezése

Ez a szolgáltatás lehetővé tette a három alap termékdimenzió egyikének (méret, szín vagy stílus) átnevezését egy olyan névre, amely jobban megfelel az üzleti követelményeknek. Az átnevezés kiterjedt minden olyan címkére, ahol megjelent a termékdimenzió neve.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Dynamics AX jelenlegi verziója nem támogatja címkék módosítását futtatás alatt. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                                                            |
| **Érintett területek**         | Termékinformációk kezelése                                                |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.                                                |

### <a name="retail-server-connectivity-using-http"></a>Retail Server kapcsolat ellenőrzése HTTP segítségével

A Dynamics AX 2012 R3 rendszerben a Retail Server a HTTP-kommunikáció (nem védett) használatával működött. Ez a szabványos HTTPS-t használó szokásos kommunikáció mellett működött.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Új biztonsági óvintézkedések következményeképpen kizárólag a TLS 1.2 (vagy az újabb, ha rendelkezésre áll) protokollt használó biztonságos kommunikáció támogatott. Az önkiszolgáló telepítő automatikusan konfigurálja a számítógépet ehhez a kommunikációs módhoz. |
| **Felváltotta másik szolgáltatás?**   | Szám Jelenleg csak a szabványos HTTPS által biztosított kommunikáció támogatott. |
| **Érintett területek**         | Kiskereskedelmi kiszolgáló  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve. |

### <a name="role-center-pages"></a>Szerepkör főoldalak lapjai

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Szerepkör főoldalak lapjai a már megszűnt Enterprise Portal platformra épültek, amelynek helyét a Dynamics AX jelenlegi verziójában az új webes ügyfélplatform vette át. |
| **Felváltotta másik szolgáltatás?**   | Az új Munkaterület képernyőminta folyamatközpontú tervezése egyszerű hozzáférést biztosít az adott folyamaton belül gyakran használt feladatokhoz.                       |
| **Érintett területek**         | Minden modul    |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve   |

### <a name="sales-tax-jurisdictions"></a>Áfailletékességek

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony vevői használat és korlátozott szolgáltatáskészlet. |
| **Felváltotta másik szolgáltatás?**   | Nincs                                           |
| **Érintett területek**         | Amerikai áfa                                 |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.               |

### <a name="sites-services"></a>Sites Services

Az Oldal Szolgáltatások lehetővé teszik olyan weboldalak megalkotását, melyek kiterjesztik az üzleti folyamatokat az internetre informatikai segítség nélkül.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Dynamics AX által használt Microsoft Azure infrastruktúra új helyettesítő lehetőségekkel rendelkezik (például Azure oldalakkal). |
| **Felváltotta másik szolgáltatás?**   | Nincs   |
| **Érintett területek**         | HR-toborzás, esetkezelés, ajánlatkérés, szállítóregisztrálás, lehetőségekhez és kampányokhoz tartozó együttműködési munkaterületek  |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.    |

### <a name="ssas-demand-forecasting-strategy"></a>SSAS igény-előrejelzési szolgáltatások

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A funkció kialakítása az új felhő architektúrában nem támogatható. |
| **Felváltotta másik szolgáltatás?**   | Azure gépi tanulási kereslet-előrejelzési stratégia                           |
| **Érintett területek**         | Alaptervezés                                                              |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Szállítói számlagyűjtő a feladási részletek nélkül

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony használat. Ezt a funkciót felváltotta a munkafolyamat funkcióval rendelkező Számlanapló. |
| **Felváltotta másik szolgáltatás?**   | A Számlanapló munkafolyamat funkciói.     |
| **Érintett területek**         | Kötelezettségek |
| **Állapot**                         | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.    |


### <a name="virtual-company-accounts"></a>Virtuális vállalati számlák

A virtuális vállalatok funkció már nem támogatott a Dynamics AX rendszerben. A virtuális vállalatok funkció lehetővé tette a felhasználók számára, hogy vállalatok egy csoportja által közösen használható táblákat állítsanak be. A szolgáltatás leírása itt található: [Vállalati számlák és Virtuális vállalati számlák](https://msdn.microsoft.com/library/aa834382(v=ax.10).aspx). A szolgáltatás úgy működik, hogy a táblákat gyűjteményekbe csoportosítja, ezeket pedig virtuális vállalatokhoz társítja. Utóbbiak létező, „valódi” vállalatok csoportjait jelentik. Lekérdezések jönnek létre, amelyek révén a virtuális vállalatban szereplő összes vállalat hozzáférhet a társított táblagyűjtemény tábláiban lévő adatokhoz.

|   |  | 
|------------|--------------------|
| **Elavulás/eltávolítás oka** | - A virtuális vállalatokat még az adatok táblákban való tárolása előtt be kell állítani. A virtuális vállalatok, már meglevő implementációra történő modernizálása nagyon nehézkes.<br><br>- Mivel a Dynamics AX jelenlegi verziójában rengeteg adatnormalizáció történt, igen nehézkessé vált átlátni azt, hogy a táblagyűjteményekhez mit szükséges hozzáadni. Például nehéz megállapítani, mely táblák kerüljenek megosztásra. A virtuális vállalatokban lévő táblákból hivatkozott összes egyéb táblát is hozzá kell adni. A táblanormalizáció miatt, még egy több táblában szétszóródó egyszerű alapadatot is a virtuális vállalat részévé kell tenni. Bármilyen itt történő hiba működési diszfunkciókat okozhat.<br><br>- Egy virtuális vállalat részét képező táblában elvesznek az adatok eredetére vonatkozó információk, és csak a virtuális vállalat kerül rögzítésre.   |
| **Felváltotta másik szolgáltatás?** | Globális táblák használatával a táblákat elérhetővé teheti az összes vállalatból. Jelenleg nincs helyettesítés. |   
| **Érintett területek**       | Minden modul |   
| **Állapot**                       | Eltávolítva a Dynamics AX 7.0-s verziójától kezdve.   |   

### <a name="windows-8-tablet-app"></a>Windows 8 táblagépes alkalmazás

A Windows 8-ra készült táblagépes alkalmazás lehetővé tette a költségbeírást és a jóváhagyást.

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Finance and Operations kompatibilis a táblagépekkel. A táblagépes alkalmazásra már nincs szükség.    |
| **Felváltotta másik szolgáltatás?**   | Szám          |
| **Érintett területek**         | Költséggazdálkodás   |
| **Állapot**                         | Eltávolítva: Ez a funkció csak a Dynamics AX 2012 R3 verzióban érhető el. |

### <a name="workplanner"></a>Munkatervező

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Alacsony használat |
| **Felváltotta másik szolgáltatás?**   | Nem, de a **Profilkapcsolat** lap (amely a **Profilcsoportok** oldalon nyitható meg), ugyan azt az üzleti forgatókönyvet támogatja, mint az elavult **Munkatervező** oldal. |
| **Érintett területek**         | Munkaidő és jelenlét     |
| **Állapot**                         | A kódot nem távolítottuk el. Azonban a JmgWorkPlanner űrlap nem lett áttelepítve.    |

### <a name="x-financial-statements"></a>X++ pénzügyi kimutatások

|                                                 |                                                                                                          |
|-------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <strong>Elavulás/eltávolítás oka</strong> |                         Ezt a szolgáltatást egy másik szolgáltatás váltotta fel.                         |
|  <strong>Felváltotta másik szolgáltatás?</strong>  | Management Reporter (a Dynamics AX jelenlegi verziójában <strong>Pénzügyi jelentéskészítés</strong> megjelöléssel) |
|     <strong>Érintett területek</strong>     |                                              Főkönyv                                              |
|             <strong>Állapot</strong>             |                                      Eltávolítva a Dynamics AX 2012-s verziójától kezdve                                      |

