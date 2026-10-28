# ♞ Gambīts — šahs ar draugu pa saiti

Izveido spēli, nosūti saiti draugam, un spēlējat. Reģistrācija nav vajadzīga.

**Draugi:** sākumlapā ir tava „drauga saite”. Nosūti to draugam vienu reizi, un jūs būsiet viens otra
sarakstā. Tālāk redzi, kurš ir tiešsaistē, un spied **Izaicināt**. Draugam parādās uzaicinājums,
un pēc „Spēlēt” jūs abi nonākat spēlē. Pretinieku var pievienot draugiem arī pēc spēles.
Draugu saraksts glabājas pārlūkā, tāpēc citā ierīcē tas jāpievieno no jauna.

**Iespējas:** laika kontroles (1 min … 30 min, ar papildlaiku vai bez laika), pulksteņi,
vilkšana vai klikšķis, legālo gājienu punkti, pēdējā gājiena un šaha izcelšana,
figūras paaugstināšana, izsistās figūras un materiāla pārsvars, gājienu saraksts ar pārskatīšanu (← →),
skaņas, čats, neizšķirta piedāvājums, padošanās, revanšs (krāsas samainās), skatītāji
(trešais cilvēks ar to pašu saiti), automātiska pievienošanās atpakaļ pēc lapas pārlādes.
Darbojas arī telefonā.

Serverim nekas nav jāinstalē: tikai Python 3.

## Palaišana savā datorā

```
python server.py
```
Pēc tam atver http://localhost:8000

## Bezmaksas hostings internetā (Render.com)

1. Izveido kontu **github.com** (bez maksas).
2. Spied **New repository**, nosauc `gambits`, izvēlies **Public**, spied **Create repository**.
3. Spied **uploading an existing file** un ievelc VISUS šīs mapes failus
   (`server.py`, `render.yaml`, `README.md` un mapi `public`). Spied **Commit changes**.
4. Izveido kontu **render.com** (var ieiet ar to pašu GitHub kontu).
5. Render panelī: **New + → Blueprint**, izvēlies savu `gambits` repozitoriju, spied **Apply**.
   (Vai arī: **New + → Web Service**, repozitorijs `gambits`, Runtime **Python**,
   Build Command `echo ok`, Start Command `python server.py`, Instance Type **Free**.)
6. Pēc 1–3 minūtēm saņemsi adresi, piem. `https://gambits-xxxx.onrender.com`. Tā ir tava šaha vietne.

### Svarīgi par bezmaksas plānu
- Ja 15 minūtes neviens neienāk, Render serveri „aizmidzina”. Pirmā atvēršana pēc tam
  aizņem ~30–60 sekundes, tad viss strādā normāli.
- Lai serveris būtu nomodā visu laiku (24/7): izveido bezmaksas kontu **uptimerobot.com**,
  spied **New monitor → HTTP(s)**, adrese `https://TAVA-ADRESE.onrender.com/health`,
  intervāls 5 minūtes. Bezmaksas plānā ir 750 stundas mēnesī, un ar to pietiek vienam serverim visu mēnesi.
- Spēles glabājas servera atmiņā. Ja Render serveri restartē, nepabeigtās spēles pazūd,
  un jāizveido jauna (tas aizņem 2 sekundes).
