# zProbe - Web Scraping and Data Extraction Module

zProbe is a Python module designed to scrape and extract various types of data from web pages. It provides functionalities to extract comments, metadata, URLs, emails, robots.txt, sitemap.xml, XML URLs, and WordPress login form parameters from a given URL.

## Features

- Extract comments from HTML source.
- Extract metadata (e.g., name and content attributes of meta tags).
- Extract URLs (links, image sources, script sources, etc.).
- Extract email addresses from HTML source.
- Extract content of robots.txt file.
- Extract URLs from a sitemap.xml file.
- Extract URLs from XML content conforming to the sitemap schema.
- Extract WordPress login form parameters.

## Installation

To use zProbe, you need to have Python 3.x installed. To install zProbe, simply clone this repository:

```bash
git clone https://www.github.com/edgerunner0x01/zProbe.git
```

## Dependencies

zProbe relies on the following Python packages:

* BeautifulSoup4
* Requests
* XML

Install the dependencies using pip:

```bash
pip install beautifulsoup4 requests
```

## Usage

Here's how you can use zProbe in your Python projects:

```python

import zProbe

# Initiate The zProbe Logger And the Log Level [ INFO,DEBUG,WARNING,ERROR,CRITICAL ]
zProbe.logger = zProbe.Log("INFO").logger

# Create a Target object with the URL you want to scrape
url = "https://example.com"
target = zProbe.Target(url)

# Extract comments from the HTML source
comments, success = target.Extract_Comments()
if success:
    print("Comments:", comments)
else:
    print("Failed to extract comments.")

# Extract metadata from the HTML source
metadata, success = target.Extract_MetaData()
if success:
    print("Metadata:", metadata)
else:
    print("Failed to extract metadata.")

# Extract URLs from the HTML source
urls, success = target.Extract_URLS()
if success:
    print("URLs:", urls)
else:
    print("Failed to extract URLs.")

# Extract email addresses from the HTML source
emails, success = target.Extract_Emails()
if success:
    print("Emails:", emails)
else:
    print("Failed to extract emails.")

# Extract content of robots.txt file
robots_content, status_code, success = target.Extract_Robots()
if success:
    print("Robots.txt Content:", robots_content)
else:
    print(f"Failed to retrieve robots.txt. Status code: {status_code}")

# Extract URLs from a sitemap.xml file
sitemap_urls, status_code, success = target.Extract_Sitemap()
if success:
    print("Sitemap URLs:", sitemap_urls)
else:
    print(f"Failed to retrieve sitemap.xml. Status code: {status_code}")

# Extract URLs from XML content conforming to the sitemap schema
xml_urls, status_code, success = target.Extract_XML_URLS()
if success:
    print("XML URLs:", xml_urls)
else:
    print(f"Failed to retrieve XML content. Status code: {status_code}")

# Extract WordPress login form parameters
wp_login_params, status_code, success = target.Extract_WPLOGIN()
if success:
    print("WordPress Login Form Parameters:", wp_login_params)
else:
    print(f"Failed to retrieve wp-login.php. Status code: {status_code}")
```

## License

This project is licensed under the MIT License - see the [LICENSE](https://opensource.org/licenses/MIT) file for details.

## Author

- [edgerunner0x01](https://www.github.com/edgerunner0x01)

## Contributing

Contributions are welcome! Please feel free to submit a pull request.
