---
title: Az elektronikus aláírások áttekintése
description: Ez a cikk áttekintést nyújt az elektronikus aláírásokról, és bemutatja, hogy hogyan használhatók.
author: maertenm
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d0279f4ce7e3c7fcd8a10bbf16a6fbdd8a423b7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565649"
---
# <a name="electronic-signatures-overview"></a>Az elektronikus aláírások áttekintése

[!include [banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt az elektronikus aláírásokról, és bemutatja, hogy hogyan használhatók.

## <a name="what-is-an-electronic-signature"></a>Mi az elektronikus aláírás?

Az elektronikus aláírás igazolja annak a személynek a személyazonosságát, aki egy számítási folyamat elindítása vagy jóváhagyása előtt áll. Egyes ágazatokban az elektronikus aláírás ugyanúgy jogilag kötelező érvényű, mint a kézzel írott aláírás.

Az elektronikus aláírás használatát törvény írja elő számos szabályozott iparágban, például a gyógyszeriparban, az élelmiszer- és italgyártás, a repülőgépgyártás és a honvédelem területén. Az Amerikai Egyesült Államok élelmiszer- és gyógyszerügyi hatóságának (FDA, Food and Drug Administration) 21 CFR Part 11 szabályozásában meghatározott követelmények teljesítéséhez szintén szükséges.

> [!NOTE]
> Az elektronikus aláírás önmagában nem ugyanaz, mint a digitális aláírás. Az elektronikus aláírás mindössze a kézzel írt aláírás helyettesítése, míg a digitális aláírás további biztonsági szolgáltatásokat biztosít. A digitális aláírások esetén meghatározható, hogy egy másik felhasználó vagy folyamat nem módosította-e illetéktelenül az adatokat. A digitális aláírások ellenőrizhetők, és ennek az ellenőrzésnek az eredményét nem cáfolhatja meg még az adatok aláírására használt tanúsítvány tulajdonosa sem. Az alábbi leírásból kiderül, hogy az elektronikus aláírásokba a digitális aláírások funkciói is be vannak építve.

## <a name="electronic-signatures"></a>Elektronikus aláírások

A kritikus üzleti folyamatoknál használhatja az elektronikus aláírásokat. Egyes folyamatokba be vannak építve az elektronikus aláírási funkciók. Ugyanezen a képernyőn egyéni elektronikus aláírási követelményeket is létrehozhat, tetszőleges adatbázis-táblára és mezőre vonatkozóan.

Az elektronikus aláírásokba a digitális aláírások funkciói is be vannak építve. Minden felhasználónak, aki dokumentumokat ír alá, be kell szereznie egy érvényes kriptográfiai tanúsítványt. A dokumentum aláírásakor a tanúsítványhoz társított titkos kulcsot ellenőrzi a rendszer. Egy naplóban vannak rögzítve az elektronikus aláírások adatai, ezáltal gondoskodik az ellenőrzéshez szükséges könyvvizsgálati naplóról. Az elektronikus aláírások beállításához lásd: [Elektronikus aláírások beállítása](tasks/set-up-electronic-signatures.md).

## <a name="users-who-require-access-to-electronic-signatures"></a>Felhasználók, akik az elektronikus aláírásokhoz kérnek hozzáférést

Általában háromféle felhasználónak van szüksége biztonsági hozzáférésre az elektronikus aláíráshoz: az elektronikus aláírás rendszergazdái, az aláírók és az elektronikus aláírás felülvizsgálói.

### <a name="electronic-signature-administrator"></a>Elektronikus aláírás rendszergazdája

Az elektronikus aláírás rendszergazdája állítja be az aláírási követelményeket, az általános paramétereket és a jóváhagyókat, valamint ő kap figyelmeztetést, ha egy aláírást nem lehet ellenőrizni. Alapértelmezés szerint egy felhasználó, aki az **Informatikai vezető** biztonsági szerepkörbe tartozik, rendelkezik engedéllyel az elektronikus aláírások felügyeletére.

### <a name="signer"></a>Aláíró

A kötelezően aláírandó dokumentumokhoz és folyamatokhoz az aláírónak kell elektronikus aláírást csatolnia. Alapértelmezés szerint a **Rendszer felhasználója** biztonsági szerepkörbe tartozó felhasználó rendelkezik engedéllyel a dokumentumok elektronikus aláírására.

> [!NOTE]
> Az aláírónak ezenkívül további engedélyekre lehet szüksége, hogy hozzáférjen az aláírandó dokumentummal vagy folyamattal kapcsolatos adatokhoz. Annak a felhasználónak, aki adatokat módosít, majd ezeket a módosításokat alá kell írnia, engedéllyel kell rendelkeznie az adatok módosítására. A más felhasználó nevében aláíró felhasználónak nem kell rendelkeznie az adatokhoz való hozzáféréssel. Ilyen típusú felhasználó például egy felettes, aki aláírja az alkalmazottak módosításait.

### <a name="electronic-signature-auditor"></a>Elektronikus aláírások felülvizsgálója

Az elektronikus aláírás felülvizsgálójának feladata az adatbázisnapló és az aláírások adatbázisnaplóban elérhető felülvizsgálati naplójának áttekintése. Alapértelmezés szerint egy felhasználó, aki az **Informatikai vezető** biztonsági szerepkörbe tartozik, rendelkezik engedéllyel az elektronikus aláírások auditálására.

Ha az **Informatikai vezető** szerepkörtől eltérő szerepben van, győződjön meg arról, hogy szerepe rendelkezik-e a következő jogosultságokkal:

- Sikertelen elektronikus aláírások megtekintése
- Adatbázisnapló megtekintése

## <a name="signing-documents-electronically"></a>Dokumentumok elektronikus aláírása

### <a name="get-a-certificate"></a>Tanúsítvány beszerzése

Ahhoz, hogy Ön elektronikusan alá tudja írni a dokumentumokat, kérvényeznie kell egy tanúsítványt.

> [!NOTE]
> A Microsoft SQL Server szolgáltatásai vannak használva a tanúsítványok létrehozására és az elektronikus aláírás engedélyezésére. Nincs szükség további tanúsítványokra és nyilvános kulcsok infrastruktúrájára (PKI).

Amikor tanúsítványt kérvényez, a rendszer létrehoz Önnek egy nyilvános és egy titkos kulcsot az adatbázisban. A titkos kulcsot egy olyan jelszóval titkosíthatja, amelyet csak Ön ismer. Amikor elektronikusan aláír egy dokumentumot, akkor a jelszó megadásával igazolhatja a személyazonosságát.

A tanúsítvány igényléséhez ugorjon a **Beállítások** oldalon a **Számlák** lapra, majd kattintson a **Tanúsítvány beszerzése** parancsra.

Adja meg és erősítse meg a jelszót, amelyet aláírásra kíván használni. A jelszó a titkos kulcsot védi, valamint engedélyezi a tanúsítvány használatát. Ezt a jelszót nem tárolja az adatbázis, és senki más nem érheti el, még a rendszergazdája sem.

Ha elfelejti a tanúsítványhoz tartozó jelszót, akkor a tanúsítványt alaphelyzetbe kell állítani. A tanúsítvány alaphelyzetbe állítása nincs hatással azokra a dokumentumokra, amelyeket a korábbi tanúsítvánnyal írt alá. A tanúsítvány alaphelyzetbe állításához a **Beállítások** oldalon, kattintson a **Tanúsítvány alaphelyzetbe állítása**.

### <a name="sign-a-document-electronically"></a>A dokumentumok elektronikus aláírása

Ha olyan módosítást végez, amelyhez elektronikus aláírás szükséges, akkor megjelenik a **Dokumentum aláírása** képernyő.

1. A **Dokumentum aláírása** oldalon kattintson a **Dokumentum** fülre, és tekintse át a dokumentumon végzett módosításokat.
2. Az **Aláírás** lapon válasszon ki egy okkódot.
3. Írjon be megjegyzést, ha megjegyzés szükséges.
4. Ha a felhasználói azonosítója nem jelenik meg az **Aláíró** mezőben, akkor válassza ki a listából.
5. Ha szükséges, akkor adja meg a helyét.
6. Kattintson az **OK** gombra.

### <a name="sign-for-another-users-changes"></a>Más felhasználó változtatásainak aláírása

Bizonyos esetekben előfordulhat, hogy az egyik felhasználó által végzett módosításokat egy másik felhasználónak kell aláírnia. Például egy felettes számára kötelező lehet a beosztottja által az anyagjegyzékeken végzett módosítások aláírása (Anyagjegyzék). A következő eljárással jelölheti ki egy másik felhasználó aláírójaként a felhasználót.

> [!NOTE]
> Amikor egy felhasználó egy másik felhasználó módosításait írja alá, akkor az aláírást azon a munkaállomáson kell elvégezni, amelyen a módosítást elvégezték. A felhasználó mindaddig nem tudja menteni a módosítást, amíg meg nem történik az aláírás.

Jóváhagyók kijelöléséhez kövesse az alábbi lépéseket.

1. A **Beállítások** oldalon a **Számlák** fülön kattintson **Jóváhagyó kijelölése** parancsra.
2. A **Jóváhagyó felhasználó azonosítója** mezőben válassza ki annak a felhasználónak az azonosítóját, akinek alá kell írnia egy másik felhasználó által végzett módosításokat.
3. Az **Aláírható felhasználó azonosítója** mezőben válassza ki annak a felhasználónak az azonosítóját, akinek a módosításait alá kell írni.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]