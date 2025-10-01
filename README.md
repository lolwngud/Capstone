# Blind Navigation System (Raspberry Pi + GPS)

Assistive navigation prototype for visually impaired users using Raspberry Pi, GPS module, and C/Python.
- **Platform**: Raspberry Pi (Embedded Linux)
- **Languages**: C, Python
- **Features**: GPS parsing, route guidance, real-time feedback (audio/buzzer), robust error handling

![demo](docs/images/demo.jpg)

## 1. Why this project matters
- Real-world assistive scenario → reliability & real-time constraints considered
- Designed with **safety**, **stability**, and **simple UX** in mind

## 2. System Architecture
![architecture](docs/images/architecture.png)

- `src/c/` : Serial I/O with GPS, low-level parsing
- `src/python/` : Route guidance, state machine, logging
- Communication: UNIX socket / FIFO (택1, 실제 구현에 맞게 기재)

## 3. Hardware
- Raspberry Pi 4 (or 3B+)
- GPS Module (u-blox NEO-6M 등)
- Optional: Buzzer, Button, Headphones
See `docs/hardware.md` for wiring diagrams.

## 4. Getting Started
```bash
# Raspberry Pi
sudo apt update && sudo apt install -y python3-pip gcc make
pip3 install -r requirements.txt

# Build C module
make -C src/c

# Run (example)
python3 src/python/main.py --port /dev/ttyS0 --baud 9600
