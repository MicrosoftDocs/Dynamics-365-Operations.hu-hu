---
title: Munkavégzési helyszínek típusai
description: Ez a cikk azt ismerteti, hogy hozhatók létre a munkavégzési helyszínek típusai az Eszközkezelésben.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0468cb0b1717b7cf0ccb391da09a4e7d788124f3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812214"
---
# <a name="functional-location-types"></a>Munkavégzési helyszínek típusai

[!include [banner](../../includes/banner.md)]

 

Ez a cikk azt ismerteti, hogy hozhatók létre a munkavégzési helyszínek típusai az Eszközkezelésben. A munkavégzési helyszínek típusaival a munkavégzési helyszínek követelményei kezelhetők (például az eszközök munkavégzési helyszíneken történő telepítésének módja). Az adott típusú munkavégzési helyszínhez használható eszköztípusok és karbantartási tervek, a munkavégzési helyszínek attribútumai és az eszközattribútumok követelményei beállíthatók. Amikor új munkavégzési helyszínt hoz létre, meg kell adni a munkavégzési helyszín típusát.

>[!NOTE] 
>Ha munkavégzési helyszíneket szeretne használni, létre kell hoznia egy alapértelmezett munkavégzési helyszínt, amelyet csak új eszközök létrehozásához használ majd. Ehhez az alapértelmezett munkavégzési helyszínhez létre kell hoznia egy olyan alapértelmezett típust, ami kifejezetten egyszerű, és lehetővé teszi több eszköz telepítését az alapértelmezett munkavégzési helyszínen. A munkavégzési helyszínek beállításáról a [Munkavégzési helyszínek létrehozása](../functional-locations/create-functional-locations.md) című cikkben talál további információt.

## <a name="create-a-default-functional-location-type"></a>Munkavégzési helyszín alapértelmezett típusának létrehozása

Ez az eljárás bemutatja, hogyan hozható létre a munkavégzési helyszínek olyan alapértelmezett típusa, amelyet az alapértelmezett munkavégzési helyszínekhez használhat.

1. Válassza ki az **Eszközök kezelése** > **Beállítás** > **Munkavégzési helyszínek** > **Munkavégzési helyszínek típusai** lehetőséget.
2. Ha új típust szeretne létrehozni a munkavégzési helyszínekhez, válassza ki az **Új** lehetőséget.
3. Adja meg a munkavégzési helyszín típusának azonosítóját a **Munkavégzési helyszínek típusai** mezőben (például „Alapértelmezett”) és egy nevet a **Név** mezőben.
4. Válasszon ki egy életciklusmodellt a **Munkavégzési helyszín életciklusmodellje** mezőben.
5. A **Több eszköz** váltógombnál válassza az „Igen” lehetőséget, hogy több eszközt tudjon telepíteni ezzel a típussal egy munkavégzési helyszínen (az alapértelmezett munkavégzési helyszínen).

Ezzel létrejött a munkavégzési helyszín kizárólag alapértelmezett munkavégzési helyszínhez használható alapértelmezett típusa. A munkavégzési helyszín ezen alapértelmezett típusához ne adjon hozzá több követelményt vagy korlátozást.


## <a name="create-functional-location-types"></a>Munkavégzési helyszínek típusainak létrehozása

