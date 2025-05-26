==============================
APRS SERVICES REFERENCE (RST)
==============================

SMS Gateway Commands
====================

+----------------------+---------+----------------------------------------------------------+
| Action               | To      | Message Format                                           |
+======================+=========+==========================================================+
| Send SMS             | SMS     | @<number> <message>                                     |
+----------------------+---------+----------------------------------------------------------+
| Send SMS to APRS     | Gtwy #  | @<callsign> <message>                                   |
+----------------------+---------+----------------------------------------------------------+
| Add SMS Alias        | SMS     | #alias #add <alias> <number>                            |
+----------------------+---------+----------------------------------------------------------+
| Remove SMS Alias     | SMS     | #alias #remove <alias> <number>                         |
+----------------------+---------+----------------------------------------------------------+

Winlink (WLNK-1) Commands
=========================

+--------------------------+----------------------------------------------------------+
| Action                   | Message                                                  |
+==========================+==========================================================+
| Query All Messages       | L                                                        |
+--------------------------+----------------------------------------------------------+
| Query Specific Msg       | R[message number]                                        |
+--------------------------+----------------------------------------------------------+
| Reply to Message         | Y[message number]                                        |
+--------------------------+----------------------------------------------------------+
| Delete Message           | K[message number]                                        |
+--------------------------+----------------------------------------------------------+
| Forward Message          | F[message number] [email address]                        |
+--------------------------+----------------------------------------------------------+
| Send Long Message        | SP [to] [subject] send [text] /EX                        |
+--------------------------+----------------------------------------------------------+
| Send One-Line SMS        | SMS [callsign] [text]                                    |
+--------------------------+----------------------------------------------------------+
| Add Alias                | A [alias]=[email]                                        |
+--------------------------+----------------------------------------------------------+
| Delete Alias             | A [alias]=                                               |
+--------------------------+----------------------------------------------------------+
| List Aliases             | AL                                                       |
+--------------------------+----------------------------------------------------------+
| Query RMS Gateways       | G[number]                                                |
+--------------------------+----------------------------------------------------------+
| List Commands            | H                                                        |
+--------------------------+----------------------------------------------------------+
| Help on Command          | ?[cmd]                                                   |
+--------------------------+----------------------------------------------------------+

MPAD – Multi-Purpose APRS Daemon
================================

Supports queries for weather, satellite passes, repeater data, and more.

+--------------------------+---------------------------------------------------------------+
| **Command**              | **Description**                                               |
+==========================+===============================================================+
| `metar`                  | METAR for nearest airport                                     |
| `taf`                    | TAF forecast                                                  |
| `icao <code>`            | METAR/TAF for ICAO code                                       |
| `iata <code>`            | METAR/TAF for IATA code                                       |
| `cwop`                   | Nearest CWOP weather                                          |
| `cwop <id>`              | Specific CWOP station                                         |
| `repeater`              | Nearest repeater info                                         |
| `repeater <band>`        | Filter by band (e.g., 70cm)                                   |
| `repeater <mode>`        | Filter by mode (e.g., c4fm)                                   |
| `riseset`                | Sunrise/Sunset and Moonrise/Moonset                          |
| `satpass <sat>`          | Next satellite pass                                           |
| `vispass <sat>`          | Visible satellite pass                                        |
| `osm <category>`         | Nearest feature (e.g., supermarket)                           |
| `posmsg <email>`         | Send position via email                                       |
| `dapnet <user> <msg>`    | Send pager message via DAPNET                                 |
| `fortuneteller`          | Get a fortune                                                 |
+--------------------------+---------------------------------------------------------------+

**Examples**:

- `To: MPAD` → `icao CYYC`  
- `To: MPAD` → `repeater 70cm`  
- `To: MPAD` → `satpass iss`  
- `To: MPAD` → `osm pharmacy`

WXYO – Weather Forecast Auto Responder
======================================

Provides forecasts via location, time, or callsign.

+-----------------------------+-------------------------------------------------------------+
| Input                      | Description                                                 |
+=============================+=============================================================+
| `<hours>`                 | Forecast for the next N hours                               |
| `<lat>/<lon>`             | Forecast for coordinates                                    |
| `<grid square>`           | Forecast by Maidenhead grid                                 |
| `<city>,<state>`          | City-based forecast                                         |
| `<callsign>`              | Forecast for station's last known location                  |
| `current`                 | Current conditions                                           |
| `cwop`                    | From nearest CWOP station                                   |
| `cwop <id>`               | Specific CWOP station                                       |
| `help` or `?`             | Help message                                                |
+-----------------------------+-------------------------------------------------------------+

**Examples**:

- `To: WXYO` → `24`  
- `To: WXYO` → `41.123/-122.1123`  
- `To: WXYO` → `KN20ZZ`  
- `To: WXYO` → `Calgary,AB 3 full`  
- `To: WXYO` → `cwop DW6273`