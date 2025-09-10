Molecule Test: Java Role
--------------------------

This directory contains the [Molecule](https://molecule.readthedocs.io/) test scenarios for the `java` Ansible role. It helps ensure that the role installs and configures Java correctly on supported platforms.

---

📁 Directory Structure
----------------------

```bash
molecule/
└── default/
    ├── converge.yml       # Applies the role to the test instance
    ├── verify.yml         # Verifies Java installation and environment setup
    └── molecule.yml       # Molecule configuration file
```
⚙️ Prerequisites
---------------
You must have the following tools installed:
- Python 3.x
- Docker installed and running
- `pip` (Python package manager)

🚀 Installing Molecule
----------------------
### 1. Create a Python virtual environment (recommended)
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2. Install Molecule with Docker support
```bash
pip install molecule molecule-docker ansible-core docker
```

### 3. To verify Molecule is installed
```bash
molecule --version
```

🧪 Running Tests
----------------------

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/java.git
cd java/
```

### 2. Run Molecule Tests
To run the full test sequence (create, converge, verify, and destroy):
```bash
molecule test
```
To run each step manually:
```plain
molecule create      # Launch the test instance
molecule converge    # Apply the role
molecule verify      # Run test assertions
molecule destroy     # Clean up
```

🖥️ Platforms Tested
-------------------
- Ubuntu 24.04
- RockyLinux:9

You can customize platforms: in molecule.yml to add/remove distributions.


🧩 Custom Docker Image (Optional)
---------------------------------
If using a custom base image (e.g., Ubuntu 24.04 with systemd support), set pre_build_image: false in molecule.yml and define a Dockerfile.j2 under molecule/default.

📝 Notes
--------
- Ensure Docker daemon is running before executing Molecule commands.
- Use virtual environment to avoid dependency issues.
- After modifying molecule.yml, use molecule destroy before re-running to reset the environment.