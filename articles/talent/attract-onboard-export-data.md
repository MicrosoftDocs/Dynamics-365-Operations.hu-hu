---
title: Adatok exportálása az Attract és az Onboard modulból
description: Adatok exportálása a Dynamics 365 Talent Attract és az Onboard modulból.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461345"
---
# <a name="export-data-from-attract-and-onboard"></a>Adatok exportálása az Attract és az Onboard modulból

[!include [banner](includes/banner.md)]

Ahogy azt bejelentettük a [Dynamics 365 Talent: Attract és Dynamics 365 Talent: Onboard alkalmazások megszüntetése](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps) című bejegyzésben, megszüntetjük a Dynamics 365 Talent: Attract és Dynamics 365 Talent: Onboard alkalmazásokat 2022. február 1-jén. Hogy segítséget nyújtsunk másik termékbe való áttelepítéssel, mindkét alkalmazásban találhatók adatexportálási lehetőségek.

## <a name="export-data-from-attract"></a>Adatok exportálása az Attract modulból

Az adatok az Ön környezetéhez való hozzáférés korlátozása nélkül exportálhatók. Erre akkor lehet szükség, ha tesztelési célokra vagy az adatstruktúránk megértésére lenne szükség. Ha készen áll az áttelepítésre, korlátozza a hozzáférést az Attract környezethez az eljárás utáni utasítások alapján. Mindenképpen exportálja az adatokat ismét. 

1. Ugorjon ide: [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Az **adatexportálás** területen válassza az **Adatexportálás kérése** lehetőséget.

   ![[Adatexportálás kérése az Attract modulból](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. Ha megjelenik a **Kérelem feldolgozása folyamatban van** üzenetablak, válassza az **OK** lehetőséget. Az adatexportálás akár 20 percig is tarthat, attól függően, hogy milyen méretű az exportálás.

4. Az Exportálás befejeződése után válassza ki a mellette található **Letöltés** gombot. 

   >[!NOTE]
   >Az összes adatexportálás 7 napig elérhető, ami után a **Letöltés** hivatkozás elévül.</br>
   
A letöltés tartalmaz egy .zip fájlt az Attract adatokkal, többek között a következő mappákat:

| Mappa neve | Leírás |
| --- | --- |
| Adminisztratív beállítások | Attract felügyeleti központ konfigurációi. |
| Jelöltek | Az összes jelölt, akiket állásokhoz vagy tehetségállományokhoz hozzáadtak. |
| E-mail-sablonok | A környezethez konfigurált összes e-mail-sablon. |
| Állásajánlati csomagok sablonjai | A létrehozott összes állásajánlat-csomagsablon, valamint a társított konfigurációk. |
| Állásajánlat-szabályegyüttesek |  Minden szabályegyüttes-fájl, amelyet az ajánlatkezeléshez feltöltöttek. |
| Állásajánlat-sablonok | A környezethez létrehozott összes állásajánlat-dokumentumsablon. |
| Álláslehetőségek | Minden létrehozott állás. A törölt állások nem exportálhatók. Az almappákban szerepelnek a jelöltek pályázatai, további almappákkal a jelölti pályázatok mellékletei és ajánlati csomagok számára, ha szükséges. |
| Munkalehetőség-sablonok | A környezetben konfigurált összes munkafolyamat-sablon. |
| Tehetségállományok | Az összes létrehozott tehetségállomány, a közreműködőik listája, és a tehetségállomány jelölti listája. |
| Dolgozók | A környezetben jelenlévő összes dolgozó listája, valamint a szerepköreik. |
| (gyökérmappa) | A JSON-séma fájlja, amely az adatszerkezet mezőit írja le. |

### <a name="restrict-access-to-attract"></a>Hozzáférés korlátozása az Attract modulhoz

Ha készen áll az áttelepítésre, korlátozza a nem rendszergazdák hozzáférését az Attract környezethez, és exportálja adatait.

>[!IMPORTANT]
>Az Attract környezethez való hozzáférés korlátozása végleges, és nem vonható vissza. Ha azt szeretné, hogy a nem rendszergazda felhasználók továbbra is hozzáférjenek a környezethez, hagyja ki ezt a lépést.

1. Ugorjon ide: [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Ha korlátozni szeretné a nem rendszergazdák számára az Attract környezethez való hozzáférést, akkor a **Hozzáférés korlátozása ennél az alkalmazásnál** pontban válassza a **Hozzáférés korlátozása most** lehetőséget. A hozzáférés korlátozásával visszavonja az összes közzétett aktív állás közzétételét.

   ![[Nem rendszergazdai hozzáférés korlátozása az Attract modulhoz](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. Amikor megjelenik az **Ez végleges módosítás** figyelmeztetés, válassza a **Hozzáférés korlátozása** lehetőséget a környezethez való végleges korlátozáshoz nem rendszergazda felhasználók számára. Ha nem szeretné végrehajtani ezt a lépést, válassza a **mégse** lehetőséget.

   ![[Figyelmeztetés, hogy a hozzáférés korlátozása végleges módosítás](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   >A rendszergaudák továbbra is hozzáférhetnek az adatok exportálásához és a személyek jelentéséhez szükséges oldalakhoz, miután korlátozza a hozzáférést az Attract környezethez.

## <a name="export-data-from-onboard"></a>Adatok exportálása az Onboard modulból

Ha készenáll, letöltheti a sablonokat, útmutatókat és a jelöltek adatait az Onboard modulból.

1. Ugorjon ide: [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).

2. Az **adatexportálás** területen válassza az **Adatexportálás kérése** lehetőséget. 

   ![[Adatexportálás kérése az Onboard modulból](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. Ha megjelenik a **Kérelem feldolgozása folyamatban van** üzenetablak, válassza az **OK** lehetőséget. Az adatexportálás akár 20 percig is tarthat, attól függően, hogy milyen méretű az exportálás.

4. Az Exportálás befejeződése után válassza ki a mellette található **Letöltés** gombot. 

   ![[Adatok exportálásának letöltése az Onboard modulból](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   >Az adatexportálás hét napig áll rendelkezésre. Hét nap után a **Letöltés** hivatkozás lejár, és új exportálást kell kérnie, ha ismét szeretné letölteni adatait. Új adatexportálás indításakor az új export sikeres végrehajtása után minden létező már meglévő letöltés elévül.

A letöltés egy .zip-fájl, amely a következőket tartalmazza:

- A **Sablonok** mappát, amely az Onboard-sablonokat Word-formátumban tartalmazza.

- Az **Útmutatók** mappát, amely az Onboard-útmutatókat Word-formátumban tartalmazza.

## <a name="see-also"></a>Lásd még

[Dynamics 365 Talent: Attract és Dynamics 365 Talent: Onboard alkalmazások megszüntetése](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)