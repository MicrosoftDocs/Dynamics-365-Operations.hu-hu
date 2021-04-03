---
title: Első lépések az Egyiptomra vonatkozó elektronikus számlázási bővítmény használata során
description: Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az Első lépéseket az egyiptomi elektronikus számlázásbővítmény Finance és Supply Chain Management szolgáltatásban való használatát.
author: gionoder
manager: AnnBe
ms.date: 02/26/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 68ee08226f440e850a080600dbf5e16768b45e43
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592598"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-egypt"></a>Első lépések az Egyiptomra vonatkozó elektronikus számlázási bővítmény használata során

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ez a témakör olyan információkat tartalmaz, amelyek bemutatják az egyiptomi elektronikus számlázásbővítménnyel kapcsolatos első lépéseket. Ez a témakör végigvezeti a Regulatory Configuration Services (RCS) országfüggő konfigurációs lépésein, amelyek kiegészítik az [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md) részben leírt lépéseket.

## <a name="country-specific-configuration-for-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Országspecifikus konfiguráció az egyiptomi elektronikus számla (EG) elektronikus számlázási funkcióhoz

Az egyiptomi elektronikus számla (EG) elektronikus számlázási funkció konfigurálása előtt néhány lépést kell végrehajtani. A rendszer a konfigurációk néhány paraméterét az alapértelmezett értékekkel teszi közzé, így azok áttekintésére és frissítésére van szükség, hogy az üzleti műveletei számára megfelelőbb legyen.

### <a name="prerequisites"></a>Előfeltételek

Mielőtt ezt az eljárást elvégezné ebben a részben, a következőket kell tennie:

- Hozzon létre egy digitális tanúsítvány titkos kódját az [Első lépések az elektronikus számlázási bővítmény szolgáltatásfelügyeletének használata során](e-invoicing-get-started-service-administration.md) rész **Digitális tanúsítvány titkos kódjának létrehozása** pontjában leírtaknak megfelelően. Tesztelési célokra az egyiptomi adóhatóság olyan specifikus digitális tesztelési tanúsítványokat biztosít, amelyek csak a tesztelési és megoldás-ellenőrzési fázisok során használhatók. További információkért tekintse meg az egyiptomi adóhatóság webhelyét, és használja az [Egyiptomi e-számlázási SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/) részben megadott hivatkozást.
- Hozzon létre egyegyiptomi elektronikus számla (EG) elektronikus számlázási funkciót a szervezete számára az **Elektronikus számlázási funkció létrehozása a szervezetszolgáltató keretében** részben leírtaknak megfelelően, amely az [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md) pontban található.

1. RCS-ben a **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.
2. Az **Elektronikus számlázás-bővítmény funkciók** oldalon ellenőrizze, hogy be van-e jelölve a létrehozott **Egyiptomi elektronikus számla (EG)** Elektronikus számlázás funkciója.
3. A **Verziók** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
4. A **Beállítások** lap rácsán válassza az **Értékesítési számla** funkció beállítását.
5. Jelölje be a **Szerkesztés** lehetőséget, és a **Műveletek** mezőcsoport **Műveletek** lapján válassza az **Egyiptomi adóhatóság json-dokumentumának aláírása** lehetőséget.
6. A **Paraméterek** mezőcsoportban válassza ki a paramétert, a **Tanúsítvány** nevét, és válassza ki az elektronikus számlázási funkcióval használni kívánt digitális tanúsítvány nevét.
7. A **Műveletek** mezőcsoportban válassza az **Integráció az Egyiptomi ETA-szolgáltatással** lehetőséget. Ismételje meg ezt a lépést a művelet két előfordulásával.
8. A **Paraméterek** mezőcsoportban válassza ki a **Webszolgáltatás URL-címe** és a **Bejelentkezési URL-cím** lehetőséget, és ha szükséges, ellenőrizze az URL-cím paramétereit. A tesztelési és éles környezetben használandó URL-címért lépjen az egyiptomi adóhatóság webhelyére, amelyhez használja az [Egyiptomi e-számlázási SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/) részben megadott hivatkozást.
9. Válassza a **Mentés** gombot, és zárja be az oldalt.
10. Az alkalmazás beállításának konfigurálása az [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md) oldalon látható.

## <a name="country-specific-configuration-of-the-application-setup-for-the-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Az Egyiptomi elektronikus számla (EG) Elektronikus számlázási funkció alkalmazásbeállításának országspecifikus konfigurációja

