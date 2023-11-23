# Rəqəmsal İmza Aləti Docs

## Ümumi açıqlama

Rəqəmsal İmza Aləti, DOCX fayllarında rəqəmsal imza yaratmağa və doğrulamağa imkan verən Python skriptidir. Bu alət rəqəmsal imza yaratmaq və doğrulamaq üçün SHA-256 hash funksiyasından istifadə edir və əlavə olaraqda tarixi əlavə edir.

## Vacib olan kitabxanalar

Aşağıdakı Python kitabxanalarının qurulu olduğundan əmin olun:

- `hashlib`: SHA-256 hash yaratmaq üçün.
- `docx`: DOCX faylları ilə işləmək üçün.
- `datetime`: Rəqəmsal imza üçün tarixi qeyd etmək üçün.

Kitabxanaları aşağıdakı komanda ilə qura bilərsiniz:

```bash
pip install hashlib docx
````

# İstifadə

## 1. Sənədə İmza Atmaq

Sənədi imzalamaq üçün, `sign_document` funksiyasına parametr olaraq fayl yolunu göndəririk. Funksiya sənənin məzmununa əsaslanan rəqəmsal imza yaradır, ona tarix əlavə edir və sonra sənədə əlavə edir.

```python
sign_document("/path/sənəd_adi.docx")
```
İmzalanmış sənəd eyni qovluqda "signed_document.docx" adı altında yaradılacaqdır.

## 2. İmza Doğrulamaq

İmzalanmış bir sənədin rəqəmsal imzasını doğrulamaq üçün, `verify_signature` funksiyasını imzalanmış sənədin fayl yolu ilə işlədəsiniz. Funksiya rəqəmsal imzanın doğruluğunu yoxlayır və nəticəni çap edir.

```python
verify_signature("signed_document.docx")
```

# Funksiyalar

## `calculate_sha256(data)`

Bu funksiya bayt tipli obyekti (`data`) qəbul edir və onun SHA-256 hashini onluq sistemdə qaytarır.

## `sign_document(file_path)`

Bu funksiya, `file_path` tərəfindən göstərilən sənədi rəqəmsal imza ilə əlavə edir. Sənədin məzmununun SHA-256 hashinin hesablayır, tarixi əlavə edir və onu sənədə əlavə edir.

```python
sign_document("sənəd_yolu.docx")
```

## verify_signature(file_path)

Bu funksiya, file_path tərəfindən göstərilən imzalanmış bir sənədin rəqəmsal imzasını yoxlayır. Hesablanan SHA-256 heşi ilə sənədəki imza uyğun gəlirsə, nəticəni çap edir.

```python
verify_signature("imzalanmış_sənəd.docx")


