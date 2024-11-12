# MQTT5 Broker

Acest proiect implementează un broker MQTT5 simplu care gestionează conexiunile clienților, autentificarea și menținerea conexiunilor printr-un server SQL pentru stocarea datelor clientului. Codul este structurat în mai multe module, fiecare având funcționalități specifice pentru decodificarea și crearea pachetelor MQTT, precum și gestionarea conexiunilor și autentificării.

## Structura Proiectului

### Fișierele Principale

- **`main.py`**: Punctul de intrare al serverului MQTT5 Broker. Configurează serverul, acceptă conexiunile și gestionează interacțiunea cu clienții.
  - [Explicație detaliată pentru `main.py`](Docs/main.md)

- **`sqlServer.py`**: Modulul care gestionează operațiile legate de baza de date, incluzând autentificarea, stocarea și actualizarea informațiilor despre clienți în baza de date SQLite.
  - [Explicație detaliată pentru `sqlServer.py`](Docs/sqlServer.md)

- **`decoder.py`**: Implementează clasa `MQTTDecoder`, care este utilizată pentru decodificarea pachetelor MQTT primite de la clienți, cum ar fi `CONNECT`, `PINGREQ` și `DISCONNECT`.
  - [Explicație detaliată pentru `decoder.py`](Docs/decoder.md)

- **`packet_creator.py`**: Conține funcțiile necesare pentru crearea pachetelor MQTT, cum ar fi `CONNACK`, `PINGRESP` și `DISCONNECT`, ce sunt trimise ca răspuns către clienți.
  - [Explicație detaliată pentru `packet_creator.py`](Docs/packet_creator.md)

## Cerințe

- Python 3.x
- Biblioteca `socket` (inclusă nativ în Python)
- Biblioteca `struct` (inclusă nativ în Python)

## Configurare Server

Serverul este configurat să ruleze pe adresa IP `127.0.0.1` (localhost) și pe portul `5000`. Aceste valori pot fi modificate în fișierul `main.py`.

## Utilizare

1. **Pornirea Serverului**:
   Pentru a porni serverul MQTT5 Broker, rulează comanda:
   ```bash
   python main.py
