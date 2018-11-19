---
title: "A kiskereskedelmi csatorna pénzügyi integrálása"
description: "Ez a témakör a Retail POS pénzügyi integrálásáról nyújt áttekintést."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: hu-hu
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a>A kiskereskedelmi csatorna pénzügyi integrálása

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 for Retail pénzügyi integráció funkciójáról. A pénzügyi integráció funkció keretrendszer, amely támogatja a helyi pénzügyi törvényeket, amelyek célja a csalások elleni harc a kiskereskedelemben. A tipikus, pénzügyi integráció használatával megoldható esetek:

- Pénzügyi nyugta nyomtatása, és odaadása a vevőnek.
- A pénztárban végrehajtott értékesítéshez és visszáruhoz kapcsolódó adatok benyújtásának biztonságossá egy külső, az adóhatóság által nyújtott szolgáltatásba.
- A hatóság engedélyezte digitális aláírással adatvédelem használata.

Ez a témakör bemutatja, hogyan kell a pénzügyi integrációt beállítani, hogy a felhasználók végrehajthassák a következő feladatokat. 

- Állítsa be a pénzügyi összekötőket, amelyek pénzügyi eszközök és szolgáltatások pénzügyi regisztrációs célokra, például ezekhez: mentés, digitális aláírások és a pénzügyi adatok biztonságos benyújtása.
- Állítsa be a dokumentum-szolgáltatót, amely meghatároz egy kimeneti módszert, valamint a pénzügyi bizonylat létrehozásának algoritmusát.
- Konfigurálja a pénzügyi regisztráció folyamatát, amely meghatározza lépések sorát, és minden egyes lépéshez a használt összekötők csoportját.
- POS-funkcióprofilokhoz rendeljen pénzügyi regisztrációs eljárást.
- Rendeljen összekötő műszaki profilokat vagy hardverprofilokhoz (a helyi pénzügyi összekötőkhöz) vagy POS-funkcióprofilokhoz (más pénzügyiösszekötő-típusokhoz).

## <a name="fiscal-integration-execution-flow"></a>Pénzügyi integráció végrehajtási folyamat
A következő helyzet a közös pénzügyi integráció végrehajtási folyamatát jeleníti meg.

1. A pénzügyi regisztrációs folyamat elkezdése.
  
   Bizonyos pénzügyi regisztrálást igénylő műveletek végrehajtása után (például kiskereskedelmi tranzakciók lezárása) a pénzügyi regisztrációs folyamat társítva van a jelenlegi pénztár funkcióprofillal.

1. Pénzügyi összekötő keresése.
   
   Minden egyes pénzügyi regisztrációs lépéshez, amely szerepel a pénzügyi regisztráció folyamatban, a rendszer megfelelteti a pénzügyi összekötők listáját. Az összekötőknek van egy funkcióprofiljuk a megadott összekötőcsoportban, összekötők egy csoportjával, amelyeknek a műszaki profilja társítva van a jelenlegi hardverprofillal (a csak **helyi** típusú összekötő esetében), illetve az aktuális pénztár funkcióprofillal (a többi összekötőtípusnál).
   
1. Hajtsa végre a pénzügyi integrációt.

   A rendszer végrehajt minden szükséges műveletet, amelyeket megad a megtalált összekötőhöz kapcsolódó szerelvény. Ez a működési profil és a műszaki profil beállításainak megfelelően történik, amelyeket az előző lépésben találtunk meg az összekötőhöz.

## <a name="setup-needed-before-using-fiscal-integration"></a>A pénzügyi integráció használatát megelőzően szükséges beállítás
Mielőtt a pénzügyi integráció funkciót használná, adja meg a következő beállításokat:

- A számsorozatot adja meg a **Kiskereskedelmi paraméterek** lapon a pénzügyi funkcionális profilszám számára.
  
- A számsorozatokat adja meg a **Megosztott kiskereskedelmi paraméterek** lapon a következő hivatkozásokhoz:
  
  - Pénzügyi technikai profil száma
  - Pénzügyi csatlakozócsoport száma
  - Regisztrációs folyamat száma

- Hozzon létre egy **Pénzügyi összekötőt** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Pénzügyi összekötők** elemnél minden eszközre vagy szolgáltatásra, amelyet pénzügyi integrációs célokra tervez használni.

-  Hozzon létre egy **Pénzügyi bizonylat szolgáltatót** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Pénzügyi bizonylat szolgáltatók** elemnél az összes pénzügyi összekötőre. Az adatleképezést a pénzügyi bizonylat szolgáltató részének kell tekinteni. Azonos összekötőhöz különböző adatleképezések beállításához (például államspecifikus előírások) eltérő pénzügyi bizonylat szolgáltatókat kell létrehozni.

- Hozzon létre egy **Összekötő funkcionális profilt** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Összekötő funkcionális profilok** elemnél az egyes pénzügyi bizonylat szolgáltatókhoz.
  - Válasszon ki egy összekötőnevet.
  - Válasszon ki egy bizonylatszolgáltatót.
  - Adja meg az áfaszázalékok beállításait a **Szolgáltatásbeállítás** lapon.
  - Adja meg az áfakódok leképezését és a fizetőeszköz-típus leképezését az **Adatleképezés** lapon.

  #### <a name="examples"></a>Példák 

  |  | Formátum | Példa | 
  |--------|--------|--------|
  | Áfaszázalékok beállítása | value : VATrate | 1 : 2000, 2 : 1800 |
  | Áfakódok leképezése | VATcode : value | vat20 : 1, vat18 : 2 |
  | Fizetőeszköz-típusok leképezése | TenderTyp : value | Cash : 1, Card : 2 |

