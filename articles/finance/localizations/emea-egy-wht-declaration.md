---
title: Adóelőleg-bevallás Egyiptom számára
description: Ez a cikk bemutatja, hogy hogyan kell konfigurálni és létrehozni az adóelőleg-bevallásokat Egyiptomi számára.
author: AdamTrukawka
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.search.scope: ''
ms.openlocfilehash: 83def72f1ff0423d1c2d217847082fa9bf1c3bca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269374"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a>Adóelőleg-bevallás Egyiptom számára (EG-00005)

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a>Áttekintés
Ez a cikk bemutatja az adóelőleg-bevallás beállítását és előállítását, valamint az egyiptomi jogi személyek 41-es és 11-es űrlapja 41-es és 11-es adóelőleg-bevallásokat. 

Minden egyiptomi entitásnak elő kell készítenie a 41-es űrlapot, amely összegzi a helyi szállítóktól és szolgáltatóktól visszatartott adókat. A 41-es űrlapon kívül a 11-es űrlapot is létre kell hozni, amelyen a külföldi szolgáltatóktól származó visszatartott adót kell részletezni. 

**A** Dynamics 365 Pénzügy adóelőleg-bevallása a következő jelentéseket tartalmazza:

- Bevallás űrlapja, szám: 41
- Bevallás űrlapja, szám: 11
    
    
## <a name="prerequisites"></a>Előfeltételek
A jogi személy elsődleges címének Egyiptomban kell lennie.
Be kell kapcsolni a következő funkciókat a **Funkció kezelése** munkaterületen:

   - **Globális adóelőleg**

A funkciók engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

1. Lépjen az **Adó** > **Beállítás** > **Paraméterek** > **Főkönyvi paraméterek** pontra, majd az **Adóelőleg** lapon állítsa a **Globális adóelőleg engedélyezése** beállítást **Igen** értékre.
2. Az **Elektronikus jelentéskészítés** munkaterületen importálja az adattárból a következő elektronikus jelentési formátumokat:

    - WHT bevallás Excel (EG)

    > [!NOTE]
    > A fenti formátum az **Adóbevallás modellen** alapul, és az **Adóbevallási modell-leképezését** használja. Ezt a további konfigurációt a program automatikusan importálja.

