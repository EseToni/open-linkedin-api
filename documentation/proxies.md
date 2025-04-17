## Using Proxies for Authentication

You can configure proxies to route your API requests through specific IP addresses. This can be useful if you want to avoid being rate-limited by LinkedIn or if you need to hide your IP address. The `open_linkedin_api` allows you to specify proxies in your requests.

### Setting Up Proxies

To use a proxy, you need to provide a dictionary containing the proxy settings in the format:

```python
{
    'http': 'http://your_proxy_address',
    'https': 'https://your_proxy_address'
}
```

You can pass this dictionary as a proxies parameter when authenticating with the LinkedIn API.

### Example

Here’s how to authenticate using cookies:

```python
from open_linkedin_api import Linkedin

# Define the proxy settings
proxies = {
    'http': 'http://your_proxy_address',
    'https': 'https://your_proxy_address'
}

# Authenticate using your LinkedIn credentials and the proxy settings
api = Linkedin(username='your_email@example.com', password='your_password', proxies=proxies)

# Fetch a LinkedIn profile
profile = api.get_profile('public_identifier')
```

# Notes on using proxies

- Proxy Authentication: Some proxies may require authentication. In that case, you can pass the credentials in the proxy URL, like this:

```python
proxies = {
    'http': 'http://username:password@your_proxy_address',
    'https': 'https://username:password@your_proxy_address'
}
```

# Using Proxies with Cookies

You can combine proxy usage with cookie-based authentication as well. Here’s how to do it:

```python
from open_linkedin_api import Linkedin
from requests.cookies import RequestsCookieJar

# Define the proxy settings
proxies = {
    'http': 'http://your_proxy_address',
    'https': 'https://your_proxy_address'
}

# Set the cookies required for authentication
cookies = RequestsCookieJar()
cookies.set('li_at', 'your_li_at_cookie_value', domain='www.linkedin.com')
cookies.set('JSESSIONID', 'ajax:your_jsessionid_cookie_value', domain='www.linkedin.com')

# Authenticate using cookies and proxy settings
# Make sure to pass an empty password when using cookies
api = Linkedin(username='example@gmail.com', password='', cookies=cookies, proxies=proxies)

# Fetch a LinkedIn profile
profile = api.get_profile('public_identifier')

```