- Hozzon létre **Pénzügyi összekötő csoportokat** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Összekötő pénzügyi csoport** elemnél. Az összekötőcsoport a funkcionális profil része, amely össze van kötve az azonos funkciókat végrehajtó pénzügyi összekötőkkel, és a pénzügyi regisztrációs folyamat azonos szakaszában használt.

   - Működési profilok hozzáadása az összekötőcsoporthoz. Kattintson a **Hozzáadás** lehetőségre a **Funkcionális profilok** lapon, majd válassza ki a profil számát.
   - Ha fel szeretné függeszteni a működési profil használatát, a **Letiltás** beállítása legyen **Igen**. 
   
     Ez a módosítás csak az aktuális összekötőcsoportot érinti. Ugyanazt a funkcionális profilt az egyéb összekötőcsoportokban továbbra is használhatja.

     >[!NOTE]
     > Egy összekötőcsoporton belül minden egyes pénzügyi összekötő csak egy funkcionális profillal rendelkezhet.

- Hozzon létre egy **Összekötő műszaki profilt** a **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Összekötő funkcionális profilok** elemnél az egyes pénzügyi összekötőkhöz.
  - Válasszon ki egy összekötőnevet.
  - Válasszon ki egy összekötőtípust. 
      - **Helyi** – Állítsa be ezt a típust a fizikai eszközökhöz vagy a helyi számítógépen telepített alkalmazásokhoz.
      - **Belső** – Állítsa be ezt a típust a kiskereskedelmi kiszolgálóhoz kapcsolódó pénzügyi eszközökhöz és szolgáltatásokhoz.
      - **Külső** – Állítsa be ezt a típust a külső pénzügyi szolgáltatásokhoz, például az adóhatóság által megadott külső webportálokhoz.
    
  - A beállításokat adja meg a **Kapcsolat** lapon.

      
 >[!NOTE]
 > Egy korábban betöltött konfiguráció frissített változata lesz betöltve a funkcionális és a műszaki profilokhoz is. Ha egy megfelelő összekötő vagy dokumentum szolgáltató már használatban van, akkor értesítést kap. Alapértelmezés szerint a funkcionális és a műszaki profilokban saját kezűleg végrehajtott összes módosítás tárolva lesz. Annak érdekében, hogy ezeket a profilok a konfigurációból származó paraméterek alapértelmezett csoportjával felülbírálja, kattintson a **Frissítés** elemre az **Összekötő funkcionális profil** lapon és az **Összekötő műszaki profilok** lapon.
 
- Hozzon létre egy **Pénzügyi regisztráció folyamatot** itt: **Kiskereskedelem > Csatorna beállítása > Pénzügyi integráció > Pénzügyi regisztrációs eljárás**, a pénzügyi integráció minden egyedi folyamatához. A regisztrációs folyamatot a regisztrációs lépések sorrendje, és az egyes lépéseknél használt összekötőcsoport határozza meg. 
  
  - Regisztráció lépéseket adjon hozzá a folyamathoz:
      - Kattintson a **Hozzáadás** gombra.
      - Válasszon ki egy összekötőtípust.
      
      >[!NOTE]
      > Ez a mező határozza meg, hogy a rendszer hol keresi az összekötőt a műszaki profilban, vagy a hardverprofilokban a **helyi** összekötőtípusnál, vagy a POS-funkcióprofilokban az egyéb pénzügyiösszekötő-típusoknál.
      
   - Válasszon ki egy összekötőcsoportot.
   
     >[!NOTE]
     > Kattintson az **Érvényesítés** elemre a regisztrációs folyamat szerkezeti integritásának ellenőrzéséhez. Ellenőrzéseket végezni a következő esetekben ajánlott:
       >- Egy új regisztrációs folyamathoz, miután minden beállítás befejeződött, többek között a POS-funkcióprofilok és hardverprofilok kötése.
       >- Miután frissítéseket hajtottak végre egy meglévő regisztrációs folyamaton.

-  A pénzügyi regisztrációs folyamatok kötése a POS-funkcióprofilokhoz: **Kiskereskedelem > Csatorna beállítása > POS-beállítás > POS-profilok > Funkcióprofilok**.
   - Kattintson a **Szerkesztés** elemre, és válassza ki a **Folyamatszám** elemet a **Pénzügyi regisztrációs folyamat** lapon.
- Az összekötő műszaki profilok kötése a hardverprofilokhoz: **Kiskereskedelem > Csatorna beállítása > POS-beállítás > POS-profilok > Hardverprofilok**.
   - Kattintson a **Szerkesztés** elemre, majd kattintson az **Új** elemre a **Pénzügyi műszaki profil** lapon.
   - Válasszon egy összekötő műszaki profilt a **Profil száma** mezőben.
   
     >[!NOTE]
     > Egy hardverprofilhoz több technikai profilt adhat hozzá. Azonban ez nem támogatott, ha a hardverprofilnak egynél több metszete van bármely összekötőcsoporttal. A helytelen beállítások elkerülése érdekében azt ajánljuk, hogy az összes hardverprofil frissítése után ellenőrizze a regisztrációs folyamatot.

