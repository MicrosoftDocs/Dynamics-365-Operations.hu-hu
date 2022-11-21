---
title: Dynamics 365 Human Resources vevő áttelepítése a pénzügyi és műveleti infrastruktúrába
description: Ez a cikk a Microsoft Dynamics 365 Human Resources pénzügyi és üzemeltetési infrastruktúrába való áttelepítését írja le.
author: twheeloc
ms.date: 10/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4df9a68ea0128378224bf77bd66423fd2e13fa55
ms.sourcegitcommit: e5b290bac7e8f468167caa1a5607aac6eac9aaea
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760362"
---
# <a name="dynamics-365-human-resources-customer-migration"></a>Dynamics 365 Human Resources vevő áttelepítése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

A vevők áttelepítése egy vevőadatbázis "növekedési és műszakváltásos áttelepítése" a pénzügyi és műveleti infrastruktúrába. Az automatizált áttelepítési eszköz használható hozzá. Az eredmény egy új pénzügyi és műveleti környezet, amely a vevő emberi erőforrások adatbázisát használja.

## <a name="prerequisites"></a>Előfeltételek

### <a name="user-access-and-permissions"></a>Felhasználói hozzáférés és engedélyek

- A Microsoft Dynamics Lifecycle Services felhasználónak rendszergazdai szerepkört kell **betöltötte a szervezethez**.
- A felhasználónak projekteket kell [létrehoznia Azure DevOps,](/azure/devops/organizations/projects/create-project) vagy egy meglévő projektet kell használnia Azure DevOps.
- A felhasználónak hozzáféréssel kell rendelkezik [Azure DevOps](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) egy személyes hozzáférési jogkivonat létrehozásához, vagy pedig egy olyan tokennek, amely használható.

### <a name="dataverse-environment-backup-sandbox"></a>Dataverse környezeti biztonsági másolat (Box)

 - Nem kötelező, de ajánlott: Frissítse a meglévő Emberi erőforrások szövegdobozkörnyezetet az Emberi erőforrások termelési környezet másolatának használatával.
 - Hozzon létre egy új Dataverse környezetet a rendszergazdai Power Platform központ segítségével.
 - Az önálló Dataverse Emberi erőforrások alkalmazáshoz kapcsolt meglévő környezet másolása az előző lépésben létrehozott környezetbe.

