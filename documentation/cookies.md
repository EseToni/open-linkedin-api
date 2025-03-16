## Using Cookies for Authentication

You can also authenticate with LinkedIn using cookies instead of email and password. This can be helpful if you want to avoid logging in every time you use the API. To do this, you need to set the `li_at` and `JSESSIONID` cookies that are generated when you log into LinkedIn.

### Steps to Use Cookies

1. **Obtain Cookies**: You can extract the `li_at` and `JSESSIONID` cookies from your browser's Developer Tools while logged into LinkedIn.

2. **Set Cookies in Requests**: Use the `RequestsCookieJar` to store the cookies and pass them to the `Linkedin` API.

### Example

Here’s how to authenticate using cookies:

```python
from open_linkedin_api import Linkedin
from requests.cookies import RequestsCookieJar

# Create a RequestsCookieJar object to hold cookies
cookies = RequestsCookieJar()

# Set the cookies required for authentication
cookies.set('li_at', 'your_li_at_cookie_value', domain='www.linkedin.com')
cookies.set('JSESSIONID', 'ajax:your_jsessionid_cookie_value', domain='www.linkedin.com')

# Authenticate using the cookies
api = Linkedin(cookies=cookies, username='example@gmail.com')

# Fetch a LinkedIn profile using the authenticated session
profile = api.get_profile('public_identifier')
```
