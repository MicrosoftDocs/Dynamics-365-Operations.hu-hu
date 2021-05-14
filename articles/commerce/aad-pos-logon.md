---
title: Azure Active Directory-hitelesítés konfigurálása a pénztári bejelentkezéshez
description: Ez a témakör bemutatja, hogy hogyan kell konfigurálni az Azure Active Directoryt mint hitelesítési módszert a Microsoft Dynamics 365 Commerce pénztárban.
author: boycezhu
manager: annbe
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 34a7946a56a58655bc9ae23e060fc50ab01f2c6e
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937458"
---
# <a name="configure-azure-active-directory-authentication-for-pos-sign-in"></a>Azure Active Directory-hitelesítés konfigurálása a pénztári bejelentkezéshez

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör bemutatja, hogy hogyan kell konfigurálni az Azure Active Directoryt (Azure AD) mint hitelesítési módszert a Microsoft Dynamics 365 Commerce pénztárban (POS).

Olyan kiskereskedők, akik a Dynamics 365 Commerce-t Microsoft más felhőszolgáltatásával, például a Microsoft Azure, a Microsoft 365 és a Microsoft Teams szolgáltatással együtt használják, általában az Azure AD-t a felhasználói hitelesítő adatok centralizált kezeléséhez szeretnék használni azért, hogy az alkalmazásokban biztonságos és zökkenőmentes bejelentkezési élmény váljon lehetővé. Az Azure AD-hitelesítés Commerce-pénztárhoz való használatához először konfigurálnia kell az Azure AD-t hitelesítési módszerként a kereskedelmi központban.

## <a name="configure-pos-authentication-method"></a>Pénztár-hitelesítési mód konfigurálása

A Commerce központ pénztár-hitelesítési módjának konfigurálásához kövesse az alábbi lépéseket.
    
1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Pénztár beállítása \> Pénztárprofilok \> Funkcióprofilok** menüpontra, és válassza ki a módosítani kívánt funkcióprofilt.
1. A **Pénztári személyzet bejelentkezése** szakaszban a **Funkciók** gyorslapon válassza ki a kívánt hitelesítési mód lehetőségét a **Bejelentkezés hitelesítésének módja** legördülő listából.

    A **Bejelentkezés hitelesítési módszer** három lehetőségből áll:
    
    - **Személyzeti azonosító és jelszó** – Ennél az alapértelmezett beállításnál a pénztárfelhasználóknak meg kell adniuk a személyzeti azonosítójukat és jelszavukat a pénztárba való bejelentkezéshez, hogy hozzáférhessenek a kezelői felülbírálás funkcióhoz.
    - **Azure AD egyszeri bejelentkezés nélkül** – ez a beállítás megköveteli a pénztárfelhasználóktól, hogy Azure AD-hitelesítő adatokkal jelentkezzenek be a pénztárba és hozzáférhessenek a kezelői felülbírálás funkcióhoz. A pénztárkliens frissítése vagy ismételt megnyitása után a pénztárfelhasználónak meg kell adnia a Azure AD-hitelesítő adatokat, hogy újra bejelentkezzen.
    - **Azure AD egyetlen bejelentkezéssel** - Ha ez a beállítás van kiválasztva, a pénztáfelhasználók bejelentkezhetnek a felhőpénztárba (CPOS) olyan aktív Azure AD-hitelesítő adatokkal, amelyeket más webalkalmazások ugyanabban a böngészőben használnak, vagy bejelentkezhetnek a Modern POS (MPOS) alkalmazásba olyan Azure AD-hitelesítő adatokkal, amelyekkel be vannak jelentkezve a Windowsba. Mindkét módszer lehetővé teszi a bejelentkezést anélkül, hogy Azure AD-hitelesítő adatokat kellene megadnia a pénztár bejelentkezési képernyőjén. A pénztárkezelő felülbírálási funkcióinak eléréséhez azonban továbbra is be kell jelentkezni Azure AD-hitelesítő adatokkal.

1. Nyissa meg a **Kiskereskedelem és kereskedelem > Kiskereskedelem és kereskedelem IT > Leosztási ütemezés** lehetőséget, és futtassa az **1070 (csatornakonfiguráció)** feladatot, amellyel a legújabb funkcióprofil-beállítások szinkronizálhatja a pénztáskliensekbe.

> [!NOTE]
> - Az **egyszeres bejelentkezés nélküli Azure AD** hitelesítési mód lehetősége felváltja az **Azure Active Directory** beállítást a Commerce 10.0.18-as és korábbi verzióiban.
> - Az Azure AD-hitelesítéshez aktív internetkapcsolat szükséges, és nem működik, ha a pénztár offline állapotban van.

## <a name="associate-azure-ad-accounts-with-pos-users"></a>Azure AD-számlák társítása pénztárfelhasználókhoz

Ahhoz, hogy az Azure AD-t mint pénztári hitelesítési módszer használja, társítania kell az Azure AD-fiókokat pénztárfelhasználókkal a Commerce központban. 

Az Azure AD-fiókok pénztárfelhasználókhoz való társításához a Commerce-központban kövesse ezeket a lépéseket.
    
1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem > Alkalmazottak > Dolgozók**, majd nyisson meg egy dolgozói rekordot.
1. A műveleti ablaktáblán válassza a **Kereskedelem** lapot, majd a **Külső identitás** csoportban válassza a **Meglévő identitás társítása** lehetőséget. 
1. A **Meglévő külső identitás használata** párbeszédpanelen válassza a **Keresés e-maillel** parancsot, adja meg Azure AD-e-mail címet, majd válassza a **Keresés** lehetőséget.
1. Válassza ki a visszaadott Azure AD-fiókot, majd az **OK** elemet.