Az **Egyiptomi elektronikus számla (EG)** Elektronikus számlázási funkció alkalmazásbeállításának konfigurációjának meghatározott lépések végrehajtására van szüksége. Ezeket a lépéseket az Elektronikus számlázási funkciónak az Elektronikus számlázási szolgáltatási környezetbe való telepítése előtt el kell végeznie.

### <a name="prerequisites"></a>Előfeltételek

Mielőtt ennek a szakasznak a lépését befejezi, hozzon létre és kezdeményezzen egy **Egyiptomi elektronikus számla (EG)** Elektronikus számlázási funkciót az **Egyiptomi elektronikus számla (EG)** Elektronikus számlázási funkció alkalmazásbeállításának konfigurációjához, amelynek leírása az **Alkalmazásbeállítás konfigurálása** témakörben található az [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md) pontban.

1. RCS-ben a **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.
2. Az **Elektronikus számlázás-bővítmény funkciók** oldalon ellenőrizze, hogy be van-e jelölve az **Egyiptomi elektronikus számla (EG)** Elektronikus számlázás funkciója.
3. A **Verziók** lapon ellenőrizze, hogy a **Piszkozat** verzió ki van-e választva.
4. A **Beállítások** lapon válassza ki az **Alkalmazásbeállítás** lehetőséget és a **Kapcsolódó alkalmazás** mezőben válassza ki azt az alkalmazást, ahová telepíteni szeretné.
5. A **Tábla neve** mezőben ellenőrizze, hogy ki van-e választva a vevői számlanapló.
6. Válassza ki a **Választípusok** lehetőséget, majd válassza az **Új** lehetőséget.
7. A **Válasz típusa** mezőbe írja be a "Response" szót, a **Leírás** mezőbe pedig a "Description" szót.
8. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
9. A **Modell-leképezés** mezőben válassza a **Modell-leképezés válaszüzenetből** **Válaszüzenet importálási formátuma (előzetes verzió)** lehetőséget, majd válassza a **Mentés** lehetőséget.
10. Válassza az **Új**, lehetőséget majd a **Válasz típusa** mezőbe írja be a "ResponseData" rögzített értéket. A **Leírás** mezőbe írja a "Description" szót.
11. A **Beküldés állapota** mezőben válassza a **Függőben** lehetőséget.
12. Az **Adatentitás neve** mezőben válassza az **Értékesítésiszámla-fejlécek V2** lehetőséget.
13. A **Modell-leképezés** mezőben válassza az **Egyiptomi válaszadatok importálása** **Egyiptomi válaszadatok importálása (előzetes verzió)** lehetőséget, majd válassza a **Mentés** lehetőséget.
14. Az Elektronikus számlázási funkció telepítését lásd: [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

Az **Egyiptomi elektronikus számla (EG)** funkcióhoz korlátozott számú adat küldése válhat szükségessé, ideértve a szervezet adóregisztrációs azonosítóját. Az adatokat továbbítják az adóhatóság által kinevezett harmadik fél ügynökségekhez, az elektronikus számlák – kormányzati szervek webszolgáltatással való integrációhoz szükséges, előre meghatározott formátumban való – adott adóhatósághoz történő elküldése céljából. A rendszergazda engedélyezheti és letilthatja a funkciót a **Szervezeti adminisztráció** > **Beállítások** > **Elektronikus dokumentumparaméterek** lehetőségre való navigálással. Válassza ki a **Funkciók** lapot, majd az **Egyiptomi elektronikus száma (EG)** funkciót tartalmazó sorokat, és végezze el a megfelelő kijelölést. A külső rendszerekből ebbe a Dynamics 365 online szolgáltatásba importált adatok az [Adatvédelmi nyilatkozatunk](https://go.microsoft.com/fwlink/?LinkId=512132) hatálya alá tartoznak. További tájékoztatásért olvassa el az országspecifikus funkciók dokumentációja szakaszokban található Adatvédelmi nyilatkozatot.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus számlázási bővítmény áttekintése](e-invoicing-service-overview.md)
- [Első lépések az elektronikus számlázási bővítményszolgáltatás adminisztrálása során](e-invoicing-get-started-service-administration.md)
- [Első lépések az elektronikus számlázási bővítmény használata során](e-invoicing-get-started.md)
- [Elektronikus vevői számlák Egyiptomban](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
