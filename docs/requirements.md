## 1. Project identity

- **Project name:** `Rasberry Pi Sata Hat`
- **Hardware revision:** `Rev 1.0`
- **Author:** `ZayaanK`
- **Document version:** `0.1`
- **Date:** `July 13th 2026`
- **Current project phase:** `Requirements & Research`

### One-sentence description

`Goal is a 2-port SATA expansion board for the Raspberry Pi 5 intended for NAS development.`

## 2. Revision 1 scope

Revision 1 must demonstrate:

- `Raspberry Pi 5 compatibility`
- `Separate external power input for the drives and board`
- `Two standard SATA data connector`
- `Linux-compatible controller with an existing mainline driver`
- `One PCIe-to-two-port SATA controller`

Revision 1 should demonstrate, if practical:

- `Reliable operation with two SATA SSDs`
- `Stable multi-hour file-transfer test`
- `300-400 MB/S aggregate sequential throughput`

Revision 1 will intentionally **not** include:

- `Five SATA Ports`
- `NVME Support`
- `Custom Drivers`


The project will be considered successful when `PCB delieverable is completed`.

## 3. Host interface

- **Supported host:** `Raspberry Pi 5`
- **Host connection:** `exposed PCIe FFC connector`
- **Target PCIe generation:** `TBD`
- **Required PCIe lane count:** `TBD`
- **Minimum acceptable host bandwidth:** `TBD`
- **GPIO header passthrough required:** `TBD`
- **HAT identification EEPROM required:** `TBD`

The board must be recognized by the host as `[device/controller type]`.

## 4. Storage requirements

- **Number of SATA ports:** `2`
- **Supported devices:** `2.5-inch SSD`
- **Target SATA generation:** `TBD`
- **Minimum speed per active port:** `TBD`
- **Expected simultaneous active drives:** `2`
- **Booting from an attached drive required:** `Nice-to-have`
- **Hot-plug required:** `Future revision`
- **Port activity indicators required:** `Yes`
- **Drive presence detection required:** `Yes`

The board must support `2` drives operating simultaneously without `[unacceptable behaviour]`.

## 5. Performance targets

- **Target sequential read speed, one drive:** `[TBD] MB/s`
- **Target sequential write speed, one drive:** `[TBD] MB/s`
- **Target aggregate throughput:** `400 MB/s`
- **Maximum acceptable performance bottleneck:** `TBD`
- **Intended workloads:** `NAS`

Performance will be tested using `TBD`.

## 6. Power requirements

- **Main board power source:** `TBD`
- **Drive power source:** `TBD`
- **Input connector:** `TBD`
- **Input voltage:** `TBD`
- **Maximum planned input current:** `TBD`
- **Board-generated voltage rails:** `TBD`
- **Maximum number of drives starting simultaneously:** `TBD`
- **Staggered spin-up required:** `TBD`
- **Reverse-polarity protection required:** `Yes`
- **Overcurrent protection required:** `Yes`
- **Input fuse required:** `Yes`
- **Power-good indication required:** `Yes`
- **Safe shutdown support required:** `Yes`

The power system must tolerate a worst-case startup load of `[TBD]` without the Pi resetting or any supply falling outside `[TBD]`.

> Do not finalize the power design until actual drive startup-current specifications and connector ratings have been checked.

## 7. Controller and compatibility

- **Preferred PCIe-to-SATA controller:** `TBD`
- **Required SATA port count from controller:** `2`
- **External clock required:** `TBD`
- **External configuration memory required:** `TBD`
- **Linux kernel driver:** `TBD`
- **Minimum supported OS:** `TBD`
- **Works without a custom kernel driver:** `Not required`
- **SMART support required:** `TBD`
- **TRIM support for SSDs required:** `TBD`
- **Software RAID compatibility required:** `No`

The selected controller must have `[BLANK — sourcing, documentation, package, and driver requirements]`.

## 8. Mechanical requirements

- **Maximum PCB dimensions:** `[TBD] mm × [TBD] mm`
- **Board outline standard:** `Pi HAT-sized`
- **Number of PCB layers:** `TBD`
- **Pi mounting-hole compatibility:** `Not required`
- **Drive mounting included:** `TBD`
- **Maximum assembled height:** `TBD`
- **SATA connector orientation:** `TBD`
- **Power connector orientation:** `TBD`
- **Enclosure compatibility:** `TBD`
- **Fan mounting required:** `Yes`

Connectors must remain accessible when `[BLANK — installed configuration]`.

## 9. Thermal and environmental requirements

- **Operating environment:** `Open bench & enclosure`
- **Target ambient temperature range:** `TBD`
- **Maximum controller temperature:** `TBD`
- **Passive cooling preferred:** `Yes`
- **Heatsink required:** `Yes`
- **Forced airflow required:** `Yes`
- **Temperature monitoring required:** `Yes`

During sustained operation at `[BLANK — workload]`, the board must remain below `[BLANK/TBD] °C` at an ambient temperature of `[BLANK/TBD] °C`.

## 10. PCB and signal-integrity constraints

- **PCB manufacturer/process target:** `TBD`
- **Planned layer count:** `TBD`
- **Controlled impedance available:** `TBD`
- **PCIe differential impedance target:** `[BLANK/TBD — verify from authoritative specification]`
- **SATA differential impedance target:** `[BLANK/TBD — verify from authoritative specification]`
- **Minimum trace width/spacing:** `TBD`
- **Maximum permitted differential-pair skew:** `TBD`
- **Reference planes:** `TBD`
- **ESD protection required on external ports:** `Yes`
- **Test points required for:** `TBD`

