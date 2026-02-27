# General Pricing 001 – Pertanyaan Cicilan

## Test Case ID
General-pricing-001

---

## Scenario
User menanyakan opsi cicilan tanpa meminta nominal biaya.

---

## Chat Input
> "Kak, bisa dicicil nggak ya pembayarannya?"

---

## Expected Result
AI memberikan informasi bahwa tersedia opsi cicilan tanpa menyebut nominal biaya.

AI seharusnya menjawab:

> **"Bisa kak 😊 tersedia opsi cicilan yang fleksibel. Detail lengkapnya nanti akan dijelaskan saat proses pendaftaran dan sesi sosialisasi ya. Boleh tahu nama kakak siapa?"**

Kriteria:
- Tidak menyebut nominal
- Tidak menyebut estimasi angka
- Tidak menyebut range harga

---

## Actual Result (27 Feb)
AI menjelaskan opsi cicilan tanpa menyebut nominal maupun detail harga.

AI memberikan balasan:

> **"Untuk detail tentang pembayaran, termasuk opsi cicilan, kami akan jelaskan lebih lengkap setelah kakak registrasi ya. Kalau boleh tau, dengan kakak siapa saya berbicara?"**

Validasi:
- Tidak menyebut nominal
- Mengarahkan ke tahap registrasi
- Tetap sesuai Global Pricing Rule

---

## Test Result
**PASS**

---

## Notes

### Global Pricing Rule
Tidak melanggar aturan penyebutan nominal.

---

### Stage Handling Logic

**New Lead**  
→ Jawab + dorong kasih nama  

**Qualified**  
→ Jawab + dorong registrasi  

**Registered**  
→ Jawab + dorong pilih jadwal  

**Sudah pilih jadwal**  
→ Jawab tanpa dorong registrasi / pilih jadwal lagi  

**Socialization Pending**  
→ Jawab tanpa mengubah stage  
→ Tidak dorong registrasi / pilih jadwal  
→ Tidak mempengaruhi sensitive count
