---
title: Az elektronikus számlázási szolgáltatás használata a szállítói számlák importálására
description: Ez a témakör arról tartalmaz tájékoztatást, hogy hogyan lehet importálni a szállítói számlákat az elektronikus számlázás szolgáltatással.
author: gionoder
ms.date: 08/03/2021
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
ms.openlocfilehash: 434bf1f6a5a727a71592493b85ab166cbeff2f0980c2c968c99973a03f4dc660
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751252"
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
3. Az **Adatcsatorna** lapon a **Paraméterek** mezőcsoportban válassza a **Kiszolgáló címe** lehetőséget, és adja meg az e-mail fiók szolgáltatóját.
4. Válassza ki a **Kiszolgálóportot**, és adja meg az e-mail fiók szolgáltatója által használt port számát.
5. Válassza a **Felhasználónév titok** lehetőséget, és adja meg annak a Kulcstároló titoknak a nevét, amely az e-mail felhasználói fiók azonosítóját tartalmazza.
6. Válassza a **Felhasználói jelszó titok** lehetőséget, és adja meg annak a Kulcstároló titoknak a nevét, amely az e-mail felhasználói fiók jelszavát tartalmazza.
7. Válassza ki a **Tárgy szűrőt**. Tekintse át és frissítse az alapértelmezett e-mail tárgyát tartalmazó karakterláncot az importálandó elektronikus szállítói számlát tartalmazó e-mail azonosításához.
8. Az **Alkalmazhatósági szabályok** lapon tekintse át és szükség szerint frissítse a kritériumokat. További információ: [Alkalmazhatósági szabályok](e-invoicing-configuration-rcs.md#applicability-rules).
9. Válassza a **Mentés** gombot, és zárja be az oldalt.

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

## <a name="set-up-vendor-invoice-import-in-finance-and-supply-chain-management"></a>Szállítói számlaimport beállítása a Finance és a Supply Chain Management szolgáltatásban
Végezze el a következő két szakasz lépéseit a különböző típusú szállítói számlaimportálások beállításához.

### <a name="import-vendor-invoices-from-email"></a>Szállítói számlák importálása e-mailből

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
2. Válassza ki az **Vevői számla kontextus modell** lehetőséget, és hozzon létre egy származtatott konfigurációt.
3. A **Vázlat** verzióban válassza a **Tervező** lehetőséget.
4. Az **Adatmodell** fában jelölje ki a **Vevői számla** elemet, majd válassza a **Modell hozzárendelése adatforráshoz** lehetőséget.
5. A **Meghatározások** fán jelölje ki a **Vevői számla** elemet, majd válassza a **Tervező** elemet.
6. Az **Adatforrások** fán válassza a **Kontextus\_Csatorna** elemet. Az **Érték** mezőben válassza ki a **PEPPOL** lehetőséget. Ez annak a csatornának a neve, amelyet az RCS-ben az Elektronikus számlázás funkció adatcsatornájának konfigurációjában adtak meg. 
7. Válassza a **Mentés** gombot, és zárja be az oldalt.
8. Zárja be a lapot.
9. Válassza ki a **Vevői számla kontextus modell** lehetőséget, majd a **Verziók** gyorslapon válassza az **Állapot módosítása** > **Befejezett** lehetőséget.
10. Menjen a **Szervezeti adminisztráció** > **Beállítás** > **Elektronikus dokumentum paraméterek** menüpontba, és a **Jellemzők** lapon győződjön meg arról, hogy a **PEPPOL Global elektronikus számlák** van kiválasztva. 
11. A **Külső csatornák** lapon a **Csatornák** mezőcsoportban válassza a **Hozzáadás** lehetőséget.
12. A **Csatorna** mezőbe írja be a **PEPPOL** értéket. Adjon meg egy leírást a **Leírás** mezőben.
13. A **Vállalat** mezőben válassza ki a jogi személyt. A **Dokumentum kontextus** mezőben válassza az **Vevői számla kontextus - Vevői számla kontextus modell** lehetőséget.
14. Válassza a **Mentés** gombot, majd zárja be az oldalt.


## <a name="receive-electronic-invoices"></a>Elektronikus számlák fogadása
Ha elektronikus számlákat szeretne kapni, kövesse az alábbi lépéseket:

1. Menjen a **Szervezeti adminisztráció** > **Időszakos** > **Elektronikus dokumentumok** > **Elektronikus dokumentumok fogadása** menüpontra.
2. Válassza az **OK** lehetőséget, majd zárja be az oldalt.

## <a name="view-receive-logs-for-electronic-invoices"></a>Elektronikus számlák fogadási naplóinak megtekintése

Az elektronikus számlák fogadási naplóinak megtekintéséhez lépjen a **Szervezet adminisztráció** > **Időszakos** > **Elektronikus dokumentumok** > **Elektronikus dokumentumok fogadási naplója** menüpontra.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
