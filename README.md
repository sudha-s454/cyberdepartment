import requests

def fetch_google_homepage():
    url = 'http://www.google.com/'
    try:
        response = requests.get(url)
        response.raise_for_status()  # Raise an exception for HTTP errors (4xx or 5xx)
        html_content = response.text
        return html_content
    except requests.exceptions.RequestException as e:
        print(f'An error occurred: {e}')
        return None

# Function call to fetch and print Google homepage HTML
google_html = fetch_google_homepage()
if google_html:
    print(google_html[:1000])  # Print first 1000 characters of HTML content