További információért azzal kapcsolatosan, hogyan importálhat le Elektronikus jelentéstételi konfigurációkat, lásd: [Az elektronikus jelentéskészítési konfigurációk letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Elektronikus jelentéskészítési konfigurációk letöltése

Az Egyiptomra vonatkozó WHT bevallás űrlapjainak végrehajtása az elektronikus jelentéskészítési (ER) konfigurációkon alapul. A konfigurálható jelentésekkel kapcsolatos funkciókról és fogalmakról további információkat itt talál: [Elektronikus jelentéskészítés](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

A termelési és felhasználói elfogadási tesztelési (UAT) [környezetekben kövesse az elektronikus jelentéskonfigurációk letöltése a Lifecycle Services szolgáltatásból útmutatót](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Az adóelőleg-bevallás egyiptomi jogi személynél való létrehozásához fel kell töltenie a következő konfigurációkat:

- Adóbevallás modell.verzió.82.xml vagy újabb verzió
- Adóbevallás modell-leképezés.verzió.82.xml vagy újabb verzió
- WHT bevallás Excel (EG).verzió.82.21 vagy újabb verzió

Miután befejezte az ER-konfigurációk letöltését a Lifecycle Services (LCS) szolgáltatásból vagy a globális adattárból, kövesse az alábbi lépéseket.

1. Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** csempét.
1. A **Konfigurációk** lapon a műveleti ablaktáblában válassza az **Átváltás > Betöltés XML-fájlból** elemet.
1. Töltse fel az összes fájlt abban a sorrendben, amelyben az előző felsorolásban szerepelnek. Miután minden konfigurációt feltöltött, a konfigurációs fának jelen kell lennie a Finance rendszerben.

## <a name="set-up-application-specific-parameters"></a>Alkalmazásfüggő paraméterek beállítása

Az alkalmazásspecifikus paraméterek beállítással a felhasználók megszahatják, hogyan történjen az adótranzakciók osztályozása és kiszámítása a létrehozott jelentés egyes soraiban az **adóelőleg cikkcsoportjának** vagy a keresés definíciójában meghatározott egyéb feltételeknek megfelelően.

A 41-es adóelőleg-bevallás egy konkrét oszlopot tartalmaz, amelyben az adóelőleg-tranzakciót az adóhatóság **Engedmény kódjának típusa** nevű osztályozásának megfelelően kell osztályozni. Ahelyett, hogy ezeket az új osztályozásokat új bejegyzési adatként határoznák meg a tranzakciók feladása során, az osztályozásokat a **Konfigurációk** > **Alkalmazásspecifikus paraméterek** > **Beállítás** pontban bevezetett különböző keresések alapján határozzák meg az egyiptomi adóelőleg-jelentésekkel szemben támasztott követelményeknek való megfelelés érdekében. 

Az Adóelőleg-bevallás 41-es űrlapján a következő konfiguráció használatos a tranzakciók osztályozására:

- **DiscountTaxTypeLookup**-> 18. oszlop 

A következő lépések alapján beállíthatja a WHT bevallást és vonatkozó könyvekkel kapcsolatos jelentéseket generáló különféle kereséseket. 

1. Az **Elektronikus jelentéskészítés** munkaterületen a **Konfiguráció** > **Beállítás** kiválasztásával adja meg, hogy milyen szabályok szerint történjen a tranzakciók a WHT bevallási jelentésben való osztályozása. 
2. Válassza ki az aktuális verziót, és a **Keresések** gyorslapon válassza ki a keresési nevet. Például: **DiscountTaxTypeLookup**. Ez a keresés azonosítja az adóhatóság által előírt engedménytípusok listáját.
3. Válassza ki a **Feltételek** gyorslapon a **Hozzáadás** lehetőséget, és a **Keresés eredménye** oszlopban az új sorban válassza ki azt a kapcsolódó sort, amely a **18. oszlopban** található osztályozásnak felel meg.
4. Az **Adóelőleg – cikkcsoport** oszlopban válassza ki az osztályozás azonosításához használt kódot. Például: **Megengedett engedmény**.  
5. Ismételje meg a 3–4. lépést az összes elérhető kereséssel.
6. Válassza újra a **Hozzáadás** lehetőséget a végső rekordsor beemeléséhez, és a **Keresés eredménye** oszlopban válassza a **Nem alkalmazható** lehetőséget. 
7. A többi oszlopban válassza a **Nem üres** lehetőséget. 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a>Főkönyvi paraméterek beállítása

A WHT bevallás jelentéseinek Microsoft Excel alkalmazásban való létrehozásához definiáljon ER-formátumot a **Főkönyvi paraméterek** oldalon.

1. Lépjen az **Adó** > **Beállítás** > **Főkönyvi paraméterek** pontra.
2. Az **Adóelőleg** lapon a **WHT bevallás formátum-hozzárendelése** mezőben válassza a **WHT bevallás Excel (EG)** lehetőséget. Ha üresen hagyja ezt a mezőt, a normál áfajelentés SSRS-formátumban jön létre.


![Bevallás űrlapja.](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a>Adóelőleg-bevallás űrlapjainak létrehozása
Az adóelőleg-bevallás egy adott időszakra történő elkészítésének és benyújtásának folyamata a kiegyenlítési és kifizetési feladási adóügyi feladat során feladott adóelőleg-tranzakcióin alapul. A globális adóelőleggel kapcsolatos további tudnivalókat lásd: [Globális adóelőleg](../general-ledger/global-withholding-tax-overview.md).

Az áfabevallási jelentés létrehozásához kövesse az alábbi lépéseket.

1. Lépjen ide: **Adó** > **Bevallások** > **Adóelőleg** > **Adóelőleg kifizetése*.
2. Válassza ki a kiegyenlítési időszakot, majd válassza ki a jelentés dátumát. 
3. Írja be a tranzakció dátumát, majd kattintson az **OK** gombra.
4. A megnyíló párbeszédpanelen válasszon ki egy vagy több nyomtatványtípust a **41. számú nyomtatvány**, a **11. számú nyomtatvány** vagy a **Nincs** közül. Ha a **Nincs** lehetőséget választja, a normál jelentés jön létre. 
5. Válassza ki a nyelvet. Minden jelentés fordítása **en-us** és **ar-eg**.
6. Írja be azon fiók és bank nevét, ahol az adóbefizetés megtörténik.
7. Válassza ki az üzlettípust, majd adja meg a csekk- és dokumentumszámokat. 
8. Írja be az entitás típusát. 
9. Adja meg az árlap hozzárendeléséhez regisztrált személy nevét, és a jelentés generálásának megerősítéséhez kattintson az **OK** gombra. 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
