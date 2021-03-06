---
title: Elektronikus számlázás áttekintése
description: Ez a témakör információkat tartalmaz arról, hogyan tudja beállítani az Elektronikus számlázást a Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokban.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a6a8ea3fcad980dc02f489e07a7b21fe1c1b5a5a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839980"
---
# <a name="electronic-invoicing-overview"></a>Elektronikus számlázás áttekintése

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 Finance és Dynamics 365 Supply Chain Management Elektronikus számlázása egy tetszőlegesen méretezhető multibérlő szolgáltatás, amely lehetővé teszi az elektronikus számlázási dokumentumok konfigurálható feldolgozását, valamint a dokumentumok konfigurálható cseréjét. A feldolgozási és integrációs szabályok teljes mértékben konfigurálható, és a logikát a Finance and Supply Chain Management szolgáltatáson kívül futtatja. A szolgáltatás elsősorban az e-számla feldolgozását célozza a vállalatok és kormányzati szervek közötti forgatókönyvek esetére, de más célokra is konfigurálhatók.

Az Elektronikus számlázás a következő célok elérése érdekében használhatók:

- Ország-/régióspecifikus követelmények gyors és egyszerű elfogadása
- Elektronikus számlázás-megoldás szabványosított végrehajtásai
- Dokumentumok előzményeinek továbbfejlesztett nyomon követése
- Rövidebb végrehajtási ciklus
- Csökkentett teljes bekerülési költség (TCO)
- A kódmódosítást nem igénylő, egyszerűen állítható konfigurációk
- Egyszerűsített konfigurációcsomagolás
- Beépített exportálás, importálás és integráció, valamint egyszerű bővíthetőség az e-számla dokumentumainak feldolgozásában
- Ugyanazon exportálási, importálási és integrációs konfigurációk egyszerű újrahasználata a vállalatok között

Az Elektronikus számlázás használatához telepítenie kell a bővítményt a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban lévő projektből. Ezután kövesse a beállítási eljárást, hogy a Finance vagy Supply Chain Management szolgáltatással be tudja kapcsolni az integrációt. További tájékoztatást az [Első lépések – Elektronikus számlázás](e-invoicing-get-started.md) részben talál.

## <a name="service-availability"></a><a name="availability"></a>-szolgáltatás rendelkezésre állása

Az Elektronikus számlázás jelenleg az előzetes verzión keresztül érhető el a vevők számára, és a következő fázisban a szolgáltatás általánosan elérhetővé válik. Mivel az ország-/régióspecifikus követelményeknek megfelelő funkciók a kiadás különböző fázisaiban korlátozottak lehetnek, ezért mindig a legfrissebb dokumentációt kell ellenőriznie, amely kiemeli a támogatott ország-/régióspecifikus megoldások lefedettségét és terjedelmét.

Az Elektronikus számlázás a következő Azure földrajzi régiókban telepíthető:

- Amerikai Egyesült Államok
- Európa

> [!NOTE]
> Az Elektronikus számlázás nem támogatja a helyszíni telepítéseket.

## <a name="extended-configurability"></a>Kiterjesztett konfigurálhatóság

Az Elektronikus számlázás olyan helyzetekben használható, amikor a kijelölt felek számára létre kell hoznia, és el kell küldenie egy elektronikus dokumentumot. Ez kifejezetten a kapott adatok alapján történő konfigurálható feldolgozási műveletek futtatására szolgál. A Finance and Supply Chain Management szolgáltatásban rendelkezésre álló beállítási lehetőségek csak a dokumentumátalakításra korlátozódnak. A szolgáltatás a rendelkezésre álló konfigurálható integrációk hozzáadásával kiterjeszti ezeket a beállításokat. Ezenkívül az összes korábban rendelkezésre álló elektronikus számlafunkciók, például a brazil Nota pénzügyi eletrônica (NF-e), a mexikói Comprobante pénzügyi Digital por Internet (CFDI) vagy más Nyugat-európai Universal Business Language (UBL)/páneurópai közbeszerzés OnLine (PEPPOL) funkciók az exportálási és importálási konfigurációk, valamint a külső webszolgáltatások integrációjának engedélyezésére használhatók.

## <a name="feature-highlights"></a>A funkció újdonságai

- Kulcsrakész integráció a Finance and Supply Chain management szolgáltatással
- Egységes felhasználói élmény az e-számla folyamatának konfigurálásához és nyomon követéséhez az összes országban vagy régióban
- Az Elektronikus számlázás megoldások új országokban vagy régiókban történő gyorsabb, könnyebb és olcsóbb elfogadása
- A szolgáltatás konfigurációja a Regulatory Configuration Service (RCS) szolgáltatással és a Globalizációs funkció beállításával
- Üzleti adatok átalakítása több e-számla formátumba (XML, JavaScript Object Notation \[JSON\], TXT és vesszővel tagolt értékek \[CSV\]) az RCS-ben meghatározott konfigurációk használatával:

    - Azok az elektronikus jelentési formátumok, amelyek elérhetők azon országokban vagy régiókban, ahol az e-számla átalakításának konfigurálhatósága nem érhető el