1. Válassza ki az **Eszközök kezelése** > **Beállítás** > **Munkavégzési helyszínek** > **Munkavégzési helyszínek típusai** lehetőséget.
2. Ha új típust szeretne létrehozni a munkavégzési helyszínekhez, válassza ki az **Új** lehetőséget.
3. Adja meg a munkavégzési helyszín típusának azonosítóját a **Munkavégzési helyszínek típusai** mezőben és egy nevet a **Név** mezőben.
4. Válasszon ki egy életciklusmodellt a **Munkavégzési helyszín életciklusmodellje** mezőben. A munkavégzési helyszínek életciklus-állapotairól és életciklusmodelljeiről a [Munkavégzési helyszín életciklus-állapotai](../setup-for-functional-locations/functional-location-stages.md) című témakörben talál további információt.
5. A **Több eszköz** váltógombnál válassza az „Igen” lehetőséget, ha azt szeretné, hogy több eszközt tudjon telepíteni egy munkavégzési helyszínen a munkavégzési helyszín ezen típusával. Ha a „Nem” lehetőséget választja ki, csak *egy* eszközt tud telepíteni egy munkavégzési helyszínen a munkavégzési helyszín ezen típusával.
6. Az **Eszközdimenzió frissítése** váltógombnál válassza az „Igen” lehetőséget, ha azt szeretné, hogy az ilyen típusú munkavégzési helyszíneken telepített eszközök automatikusan a munkavégzési helyszínnel összekapcsolt pénzügyi dimenziókat használják. Ez azt jelenti, hogy ha módosítja a pénzügyi dimenziókat a [Munkavégzési helyszínek létrehozása](../functional-locations/create-functional-locations.md) űrlapon, és a munkavégzési helyszín olyan típusú, amelynél „Igenre” állította a váltógombot, akkor a pénzügyi dimenziók automatikusan frissülnek az ehhez a munkavégzési helyszínhez telepített összes eszközön.
7. Az **Eszköztípus** mezőt akkor használja, ha automatikusan létre szeretne hozni *egy* eszközt az éppen létrehozott munkavégzési helyszínével egyező azonosítójú és nevű munkavégzési helyszínhez. Ez például akkor lehet lényeges, ha statikus munkavégzési helyszínt hoz létre (például épületet vagy csővezetéket). Ilyen esetben válassza ki azt az eszköztípust, amelyet az automatikusan létrehozott eszközhöz szeretne használni. Ne feledje, ha ebben a mezőben ad meg értéket, a **Több eszköz** váltógombot „Nem” értékűre kell állítani.
8. Az **Eszköztípusok** gyorslapon válassza ki azokat az eszköztípusokat, amelyeket össze szeretne kapcsolni a munkavégzési helyszín típusával. Válassza ki a **Sor hozzáadása** lehetőséget, majd az eszköztípusokat. Ha itt ad hozzá eszköztípusokat, csak az adott típusú eszközöket tudja majd telepíteni egy ilyen típusú munkavégzési helyszínen. Ha nem választ ki eszköztípust az **Eszköztípusok** gyorslapon, az összes típus telepíthető lesz.
9. A **Karbantartási tervek** gyorslapon válassza ki azokat a karbantartási terveket, amelyeket automatikusan be szeretne állítani az ilyen típusú munkavégzési helyszíneken. Válassza ki a **Sor hozzáadása** lehetőséget, majd a karbantartási terveket. Ha itt ad hozzá karbantartási terveket, csak azokat a terveket tudja majd használni az ilyen típusú munkavégzési helyszínen.
10. Az **Eszközattribútum követelményei** gyorslapon állítsa be azokat az eszközattribútumokat, amelyeket automatikusan be szeretne állítani az ilyen típusú munkavégzési helyszíneken. Válassza ki a **Sor hozzáadása** lehetőséget, majd az attribútumot. Az attribútum követelményei irányelvként szolgálnak. Nincsenek összevetve az eszközön beállított attribútumokkal (**Eszközök kezelése** > **Közös** > **Eszközök** > **Minden eszköz** > válasszon ki eszközt a listaoldalon > **Általános** lap > **Attribútumok** gomb). Az attribútumokra vonatkozó követelmények megjelennek, amikor eszközöket telepít munkavégzési helyszíneken.
11. Az **Engedélyezett típusok** gyorslapon válassza ki a munkavégzési helyszín azon típusait, amelyeknek érvényesnek kell lenniük a munkavégzési helyszínnek a munkavégzési helyszín kiválasztott típusát használó szülő típusával összekapcsolt altípusok esetében.
12. Az **Attribútumok** gyorslapon válassza ki a munkavégzési helyszín azon attribútumait, amelyeket automatikusan be szeretne állítani az ilyen típusú munkavégzési helyszíneken. Válassza ki a **Sor hozzáadása** lehetőséget, majd az attribútumot.


>[!NOTE] 
>Az **Általános** gyorslapon áttekintheti a munkavégzési helyszín típusához beállított eszköztípusok számát, karbantartási terveket, az eszközattribútumok követelményeit, az engedélyezett típusokat és a munkavégzési helyszíneket. A **Munkavégzési helyszínek** mezőben látható a munkavégzési helyszín típusát használó munkavégzési helyszínek száma. A **Másolás** gombbal átmásolhatja a munkavégzési helyszín típusának beállításait a munkavégzési helyszín kiválasztott típusába.
