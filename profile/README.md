# Welcome to Openwater 👋
![OpenwaterHealth Banner](openwater-3.png)
<p align="center">
  <a href="https://openwater.health"><img src="https://img.shields.io/badge/Website-openwater.health-00A86B?style=flat&logo=globe&logoColor=white" alt="Website"/></a> &nbsp;|&nbsp;
  <a href="https://docs.openwater.health"><img src="https://img.shields.io/badge/Docs-docs.openwater.health-2196F3?style=flat&logo=readthedocs&logoColor=white" alt="Docs"/></a> &nbsp;|&nbsp;
  <a href="https://www.openwater.health/blog"><img src="https://img.shields.io/badge/Blog-FF5722?style=flat&logo=rss&logoColor=white" alt="Blog"/></a> &nbsp;|&nbsp;
  <a href="https://www.youtube.com/channel/UCvoo5XMm3a7wfeiVkBosznw"><img src="https://img.shields.io/badge/YouTube-Subscribe-FF0000?style=flat&logo=youtube&logoColor=white" alt="YouTube"/></a> &nbsp;|&nbsp;
  <a href="https://x.com/OpenwaterHealth"><img src="https://img.shields.io/badge/X-Follow-000000?style=flat&logo=x&logoColor=white" alt="X"/></a> &nbsp;|&nbsp;
  <a href="https://discord.gg/fS7vfAX4fA"><img src="https://img.shields.io/badge/Discord-Join%20Community-5865F2?style=flat&logo=discord&logoColor=white" alt="Discord"/></a>
