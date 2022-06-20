---
title: Konszolidáció importálási formátuma
description: Ez a cikk részletes információkat nyújt a több jogi személytől származó pénzügyi adatok konszolidálása során használt importálási formátumról.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 0aee830f8fbfa384c86dc16465b202be36f07b73
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871304"
---
# <a name="import-format-for-consolidation"></a>Konszolidáció importálási formátuma

[!include [banner](../includes/banner.md)]

Ez a cikk részletes információkat nyújt a több jogi személytől származó pénzügyi adatok konszolidálása során használt importálási formátumról. Az importálási formátumot szövegfájlként (.txt) kell menteni.

## <a name="import-format"></a>Importálás formátuma

A következő táblázat felsorolja azokat az importálási formátumokat, amelyek az importálás során konszolidáció esetén használhatók.

| Rekordtábla | Formátum | Jegyzetek |
|--------------|---------|-------|
| 1            | 170150, Goodwill, 4 | <ul><li>A rekordtábla</li><li>A forrásul szolgáló fő számla azonosítója</li><li>A fő számlasor</li><li>A fő számla típusa</li></ul> |
| 2            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>A fő számla azonosítója</li><li>A tranzakció dátuma</li><li>A pénzügyi időszak típusa (**0** = Nyitó, **1** = Működési és **2** = Zárás)</li><li>A tranzakció pénzneme</li><li>Tartozik vagy követel (**0** = Tartozik és **1** = Követel)</li><li>A feladási réteg</li><li>Tranzakcióösszegek</li><li>Mennyiség</li><li>A helyi RecID (a tranzakció nem egyértelmű, egyedi, int64 értéke)</li></ul> |
| 3            | USMF0000009, 2017/01/01, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>A bejegyzés száma (költségvetési fejléc tranzakciószáma)</li><li>A költségvetési fejléc alapértelmezett dátuma</li><li>A költségvetési modell azonosítója</li><li>Költségvetés típusa (**1** - Eredeti költségvetés, **2** - Átvitel, **3** - Felülvizsgálat, **4** - Kötelezettségvállalás, **5** - Előzetes Kötelezettségvállalás, **6** - Áthozott költségvetés, **7** - Projekt, **8** - Tárgyi eszközök, **9** - Igény-előrejelzés, **10** - Ellátási előrejelzés, **11** - Arányosítások, **12** - Előzetes költségvetés.)</li><li>A sor dátuma</li><li>A sor fő számlaazonosítója</li><li>A sor pénznemkódja</li><li>A sor összege a tranzakció pénznemében</li><li>A sor költségvetési típusának (költség vagy bevétel) felsorolási egész értéke</li></ul> |
| 4            | DEMF | A RecordCompany a Forrás jogi személy. |
| 5            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>Fő számla azonosítója</li><li>Tranzakció dátuma</li><li>Pénzügyi időszak típusa (0 Nyitó, 1 Működési és 2 Zárás)</li><li>Tranzakció pénzneme</li><li>Tartozás vagy jóváírás (0 = Tartozás; 1 = Jóváírás)</li><li>Feladási réteg</li><li>Tranzakció összege</li><li>Mennyiség</li><li>Helyi RecID (a tranzakció nem egyértelmű, egyedi, int64 értéke)</li></ul>  |
| 6            | Üzleti egység, 1 részleg, 2 | A szegmenssorrendben meghatározott pénzügyi dimenzióattribútumok.<p>Az **Exportálás** lapon ellenőrizheti, hogyan vannak meghatározva az attribútumok.</p> |
| 7            | 002,1,658 | <ul><li>A pénzügyi dimenzióérték</li><li>A pénzügyi dimenzió mint a RecordDimensions által biztosított index</li><li>Egyértelmű, egyedi rekordazonosító, amely a RecordTrans vagy a RecordTrans2 egyedi rekordazonosítóhoz van társítva</li></ul> |
| 8            | 002,1,1 | <ul><li>A RecordBudget tranzakcióhoz társított dimenzióértékek</li><li>A pénzügyi dimenzió mint a RecordDimensions által biztosított index</li><li>Nem egyértelmű sorrekord-azonosító, amely igazodik a fájlban található tranzakciósorok sorrendjéhez</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
