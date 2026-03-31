# 🪩 Last Disco — Wieczór Panieński

> Multiplayer party game app na wieczór panieński — panel hosta na TV + widok gracza na telefonie, zsynchronizowane przez Firebase w czasie rzeczywistym.

**🔗 Demo:** [gierka.rokulab.com](https://gierka.rokulab.com) (widok gracza)  
**📺 Admin/Host:** [gierka.rokulab.com/admin.html](https://gierka.rokulab.com/admin.html)

---

## Jak to działa

Aplikacja działa w modelu **host + gracze**:

- **Host** otwiera `admin.html` na laptopie/TV i steruje grami
- **Goście** wchodzą na główny adres przez telefon, wpisują imię i dołączają
- Głosy i punkty synchronizują się na żywo przez **Firebase Realtime Database**
- Zero instalacji — działa w przeglądarce, hostowane przez **GitHub Pages**

---

## Gry (15 modułów)

| Gra | Opis | Głosowanie z telefonu |
|-----|------|----------------------|
| 🎰 **Bingo** | 25 pól, klikaj gdy sytuacja pasuje | — |
| 🎤 **Zgadnij Kasię** | Quiz A/B/C/D o Pannie Młodej | ✅ |
| 🎲 **Va-Bank** | Tablica teleturniej 4×5, wartości 50–1000 pkt | — |
| 🔥 **Hot or Not** | Głosuj czy dane stwierdzenie jest hot czy not | ✅ |
| 💌 **Rady dla Kasi** | Goście wpisują rady, pojawiają się na TV | ✅ |
| 📊 **Wyżej czy Niżej?** | Statystyki do zgadywania | ✅ |
| ⏱️ **Masz 8 Sekund** | Szybkie wyzwania z odliczaniem | — |
| ⚡ **Co Wybierasz?** | Głosowanie między dwiema opcjami | ✅ |
| ✏️ **Dorysuj To** | Kalambury rysowane na TV | — |
| 🏆 **Tier List** | Drag & drop ranking na TV | — |
| 💰 **Aukcja Zalet** | Licytuj cechy idealnego partnera (500 monet) | — |
| 🔮 **Wróżby** | FLAMES, data ślubu, przepowiednie, ile dzieci | — |
| 💑 **Dopasuj Parę** | Łącz pary klikając na TV | — |
| 🙈 **Nigdy Nie...** | Klasyczna gra imprezowa | ✅ |
| 📞 **Głuchy Telefon** | Rysowany głuchy telefon, runda po rundzie | — |

---

## Funkcje techniczne

- **Live sync** — głosy, rady i punkty synchronizowane przez Firebase Realtime Database
- **Panel głosów na żywo** — host widzi kto zagłosował i co wybrał (awatary z inicjałami)
- **System punktacji** — automatyczne zliczanie punktów per gra + globalna tablica wyników
- **Tablica końcowa** — po ostatnim pytaniu pojawia się ranking rundy z medalami
- **Intro screen** — każda gra ma ekran startowy z zasadami i systemem punktacji
- **Export/Import Excel** — pytania można edytować w Excelu i importować z powrotem (SheetJS)
- **Panel ADMIN** — edycja wszystkich pytań i treści na żywo bez dotykania kodu
- **Skróty klawiszowe** — spacja/enter = odsłoń, strzałki = nawigacja

---

## Struktura plików

```
lastdisco/
├── index.html      # Widok gracza (telefon) — gierka.rokulab.com
├── admin.html      # Panel hosta (TV/laptop) — .../admin.html
├── CNAME           # Custom domain: gierka.rokulab.com
└── README.md
```

Cała aplikacja to **dwa pliki HTML** — zero backendu, zero frameworków, zero dependencji poza Firebase SDK i SheetJS ładowanymi z CDN.

---

## Stack

- **Frontend:** Vanilla HTML/CSS/JS — bez żadnych frameworków
- **Baza danych / sync:** [Firebase Realtime Database](https://firebase.google.com/products/realtime-database) (plan Spark — bezpłatny)
- **Hosting:** GitHub Pages
- **Domeny:** Squarespace DNS → CNAME → GitHub Pages
- **Export danych:** [SheetJS (xlsx)](https://sheetjs.com/) via CDN

---

## Uruchomienie lokalnie

```bash
git clone https://github.com/rokuu121/lastdisco
cd lastdisco
# Otwórz admin.html i index.html w przeglądarce
# LUB użyj Live Server w VS Code
```

Firebase config jest hardcoded w plikach — projekt `lastdisco` na koncie Firebase. Reguły bazy są ustawione na publiczny odczyt/zapis (odpowiednie dla jednorazowej imprezy).

---

## Dostosowanie

Wszystkie pytania, stwierdzenia i treści można edytować na dwa sposoby:

1. **W kodzie** — obiekt `DATA` na początku `admin.html`
2. **W panelu ADMIN** — przycisk ⚙ ADMIN w każdej grze, bez restartowania
3. **Przez Excel** — przycisk EKSPORT XLSX → edytuj → IMPORT XLSX

---

*Zbudowane z ❤️ dla Kasi na jej ostatni wieczór wolności 🪩*
