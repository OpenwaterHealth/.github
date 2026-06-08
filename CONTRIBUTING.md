# Contributing to Openwater

Thank you for your interest in contributing to Openwater. We're building open-source medical devices used by research labs at MIT Lincoln Laboratory, UCLA, the University of Pennsylvania, Brown, the University of Arizona, and ETH Zurich. Contributions land in real research work.

## 🎯 Quick Start

**First time contributing?**

1. Join our [Discord community](https://discord.gg/openwater)
2. Read our [Code of Conduct](CODE_OF_CONDUCT.md)
3. Browse [Good First Issues](https://github.com/search?q=org%3AOpenwaterHealth+label%3A%22good+first+issue%22&type=issues)
4. Follow the [contribution workflow](#contribution-workflow) below

**Experienced contributor?**

- Visit the [community hub](https://openwaterhealth.github.io/openwater-community/) for current focus areas
- Join us at [office hours on Discord](https://discord.gg/openwater) — see the hub for the next session

## 🤝 Ways to Contribute

You do not need an Openwater device to contribute. Most of our community will never receive a physical unit, and that's fine — the work that moves the platform forward happens in code, documentation, quality, research methodology, and clinical workflow design. We call this the **Contribute Without a Unit** track. See it on the [community hub](https://openwaterhealth.github.io/openwater-community/#contribute-without-a-unit).

### 💻 Code Contributions

- **Software:** Python, C/C++, JavaScript, APIs
- **Firmware:** Embedded systems, device drivers
- **Hardware:** CAD designs (mechanical), schematics (electrical)
- **Testing:** Unit tests, integration tests, validation

### 📚 Documentation

- Improve getting-started guides
- Write tutorials and examples
- Build glossaries and references
- Translate documentation

### 🐛 Bug Reports & Feature Requests

- Report issues you encounter
- Suggest enhancements
- Provide feedback on proposals

### 🎓 Community Support

- Answer questions on Discord
- Review pull requests
- Mentor new contributors
- Present at office hours

### 🔬 Research & Clinical

- Contribute literature reviews and methodology
- Share anonymized research data
- Validate medical applications
- Peer review proposals

## 📋 Contribution Workflow

### 1. Find or Create an Issue

**Before starting work:**

- Search existing [issues](https://github.com/search?q=org%3AOpenwaterHealth+is%3Aissue&type=issues)
- If none exist, create a new issue describing your proposal
- Wait for feedback from maintainers (usually within 48 business hours)
- Get approval before starting significant work

**Good first issues:**

```
https://github.com/search?q=org%3AOpenwaterHealth+label%3A%22good+first+issue%22&type=issues
```

### 2. Fork and Clone

```bash
# Fork the repository on GitHub, then:
git clone https://github.com/YOUR-USERNAME/REPO-NAME.git
cd REPO-NAME

# Add upstream remote
git remote add upstream https://github.com/OpenwaterHealth/REPO-NAME.git
```

### 3. Create a Branch

```bash
# Create a descriptive branch name
git checkout -b feature/add-pulse-sequence-validation
git checkout -b fix/memory-leak-in-reconstruction
git checkout -b docs/improve-installation-guide
```

**Branch naming convention:**

- `feature/` — New features
- `fix/` — Bug fixes
- `docs/` — Documentation
- `refactor/` — Code refactoring
- `test/` — Adding tests
- `hardware/` — Hardware design changes

### 4. Make Your Changes

**Before coding:**

- Read relevant documentation
- Review similar existing code
- Follow the style guide for your language

**While coding:**

- Write clear, self-documenting code
- Add comments for complex logic
- Include docstrings for functions
- Write or update tests
- Update documentation

**Commit guidelines:**

```bash
# Use conventional commit format
git commit -m "feat: add pulse sequence validation"
git commit -m "fix: resolve memory leak in reconstruction algorithm"
git commit -m "docs: improve installation troubleshooting section"
```

**Commit message format:**

```
<type>: <short description>

<optional longer description>

<optional footer>
```

**Types:**

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation
- `style`: Formatting, missing semicolons, etc.
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance tasks

### 5. Test Your Changes

**Software/Firmware:**

```bash
# Run existing tests
pytest tests/

# Run linters
ruff check src/
black src/

# Test manually
python examples/test_your_feature.py
```

**Hardware:**

- Verify CAD files open without errors
- Check STEP/STL exports are valid
- Update BOM if components changed
- Include renders/photos of changes

**Documentation:**

```bash
# Test MkDocs site locally
mkdocs serve

# Check for broken links
markdown-link-check docs/**/*.md
```

### 6. Push and Create Pull Request

```bash
# Push to your fork
git push origin feature/add-pulse-sequence-validation
```

**Create Pull Request:**

1. Go to the original repository on GitHub
2. Click "New Pull Request"
3. Select your fork and branch
4. Fill out the PR template completely
5. Link related issues (e.g., "Closes #123")

**PR Title Format:**

```
feat: add pulse sequence validation

fix: resolve memory leak in reconstruction

docs: improve installation guide
```

### 7. Code Review Process

**What to expect:**

- Initial review within 48–72 business hours
- Feedback from maintainers and the community
- Possible requests for changes
- CI/CD checks must pass

**During review:**

- Respond to comments promptly
- Make requested changes
- Push updates to the same branch
- Be open to feedback and learning

**After approval:**

- A maintainer will merge your PR
- Your contribution is live 🎉

## 🎨 Style Guides

### Python

```python
# Follow PEP 8
# Use type hints
# Maximum line length: 100 characters

def calculate_pressure(
    transducer_params: TransducerParams,
    target_location: np.ndarray,
    frequency: float = 500e3
) -> np.ndarray:
    """Calculate acoustic pressure at target location.

    Args:
        transducer_params: Transducer configuration
        target_location: 3D coordinates in mm
        frequency: Ultrasound frequency in Hz (default 500kHz)

    Returns:
        Pressure field as numpy array

    Raises:
        ValueError: If target_location is outside valid range
    """
    # Implementation here
    pass
```

**Python tools:**

- Formatter: `black`
- Linter: `ruff` (preferred) or `flake8`
- Type checker: `mypy`
- Import sorter: `isort`

### C/C++

```cpp
// Follow Google C++ Style Guide
// Use meaningful variable names
// Maximum line length: 100 characters

namespace openwater {
namespace lifu {

class PulseGenerator {
 public:
  PulseGenerator(uint32_t sample_rate, uint16_t num_channels);

  std::vector<float> GenerateSequence(
      const PulseParams& params,
      uint32_t duration_ms);

 private:
  uint32_t sample_rate_;
  uint16_t num_channels_;
};

}  // namespace lifu
}  // namespace openwater
```

### Hardware (CAD/EDA)

- **Mechanical:** SolidWorks, Fusion 360, FreeCAD
  - Export STEP files (universal)
  - Export STL files (3D printing)
  - Include assembly drawings
- **Electrical:** KiCad (preferred), Altium, Eagle
  - Export schematics as PDF
  - Export Gerber files for PCB
  - Include assembly drawings
- **BOM Management:**
  - CSV format with headers: Part Number, Description, Quantity, Manufacturer, Supplier, Cost
  - Include datasheets in `docs/datasheets/`
  - Note any substitutable components

### Markdown Documentation

Use ATX-style headers (`#`, `##`, `###`). Keep line length to ~100 characters. Use fenced code blocks with language specified. Link format: `[descriptive text](https://url.com)`.

## 🔒 Licensing and Contributor License Agreement

**Current license:** Openwater repositories are licensed under **AGPL v3.0**.

**Planned transition:** We intend to move to **Apache 2.0** to support broader commercial adoption while preserving the open-source character of the platform. This transition is gated on standing up a Contributor License Agreement (CLA) flow.

**Status of the CLA flow:** In progress. Until the CLA flow is live, contributions are accepted under AGPL v3.0 by virtue of contributing to the relevant repository.

**What this means for you in practice:**

- Open your PR normally — there is no extra paperwork required today.
- Once the CLA flow is live, we will add a routing step at PR-open time: a one-time signing process that covers all your future contributions across all Openwater repos.
- You will retain copyright on your work. The CLA, once signed, will grant Openwater a license to use, distribute, and relicense your contribution — it does not transfer ownership.

If you have questions about how this affects your contribution, email [community@openwater.health](mailto:community@openwater.health).

## 🏆 Recognition

**Contributors are recognized:**

- Listed in commit history and on the contributors graph
- Mentioned in monthly "What we shipped" community updates
- Invited to office hours and community discussions
- Considered for maintainer roles as they build sustained contribution history

**Contribution ladder:**

1. **Contributor** — First merged PR
2. **Regular Contributor** — Multiple sustained contributions
3. **Core Contributor** — Sustained activity, reviews others' work, mentors newcomers
4. **Maintainer** — Responsible for specific repositories; commit access; named in the contacts table for their area

The path from Contributor to Maintainer is paved by people who do the unglamorous work consistently — issue triage, documentation, helping new contributors. If you want to take on more responsibility, tell us.

## 📞 Getting Help

**Stuck? Have questions?**

**Discord (fastest response):**

- `#general` — General questions
- `#contributing` — Development help
- `#hardware` — Hardware questions

[Join the Discord](https://discord.gg/openwater)

**GitHub:**

- [Discussions](https://github.com/OpenwaterHealth) — Long-form Q&A
- Issues in the relevant repo — Bug reports, features

**Other channels:**

- Email: [community@openwater.health](mailto:community@openwater.health)
- Office hours: Weekly on Discord; see the [community hub](https://openwaterhealth.github.io/openwater-community/) for the next session

## 🎓 Learning Resources

**New to medical devices?**

- [Medical Device Basics](https://docs.openwater.health/learning/medical-devices-101/)
- [Ultrasound Physics](https://docs.openwater.health/learning/ultrasound-physics/)
- [Optical Imaging Fundamentals](https://docs.openwater.health/learning/optical-imaging/)

**New to open source?**

- [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/)
- [First Timers Only](https://www.firsttimersonly.com/)
- [Open Source Friday](https://opensourcefriday.com/)

**New to hardware?**

- [KiCad Getting Started](https://docs.kicad.org/master/en/getting_started_in_kicad/getting_started_in_kicad.html)
- [FreeCAD Tutorials](https://wiki.freecadweb.org/Tutorials)

## ⚖️ Code of Conduct

All contributors must follow our [Code of Conduct](CODE_OF_CONDUCT.md).

**Summary:**

- Be respectful and inclusive
- Welcome newcomers
- Assume good intentions
- Focus on what's best for the community
- Show empathy toward others

**Reporting issues:**

- Email [community@openwater.health](mailto:community@openwater.health)
- All reports are confidential
- Response within two business days

## 🩺 Regulatory Note

Openwater's platforms are exclusively intended for research purposes and are not cleared or approved by the FDA for clinical use. If your contribution touches anything that could be read as a clinical claim — a documentation change, a parameter description, a summary of trial results — please include or preserve the short-form disclaimer:

Openwater's platform is intended exclusively for research purposes and is not cleared or approved by the FDA for clinical use.

We will flag this in review if it's missing. It is not optional.

## 🙏 Thank You

Your contributions make Openwater possible. Whether you're fixing typos, adding features, or helping others, you're part of building open-source medical technology used by real research labs treating real conditions. Every contribution matters.

Welcome to the Openwater community. 🌊

---

**Questions?** Join us on [Discord](https://discord.gg/openwater) or email [community@openwater.health](mailto:community@openwater.health)