> [!NOTE]
> Adatbázis hozzáadásakor győződjön meg arról, **hogy a Dynamics 365-alkalmazások** engedélyezése beállítás Igen beállításra **van állítva**. Részletes információk: Környezet [előkészítése Power Platform](hr-cust-migration.md#prepare-a-power-platform-environment)

### <a name="dataverse-capacity"></a>Dataverse Kapacitás

1. A rendszergazdai **központ** összegző lapján Power Platform [Dataverse ellenőrizheti, hogy a tárolónak](/power-platform/admin/finance-operations-storage-capacity) van-e elég szabad kapacitása a környezeti példány számára.
2. Ha nincs elég szabad kapacitás, [az](/power-platform/admin/free-storage-space) útmutató segítségével felszabadítja a tárolóterületet a teljes felhasználás csökkentése érdekében. A vevők további tárolási [kapacitást is hozzáadhatnak](/power-platform/admin/add-storage).

## <a name="customer-migration-process"></a>Vevőáttelepítési folyamat

### <a name="create-a-lifecycle-services-project-for-human-resources-migration"></a>Lifecycle Services-projekt létrehozása az emberi erőforrások áttelepítéséhez

Az első lépés az új pénzügyi és műveleti megvalósítási projekt létrehozása a Lifecycle Services szolgáltatásban. Az ügyfélhez egy meglévő Emberi erőforrások Lifecycle Services projektje lesz. A meglévő Emberi erőforrások környezeteket áttelepíti a rendszer az új pénzügyi és műveleti megvalósítási projektbe.

A következő lépések szerint hozhat létre új projektet.

1. Jelentkezzen be a Lifecycle Services szolgáltatásba globális rendszergazdaként vagy a kijelölt szolgáltatásfiók felhasználójaként.
2. Válassza a Lifecycle Services kezdőlapján **a Létrehozás/új (+) lehetőséget**.
3. Válassza ki termékként a pénzügyi és a műveletalkalmazásokat.
4. A Projekt célja **mezőben** válassza a Megvalósítás **lehetőséget**.
5. Adja meg a projekt nevét és leírását.
6. A Projekt egyéni típus mezőjében **válassza ki a Microsoft áttelepítését** **Dynamics 365 Human Resources.**
7. Jelölje be a jelölőnégyzetet, ha a feltételeket elfogadja.
8. Válassza a **Létrehozása** lehetőséget.

Miután létrehozott egy új Lifecycle Services-projektet, a következő lépések szerint állíthatja be és állíthatja be.

1. A **projektbe való berakodás** befejezéséhez válassza a Projekt - onboarding lehetőséget. A további tudnivalókat lásd [a Projekt hajóra való felhozatásnál](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md).

    - Válassza ki ugyanazt a régiót, mint az aktuális környezet. Ez a beállítás nem fogja befolyásolni az áttelepítést.
    - Az örökölt rendszereknél válassza az Egyéb **lehetőséget**.

2. A projektbeállítások megadása. A lépés részeként SharePoint szükség esetén konfigurálnia kell az online Azure DevOps tárat és az Azure-kapcsolatokat. A további tudnivalókat lásd a [Lifecycle Services (LCS) felhasználói útmutatóban](../dev-itpro/lifecycle-services/lcs-user-guide.md).

> [!NOTE]
> A vevők egy meglévő projektet és Azure DevOps a hozzá tartozó személyes hozzáférési jogkivonatot is használhatjak. Ha meglévő projektet használ, a projekthez kapcsolódó konfigurációk automatikusan elérhetők lesznek, és pontosság szerint ellenőrizni lehet őket.

### <a name="migrate-a-human-resources-sandbox-environment"></a>Az Emberi erőforrások üzenetkészlet környezetének áttelepítése

#### <a name="prepare-to-migrate-the-sandbox-environment"></a>Felkészülés abox környezet áttelepítésére

Miután létrehozta az új Lifecycle Services-projektet, és befejeződött a projekt onboarding folyamata, készen áll az első környezet áttelepítésére. Mielőtt elindítja ezt a folyamatot, ajánlott frissíteni azt a postafiókkörnyezetet, amely a termelési környezetből, önálló infrastruktúrán keresztül kíván átállni.

#### <a name="prepare-a-power-platform-environment"></a>Power Platform Környezet előkészítése

> [!NOTE]
> Ez a lépés csak abox környezet áttelepítésére alkalmazható. A termelési környezet áttelepítésekor Power Platform a rendszer áthozatalja a termelési környezethez kapcsolt meglévő adminisztrációsközpont-környezetet. Adatbázis hozzáadásakor győződjön meg arról, **hogy a Dynamics 365-alkalmazások** engedélyezése gomb igenre van **állítva**. 

- A Power Platform felügyeleti központjában hozzon létre egy olyan környezetet, [amely](/power-platform/admin/create-environment#create-an-environment-with-a-database) adatbázist használ az üzenetdoboz áttelepítéséhez, vagy válasszon egy meglévő környezetet.
- [Környezet másolása a](/power-platform/admin/copy-environment) megfeleltetésre Power Platform használt környezet frissítéséhez.

#### <a name="migrate-the-sandbox-environment"></a>Az üzenetdoboz környezet áttelepítése

1. Jelentkezzen be a Lifecycle Services szolgáltatásba globális rendszergazdaként vagy a kijelölt szolgáltatásfiók felhasználójaként.

    > [!NOTE]
    > Javasoljuk, hogy elnevezett felhasználói fiókot használjon. A bejelentkezett felhasználónak **a** **Projekttulajdonos** vagy a Környezetvezető biztonsági szerepkörrel kell lennie a önálló Emberi erőforrások Lifecycle Services projektben.

2. Az újonnan létrehozott emberi erőforrásokkal kapcsolatos áttelepítési projekt megnyitása.
3. Az áttelepítési módszertan megfelelő fázisai és a projektbe való bevezető folyamat áttekintése és befejezése.
4. Válassza a HR áttelepítését **a projekt-irányítópult Alapértelmezett: Szabványos** elfogadási **tesztablakában**.
5. Válassza ki **a Megfelelő** Lifecycle Services-projektet és az eredeti Emberi erőforrások környezetet (a forrás önálló Emberi erőforrások alkalmazásból) a Kijelölés környezetben.
6. A **Leképezés engedélyezése az új környezetbe Power Platform** és a megfelelő környezet Power Platform kiválasztása. Majd válassza a **Következő** lehetőséget.
7. A részletes adatok **és a vevői bejelentkezés megerősítéséhez töltse ki a Telepítési beállítások (Pénzügy és műveletek – jelölőnégyzet)** varázslót, majd válassza **a Telepítés lehetőséget**.

A környezet állapota mutatja az előrehaladást. Az állapot a Betöltés **állapotról** **a Telepítettre** való telepítésre **változik.**

> [!NOTE]
> A termelési ablak csak akkor érhető el, ha be nem fejeződött a projekt élő készenlét-ellenőrzőlistája. További tájékoztatás: Felkészülés [az élő élőre](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

#### <a name="considerations-and-assumptions"></a>Szempontok és feltételezések

A bérlő egy Lifecycle Services-projektjában a következő jellemzőkkel rendelkezik:

- Az Emberi erőforrások üzenetkészlet környezet nem kapcsolható meglévő egyesített környezethez. Adott emberi erőforrások környezetben egyszerre csak egy áttelepítés lehet folyamatban.
- Az egyes környezetek engedélyezett száma az Emberi erőforrások licenceiben alapul. Ha elég licencet vásárol a bérlő számára, **további** üzenetpanel-környezetek megjelenik a projekt Környezetek ablakában.
- Az azonos típusú környezetek áttelepítését el kell végezve. Más szóval csak a "box-to-box" vagy "termelésről termelésre" áttelepítések amelyekre lehetőség van.

    > [!NOTE]
    > Csak az Emberi erőforrások környezettípusokat kell figyelembe venni a termelés vagy a beérkezett üzenetek állapotának meghatározásakor. Ha a környezetek helytelenül vannak kategorizálva (vagyis a termelési környezet egy üzenetdoboz-környezetként van megjelölve, vagy abox-környezet termelési környezetként van megjelölve), forduljon a Támogatási szolgálathoz.

- Ha az áttelepítés nem sikerül, hibaüzenet jelenik meg, és elérhetővé válik a **Törlés** gomb. Ezzel a gombbal törölheti a sikertelen áttelepítést. Ezután át lehet áttelepítésre a környezetet.

#### <a name="validate-the-sandbox-migration"></a>Abox áttelepítésének ellenőrzése

Abox áttelepítési folyamat sikeres befejezése után hozzon létre egy részletes teszttervet az összes üzleti folyamat ellenőrzéséhez és kijelentkezéséhez.

A tesztelés megkezdése előtt ellenőrizze a következő adatokat:

- Győződjön meg arról, hogy az áttelepített környezet elérhető a generált URL-címen.
- Győződjön meg arról, hogy a felhasználók hozzáférhetnek az áttelepített üzenetdobozhoz.
- Győződjön meg arról Dataverse, hogy az áttelepített beérkezett üzenetek környezetéhez társított környezet elérhető.
- Különböző adatok azonnali ellenőrzése annak megerősítéséhez, hogy a legfrissebb adatok elérhetők.
- Az ellenőrzés során kritikus üzleti folyamatok befejezése.
- Győződjön meg arról, hogy a biztonsági házirendek alkalmazandók.
- Győződjön meg arról, hogy a kötegelt feladatok a várt módon kiváltva vannak.

Az áttelepített postafiókhoz nem lesz távoli asztali hozzáférése. Az önkiszolgáló rendszer lehetőségeit és eszközeit a 2. szint+ üzenetkészlet környezetében a következő műveletek elvégzésére használhatja:

- Hozzáférés az [Azure SQL-adatbázishoz](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-the-azure-sql-database).
- A naplófájlok [elérése](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-log-files).
- Használjon [perfmon eszközöket](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#use-perfmon-tools).
- A Karbantartási [mód be- és kikapcsolása](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-self-service-logs).
- Szolgáltatások [újraindítása](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#restart-services).
- [A Regression suite automatizálási eszköz konfigurálása](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#configure-the-regression-suite-automation-tool)

A további tudnivalókat lásd az [önkiszolgáló rendszer telepítéséhez szükséges gyakori kérdéseknél](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md).

### <a name="migrate-a-human-resources-production-environment"></a>Emberi erőforrások termelési környezet áttelepítése

Miután befejezte az áttelepítést és az üzenetkészlet környezetének érvényességét, kövesse ezeket a lépéseket a termelési környezet áttelepítéséhez.

#### <a name="prerequisites"></a>Előfeltételek

- Az előfizetés becslését ki kell tűzni.
- Az élő készenlétet [el](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md) kell végezni.

#### <a name="migrate-the-production-environment"></a>A termelési környezet áttelepítése

1. Jelentkezzen be a Lifecycle Services szolgáltatásba globális rendszergazdaként vagy a kijelölt szolgáltatásfiók felhasználójaként.

    > [!NOTE]
    > Javasoljuk, hogy elnevezett felhasználói fiókot használjon. A bejelentkezett felhasználónak a **Projekttulajdonos** **vagy** a Környezetvezető biztonsági szerepkörrel kell lennie a Lifecycle Services projektben.

2. Az új emberi erőforrásokkal kapcsolatos áttelepítési projekt megnyitása
3. Az áttelepítési módszertan és a projekt -onboarding megfelelő fázisának áttekintése és befejezése.
4. A projekt-irányítópult Termelési ablaktáblán **válassza** a **HR áttelepítése lehetőséget**.
5. A Környezet **kiválasztása áttelepítéshez** ablakban válassza ki a megfelelő Lifecycle Services-projektet és az eredeti Emberi erőforrások környezetet (a forrás önálló Emberi erőforrások alkalmazásból). Majd válassza a **Következő** lehetőséget.
6. A részletes adatok **és a vevői bejelentkezés megerősítéséhez töltse ki a Telepítési beállítások (Pénzügy és műveletek – jelölőnégyzet)** varázslót, majd válassza **a Telepítés lehetőséget**.

A környezet állapota mutatja a telepítés állapotát. Az állapot a Betöltés **állapotról** **a Telepítettre** való telepítésre **változik.**

#### <a name="post-migration-considerations"></a>Áttelepítés utáni szempontok

- A legújabb minőségi [frissítések alkalmazása](/fin-ops-core/fin-ops/get-started/quality-updates) az ön környezetére.
- Ha virtuális táblákat [használ](hr-admin-integration-common-data-service-virtual-entities.md), konfigurálja újra a végpontokat.
- Konfigurálja újra a kettős írású integrációt. Kiértékelheti, hogy mely entitásokat kell engedélyezni.
- A két írásos integráció helyett érdemes megfontolni a virtuális táblákat.

#### <a name="dual-write-integration"></a>Kettős írás integrációja

##### <a name="set-up-microsoft-power-platform-dual-write-integration"></a>Kettős írású Microsoft Power Platform integráció beállítása

1. Menjen a rendszergazdai Power Platform központhoz, és válassza a **Bal** oldali navigáció Környezetek beállítását.
2. Válassza ki a korábban másolt/frissített környezetet, és győződjön meg arról, hogy az állapot **Kész**.
3. Menjen a Lifecycle Services szolgáltatásba, és erősítse meg, hogy az áttelepítési projekt állapota Telepítve **.**
4. Az áttelepített környezetben válassza **a Teljes részletek** lehetőséget a további részletek [áttekintéséhez és a kétírásos alkalmazás beállításához](../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#set-up-dual-write-for-new-or-existing-dataverse-environments).
5. A Két írásos **alkalmazás konfigurációs ablaktáblán** jelölje be ezt a jelölőnégyzetet, ha elfogadja az adatbázisok közötti adatok leképezésében és szinkronizálásában, majd válassza a Konfigurálás **lehetőséget**.
6. Ha egy üzenetmező értesít a sikeres kétírásos konfigurációról, válassza az **OK gombra.**
7. A részletekben nyomon követheti a konfiguráció előrehaladását.
8. Ha elkészült a konfigurációval, **a rendelkezésre álló adatentitások szinkronizálása érdekében válassza a Power Platform Hivatkozás** környezethez lehetőséget.
9. Ha az állapot azt jelzi, hogy sikeresen megtörtént a környezetek összekapcsolása, Power Platform menjen a felügyeleti központhoz, és válassza ki a megfelelő entitásokat.
10. Válassza a bal oldali ablaktáblában a **Dynamics 365-alkalmazások – Erőforrások \> lehetőséget**.
11. Győződjön meg róla, hogy a kettős írású Emberi erőforrások alkalmazás állapota engedélyezve **van**.
12. Válassza a kettős írású Emberi erőforrások alkalmazást, majd válassza a Telepítés **lehetőséget**.
13. Válassza ki a **csomag telepítéséhez a megfelelő környezetet a Két írásos Dynamics 365 Human Resources** alkalmazás telepítése ablakban.
14. Jelölje be a jelölőnégyzetet, ha elfogadja a szolgáltatási feltételeket, majd válassza a Telepítés **lehetőséget**.
15. A Dynamics 365 alkalmazáskörnyezetben **a** telepítés folyamatban lévő állapotában a Telepítés állapot jelenik meg. A telepítés befejeződése után **a** rendszer "Telepítve" lesz.

##### <a name="review-and-apply-a-dual-write-solution"></a>Kettős írású megoldás áttekintése és alkalmazása

1. Az új pénzügyi és műveleti környezetben az **Adatkezelés \> kettős írása funkcióban indul el**.
2. Válassza a **Megoldás alkalmazása lehetőséget**.
3. Az ablaktáblában válassza **ki a telepített Dynamics-megoldásokat**, **a kétírásos alkalmazások alapvető entitás-leképezésekét** és térképeit **Dynamics 365 Human Resources**. Ezután válassza az Alkalmaz **lehetőséget**. Egy üzenet megerősíti, hogy a megoldás alkalmazása folyamatban van. A megoldás sikeres alkalmazása után megjelenik az összes elérhető táblatérkép.
4. Az integráció kiválasztásához és futtatásához tekintse át a rendelkezésre álló táblatérképeket két írásos módszer használatával.
5. Ha a kétbetűs integrációt első alkalommal futtatja a táblatérképek számára, jelölje **be a Kezdeti szinkronizálás** jelölőnégyzetet. Ha a forrás emberi erőforrások környezetben integráció van, **akkor** a táblatérképek integrációjának futtatásakor nem kell bejel kiválasztani a Kezdeti szinkronizálás jelölőnégyzetet.

#### <a name="recommended-practices"></a>Ajánlott eljárások

Ez a szakasz a különálló infrastruktúra és a pénzügyi és a műveleti infrastruktúra áttelepítésére vonatkozó ajánlásokat ismerteti.

- Kifejezetten ajánljuk, hogy működjön együtt partnerével Microsoft Dynamics az emberi erőforrások környezetének áttelepítése során.
- A megfelelő idő megtervelése a teljes felhasználói elfogadás tesztelésére (UAT) a beérkezett üzenetek áttelepített környezetében.
- Az integráció áttelepítésére vonatkozó részletes lépések megtervzése és dokumentálása az áttelepített környezetbe.
- Részletes ellenőrzőlista létrehozása az áttelepítés átállási folyamatának felvázolása érdekében.
- Az áttelepítés során tervezze meg a megfelelő mennyiségű le leállást a vállalat számára.
- Kifejezetten ajánljuk, hogy a FastTrack minősítésű vevők együtt dolgozzon a FastTrack megoldástervezőjükkel, hogy segítséget kapják az áttelepítési folyamat felügyeletéért.
- Kifejezetten ajánljuk, hogy az első áttelepítés előtt frissítse a beérkezett üzenetek környezetét az önálló infrastruktúra területén. Ennek a frissítésnek tartalmaznia kell azt Dataverse a környezetet, amely ahhoz a beérkezettdoboz-környezethez kapcsolódik, amelybe át fog áttelepítést tervezni.
- Kifejezetten ajánljuk, hogy használjon szolgáltatásfiókot Lifecycle Services-projekt telepítése, áttelepítése és létrehozása során.
- A jelölőnégyzet környezetének frissítését tervezi, hogy a rendszer érvényesítsen-e UAT-ellenőrzést a legutóbbi általános elérhetőségi (GALL) kiadásban. További tájékoztatás a szempontoknál [található](hr-infrastructure-merge.md#considerations).