- E-számlák konfigurálható küldése a külső webszolgáltatásokhoz, többek között a digitális aláírásokon keresztül történő minősítéshez:

    - Beépített, könnyen kiterjeszthető és konfigurálható integráció több ország számára további tartalmakkal

    > [!NOTE]
    > Jelenleg korlátozott számú közvetlen beküldés támogatott. További tudnivalókat a témakör korábbi, [A szolgáltatás elérhetősége](#availability) című része tartalmaz. A támogatás a jövőben is ki lesz terjesztve.

- A webszolgáltatások válaszának kezelése, beleértve a konfigurálható kivételre vonatkozó üzenetek kezelését
- Elektronikus aláírások támogatása (például az XMLDSig aláírási algoritmus használatával)
- E-számla üzenetek kötegelt feldolgozása

## <a name="architecture-and-data-flow"></a>Architektúra és az adatforgalom

Amikor az Elektronikus számlázás az LCS rendszerből telepíti, és a kötelező beállítások minden szükséges alkalmazásban be vannak fejezve, akkor létrejön egy biztonságos kapcsolat. A szolgáltatás jelenleg az Egyesült Államok és Európa adatközpontjaiban található. Ezért a szolgáltatás helye eltérhet a kapcsolódó Finance vagy Supply Chain Management példány helyétől. Miután befejezte az Elektronikus számlázás beállítását, és bekapcsolta az integrációt az elektronikus számla elküldésekor, a program elküldi az adott dokumentummal kapcsolatos alapadatokat és tranzakciós adatokat az Elektronikus számlázásnak.

> [!NOTE]
> Ha az elektronikus számla vagy bármely más dokumentum személyes adatokat tartalmaz, akkor győződjön meg róla, hogy a funkció használata megfelel az általános adatvédelmi rendeletnek (GDPR) és más, a személyes adatok átvitelével kapcsolatos előírásoknak.

### <a name="high-level-description-of-the-data-flow"></a>Az adatfolyamok magas szintű leírása

1. A vevő egy Canonical üzleti dokumentumot küld a szolgáltatásnak.
2. A vevőtől kapott környezeti információ alapján a szolgáltatás kiválasztja a megfelelő feldolgozási folyamatot.
3. A szolgáltatás futtatja a feldolgozási műveleteket. Ezen műveletek közé tartozhat például az üzleti dokumentum átalakítása elektronikus számlává, az elektronikus aláírás alkalmazása és a dokumentum külső webszolgáltatásba küldése.
4. A kapott és feldolgozott dokumentumok a vevő Azure Blob-tárhelyén lesznek tárolva.
5. Minden feldolgozásra használt bérlői titok és tanúsítvány a vevő Azure kulcstartójában lesz tárolva.
6. A szolgáltatás igény szerint információt nyújt a vevőnek az elküldött üzleti dokumentum feldolgozási állapotáról.
7. A vevő a teljesített feldolgozási végrehajtással kapcsolatos adatokat kap, és a napló összes adatát elérhetővé teszi. A feldolgozás során létrehozott vagy fogadott dokumentumot is elérhetővé teszi.

A következő ábra bemutatja, hogyan áramlik ki és be az adat az elektronikus számlázásba.

![Az Elektronikus számlázás adatfolyama](media/e-invoicing-service-data-flow-diagram-overview.png)

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat
Az Elektronikus számlázás engedélyezése és használata korlátozott adatok küldését igényelheti, ideértve a szervezet adóregisztrációs azonosítóját. Ezek továbbítva lesznek az adóhatóságok által kinevezett harmadik fél ügynökségekhez, az elektronikus számlák – kormányzati szervek webszolgáltatásaival való integrációhoz szükséges, előre meghatározott formátumban való – elküldése céljából. A külső rendszerekből ebbe a Dynamics 365 online szolgáltatásba importált adatok az [Adatvédelmi nyilatkozatunk](https://go.microsoft.com/fwlink/?LinkId=512132) hatálya alá tartoznak. További tájékoztatásért olvassa el az országspecifikus funkciók dokumentációja szakaszokban található Adatvédelmi nyilatkozatot.

## <a name="additional-resources"></a>További erőforrások
- [Szolgáltatásfelügyelet](e-invoicing-service-administration.md)
- [Elektronikus számlák konfigurálása az RCS szolgáltatásban](e-invoicing-configuration-rcs.md)
- [Elektronikus számlák kibocstása a Finance és Supply Chain Management szolgáltatásokban](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
