# PhantomCrawler: Web Security Scanner by GihanIT

**PhantomCrawler** is a lightweight web application reconnaissance and security testing tool designed for security researchers and penetration testers. It performs multi-threaded crawling, JavaScript analysis, secret detection, GraphQL endpoint probing, JWT token analysis, security header validation, and form fuzzing for XSS vulnerabilities, with comprehensive JSON and HTML reporting.

⚠️ **Ethical Use**: PhantomCrawler is intended solely for security researchers and penetration testers with explicit written permission to test target systems. Unauthorized use is illegal and unethical. The author assumes no liability for any misuse or damage caused by this tool.

-----

## Features

  * Multi-threaded crawling with rate limiting
  * JavaScript analysis for risky patterns
  * Secret and credential detection
  * GraphQL endpoint discovery and testing
  * JWT token analysis
  * Security header validation
  * Form discovery and XSS fuzzing
  * Comprehensive JSON and HTML reporting

-----

## Version

  * **Current Version**: 1.0

-----

## Prerequisites

PhantomCrawler requires **Python 3.8+**. Kali Linux typically includes Python 3 pre-installed.

Verify your Python version:

```bash
python3 --version
```

-----

## Installation

### 1\. Update System (Optional but Recommended)

```bash
sudo apt update
sudo apt upgrade -y
```

### 2\. Install pip3 (if not already installed)

```bash
sudo apt install python3-pip -y
```

### 3\. Clone the Repository

```bash
# Create a directory for security tools
mkdir -p ~/security-tools
cd ~/security-tools

# Clone the repository
git clone https://github.com/GihanIT/Phantom-Crawler.git
cd Phantom-Crawler
```

### 4\. Install Dependencies

PhantomCrawler requires `requests`, `beautifulsoup4`, and `colorama`. These are listed in `requirements.txt`.

```bash
pip3 install -r requirements.txt
```

**Note**: Dependencies like `lxml`, `certifi`, and `urllib3` are typically included with `requests` or `beautifulsoup4`. If you encounter issues, install them manually:

```bash
pip3 install lxml certifi urllib3
```

### 5\. Make Script Executable

```bash
chmod +x PhantomCrawler.py
```

### 6\. Test Installation

```bash
python3 PhantomCrawler.py --help
```

You should see the help menu with available options.

### 7\. Optional: Create Symlink for Global Access

To run PhantomCrawler from anywhere:

```bash
sudo ln -s $(pwd)/PhantomCrawler.py /usr/local/bin/PhantomCrawler
```

Then run it as:

```bash
PhantomCrawler https://example.com --depth 2
```

### 8\. Optional: Use a Virtual Environment

For isolated dependencies:

```bash
# Install venv
sudo apt install python3-venv -y

# Create and activate virtual environment
python3 -m venv phantom-env
source phantom-env/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run the tool
python PhantomCrawler.py https://example.com

# Deactivate when done
deactivate
```

-----

## Usage Examples

### Basic Reconnaissance

```bash
python3 PhantomCrawler.py https://example.com --depth 2 --threads 5
```

### Deep Scan with Fuzzing

```bash
python3 PhantomCrawler.py https://example.com --depth 3 --fuzz --threads 10
```

### GraphQL Endpoint Probing

```bash
python3 PhantomCrawler.py https://api.example.com --graphql --depth 1
```

### Full Security Audit

```bash
python3 PhantomCrawler.py https://example.com --depth 3 --fuzz --graphql --threads 8 --out full_audit.json
```

### Output to Custom File

```bash
python3 PhantomCrawler.py https://example.com --out my_report.json
```

-----

## Command-Line Options

```bash
python3 PhantomCrawler.py --help
```

| Option | Description | Default |
| :--- | :--- | :--- |
| `target` | Base target URL (e.g., `https://example.com`) | **Required** |
| `--depth` | Crawl depth | 1 |
| `--threads` | Number of threads | 3 |
| `--fuzz` | Enable XSS fuzzing on forms | Disabled |
| `--graphql` | Probe GraphQL endpoints | Disabled |
| `--out` | Output report file | `phantom_report.json` |
| `--no-html` | Skip HTML report generation | HTML enabled |

-----

## Troubleshooting

### `ModuleNotFoundError`

**Solution**: Install the missing module:

```bash
pip3 install <module_name>
```

### `Permission Denied`

**Solution**: Ensure the script is executable:

```bash
chmod +x PhantomCrawler.py
```

### SSL Certificate Errors

**Solution**: Update `certifi`:

```bash
pip3 install --upgrade certifi
```

### `pip3 Not Found`

**Solution**: Install `pip`:

```bash
sudo apt install python3-pip
```

-----

## Uninstallation

To remove PhantomCrawler:

```bash
# Remove the repository
rm -rf ~/security-tools/PhantomCrawler

# Remove symlink (if created)
sudo rm /usr/local/bin/PhantomCrawler

# Uninstall Python packages (if not used by other tools)
pip3 uninstall requests beautifulsoup4 colorama lxml certifi urllib3
```

## License
This project is licensed under the MIT License - see the LICENSE file for details.
### Legal Notice
⚠️ IMPORTANT: PhantomCrawler is intended solely for security researchers and penetration testers with explicit written permission to test target systems. Unauthorized use is illegal and unethical. The author assumes no liability for any misuse or damage caused by this tool.