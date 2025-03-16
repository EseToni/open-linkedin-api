# OpenLinkedInAPI

**An Open-Source Python Library for LinkedIn Automation**

[![Build](https://img.shields.io/github/actions/workflow/status/your-repo/openlinkedinapi/build.yml)](https://github.com/your-repo/openlinkedinapi/actions)  
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

## Features

✅ No official API access required – just use a valid LinkedIn account.  
✅ Direct HTTP API interface – no Selenium, Puppeteer, or browser-based scraping.  
✅ Search and retrieve profiles, companies, jobs, and posts.  
✅ Send and receive messages.  
✅ Send and accept connection requests.  
✅ React to posts and extract data efficiently.  
✅ Community-driven and regularly updated.

> ⚠ **Disclaimer**: This library is not officially supported by LinkedIn. Using it may violate LinkedIn's Terms of Service. Use it at your own risk.

## Installation

> **Note:** Python >= 3.10 required

```bash
pip install openlinkedinapi
```

For the latest version from GitHub:

```bash
pip install git+https://github.com/your-repo/openlinkedinapi.git
```

## Quick Start

```python
from openlinkedinapi import Linkedin

# Authenticate with LinkedIn credentials
api = Linkedin('your-email@example.com', 'your-password')

# Get a profile
profile = api.get_profile('john-doe')

# Get profile contact info
contact_info = api.get_profile_contact_info('john-doe')

# Get first-degree connections
connections = api.get_profile_connections('123456789')
```

## Development

### Dependencies

- [Poetry](https://python-poetry.org/)
- A valid LinkedIn account (avoid using your personal account)

### Setup

Clone the repository and install dependencies:

```bash
git clone https://github.com/your-repo/openlinkedinapi.git
cd openlinkedinapi
poetry install
poetry self add poetry-plugin-dotenv
```

### Running Tests

```bash
poetry run pytest
```

## Troubleshooting

### LinkedIn Challenge Prompts

LinkedIn may require additional verification (e.g., CAPTCHA, 2FA). If you encounter login issues, try:

- Logging into LinkedIn manually.
- Using a different IP (VPN or proxy).
- Avoiding excessive requests in a short period.

## How It Works

This project interacts with LinkedIn’s internal API, **Voyager**, which powers LinkedIn’s web interface. By analyzing network requests, we extract structured data directly from LinkedIn pages without requiring an official API key.

## Contributing

We welcome contributions! Feel free to submit issues, feature requests, or pull requests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
