# Open LinkedIn API - Basics

This document provides a basic overview of how to use the `open_linkedin_api` to interact with LinkedIn's data. The `open_linkedin_api` is a Python library that allows you to access LinkedIn profiles, contact information, and connections programmatically.

## Installation

To use the `open_linkedin_api`, you need to install it first. You can do this using pip:

```bash
pip install open_linkedin_api
```

Importing the Library
To start using the library, you need to import it into your Python script:

```python
from open_linkedin_api import Linkedin
```

# Authenticate using your LinkedIn credentials

Authentication
To authenticate with LinkedIn, you need to provide your LinkedIn account credentials (email and password). The library will handle the login process for you.

```python
api = Linkedin('your_email@example.com', 'your_password')
```

# Fetch a LinkedIn profile

Fetching a Profile
You can fetch a LinkedIn profile using the get_profile method. You need to provide the public identifier (username) of the profile you want to fetch.

```python
profile = api.get_profile('public_identifier')
```

# Fetch contact information of a LinkedIn profile

Fetching Contact Information
To fetch the contact information of a LinkedIn profile, use the get_profile_contact_info method.

```python
contact_info = api.get_profile_contact_info('public_identifier')
```

# Fetch 1st-degree connections of a LinkedIn profile

Fetching Connections
You can also fetch the 1st-degree connections of a given LinkedIn profile using the get_profile_connections method. You need to provide the profile ID of the user whose connections you want to fetch.

```python
connections = api.get_profile_connections('profile_id')
```
