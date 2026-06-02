# Infineon Zephyr Support Status (Prototype)

## General Information

Use this repository to answer three questions quickly:
- Which Infineon devices are usable with Zephyr today
- Which features are production-ready vs in-progress
- Which reference examples are available per platform
- How can I Contribute to the Infineon Zephyr project?


## Device Support Information

Infineon support in Zephyr spans multiple families with different maturity levels.

### Legend

- `✅` Supported
- `⏳` In progress / planned
- `❌` Not available on this device/family
- `🧪` Experimental (usable for evaluation, not yet production baseline)

### Device and Board Matrix

| Family | Representative Device | Representative Board | Upstream Zephyr | Internal Validation | Production Guidance |
|---|---|---|---|---|---|
| PSoC 6 | CY8C62xA/62x7 class | CY8CPROTO-062-4343W | ✅ | 🧪 | Pilot projects only until CI matrix is complete |
| XMC4000 | XMC45xx/XMC47xx class | XMC4700 Relax Kit class | ✅ | ⏳ | Bring-up and regression coverage in progress |
| AURIX TC3xx | TC37x/TC39x class | TC375/TC397 evaluation boards | ⏳ | ⏳ | Roadmap item; align on SMP/safety profile first |
| AIROC Wi-Fi/BT | CYW43xxx class (hosted model) | Wi-Fi/BT combo modules | ⏳ | 🧪 | Focus on hosted connectivity paths first |
| PSoC Control | C3 family (power control) | PSOC Control kits | ❌ | ⏳ | Investigating Zephyr fit for selected use-cases |

Note: Entries above are a prefilled prototype baseline and must be validated against current upstream board lists and internal test evidence.

## Peripheral Support Table (Prototype Baseline)

Columns are grouped by Infineon family for quick cross-device planning.

| Peripheral / Capability | PSoC 6 | XMC4000 | AURIX TC3xx | AIROC (hosted) | PSoC Control |
|---|---|---|---|---|---|
| CPU / IRQ / Timer base | ✅ | ✅ | ⏳ | ❌ | ⏳ |
| GPIO | ✅ | ✅ | ⏳ | ❌ | ⏳ |
| UART | ✅ | ✅ | ⏳ | ❌ | ⏳ |
| I2C | ✅ | ✅ | ⏳ | ❌ | ⏳ |
| SPI | ✅ | ✅ | ⏳ | ❌ | ⏳ |
| ADC | ✅ | ⏳ | ⏳ | ❌ | ⏳ |
| PWM | ✅ | ✅ | ⏳ | ❌ | ⏳ |
| CAN / CAN FD | ⏳ | ✅ | ⏳ | ❌ | ⏳ |
| Ethernet | ❌ | ⏳ | ⏳ | ❌ | ❌ |
| USB Device | ⏳ | ⏳ | ⏳ | ❌ | ❌ |
| Bluetooth LE | ⏳ | ❌ | ❌ | ✅ | ❌ |
| Wi-Fi | ❌ | ❌ | ❌ | ✅ | ❌ |
| Low power states | ⏳ | ⏳ | ⏳ | ❌ | ⏳ |
| MCUboot integration | ✅ | ✅ | ⏳ | ⏳ | ⏳ |

## Example Coverage

This section maps common Zephyr samples to Infineon targets and expected maturity.

| Example | Upstream Path | Primary Target Family | Target Board Class | Status | Last Verified |
|---|---|---|---|---|---|
| Blinky | `samples/basic/blinky` | PSoC 6 | CY8CPROTO-062-4343W | ✅ | 2026-06-02 |
| Hello World | `samples/hello_world` | PSoC 6, XMC4000 | Proto/Relax kits | ✅ | 2026-06-02 |
| GPIO | `samples/basic/button` | PSoC 6, XMC4000 | Proto/Relax kits | ✅ | 2026-06-02 |
| UART Echo | `samples/drivers/uart/echo_bot` | PSoC 6, XMC4000 | Proto/Relax kits | 🧪 | 2026-06-02 |
| I2C Scanner | `samples/drivers/i2c/scanner` | PSoC 6, XMC4000 | Proto/Relax kits | 🧪 | 2026-06-02 |
| SPI Loopback | `samples/drivers/spi_loopback` | PSoC 6, XMC4000 | Proto/Relax kits | 🧪 | 2026-06-02 |
| ADC | `samples/drivers/adc/adc_sequence` | PSoC 6 | CY8CPROTO-062-4343W | 🧪 | 2026-06-02 |
| PWM | `samples/basic/fade_led` | PSoC 6, XMC4000 | Proto/Relax kits | ⏳ | 2026-06-02 |
| BLE Peripheral | `samples/bluetooth/peripheral_hr` | AIROC (hosted) | CYW43xxx module + host MCU | ⏳ | 2026-06-02 |
| Wi-Fi STA sample | vendor-hosted connectivity sample | AIROC (hosted) | CYW43xxx module + host MCU | ⏳ | 2026-06-02 |

## Zephyr Releases and Device Plan

| Zephyr Train | Timeline (tentative) | Infineon Focus | Notes |
|---|---|---|---|
| 4.2 baseline | Current | Stabilize PSoC 6 + XMC4000 baseline | Freeze smoke test set |
| 4.3 | Next cycle | Expand driver coverage and CI | Add ADC/PWM/CAN regression |
| 4.4 | Following cycle | AURIX feasibility checkpoints | Safety and multicore constraints review |
| LTS track | Per Zephyr roadmap | Backfix policy only | No long-lived fork strategy |

## Zephyr Releases and Device Plan
Want to Contribute to Infineon's Zephyr Project?
(Guidelines)

