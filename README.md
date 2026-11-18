# Smart Greenhouse — IoT Automation & Control 🌱

> An embedded software system that monitors growing conditions and automates greenhouse equipment using a Raspberry Pi and ESP32.

**Stack:** Python · Raspberry Pi 5 · ESP32 · Flask · MongoDB · MQTT · AWS S3 · Sensors & Actuators

## Why this project matters
Greenhouses need reliable sensing and automated responses, not just dashboards. This system brings hardware, backend logic and data collection together to monitor environmental conditions and act on configurable growing targets (*setpoints*).

## Architecture
```text
Environmental sensors + camera
            |
            v
 Raspberry Pi 5 / Python
    |       |        |
    |       |        +--> MongoDB / operational data
    |       +-----------> MQTT / integrations
    +-------------------> ESP32 actuator interface
                                  |
                        Fans / Lighting / Pumps / Heater
```

## What it does
- Reads environmental and soil-related sensor data.
- Compares measured conditions with configurable setpoints.
- Controls greenhouse actuators through the embedded controller.
- Captures camera images and integrates with AWS S3.
- Tracks operational and resource-consumption information.
- Provides Flask-based application integration.

## Explore the code
| Location | Responsibility |
| --- | --- |
| `app.py` | Main control application and orchestration |
| `Sensors/` | Sensor acquisition |
| `Actuators/` | Equipment control |
| `setpoints.py` | Growing-target configuration |
| `mongo_db_handler.py` | MongoDB integration |
| `mqtt_handler.py` | MQTT communication |
| `rpi_camera.py` | Camera interface |
| `aws_s3_handler.py` | Storage integration |
| `tests/` | Test material |
| `docs/` | Technical materials |

## Running it
This repository is hardware-dependent: it requires compatible Raspberry Pi/ESP32 devices, correctly wired sensors and actuators, service configuration and hardware-specific Python dependencies. Review actuator safety limits before any live run.

**Security note:** Legacy source files contain service connection settings. Rotate any real credentials and move secrets to secure environment configuration before using or deploying this code.

## Project scope
This repository primarily covers the greenhouse's **monitoring and physical control layer**. The broader PlantMind AI concept also includes AI recommendations and budget-governed approvals; those components should be demonstrated through their own code or architecture materials rather than assumed to be in this repository.

---
*Engineering focus: reliable automation at the boundary between software and the physical world.*
