# Contributing to Openwater

These guidelines apply across Openwater repositories unless a repository states a more specific policy. The license in each repository's LICENSE file governs its published contents. Third-party components retain their own licenses and notices.

## Licensing layers

| Layer | License | Scope |
| --- | --- | --- |
| Reciprocal software core | AGPL-3.0-or-later | OpenLIFU console and transmitter firmware; OpenMOTION FPGA/HDL; sensing, measurement, beamforming, reconstruction, signal-processing and calibration core |
| Permissive software and integration | Apache-2.0 | OpenMOTION console and sensor firmware; all bootloaders; 3D Slicer extensions; applications and tooling; wellness and veterinary modules; partner SDKs, language bindings and scripts |
| Hardware reference designs | CERN-OHL-S-2.0 | Mechanical CAD, schematics, PCB layouts and related design sources |
| Documentation and data | CC-BY-4.0 | Documentation, templates, tutorials and sample data |

The 3D Slicer and hardware rows describe the approved destination for repositories still carrying AGPL licenses. Their current LICENSE files remain controlling until contributor rights are confirmed and the relicensing changes are merged. No contributor's work may be relicensed without the rights to do so.

Per-repository and per-path assignments will be reflected in [`license-manifest`](https://github.com/OpenwaterHealth/license-manifest) in the separate publication step. If a file's license is unclear, open a license question before contributing.

## Developer Certificate of Origin

Sign off every commit under the [DCO](https://developercertificate.org/):

```sh
git commit -s -m "Describe the change"
```

The sign-off certifies that you wrote the contribution or have the right to submit it under the applicable license. A Contributor License Agreement may also be required in areas that need relicensing authority.

## Workflow

1. Open or find an issue for substantial work.
2. Create a focused branch and make signed-off commits.
3. Preserve copyright and third-party notices. Add a valid SPDX header to new source files. Use `AGPL-3.0-or-later` for AGPL core source, `Apache-2.0` for permissive software, and `CERN-OHL-S-2.0` for hardware design sources where the corresponding license is effective.
4. Open a pull request and pass the repository's required checks and review.
5. For a license change, document rights and approvals before changing LICENSE, metadata or public license claims.

See the [Code of Conduct](CODE_OF_CONDUCT.md) for participation expectations.
