# Scraping AWS Questions using SeleniumWire
Selenium is a browser automation tool. SeleniumWire allows for inspection into the network requests made from the browser.

The site www.lleicloud.com contains lots of AWS Certification questions.
In this notebook I scrape these questions from the browser request to their wordpress backend.

The [main page](https://www.lleicloud.com/index.php/aws-certified-solutions-architect-practice-tests/) shows all the links to the test pages.
To obtian the quiz URLS:
```
[...document.querySelectorAll('a')]
  .map(el => el.href)
  .filter(url => url.startsWith('https://www.lleicloud.com/index.php/aws-certified-solutions-architect-practice-tests'))
```

These were then saved to `quiz_urls.json` and further used in the Jupyter Notebook.

The questions are processed and saved as JSON objects in `questions/`.
