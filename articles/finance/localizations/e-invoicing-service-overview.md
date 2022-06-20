---
title: Elektronikus számlázás áttekintése
description: Ez a cikk áttekintést nyújt a Microsoft Dynamics 365 Pénzügy és az Elektronikus számlázás modulról Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 01/21/2022
ms.topic: overview
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
ms.openlocfilehash: 4ce5776216855fc664b9beba68036d41920ae602
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861296"
---
# <a name="electronic-invoicing-overview"></a>Elektronikus számlázás áttekintése

[!include [banner](../includes/banner.md)]

Microsoft Dynamics A 365 Pénzügy Dynamics 365 Supply Chain Management modul elektronikus számlázása túl nagy mértékben skálázható többfelhasználós szolgáltatás, amely lehetővé teszi az elektronikus számlák konfigurálható feldolgozását és a konfigurálható elektronikus dokumentumcserét. A feldolgozási és integrációs szabályok teljes mértékben konfigurálható, és a logikát a Finance and Supply Chain Management szolgáltatáson kívül futtatja. A szolgáltatás elsősorban az elektronikus számladokumentumok feldolgozására irányul a vállalat és a kormány között. Konfigurálható azonban más célokra is, például a különböző típusú dokumentumokhoz az üzleti alkalmazásokban használható esetekre.

Az Elektronikus számlázás a következő célok elérése érdekében használhatók:

- Ország-/régióspecifikus követelmények gyors és egyszerű elfogadása
- Elektronikus számlázás-megoldás szabványosított végrehajtásai
- Dokumentumok előzményeinek továbbfejlesztett nyomon követése
- Rövidebb végrehajtási ciklus
- Csökkentett teljes bekerülési költség (TCO)
- Egyszerűen módosítható konfigurációk, amelyek nem igényelnek kódváltozást
- Egyszerűsített konfigurációcsomagolás
- Beépített exportálás, importálás és integráció, valamint egyszerű kezelhetőség az elektronikus számladokumentumok feldolgozása során
- Ugyanazon exportálási, importálási és integrációs konfigurációk egyszerű újrahasználata a vállalatok között

## <a name="service-availability"></a>-szolgáltatás rendelkezésre állása

Az Elektronikus számlázás funkció jelenleg elérhető a Pénzügy és az Ellátásilánc-kezelés vevői számára. További tájékoztatásért tekintse át az alkalmazás licencfeltételeket és feltételeket.

Mivel az ország- és régióspecifikus követelményeket lefedő funkciók a kiadás különböző fázisainál korlátozottak lehetnek, ezért mindig érdemes mindig a legfrissebb dokumentációt áttekinteni, amely a támogatott ország-/régióspecifikus megoldások hatókörét és hatókörét tartalmazza.

Az Elektronikus számlázás a következő Azure földrajzi régiókban telepíthető:

- Egyesült Államok
- Európa
- Ázsia

> [!NOTE]
> Az Elektronikus számlázás nem támogatja a helyszíni telepítéseket.

## <a name="feature-highlights"></a>A funkció újdonságai

- A pénzügy és az ellátásilánc-kezelés integrálása a dobozba
- Egységes felhasználói tapasztalat az elektronikus számlázási folyamat minden országra és régióra vonatkozó konfigurálása és figyelése során.
- Az Elektronikus számlázás megoldások új országokban vagy régiókban történő gyorsabb, könnyebb és olcsóbb elfogadása
- A szolgáltatás konfigurálása a Szabályozó konfigurációs szolgáltatás (RCS) és a globalizációs funkciók beállításával
- Az üzleti adatok átalakítása több elektronikus számlaformátumba (XML, JavaScript Object Notation \[JSON\], TXT és vesszővel elválasztott CSV\[) az RCS-ben \] megadott konfigurációk használatával:

    - Olyan országokban és régiókban elérhető elektronikus jelentési formátumok (ER), ahol nem áll rendelkezésre konfigurálható az elektronikus számla átalakítása.

- Az elektronikus számlák konfigurálható benyújtása külső webszolgáltatásokba, beleértve a tanúsítványok digitális aláíráson keresztüli kezelését:

    - Beépített, egyszerűen bővíthető és konfigurálható integráció több ország és régió további tartalmával

- Webes szolgáltatásoktól származó válaszok kezelése, beleértve a kivételüzenetek konfigurálható kezelését
- Az elektronikus aláírások támogatása (például az XMLDSig aláírási algoritmust használja)
- A dokumentumok e-mailbe küldve és a e-mailben való tárolására való képesség SharePoint
- Elektronikus számlaüzenetek kötegelt feldolgozása
- A bejövő dokumentumok konfigurálható átalakítása, valamint ezeknek a dokumentumoknak a feldolgozása a Pénzügy és az Ellátásilánc-kezelésben
- A bejövő dokumentumok fogadására való képesség a csatornákból, például az e-mailből és a SharePoint

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

Az elektronikus számlázás engedélyezése és használata korlátozott adatokat követelhet meg. Ezek az adatok tartalmazzák a szervezet adóregisztrációs azonosítóját. Ezek az adatok olyan külső szervezeteknek lesznek átküldve, amelyek az adóhatóságok engedélyei alapján a kormányzati webes szolgáltatásokkal való integrációhoz szükséges előre megadott formátumokban küldik el az elektronikus számlákat. A külső rendszerekből ebbe a Dynamics 365 online szolgáltatásba importált adatokra az adatvédelmi nyilatkozatunk [vonatkozik](https://go.microsoft.com/fwlink/?LinkId=512132). A további tudnivalókat lásd az ország-/régióspecifikus funkciódokumentáció "Adatvédelmi nyilatkozat" szakaszában.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
