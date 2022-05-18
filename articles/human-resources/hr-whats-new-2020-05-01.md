---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 1.)
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. május 1-i kiadásban.
author: andreabichsel
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eedc89be0bbcd92f541c57fb1f99a04e8706eafd
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689354"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 1.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.3196-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a>Új Teljesítménykezelés entitások érhetők el az Adatkezelő keretrendszerben (DMF)

A következő entitások állnak rendelkezésre. Ha nem látja ezeket az entitásokat az entitások listában, akkor válassza az **Entitások frissítése** lehetőséget a **Keretrendszer paraméterei > Entitásbeállítások > Entitáslista frissítése helyen**.

- **Vitafórum-kompetencia**
- **Vitafórumcélok**
- **Vitafórummérés**
- **Vitafórum-témakör**
- **Teljesítménynapló**
- **Mértékegység**
- **Cél mérése**

Ezenkívül az **Összpontszám** és **Átlagos pontszám** is hozzá lettek adva a **Vitafórum** entitáshoz.

## <a name="increase-length-of-leave-request-comments-275641"></a>A szabadságkérelmek megjegyzései hosszának növelése (275641)

A szabadságkérelmekkel kapcsolatos megjegyzésekben most már 100 több karakter is megadható.

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a>Az értékelésekkel kapcsolatos végleges megjegyzések nem jelennek meg, ha a vezető vagy az alkalmazott egy másik vállalatba van bejelentkezve (431688)

Az összes megjegyzés megjelenik az értékelések megtekintésekor.

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a>A felhasználó által definiált hivatkozások nem támogatottak az új Dolgozó képernyőn (390374)

A felhasználó által definiált hivatkozások ezentúl engedélyezve vannak a racionalizált **Dolgozó** képernyőn.

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a>A HcmRatingLevelEntity az OData API összeomlását okozza (439476)

Ez a módosítás javítja az API összeomlását. Ezt a hibát egy ismétlődő név okozta.

## <a name="in-preview"></a>Előnézetben

## <a name="leave-suspension"></a>Szabadság felfüggesztése

Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet. A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást. Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz létre. További információ: [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Felhasználói élmény frissítése annak jelzésére, hogy az elhatárolás fel van függesztve (429550)

A felhasználói élmény immár jelzi, hogy az elhatárolás fel van függesztve egy tervhez.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz (272447)

Ebben a kiadásban a HR olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez. A fizetetlen szabadság lehet egy típus, de ez nem kötelező. Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>A DMF entitás elérhető az elhatárolás-felfüggesztésekhez (429549)

A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Okkódhozzáadása az elhatárolás-felfüggesztésekhez (429547)

Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Az átállás megkezdése a humánerőforrás-paraméterektől a szabadság és távollét paramétereire

Ez a kiadás elkezdi kombinálni a Humán erőforrások paramétereit a szabadság és a távollét paramétereivel.

## <a name="carry-forward-rules"></a>Átvitel szabályai

Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve. Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat. További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Ismert problémák

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint előnézet nem használható bizonyos környezetekben

Ha egy, a SharePoint-ban tárolt dokumentum előnézete nem működik, próbálja meg a következő eljárást:

1. Ellenőrizze, hogy az Adminisztrátor felhasználói fiók rendelkezik-e a felhasználói rekordhoz társított e-mail-címmel. Ezt az információt a **Felhasználó** oldalon lehet megtekinteni. Ha nincs beállítva e-mail-cím, akkor az e-mail-címet és a szolgáltatót hozzá kell adnia az OData Excel-bővítménnyel. Alapértelmezés szerint az e-mail-cím nem szerepel az Excel-tervben. Szerkesztenie kell az Excel-tervet, minden mezőt fel kell venni, alkalmazni kell, majd frissíteni kell. Miután befejezte ezeket a lépéseket, frissítheti az adminisztrátori fiókot.

2. Miután az Adminisztrátor fiókhoz hozzá van rendelve egy e-mail-fiók, az Adminisztrátori hitelesítő adatokkal jelentkezzen be a Human Resources szolgáltatásokba.

3. A dokumentum előnézetének indításához nyisson meg egy mellékletet SharePoint-ban.

4. Jelentkezzen be egy másik olyan felhasználói fiókkal, amely hozzáférhet a mellékletekhez, és ellenőrizze, hogy az előnézet a várt módon működik-e.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]