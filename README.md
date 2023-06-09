# IRE 2023: Web scraping with Python

### 🔗 [bit.ly/ire23-scraping](https://bit.ly/ire23-scraping)

This repo contains materials for a half-day workshop at the IRE 2023 conference in Orlando on using Python to scrape data from websites.

The session is scheduled for Saturday, June 24, from 9 a.m. – 12:30 p.m. in room `Coral A` on the first floor.

### First step

Open the Terminal application. Copy and paste this text into the Terminal and hit enter:

```bash
cd ~/Desktop/hands_on_classes/20230624-saturday-web-scraping-with-python-pre-registered-attendees-only-1012 && source env/bin/activate
```

### Course outline
- Do you really need to scrape this?
- Process overview:
    - Fetch, parse, write data to file
    - Some best practices
        - Make sure you feel OK about whether your scraping project is (legally, ethically, etc.) allowable
        - Don't DDOS your target server
        - When feasible, save copies of pages locally, then scrape from those files
        - [Rotate user-agent strings](https://www.useragents.me/) and other headers if necessary to avoid bot detection
- Using your favorite brower's inspection tools to deconstruct the target page(s)
    - See if the data is delivered via undocumented API to the page in a ready-to-use format, such as JSON ([example 1](https://sdlegislature.gov/Session/Archived), [example 2](https://www.britishmuseum.org/collection)) -- [Postman](https://www.postman.com) or similar software is handy for testing out API calls
    - Is the HTML part of the actual page structure, or is it built on the fly when the page loads? ([example](https://rrctx.force.com/s/complaints))
    - Can you open the URL directly in an incognito window and get to the same content, or does the page require a specific state to deliver the content (via search navigation, etc.)? ([example](https://rrctx.force.com/s/ietrs-complaint/a0ct0000000mOmhAAE/complaint0000000008))
    - Are there [URL query parameters](https://en.wikipedia.org/wiki/Query_string) that you can tweak to get different results? ([example](https://www.worksafe.qld.gov.au/news-and-events/alerts))
- Choose tools that the most sense for your target page(s) -- a few popular options:
    - [`requests`](https://requests.readthedocs.io/en/latest/) and [`BeautifulSoup`](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
    - [`playwright`](https://playwright.dev/python) (optionally using `BeautifulSoup` for the HTML parsing)
    - [`scrapy`](https://scrapy.org/) for larger spidering/crawling tasks
- Overview of our Python setup today
    - Activating the virtual environment
    - Jupyter notebooks
    - Running `.py` files from the command line
- Our projects today:
    - [Texas burn instructors](tx-burn-instructors)
    - [U.S. Senate press gallery](us-senate-press-gallery)
    - [IRE board members](ire-board)
    - [South Dakota lobbyist registration data](sd-lobbyists)
    - [Texas Railroad Commission complaints](tx-railroad-commission)


### Need to scrape on a timer?
- [Try GitHub Actions](https://palewi.re/docs/first-github-scraper)
- Use your computer's scheduler tools
- Drop your script on a remote server with a [`crontab` configuration](https://en.wikipedia.org/wiki/Cron)
- [Switch to Google Apps Script and set up time-based triggers](https://developers.google.com/apps-script/guides/triggers)


### Running this code at home
- Install Python, if you haven't already ([here's our guide](https://docs.google.com/document/d/1cYmpfZEZ8r-09Q6Go917cKVcQk_d0P61gm0q8DAdIdg/edit))
- Clone or download this repo
- `cd` into the repo directory and install the requirements, preferably into a virtual environment using your tooling of choice: `pip install -r requirements.txt`
- `playwright install`
- `jupyter notebook` to launch the notebook server
