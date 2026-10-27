# PEMForge Pro (v1.0.0)

### CCSDS 510.0-B-1 & ISO 26900 Spacecraft Planetary Ephemeris Message (PEM) Studio

PEMForge Pro is an aerospace-grade developer studio, Chebyshev polynomial interpolation engine, celestial body trajectory propagator (Moon, Mars, Jupiter, Europa), dual KVN / XML serializer, and 10-point normative compliance auditor designed for deep-space flight dynamics teams (NASA JPL, ESA ESOC, JAXA) and commercial lunar/planetary mission operators.

---

## 🌟 Key Capabilities

- **Chebyshev Polynomial Interpolation Series**: Implements high-precision Clenshaw recurrence and discrete Chebyshev transforms (\$N=7..15\$) for compact, sub-meter trajectory approximation.  
- **Solar System Barycentric Coordinates (ICRF / SSB)**: Propagates celestial bodies in Solar System Barycentric (SSB) and planetocentric coordinate frames with Barycentric Dynamical Time (`TDB`) time systems.  
- **Analytic Velocity Derivatives**: Computes exact analytic time derivatives (\$dX/dt\$) directly from Chebyshev basis derivatives without finite-difference truncation error.  
- **Dual KVN & NDM/XML Serializers**: Outputs both classic CCSDS Key-Value Notation (KVN) and schema-compliant NDM/XML (`<pem>` container) per CCSDS 506.0-B-1.  
- **Multi-Body Ephemeris Catalogs**: Built-in support for Moon (Earth-Moon Barycenter / NAIF 301), Mars Barycenter (NAIF 499), Jupiter Barycenter (NAIF 599), and Europa (NAIF 502).  
- **10-Point Normative Auditor**: Automated verification engine enforcing rules `PEM-001` through `PEM-010` per official CCSDS Blue Book standards.

---

## 📂 Project Structure

pem-forge-pro/

├── source-code/

│   ├── pem-engine.js            \# Core Chebyshev evaluator, celestial models & serializers

│   ├── pem-auditor.js           \# 10-point normative compliance auditor

│   ├── pem\_cli.py               \# Python 3 CLI executable

│   ├── pem-cli.py               \# Python 3 CLI alias

│   ├── test\_runner.py           \# 10-suite unit test runner

│   └── index.html               \# Interactive Mission Control operations console

├── build/

│   └── pem-forge-pro-v1.0.0.zip \# Standalone production bundle

├── documentation/

│   ├── CCSDS\_PEM\_SPECIFICATION.md \# Normative protocol specification

│   └── PEM\_COMPLIANCE\_MATRIX.md   \# 10-point requirement traceability

└── screenshots/

    ├── architecture-diagram.svg   \# System architecture diagram

    └── pem-studio-preview.svg     \# Operations studio interface preview

---

## 🚀 Quick Start

### Running Automated Tests

python3 source-code/test\_runner.py \-v

### Command Line Interface

\# Generate Moon ephemeris over 10 days with Chebyshev degree 7

python3 source-code/pem\_cli.py \--mode ephemeris \--body MOON \--days 10 \--degree 7

\# Generate Mars barycentric ephemeris

python3 source-code/pem\_cli.py \--mode ephemeris \--body MARS \--days 30 \--degree 9

\# Run 10-Point Normative Compliance Audit

python3 source-code/pem\_cli.py \--mode audit

### Launching the Web Operations Console

Open `source-code/index.html` in any web browser for interactive celestial body selection, Chebyshev polynomial series inspection, KVN/XML stream export, and compliance scorecard auditing.