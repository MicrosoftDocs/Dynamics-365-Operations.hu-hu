---
title: A Dynamics 365 Commerce 10.0.30 előzetes verziója (2022. november)
description: Ez a témakör olyan funkciókat ír le, amelyek vagy Microsoft Dynamics 365 Commerce újak, vagy módosulnak a 10.0.30-as dokumentumban.
author: josaw1
ms.date: 08/31/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-09-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 0149c9671e8baeb26965b4f136ed91d09e2d039b
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405516"
---
# <a name="preview-of-dynamics-365-commerce-10030-november-2022"></a>A Dynamics 365 Commerce 10.0.30 előzetes verziója (2022. november)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek újak Microsoft Dynamics 365 Commerce vagy módosulnak a 10.0.30-as verzió előnézetében. Ennek a verziónak a buildszáma több 10.0.1362, és a következő ütemezésben érhető el:

- **Kiadás előzetes verziója:** 2022. szeptember
- **A kiadás nyilvános megjelenése (önkiszolgáló frissítés):** 2022. október
- **A kiadás nyilvános megjelenése (automatikus frissítés):** 2022. november

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Előfordulhat, hogy a cikk frissítése a cikk eredeti közzététele után a buildhez hozzáadott funkciókat is tartalmazza.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---------|------------------|----------------|--------------| 
| Ügyfélszolgálat   | Csevegés egy e-commerce webhelyen egy élősúdó Power Virtual Agents használatával. | Ez a funkció lehetőséget nyújt az e-commerce webhely felhasználóinak arra Power Virtual Agents, hogy támogatási kérések esetén egy csevegési funkciót használjanak. | A rendszergazdák/döntéshozók engedélyezik a végfelhasználók számára. |
| Információ  |  Üzemi adatelemzési eseményeket hoz létre a számlájához a pénztári rendszer Application Insights. | [A naplók elérése a következőben: Application Insights](../dev-itpro/retail-component-events-diagnostics-troubleshooting.md#enable-diagnostic-events-in-application-insights)   |  Pro/fejlesztői jelentkezés   |
|  Fizetések  | PayPal rendelés támogatása 29 napos engedélyezési időszak után | A PayPal maximális engedélyezési időszaka 29 nap, ezt követően új engedélyezési és rendelésazonosítót kell generálni. A PayPal egy másik lehetőségként olyan lehetőséget kínál, hogy a rendelésre általános rendelésként hivatkozni lehet egy PayPal rendelésre, így több engedélyezést lehet lehetővé téve, és ugyanannál a rendelésazonosítónál lehet rögzíteni, ahelyett, hogy új engedélyezést és rendelésazonosítót hoz létre 29 napon belül. | Amikor a PayPal fizetési csatlakoztató a Commerce Headquarters szolgáltatásban konfigurálható, **az OrderIntent** mező fel lett adva, és két értékkel rendelkezik:<p><p>- **Authorize** – ez a konfiguráció az alapértelmezett (ha a mező üresen marad, **az Authorize** beállítás lesz az alapértelmezett beállítás). **Az OrderIntent beállításával** engedélyezi **a** processing_instruction PayPal-NO_INSTRUCTION **·** **·**. A rendelés engedélyezve lesz a PayPal számára, és az engedélyezés nem módosítható, ha ez az érték van használva.<p>- **Mentés** – ha az **OrderIntent** érték **mentésre van állítva**, ez a PayPal-processing_instruction **·** **értékével ORDER_SAVED_EXPLICITLY.** Ez az érték használatakor a rendeléshivatkozások mentése a PayPal szolgáltatásba történik.  |
| POS-bejelentkezés  | [Az önkiszolgáló diagnózis képességének engedélyezése a POS-bejelentkezéshez](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-self-serve-diagnosis-capabilities-pos-sign-in)  |  Ez a funkció az önkiszolgáló diagnózis lehetőségeket biztosítja a pénztárnál (POS) és a Commerce Headquarters alkalmazásnál, hogy az alkalmazottak és vezetők gyorsan felismerje és kijavítsák a POS-bejelentkezésekkel kapcsolatos problémák alapvető okait.<p><p>– a POS bejelentkezési képernyőjén megjelenő hibaüzenetek segítséget nyújtanak annak érdekében, hogy konkrét gyökérinformációkat adjanak az üzletnek, akik a POS-t használják, tudják, mi történt, hogy végrehajt tudják a probléma megoldásához szükséges műveleteket.<p>– a **Commerce Headquarters** **Dolgozók** lapján elérhető a Teszt bejelentkezési funkció, így a POS-eszközöket beállítva üzletvezetők szimulálni tudja a POS-bejelentkezést. A bejelentkezés sikertelen működése esetén ez a funkció művelethez használható hibaelhárítási segédeket biztosít, így a vezetők ellenőrizhetik a megfelelő konfigurációkat, kijavítják a hibákat, és ellenőrizhetik a javításokat.  | Alapértelmezés szerint be |


## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Pénzügy és az Üzemeltetés alkalmazás platformfrissítései

A Dynamics 365 Finance 10.0.30 platformfrissítéseket tartalmaz. A további tudnivalókat [lásd a Pénzügyi és műveleti alkalmazások 10.0.30-as verziójának Platformfrissítései.](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md)

### <a name="bug-fixes"></a>Hibajavítások

A 10.0.30 verzióba foglalt frissítések hibajavításával kapcsolatos információk megtekintéséhez jelentkezzen be a Lifecycle Services (LCS) [alkalmazásba, és tekintse meg a tudásbáziscikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 és ipari felhők: 2022-es 2. kiadási hullám csomag

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Tekintse meg a [Dynamics 365 és ipari felhők: 2022-es 2. kiadási hullám csomag](/dynamics365-release-plan/2022wave2/) tartalmát. A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-features"></a>Eltávolított és elavult funkciók

A [cikk Eltávolított vagy elavult Dynamics 365 Commerce](removed-deprecated-features-commerce.md) funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva vagy el vannak távolítva a Commerce rendszerből.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Commerce](removed-deprecated-features-commerce.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