</p>
# Openwater Commons
> Building open-source medical devices — an open-source platform democratizing medical imaging and neuromodulation technology.
## 🎯 Mission
Reduce medical device development costs from $119M to $15M through open-source collaboration, bringing advanced healthcare technology to 3.5 billion underserved people worldwide.
## 🚀 Quick Start
**For Documentation:** [docs.openwater.health](https://docs.openwater.health) — guides, API references, and platform documentation<br>
**For Developers:** [Contribution Guidelines](https://github.com/OpenwaterHealth/.github/blob/main/CONTRIBUTING.md)<br>
**For Researchers:** [Discord Community](https://discord.gg/fS7vfAX4fA) — reach out about research partnerships<br>
**For Contributors:** [Code of Conduct](https://github.com/OpenwaterHealth/.github/blob/main/CODE_OF_CONDUCT.md) | [Security Policy](https://github.com/OpenwaterHealth/.github/blob/main/SECURITY.md)
---
## 🏗️ Platform Repositories
Openwater maintains two open-source medical device platforms. Each platform spans software, firmware, and hardware — everything needed to build, modify, and manufacture the device.
### Open-LIFU — Low-Intensity Focused Ultrasound
An open-source platform for focused ultrasound neuromodulation research planning and delivery.
#### Software
| Repository | Description |
|:-----------|:------------|
| [**openlifu-python**](https://github.com/OpenwaterHealth/openlifu-python) | Core Python toolbox for treatment planning, simulation, and transducer control |
| [**openlifu-desktop-application**](https://github.com/OpenwaterHealth/openlifu-desktop-application) | Desktop GUI for sonication planning and system control (C++) |
| [**SlicerOpenLIFU**](https://github.com/OpenwaterHealth/SlicerOpenLIFU) | 3D Slicer extension for Open-LIFU treatment planning |
| [**openlifu-sdk**](https://github.com/OpenwaterHealth/openlifu-sdk) | Standalone hardware I/O interface library |
| [**OpenLIFU-3DScanner**](https://github.com/OpenwaterHealth/OpenLIFU-3DScanner) | 3D mesh capture application for patient registration (Kotlin) |
#### Firmware
| Repository | Description |
|:-----------|:------------|
| [**openlifu-transmitter-fw**](https://github.com/OpenwaterHealth/openlifu-transmitter-fw) | Transmit module firmware — STM32L443, high-voltage RF signal generation |
| [**openlifu-transmitter-bl**](https://github.com/OpenwaterHealth/openlifu-transmitter-bl) | Secure DFU bootloader for the transmit module (USB + I2C, ECDSA signing) |
| [**openlifu-console-fw**](https://github.com/OpenwaterHealth/openlifu-console-fw) | Console power PCB firmware — HV power supply and USB communication |
#### Hardware
| Repository | Description |
|:-----------|:------------|
| [**openlifu-electrical**](https://github.com/OpenwaterHealth/openlifu-electrical) | PCB schematics, Gerber files, and BOMs for all Open-LIFU boards |
| [**openlifu-mechanical**](https://github.com/OpenwaterHealth/OpenLIFU-Mechanical) | Mechanical CAD files and enclosure designs |
#### Testing & Validation
| Repository | Description |
|:-----------|:------------|
| [**openlifu-test-app**](https://github.com/OpenwaterHealth/openlifu-test-app) | QML-based hardware validation and test application |
| [**openlifu-test-scripts**](https://github.com/OpenwaterHealth/openlifu-test-scripts) | Automated test scripts for hardware and integration testing |
| [**openlifu-verification-tank**](https://github.com/OpenwaterHealth/openlifu-verification-tank) | Acoustic verification tank control and measurement |
| [**openlifu-sample-database**](https://github.com/OpenwaterHealth/openlifu-sample-database) | Sample data for development and testing |
---
### Open-Motion — Near-Infrared Optical Blood Flow Imaging
An open-source platform for non-invasive cerebral blood flow measurement, with clinical validation data from a multi-site stroke study.
#### Software
| Repository | Description |
|:-----------|:------------|
| [**openmotion-bloodflow-app**](https://github.com/OpenwaterHealth/openmotion-bloodflow-app) | Blood flow imaging application (Python/QML) |
| [**openmotion-test-app**](https://github.com/OpenwaterHealth/openmotion-test-app) | QML-based hardware validation and test application |
| [**opw_bloodflow_gen2_ai**](https://github.com/OpenwaterHealth/opw_bloodflow_gen2_ai) | Deep learning blood flow classification model |
#### Firmware & FPGA
| Repository | Description |
|:-----------|:------------|
| [**openmotion-console-fw**](https://github.com/OpenwaterHealth/openmotion-console-fw) | Console board firmware — power conditioning, laser control, host communication |
| [**openmotion-camera-fpga**](https://github.com/OpenwaterHealth/openmotion-camera-fpga) | Camera sensor FPGA design files |
| [**openmotion-ta-fpga**](https://github.com/OpenwaterHealth/openmotion-ta-fpga) | Timing/aggregator FPGA design files |
#### Hardware
| Repository | Description |
|:-----------|:------------|
| [**openmotion-electrical**](https://github.com/OpenwaterHealth/openmotion-electrical) | PCB schematics and manufacturing files for all OpenMOTION boards |
| [**openmotion-mechanical**](https://github.com/OpenwaterHealth/openmotion-mechanical) | Mechanical CAD files and enclosure designs |
---
### Shared Infrastructure
| Repository | Description |
|:-----------|:------------|
| [**.github**](https://github.com/OpenwaterHealth/.github) | Org-wide governance: contributing guide, code of conduct, security policy, issue templates |
---
## 🤝 Get Involved
We're building a global community of developers, researchers, and clinicians.
- 📖 **Read the Docs:** [docs.openwater.health](https://docs.openwater.health) — platform guides, API references, and tutorials
- 💬 **Join the Community:** [Discord](https://discord.gg/fS7vfAX4fA) — ask questions, share ideas, connect with the team
- 📚 **Improve Docs:** Documentation contributions welcome across all repos
- 🐛 **Report Issues:** Open an issue in the relevant repo — [issue templates](https://github.com/OpenwaterHealth/.github/tree/main/.github/ISSUE_TEMPLATE) guide you through it
- 🎓 **Academic Research:** Reach out on Discord about research partnerships and dataset access
## 📊 Governance
Openwater uses a Technical Steering Committee (TSC) governance model inspired by CNCF and Linux Foundation practices, adapted for the unique requirements of open-source medical device development.
- [Governance Charter](https://github.com/OpenwaterHealth/.github/blob/main/GOVERNANCE.md) — Roles, decision-making, contribution evaluation, safety, and regulatory governance
- [Quality Statement](https://github.com/OpenwaterHealth/.github/blob/main/QUALITY_STATEMENT.md) — Standards for code quality, testing, documentation, and release readiness
- [Code of Conduct](https://github.com/OpenwaterHealth/.github/blob/main/CODE_OF_CONDUCT.md) — Expected behavior, reporting process, and enforcement policies
- [Contribution Guidelines](https://github.com/OpenwaterHealth/.github/blob/main/CONTRIBUTING.md) — How to submit issues, pull requests, research data, and hardware designs
- [Security Policy](https://github.com/OpenwaterHealth/.github/blob/main/SECURITY.md) — Vulnerability reporting and responsible disclosure
## 📄 License
This project is licensed under the AGPL 3.0 — see the [LICENSE](LICENSE) file for details.
## 🌟 Acknowledgments
Built with support from the global open-source medical device community. Special thanks to our research partners and contributors.
---
**Status:** 🚧 Under Active Development | Last Updated: April 24, 2026
