# 🔌 Redfish Interface Emulator - Postman Test Collection

This repository contains Postman collections for testing various Redfish API endpoints exposed by a Redfish Interface Emulator (typically running at `localhost:5000`). The collections simulate realistic system operations such as volume creation, BIOS settings update, virtual media mounting, and system resets.

---

## 📁 Repository Structure

```
Redfish-Interface-Emulator-Postman-Tests/
├── collections/
│   ├── Bios.postman_collection.json
│   ├── Volume.postman_collection.json
│   ├── Virtual Media.postman_collection.json
│   └── Computer System.postman_collection.json
└── README.md
```

---

## 🧪 Available Postman Collections

### 1. **Volume**

Test scenarios for Redfish Volume API:

* Volume creation with RAID settings
* GET Volume
* GET Volume-1
* Error handling (capacity limits, chassis mismatch, duplicates)
* Volume deletion

### 2. **Virtual Media**

Simulates remote media mount/unmount:

* Insert virtual media
* GET Virtual Media
* Eject media

### 3. **Computer System**

System control through:

* Computer reset using `ComputerSystem.Reset`

### 4. **BIOS**

BIOS management via:

* BIOS attribute update (`BootMode`, etc.)
* GET BIOS Settings
* GET BIOS
* BIOS reset to default

---

## 🔐 Authentication

All requests use HTTP Basic Authentication. Replace these placeholders with your actual credentials in Postman or environment variables:

```json
"username": "{{username}}",
"password": "{{password}}"
```

You can define these in your Postman environment.

---

## 🚀 Getting Started

### Prerequisites

* Postman (GUI) or [Newman](https://www.npmjs.com/package/newman) (CLI)
* Redfish emulator running locally (e.g., `localhost:5000`)

### Running Tests via Postman

1. Import each `*.postman_collection.json` file
2. Set up environment variables (`username`, `password`, `host`, etc.)
3. Execute individual requests or full collections

### Running via Newman (CLI)

```bash
newman run collections/Volume.postman_collection.json \
  --env-var username=Administrator \
  --env-var password=Password
```

---

## ⚠️ Notes

* **Do not commit real credentials.** Use environment variables or `.env` files.
* If you change the Redfish emulator port or host, update the URLs accordingly.

---

## 🛠️ Future Improvements

* Add Postman tests for Account and Session services
* Include Redfish schema validation
* Integrate with GitHub Actions for CI testing
* Add Newman report generation

---

## 📜 License

This project is licensed under the [MIT License](LICENSE) (or specify another license).

---

## 🙌 Acknowledgments

* [DMTF Redfish API](https://www.dmtf.org/standards/redfish)
* [Postman](https://www.postman.com/)
* [Redfish Emulator project](https://github.com/PranavDarshan/Redfish-Interface-Emulator)
