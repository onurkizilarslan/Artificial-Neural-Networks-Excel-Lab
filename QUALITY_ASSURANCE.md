# Quality assurance / Kalite kontrol — 2026-10-14

## Scope / Kapsam
Static inspection of all six Excel workbooks uploaded to the repository: workbook sheet inventories, formula counts, cached Excel error values, and mathematical teaching content. This is **not** a full Excel desktop recalculation or graphical verification.

## Findings / Bulgular

| Status | File | Finding |
|---|---|---|
| FIX PREPARED | Perceptron_TR.xlsx | 'Formüller' sheet includes cached `#VALUE!` cells (e.g. C6, C9, C12). Examples were entered as active formulas referencing descriptive labels on that page. A locally corrected candidate using literal formula examples is available for review, but **has not been uploaded** to the repository. |
| REVIEW | ADALINE_EN.xlsx, Perceptron_EN.xlsx, ADALINE_vs_Perceptron_EN.xlsx | Some training cycles use a fixed 4-sample count; documentation should state data shape limitations. English editions are not exact translations of Turkish originals (they may differ in sheet structure and epoch count). |
| REVIEW | Perceptron_EN.xlsx | Generic 'Formulas' glossary includes an ADALINE output entry; improve algorithm-specific labeling. |
| PASS (limited) | All six workbooks | XLSX archives were readable and contain populated sheets and calculation formulas. A static formula/error scan found no cached cell errors in five of the six files. |

## Release gate / Sürüm yayımlama koşulları

1. Replace the Turkish Perceptron workbook with the reviewed corrected edition.
2. Open **all six workbooks** in Microsoft Excel; force recalculation and test editable parameters, graph refresh and save/reopen.
3. Verify ADALINE LMS and Perceptron mistake updates independently against expected numerical training steps. Also check bipolar AND targets and tie handling (`net >= 0`).
4. Confirm formula examples, cross-sheet links and correct behavior outside the default parameter set.
5. Agree on a distribution license. **Do not add a license without choosing reuse terms.**
6. Only then publish a stable GitHub Release v1.0.

## Türkçe özet
Altı çalışma kitabının yapısal denetimi yapıldı. Türkçe Perceptron dosyasının **Formüller** sayfasında Excel hata değerleri saptandı ve düzeltilmiş aday dosya hazırlandı. Excel masaüstünde yeniden hesaplama ve grafik doğrulaması henüz yapılmadığından bu sonuçlar tam işlevsellik onayı sayılmaz. Kararlı v1.0 sürümü henüz önerilmez.
