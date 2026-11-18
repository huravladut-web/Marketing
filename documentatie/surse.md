# Inventar surse de date

> Document viu. Se completează pe măsură ce validăm fiecare sursă.
> Regula: **o sursă oficială = adevăr**; agregatoarele comerciale = doar cross-check.
> Status: `⬜ de verificat` · `🟡 în lucru` · `✅ validat` · `❌ indisponibil`

---

## 1. Situații financiare anuale (bilanț, cont de profit și pierdere)

Sursa de adevăr pentru profit net, cifră de afaceri, active, datorii, număr de salariați.

| Câmp | Valoare |
|---|---|
| Instituție | Ministerul Finanțelor / ANAF |
| URL | _de completat_ (portalul de bilanțuri / data.gov.ro) |
| Format | XML / CSV bulk, un fișier per an |
| Acoperire | Firme care depun situații financiare |
| Ani disponibili | _de completat_ |
| Licență / T&C | _de completat_ |
| Status | ⬜ |

**Câmpuri necesare:** CUI, denumire, an fiscal, CAEN principal, județ, localitate, cifra de afaceri netă, profit net, total active, capitaluri proprii, nr. salariați, stare firmă.

**Note:**
- Formatul se schimbă între ani → parser versionat per an.
- Firmele fără bilanț depus apar ca lipsă, nu ca zero.
- Unele valori pot fi raportate în mii RON în anumiți ani → de verificat unitatea.

- [ ] Descărcat eșantion pentru 1 an și inspectat structura
- [ ] Confirmată unitatea (RON vs. mii RON)
- [ ] Confirmat tratamentul firmelor cu bilanț nedepus

---

## 2. Date de identificare firmă (ANAF / ONRC)

Pentru denumire, adresă, CAEN, formă juridică, stare, vector fiscal.

| Câmp | Valoare |
|---|---|
| Instituție | ANAF (servicii web) / ONRC / data.gov.ro |
| URL | _de completat_ |
| Format | API / bulk |
| Acoperire | Toate firmele înregistrate |
| Status | ⬜ |

**De verificat:**
- [ ] Există endpoint bulk sau doar query per CUI?
- [ ] Rate limit / autentificare?
- [ ] Câmpul „cod CAEN principal” e Rev.2 sau Rev.3?

---

## 3. INS TEMPO — forță de muncă

| Indicator | Cod TEMPO | Status |
|---|---|---|
| Salariați pe activități CAEN și județ | _de completat_ | ⬜ |
| Salariu mediu brut/net pe județ | _de completat_ | ⬜ |
| Rata șomajului pe județ | _de completat_ | ⬜ |
| Populație activă / ocupată | _de completat_ | ⬜ |
| Număr mediu de salariați pe localități (dacă există) | _de completat_ | ⬜ |

**Note:**
- TEMPO are serii anuale; se verifică ultimul an publicat (există decalaj de ~1 an).
- Nivelul geografic real disponibil este **județ**, nu oraș → pentru orașe comparabile folosim județul sau date locale (primării).

- [ ] Exportate seriile pentru Galați + județele orașelor benchmark
- [ ] Confirmat nivelul geografic minim disponibil

---

## 4. Populație și context local

| Sursă | Ce obținem | Status |
|---|---|---|
| INS — populația după domiciliu / stabilă pe localități | Numitorul pentru „la 1.000 locuitori” | ⬜ |
| Primăria Galați / Consiliul Județean | Date locale, planuri, șomaj local | ⬜ |

- [ ] Confirmat numitorul folosit (populație stabilă vs. domiciliu)

---

## 5. Context macro / comparații (opțional)

| Sursă | Ce obținem | Status |
|---|---|---|
| Eurostat | Comparații regionale NUTS2 | ⬜ |
| BNR | Curs valutar (dacă apar sume în EUR) | ⬜ |

---

## 6. Agregatoare comerciale (DOAR validare)

> Nu sunt sursă primară. Se folosesc pentru a verifica 5–10 firme de top manual.

| Site | Utilizare | Status |
|---|---|---|
| listafirme.ro | Cross-check top firme | ⬜ |
| termene.ro | Cross-check stare/CAEN | ⬜ |

- [ ] Verificate manual 5 firme din top vs. sursa oficială

---

## 7. Nomenclatoare

| Nomenclator | Sursă | Status |
|---|---|---|
| CAEN Rev.2 (clase/diviziuni) | INS | ⬜ |
| CAEN Rev.3 | INS | ⬜ |
| Mapare CAEN Rev.2 → Rev.3 | _de găsit / de construit_ | ⬜ |
| Județe + localități (SIRUTA) | INS | ⬜ |

- [ ] Confirmat dacă datele de bilanț folosesc Rev.2 sau Rev.3
- [ ] Construit tabelul de mapare (dacă e nevoie)

---

## Jurnal decizii

| Data | Decizie | Motiv |
|---|---|---|
| _zz.ll.aaaa_ | _ex._ | _ex._ |
