# Contributing to Openwater

Thank you for your interest in contributing to Openwater! We're building open-source medical devices to democratize healthcare innovation and serve 3.5 billion underserved people worldwide.

## 🎯 Quick Start

**First time contributing?**
1. Join our [Discord community](https://discord.gg/openwater)
2. Read our [Code of Conduct](CODE_OF_CONDUCT.md)
3. Browse [Good First Issues](https://github.com/search?q=org%3AOpenwaterHealth+label%3A%22good+first+issue%22&type=issues)
4. Follow the [contribution workflow](#contribution-workflow) below

**Experienced contributor?**
- Check the [project roadmap](https://github.com/OpenwaterHealth/openwater-commons/blob/main/ROADMAP.md)
- Join [monthly community calls](https://github.com/OpenwaterHealth/openwater-commons/blob/main/community/monthly-meetings.md)
- Review [RFC proposals](https://github.com/OpenwaterHealth/openwater-governance/tree/main/rfcs)

## 🤝 Ways to Contribute

### 💻 Code Contributions
- **Software:** Python, C/C++, JavaScript, APIs
- **Firmware:** Embedded systems, device drivers
- **Hardware:** CAD designs (mechanical), schematics (electrical)
- **Testing:** Unit tests, integration tests, validation

### 📚 Documentation
- Improve getting-started guides
- Write tutorials and examples
- Create video demonstrations
- Translate documentation

### 🐛 Bug Reports & Feature Requests
- Report issues you encounter
- Suggest enhancements
- Provide feedback on proposals

### 🎓 Community Support
- Answer questions on Discord
- Review pull requests
- Mentor new contributors
- Present at community calls

### 🔬 Research & Clinical
- Contribute academic papers
- Share clinical trial data
- Validate medical applications
- Peer review research proposals

## 📋 Contribution Workflow

### 1. Find or Create an Issue

**Before starting work:**
- Search existing [issues](https://github.com/search?q=org%3AOpenwaterHealth+is%3Aissue&type=issues)
- If none exist, create a new issue describing your proposal
- Wait for feedback from maintainers (usually within 48 hours)
- Get approval before starting significant work

**Good first issues:**
```bash
# Find beginner-friendly issues across all repos
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
- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation
- `refactor/` - Code refactoring
- `test/` - Adding tests
- `hardware/` - Hardware design changes

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
flake8 src/
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
- Initial review within 48-72 hours
- Feedback from maintainers and community
- Possible requests for changes
- CI/CD checks must pass

**During review:**
- Respond to comments promptly
- Make requested changes
- Push updates to the same branch
- Be open to feedback and learning

**After approval:**
- Maintainer will merge your PR
- Your contribution is live! 🎉
- You'll be added to [CONTRIBUTORS.md](https://github.com/OpenwaterHealth/openwater-commons/blob/main/CONTRIBUTORS.md)

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
- Linter: `flake8` or `ruff`
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
  // Constructor
  PulseGenerator(uint32_t sample_rate, uint16_t num_channels);
  
  // Generate pulse sequence
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
  - Include datasheets in docs/datasheets/
  - Note any substitutable components

### Markdown Documentation
```markdown
# Use ATX-style headers (# ## ###)

## Keep line length to ~100 characters for readability

**Bold** for emphasis, *italics* for subtle emphasis.

Use `code` for technical terms, commands, filenames.

```python
# Use fenced code blocks with language specified
def example():
    pass
```

Link format: [descriptive text](https://url.com)

Image format: ![alt text](path/to/image.png)
```

## 🔒 Contributor License Agreement (CLA)

**First-time contributors must sign our CLA:**

When you submit your first pull request, our CLA bot will comment with instructions. This is a one-time process.

**Why we require a CLA:**
- Ensures Openwater can relicense code if needed
- Protects contributors and the project legally
- Standard practice for open-source medical devices
- Required for regulatory compliance (FDA)

**What you're agreeing to:**
- You have the right to contribute the code
- You grant Openwater permission to use your contribution
- Your contribution is under the Apache 2.0 license
- You retain copyright to your work

[Read full CLA](https://github.com/OpenwaterHealth/openwater-commons/blob/main/CLA.md)

## 🏆 Recognition

**Contributors are recognized:**
- Listed in [CONTRIBUTORS.md](https://github.com/OpenwaterHealth/openwater-commons/blob/main/CONTRIBUTORS.md)
- Featured in monthly newsletters
- Invited to contributor-only calls
- Eligible for bounties and grants
- Considered for maintainer roles

**Contribution levels:**
1. **Contributor** - First merged PR
2. **Regular Contributor** - 5+ merged PRs
3. **Core Contributor** - 25+ merged PRs + 6 months activity
4. **Committer** - Core contributor + TSC approval (commit access)
5. **Maintainer** - Responsible for specific repositories

[See contributor ladder](https://github.com/OpenwaterHealth/openwater-commons/blob/main/docs/community/contributor-ladder.md)

## 💰 Bounties & Grants

**Bounty Program:**
- Issues labeled with `bounty-$500`, `bounty-$1000`, etc.
- Complete the work, submit PR, receive payment
- Payment via smart contract or GitHub Sponsors

**Community Grants:**
- $50,000 annual pool for innovative projects
- Submit proposals via RFC process
- Community voting on grant recipients

[Learn more about bounties and grants](https://github.com/OpenwaterHealth/openwater-governance/blob/main/grants/README.md)

## 📞 Getting Help

**Stuck? Have questions?**

**Discord (fastest response):**
- [#general](https://discord.gg/openwater) - General questions
- [#dev-help](https://discord.gg/openwater) - Development help
- [#hardware](https://discord.gg/openwater) - Hardware questions

**GitHub:**
- [Discussions](https://github.com/OpenwaterHealth/openwater-commons/discussions) - Long-form Q&A
- [Issues](https://github.com/OpenwaterHealth/openwater-commons/issues) - Bug reports, features

**Other channels:**
- Email: [community@openwater.health](mailto:community@openwater.health)
- Office Hours: Weekly (see [schedule](https://github.com/OpenwaterHealth/openwater-commons/blob/main/community/office-hours.md))

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
- [PCB Design Best Practices](https://www.proto-electronics.com/blog/pcb-design-best-practices)

## ⚖️ Code of Conduct

All contributors must follow our [Code of Conduct](CODE_OF_CONDUCT.md).

**Summary:**
- Be respectful and inclusive
- Welcome newcomers
- Assume good intentions
- Focus on what's best for the community
- Show empathy toward others

**Reporting issues:**
- Email: [conduct@openwater.health](mailto:conduct@openwater.health)
- All reports are confidential
- Response within 24 hours

## 🙏 Thank You!

Your contributions make Openwater possible. Whether you're fixing typos, adding features, or helping others, you're part of a global movement to democratize medical technology.

**Every contribution matters.** Welcome to the Openwater community! 🌊

---

**Questions?** Join us on [Discord](https://discord.gg/openwater) or email [community@openwater.health](mailto:community@openwater.health)
