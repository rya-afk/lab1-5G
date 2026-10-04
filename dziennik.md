# Dziennik laboratoryjny — Temat 1: Rdzeń sieci 5G jako chmura funkcji: symulator architektury SBA

**Data:** 04.10.2026
**Członkowie zespołu:**
- Valeriia Koval
- Darya Drozd

---

## 1. Pytania wprowadzające
- **Czym różni się sygnalizacja od ruchu użytkownika:** Sygnalizacja (płaszczyzna sterowania / control plane) to komunikaty techniczne służące do zarządzania siecią, autoryzacji i zestawiania połączeń. Ruch użytkownika (płaszczyzna danych / user plane) to właściwe przesyłane dane użytkownika (np. strony www, wideo, transfer plików).
- **Co robi funkcja AMF:** Odpowiada za rejestrację terminala w sieci, uwierzytelnianie (we współpracy z bazą danych), zarządzanie mobilnością i przekazywanie wiadomości do odpowiednich funkcji (np. do SMF).
- **Co oznacza skrót SBA:** Service-Based Architecture — architektura oparta na usługach, w której funkcje rdzenia 5G komunikują się jak mikrousługi za pośrednictwem zapytań REST API / HTTP/2.

---

## 2. Podział ról w zespole
- **Valeriia Koval:** symulator, diagramy.
- **Darya Drozd:** dokumentacja, prezentacja.

---

## 3. Przebieg scenariusza: włączanie telefonu (lista komunikatów)
1. Telefon → Wieża (gNB): "witaj, jestem tu"
2. Wieża (gNB) → AMF: "nowy telefon się pojawił"
3. AMF → Baza danych: "czy znam tego abonenta?"
4. Baza danych → AMF: "tak, to Jan"
5. AMF → SMF: "zestaw sesję internetową"
6. SMF → Internet: "łącze gotowe"

---

## 4. Pytania, które się pojawiły
- Jak realizowane jest szyfrowanie komunikacji zanim baza danych potwierdzi tożsamość abonenta?
- Czy w pełnym standardzie SBA funkcja AMF odpytuje bezpośrednio bazę danych (UDM), czy korzysta z repozytorium UDR?

---

## 5. Diagram sekwencji
![Diagram sekwencji](lab1.drawio.png)