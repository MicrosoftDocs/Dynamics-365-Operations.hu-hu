---
title: Az elektronikus számlázási szolgáltatás használata a szállítói számlák importálására
description: Ez a témakör arról tartalmaz tájékoztatást, hogy hogyan lehet importálni a szállítói számlákat az elektronikus számlázás szolgáltatással.
author: gionoder
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c28adbfe532e77a52cab7625b9539d1e8e528bea
ms.sourcegitcommit: 19f0e69a131e9e4ff680eac13efa51b04ad55a38
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/22/2022
ms.locfileid: "7983823"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>Az elektronikus számlázási szolgáltatás használata a szállítói számlák importálására

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ez a témakör olyan információkat tartalmaz, amelyek segítenek a szállítói számlák Elektronikus számlázás szolgáltatással történő importálásában. Végigvezeti a Regulatory Configuration Services (RCS), a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management konfigurációs lépésein, amelyeket követnie kell ahhoz, hogy elektronikus szállítói számlákat kapjon a szállítóktól.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>Szállítói számlák importálásának beállítása az RCS-ben
A szállítói számlák importálásának beállításához az RCS-ben kövesse az alábbi lépéseket:

1. Tekintse meg az [általánosan elérhető elektronikus számlázási funkciók](e-invoicing-configuration-rcs.md#generally-available-features) listáját.
2. Válassza ki és importálja az Elektronikus számlázás funkciót. A további tudnivalókat lásd: [Elektronikus számlázási funkció importálása a Microsoft konfigurációs szolgáltatójából](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider).
3. Elektronikus számlázás funkció létrehozása a szervezete számára. A további tudnivalókat lásd: [az Elektronikus számlázás funkció létrehozása a szervezet szolgáltatóján belül](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider).

## <a name="configure-an-email-account-channel"></a>E-mail fiók csatornának konfigurálása

Konfiguráljon egy e-mail fiók csatornát, ha az Elektronikus számlázás funkció, amelyet létrehozott, az elektronikus szállítói számlákat e-mailben kapott csatolt fájlokból importálja.

1. Az RCS-ben válassza ki a létrehozott Elektronikus számlázás funkciót. Győződjön meg arról, hogy a **Vázlat** állapotú verziót választotta ki.
2. A **Beállítások** lapon a rácson jelölje ki a funkcióbeállítást, majd válassza a **Szerkesztés** lehetőséget.
3. Adja meg a csatorna nevét az **Adatcsatorna** lapon a **Paraméterek** mezőcsoportban az **Adatcsatorna** mezőben. A csatornanév nem lehet több tíz karakternél.
4. A **Kiszolgáló címe** mezőbe írja be az e-mail-fiók szolgáltatóját. Például a kiszolgáló címe a **https://outlook.live.com/** oldalhoz **imap-mail.outlook.com**.
5. A **Kiszolgálóport** mezőben adja meg az e-mail-fiók szolgáltatója által használt port számát. Például a **https://outlook.live.com/** kiszolgálóportja **993**.
6. A **Felhasználónév titkos kódja** mezőben adja meg annak a Kulcstároló titkos kódnak a nevét, amely az e-mail felhasználói fiók azonosítóját tartalmazza. Ezt a titkos kulcsot az Azure Key Vault szolgáltatással kell létrehozni és a szolgáltatási környezetben beállítani. 
7. A **Felhasználói jelszó titkos kódja** mezőben adja meg annak a Kulcstároló titkos kódnak a nevét, amely az e-mail felhasználói fiók jelszavát tartalmazza.
8. Nem kötelező – Adja meg az értékeket a **Szűrőtől**, **Tárgyszűrő** és **Dátumszűrő** mezőkben.
9. Adja meg azoknak a postafiók-mappáknak a nevét, amelyekre a következő műveletek vonatkoznak:

    - Importálva a következőből: **Fő mappa**
    - A sikeres feldolgozás után mentve: **Archiválási mappa**
    - A sikertelen feldolgozás után mentve:  **Hibamappa**, ezeket a mappákat nem szükséges létrehozni a postafiókban. A mappák automatikusan létrejönnek az első e-számla importálása és feldolgozása után. 
   
10. Adja hozzá a fájlszűrés adatait a **Mellékletszűrő** mezőcsoportban. A rendszer csak a megadott szűrőnek megfelelő mellékleteket dolgozza fel. Beállíthatja például az xml-kiterjesztésű mellékletekhez az "\*.xml"-t. A melléklet nevét a Dynamics 365 Finance vagy a Dynamics 365 Supply Chain Management beállítás során használja. 
11. Az **Alkalmazhatósági szabályok** lapon tekintse át és szükség szerint frissítse a kritériumokat. A **Csatorna** mezőnek meg kell egyeznie a korábban megadott **Adatcsatornával**. További információ: [Alkalmazhatósági szabályok](e-invoicing-configuration-rcs.md#applicability-rules).
12. Válassza a **Mentés** gombot, és zárja be az oldalt.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Microsoft SharePoint-csatorna konfigurálása

Konfiguráljon egy Microsoft SharePoint-csatornát, ha az Elektronikus számlázás funkció SharePoint-mappákban elhelyezett fájlokból importál elektronikus szállítói számlákat.

1. Az RCS-ben válassza ki a létrehozott Elektronikus számlázás funkciót. Győződjön meg róla, hogy a kiválasztott **Verzió** állapota **Vázlat** legyen.
2. A **Beállítások** lapon a rácson jelölje ki a funkcióbeállítást, majd válassza a **Szerkesztés** lehetőséget.
3. Az **Adatcsatorna** lapon a **Paraméterek** mezőcsoportban válassza a **SharePoint-cím** lehetőséget, és adja meg a SharePoint URL-címet.
4. Válassza ki a **Kiszolgálóportot**, és adja meg az e-mail fiók szolgáltatója által használt port számát.
5. Válassza az **Alkalmazásazonosító** lehetőséget, és adja meg a SharePoint-ügyfél azonosítóját tartalmazó kulcstároló titkos nevét.
6. Válassza az **Alkalmazás titkos kulcsa** lehetőséget, és adja meg a SharePoint-ügyfél jelszavát tartalmazó kulcstároló titkos nevét.
7. Válassza ki a **Fájlszűrő** lehetőséget. Tekintse át és frissítse a maszkot az importálandó elektronikus szállítói számlát tartalmazó fájlok szűréséhez.
8. Az **Alkalmazhatósági szabályok** lapon tekintse át és szükség szerint frissítse a kritériumokat. További információ: [Alkalmazhatósági szabályok](e-invoicing-configuration-rcs.md#applicability-rules).
9. Válassza a **Mentés** lehetőséget, és zárja be az oldalt

### <a name="deploy-an-electronic-invoicing-feature"></a>Elektronikus számlázási funkció telepítése

Az Elektronikus számlázás funkció telepítését lásd: [Az elektronikus számlázás funkció telepítése a szolgáltatási környezetbe](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-or-supply-chain-management"></a>Szállítói számlaimport beállítása a Finance vagy a Supply Chain Management szolgáltatásban
Végezze el a következő két szakasz lépéseit a különböző típusú szállítói számlaimportálások beállításához.

### <a name="import-brazilian-nf-e-from-email"></a>Brazíliai NF-e importálása e-mailből (BR)

1. Jelentkezzen be a Finance vagy a Supply Chain Management környezetbe, és ellenőrizze, hogy a megfelelő jogi személyhez tartozik-e.
2. Menjen a **Szervezeti adminisztráció** > **Beállítás** > **Elektronikus dokumentumparaméterek** lehetőségre.
3. A **Jellemzők** lapon győződjön meg arról, hogy az **NF-e Federal - Brazil elektronikus számla** van kiválasztva.
4. A **Külső csatornák** lapon a **Csatornák** mezőcsoportban válassza a **Hozzáadás** lehetőséget.
5. A **Csatorna** mezőbe írja be az **NFe** értéket (az RCS-ben az elektronikus számlázás funkció adatcsatornájának konfigurációjában megadott csatorna nevét).
6. Adjon meg egy leírást a **Leírás** mezőben. A **Vállalat** mezőben válassza ki a jogi személyt.
7. A **Dokumentum kontextus** mezőben válassza a **Pénzügyi bizonylat kontextus - Vevői számla kontextus modell** lehetőséget.
8. A **Források importálása** mezőcsoportban válassza a **Hozzáadás** lehetőséget.
9. A **Név** mezőbe írja be az **XmlFile** értéket (az RCS-ben az Elektronikus számlázás funkció adatcsatornájának konfigurációjában megadott **Csatolmányszűrő** neve).
10. A **Leírás** mezőben adjon meg egy leírást, az **Adatentitás neve** mezőben pedig válassza a **Beérkezett NF-e XML-dokumentumok** értéket.
11. A **Modell leképezés** mezőben válassza az **NF-e mail importálás - NF-e email importálás (BR)** lehetőséget, majd válassza a **Mentés** lehetőséget.
12. Az **Elektronikus dokumentum** lapon az **Elektronikus jelentéskészítés** mezőcsoportban válassza a **Hozzáadás** lehetőséget, a **Táblázat neve** mezőben pedig a **Beérkezett NF-e XML dokumentum** beállítást.
13. A **Dokumentum kontextus** mezőben válassza a **Pénzügyi bizonylat kontextus lekérdezése - Vevői számla kontextus** lehetőséget.
14. Az **Elektronikus dokumentummodell leképezés** mezőben válassza a **Lekérdezés leképezése - Pénzügyi bizonylat leképezése** lehetőséget.
15. Válassza ki a **Választípusok** lehetőséget, majd válassza az **Új** lehetőséget.
16. A **Válasz típusa** mezőbe írja be a **Válasz** értéket. A **Beküldés állapota** mezőbe írja be az **Ütemezett** értéket.
17. A **Modell leképezése** mezőben válassza a **Modell leképezése válaszüzenetből - Válaszüzenet importálási formátum** lehetőséget.
18. Válassza a **Mentés** gombot, majd zárja be az oldalt.

### <a name="import-peppol-electronic-vendor-invoices"></a>PEPPOL elektronikus szállítói számlák importálása

1. Menjen az **Elektronikus jelentéskészítés** munkaterületre, és válassza a **Jelentéskonfigurációk** menüpontot.
2. Válassza ki a **Vevői számlakontextus-modellt**, majd válassza ki a **Konfiguráció létrehozása** > **Származtatás innen: Vevői számlamodell, Microsoft** lehetőséget származtatott konfiguráció létrehozásához.
3. A **Vázlat** verzióban válassza a **Tervező** lehetőséget és az **Adatmodell** fában válassza a **Modell hozzárendelése adatforráshoz** lehetőséget.
4. A **Meghatározások** fán jelölje ki az **Adatcsatorna** elemet, majd válassza a **Tervező** elemet.
5. Bontsa ki az **Adatforrások** fában a **$Context\_Csatorna** tárolót. Az **Érték** mezőben válassza a **Szerkesztés** lehetőséget, és adja meg az adatcsatorna nevét. Ez annak a csatornának a neve, amelyet az RCS-ben az Elektronikus számlázás funkció adatcsatornájának konfigurációjában adtak meg. 
7. Válassza a **Mentés** gombot, és zárja be az oldalt.
8. Zárja be a lapot.
9. Válassza ki a **Vevői számlakontextus-modellből** az imént létrehozott származtatott konfigurációt, és a **Verziók** gyorslapon válassza a **Módosítási állapot** > **Befejezve** lehetőséget.
10. Menjen a **Szervezeti adminisztráció** > **Beállítás** > **Elektronikus dokumentum paraméterek** menüpontba, és a **Jellemzők** lapon győződjön meg arról, hogy a **PEPPOL Global elektronikus számlák** van kiválasztva. 
11. A **Külső csatornák** lapon a **Csatornák** mezőcsoportban válassza a **Hozzáadás** lehetőséget.
12. A **Csatorna** mezőben adja meg az adatcsatorna nevét, a **Leírás** mezőben pedig egy leírást.
13. A **Vállalat** mezőben válassza ki a jogi személyt. 
14. A **Dokumentumkontextus** mezőben válassza ki az újonnal származtatott konfigurációt a **Vevői számlakontextus-modellből**. A leképezés leírásának **Adatcsatorna-kontextusnak** kell lennie.
15. A **Források importálása** mezőcsoportban válassza a **Hozzáadás** lehetőséget.
16. A **Név** mezőben adja meg a **Mellékletszűrő neve** elemet, és az **Adatentitás neve** mezőben válassza ki a **Szállítói számla fejlécét**.
17. A **Modellleképezés** mezőben válassza a **Szállítói számla importálása – Import szállítói számla** lehetőséget.
18. Kattintson a **Mentés** gombra, majd zárja be az oldalt.


## <a name="receive-electronic-invoices"></a>Elektronikus számlák fogadása

Az elektronikus számlázás szolgáltatás két lépést hajt végre az adatcsatornákból történő számlázás során:

1. A postafiók elérése és az e-mail olvasása.
2. Az e-mailek feldolgozása. 
    
E két lépés végrehajtásához az ügyfélnek minden egyes lépésnél manuálisan kell meghívnia a szolgáltatást. Javasoljuk azonban, hogy állítsa be az elektronikus dokumentumok fogadására szolgáló köteget.

Ha elektronikus számlákat szeretne kapni, kövesse az alábbi lépéseket:

1. Menjen a **Szervezeti adminisztráció** > **Időszakos** > **Elektronikus dokumentumok** > **Elektronikus dokumentumok fogadása** menüpontra.
2. Válassza az **OK** lehetőséget, majd zárja be az oldalt.


## <a name="view-receive-logs-for-electronic-invoices"></a>Elektronikus számlák fogadási naplóinak megtekintése

Az elektronikus számlák fogadási naplóinak megtekintéséhez lépjen a **Szervezet adminisztráció** > **Időszakos** > **Elektronikus dokumentumok** > **Elektronikus dokumentumok fogadási naplója** menüpontra.
Ha nem látja a sikeresen feldolgozott számlákat, távolítsa el a táblaszűrőt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