A fenti konfigurációs lépések után a rendszer kitölti az **Alias**, **UPN**, **Külső részazonosító** mezőket a dolgozó adatainak oldalának **Commerce** oldalán.

A legutóbbi pénztárfelhasználó és Azure AD-fiók adatainak csatornára szinkronizálásához futtatnia kell az **1060 (Személyzet)** feladatot a **Kiskereskedelem és kereskedelem > Kereskedelem és kiskereskedelem IT > Felosztási ütemezés** pontban.

> [!NOTE]
> Az a legjobb megoldás, ha a dolgozói adatok (például a jelszó, pénztárengedély, társított Azure AD-fiók vagy alkalmazotti címjegyzék) Commerce-központban való frissítése után erősen javasoljuk, hogy futtassa az **1060 (Személyzet)** feladatot a legújabb dolgozói adatok csatornára szinkronizálásához. A pénztárkliens ezután be tudja olvasni a megfelelő adatokat a felhasználó hitelesítéséhez és a hitelesítés ellenőrzéséhez.

## <a name="pos-lock-register-and-sign-out-with-azure-ad-authentication"></a>Pénztárzárolási jegyzék és kijelentkezés Azure AD-hitelesítéssel

A következő történik, ha a pénztár az Azure AD-hitelesítő mód használatára van konfigurálva:

- A **Pénztárgép zárolása** funkció nem lesz elérhető a pénztár alkalmazásban. 
- Az **Automatikus zárolás** funkció ugyanaz, mint az **Automatikus kijelentkezés** funkció.
- Ha a pénztárfelhasználó a **Kijelentkezés** lehetőséget választja, a felhasználót a rendszer a pénztár következő indításakor felkéri az Azure AD-hitelesítő adatokkal való bejelentkezéssel, attól függetlenül, hogy engedélyezve van-e az egyszeri bejelentkezés.

## <a name="manager-override-functionality-with-azure-ad-authentication"></a>A kezelői felülbírálási funkció Azure AD-hitelesítéssel

Ha a pénztár úgy van beállítva, hogy Azure AD-hitelesítést használjon, a vezető felülbírálási funkciói egy párbeszédpanelt nyitnak meg, amely kéri a kezelő felhasználó Azure AD-hitelesítő adatait. A kezelői bejelentkezés jóváhagyása után a kezelő Azure AD-hitelesítő adatait a rendszer eldobja, és az előző felhasználó Azure AD-hitelesítő adatait használja a későbbi pénztárműveletekhez használja fel.

> [!NOTE]
> - A Commerce 10.0.18-as és korábbi verzióiban a kezelő felülbíráló funkciója nem támogatja az Azure AD-t. Még akkor is szükség van egy személyzeti azonosítóra és jelszóra, ha a pénztár az Azure AD-hitelesítési módszer használatára van beállítva.
> - A CPOS Safari böngészővel való használata esetén Apple iOS-eszközön először ki kell kapcsolnia a **Felugró ablakok letiltása** elemet a Safari beállításaiban, hogy a kezelői felülbírálás funkció működjön az Azure AD-hitelesítéssel. 

## <a name="security-best-practices-for-azure-ad-based-pos-authentication-on-shared-devices"></a>Biztonsági gyakorlati tanácsok a megosztott eszközök Azure AD-alapú pénztárhitelesítéshez

Sok kiskereskedő úgy állítja be a kiskereskedelmi üzlet környezetét, hogy több felhasználónak kell hozzáférnie a pénztár alkalmazáshoz egy megosztott fizikai eszközről. Ebben a környezetben, miközben az egyszeri bejelentkezés kényelmes és zökkenőmentes hitelesítést biztosít, olyan biztonsági hurkot hozhat létre, ahol előfordulhat, hogy az aktuális pénztárfelhasználó nem veszi észre, hogy egy másik felhasználó hitelesítő adatait használják tranzakciók vagy műveletek elvégzésére a pénztárban. Mielőtt konfigurálja a POS-t az Azure AD-hitelesítési módszer használatára, javasolt a biztonsági házirend és a megosztott eszköz bejelentkezési beállításainak áttekintése, hogy eldöntse, melyik beállítás a legmegfelelőbb.

- Ha a kiskereskedelmi környezetben megosztott fiókot (például helyi fiókot) használ a fizikai eszköz bejelentkezéséhez, akkor javasolt az **Azure AD egyszeri bejelentkezés nélkül** beállítás használata. Így garantálható, hogy minden pénztárfelhasználó explicit módon biztosítja Azure AD-hitelesítő adatait a pénztárba történő bejelentkezéshez.
- Ha a kiskereskedelmi környezet megköveteli, hogy az alkalmazottak a saját Azure AD-fiókjuk segítségével jelentkezzenek be a pénztárba és az ezt szolgáltató fizikai eszközbe is, akkor javasolt az **Azure AD egyszeri bejelentkezéssel** lehetőség használata.

## <a name="additional-resources"></a>További erőforrások

[ Dolgozó konfigurálása](tasks/worker.md)

[Retail funkcióprofil létrehozása](retail-functionality-profile.md)


[Kiterjesztett bejelentkezési funkció beállítása az MPOS-hez és a Cloud POS-hoz](extended-logon.md)

[Biztonsági gyakorlati tanácsok a felhőalapú pénztárhoz megosztott környezetekben](dev-itpro/secure-retail-cloud-pos.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