All high-speed constraints must be based on `[datasheets/specifications/fabricator stack-up]`, not estimated values.

## 11. Reliability and safety requirements

- **Data integrity has priority over:** `maximum throughput, benchmark performance, and immediate availability`
- **Behaviour after unexpected power loss:** `The board shall shut down without back-powering the Raspberry Pi or drives and shall return to normal operation when valid power is restored. Filesystem recovery remains the responsibility of the operating system; corruption of an active write cannot be guaranteed against.`
- **Behaviour after a drive fault:** `reported to the operating system without preventing access to the other drive. A drive-side power fault should be isolated where practical.`
- **Behaviour after controller overheating:** `throttle or shutdown`
- **Connector insertion/removal cycles target:** `TBD`
- **Protection against incorrect connections:** `TBD`
- **Required design margins:** `TBD`

No single drive fault should `damage the Raspberry Pi, controller, power supply, or other drive, nor cause the unaffected drive to become inaccessible under normal fault conditions.`.

## 12. Manufacturing and cost requirements

- **Prototype quantity:** `TBD`
- **Target bare-PCB cost:** `$[TBD] CAD`
- **Target BOM cost per board:** `$[TBD] CAD`
- **Maximum acceptable prototype cost:** `$[TBD] CAD`
- **Assembly method:** `Hand assembly`
- **Smallest package you can reliably assemble:** `TBD`
- **Components requiring assembly service:** `TBD`
- **Preferred component suppliers:** `Digikey`
- **Minimum acceptable component availability:** `TBD`
- **Substitutes required for critical parts:** `TBD`

No critical component should be selected unless `[BLANK — availability/documentation rule]`.

## 13. Bring-up and validation requirements

The first prototype will be tested in this order:

1. `visual inspection and unpowered resistance checks`
2. `validate each power rail without drives`
3. `verify clocks and reset`
4. `confirm PCIe enumeration`
5. `connect one drive`
6. `test all ports and sustained load`

### Required test equipment

- `Osciliscope`
- `Multimeter`
- `Logic Analyzer`
- `Thermal Camera`

### Acceptance tests

| ID | Requirement being tested | Test method | Pass condition |
|---|---|---|---|
| T-01 | `[BLANK]` | `[BLANK]` | `[BLANK]` |
| T-02 | `[BLANK]` | `[BLANK]` | `[BLANK]` |
| T-03 | `[BLANK]` | `[BLANK]` | `[BLANK]` |
| T-04 | `[BLANK]` | `[BLANK]` | `[BLANK]` |

## 14. Documentation deliverables

Before Revision 1 is considered complete, the repository must contain:

- `[ ]` Requirements specification
- `[ ]` System block diagram
- `[ ]` Design-decision records
- `[ ]` Component comparison and selection notes
- `[ ]` Schematic PDF and source files
- `[ ]` PCB source files and fabrication outputs
- `[ ]` Bill of materials
- `[ ]` Assembly notes
- `[ ]` Bring-up checklist
- `[ ]` Test results
- `[ ]` Known limitations
- `[ ]` User setup instructions

## 15. Requirement priorities

Use these labels:

- **MUST:** Revision 1 fails without it.
- **SHOULD:** Important, but the prototype remains useful without it.
- **COULD:** Optional if time, cost, and layout permit.
- **WON'T:** Explicitly excluded from Revision 1.

| ID | Priority | Requirement | Verification method | Status |
|---|---|---|---|---|
| SYS-001 | MUST | The board shall `[BLANK]`. | `[Inspection / Test / Analysis]` | Proposed |
| SYS-002 | MUST | The board shall `[BLANK]`. | `[Inspection / Test / Analysis]` | Proposed |
| PWR-001 | MUST | The power system shall `[BLANK]`. | `[Inspection / Test / Analysis]` | Proposed |
| IO-001 | MUST | The host interface shall `[BLANK]`. | `[Inspection / Test / Analysis]` | Proposed |
| PERF-001 | SHOULD | The system shall achieve `[BLANK]`. | `[Inspection / Test / Analysis]` | Proposed |
| MECH-001 | SHOULD | The assembled board shall `[BLANK]`. | `[Inspection / Test / Analysis]` | Proposed |

## 16. Assumptions

- I currently assume that `[BLANK]`.
- I currently assume that `[BLANK]`.
- I currently assume that `[BLANK]`.

Each assumption must later be confirmed, converted into a requirement, or rejected.

## 17. Open research questions

| ID | Question | Why it matters | Planned source/experiment | Status |
|---|---|---|---|---|
| RQ-01 | `[BLANK]` | `[BLANK]` | `[BLANK]` | Open |
| RQ-02 | `[BLANK]` | `[BLANK]` | `[BLANK]` | Open |
| RQ-03 | `[BLANK]` | `[BLANK]` | `[BLANK]` | Open |
| RQ-04 | `[BLANK]` | `[BLANK]` | `[BLANK]` | Open |

## 18. Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| `[BLANK — e.g., controller unavailable]` | `[Low/Medium/High]` | `[Low/Medium/High]` | `[BLANK]` |
| `[BLANK — e.g., power insufficient at spin-up]` | `[Low/Medium/High]` | `[Low/Medium/High]` | `[BLANK]` |
| `[BLANK — e.g., high-speed link fails]` | `[Low/Medium/High]` | `[Low/Medium/High]` | `[BLANK]` |

