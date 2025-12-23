# Povezava ESP32 na ESP32 (oddajnik–sprejemnik)

## Uvod
V tej vaji sem se naučil, kako lahko dve ESP32 ploščici med seboj komunicirata. En ESP32 deluje kot oddajnik, drug pa kot sprejemnik.

## Kaj sem se novega naučil
- Kako uporabiti žično komunikacijo med dvema ESP32
- Kako poslati podatke iz enega mikrokrmilnika na drugega
- Kako ESP32 prepozna MAC naslov druge naprave
- Kako obdelati prejete podatke na sprejemniku

## Nove programske rešitve
Spoznal sem uporabo knjižnice za neposredno komunikacijo med ESP32. Naučil sem se:
- vzpostavitev brezžične povezave
- pošiljanja strukturiranih podatkov

## Pomembni deli kode
Najpomembnejši del kode je pošiljanje podatkov iz oddajnika in njihovo sprejemanje na drugem ESP32.

### Oddajnik (primer)
```cpp
esp_now_send(receiverAddress, (uint8_t *) &data, sizeof(data));
```

---
#  ESP32 kot WiFi oddajnik (Access Point)


## Uvod
V tej vaji sem nastavil ESP32 kot WiFi oddajnik (Access Point), na katerega se lahko povežejo druge naprave, kot so telefon ali računalnik.

## Kaj sem se novega naučil
- Kako ESP32 deluje kot WiFi dostopna točka
- Kako ustvariti lastno WiFi omrežje
- Kako nastaviti ime omrežja (SSID) in geslo
- Kako preveriti povezane naprave

## Nove programske rešitve
Spoznal sem uporabo vgrajenih WiFi funkcij v ESP32:
- `WiFi.softAP()`
- `WiFi.softAPIP()`

Te funkcije omogočajo, da ESP32 oddaja svoje WiFi omrežje brez dodatne opreme.

## Pomembni deli kode
Najpomembnejši del kode je zagon Access Point načina.

```cpp
WiFi.softAP("ESP32_AP", "12345678");
```

---

# Povezava ESP32 na obstoječe WiFi omrežje

## Uvod
V tej vaji sem ESP32 povezal na obstoječe WiFi omrežje. Tako lahko ESP32 dostopa do interneta ali komunicira z drugimi napravami v istem omrežju.

## Kaj sem se novega naučil
- Kako ESP32 povežem na domače WiFi omrežje
- Kako preverim stanje povezave
- Kako pridobim IP naslov naprave
- Kako uporabiti WiFi za nadaljnjo komunikacijo

## Nove programske rešitve
Spoznal sem vgrajene WiFi funkcije:
- `WiFi.begin()`
- `WiFi.status()`
- `WiFi.localIP()`

Te funkcije omogočajo enostavno povezovanje v omrežje.

## Pomembni deli kode
Najpomembnejši del kode je vzpostavitev povezave.

```cpp
WiFi.begin(ssid, password);
```
ESP32 s tem ukazom začne povezovanje na omrežje.

```cpp
while (WiFi.status() != WL_CONNECTED) {
  delay(500);
}
```
Ta zanka poskrbi, da program počaka, dokler povezava ni uspešna.

#### Zaključek

Vaja mi je pomagala razumeti, kako ESP32 deluje v WiFi omrežju. To je osnova za IoT projekte, kot so spletni strežniki, senzorji in pametne naprave.
