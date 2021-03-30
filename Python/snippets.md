# Random Code Snippets
- [Random Code Snippets](#random-code-snippets)
    - [Download Notebook as PDF (jupyter generated)](#download-notebook-as-pdf-jupyter-generated)
    - [Bulk Archive Repos on GitHub](#bulk-archive-repos-on-github)

### Download Notebook as PDF (jupyter generated)
```bash
!apt-get install texlive texlive-xetex texlive-latex-extra pandoc
!pip install pypandoc

from google.colab import drive
drive.mount('/content/drive')

!cp drive/My Drive/Colab Notebooks/Untitled.ipynb ./

!jupyter nbconvert --to PDF "Untitled.ipynb"
```

### Bulk Archive Repos on GitHub
```python
import requests as r
import json
import os

# edit the below variables as per your need
org_name="GDGVIT"
created="<2018-01-01"
# create a personal access token on github
token = ""

rootURL = "https://api.github.com"
searchURL = f"{rootURL}/search/repositories?q=org:{org_name}+created:{created}&per_page=100"
testURL=f"{rootURL}/user"

# test for auth
test_resp = r.get(testURL, headers={"Authorization":f"token {token}"})
print(test_resp.json()["login"])

# get repos from search URL
search = r.get(searchURL, headers={"Authorization":f"token {token}"})
search_resp = search.json()

# cleaning
repos = search_resp['items']

# store names to be deleted
repos_tbd = []

# conditionally adding names to repos_tbd
for repo in repos:
  if repo["stargazers_count"]<5 and repo["archived"]==False:
    repos_tbd.append(repo["full_name"])
    print(repo["html_url"],repo["created_at"],repo["updated_at"])

# payload which sets archived as true
payload = json.dumps({
  "archived": True
})

# auth token header
headers = {
  'Authorization': f'token {token}',
  'Content-Type': 'application/json',
}

# for each repo PATCH it to archive
for name in repos_tbd:
  url = f"https://api.github.com/repos/{name}"
  print(url)
  response = r.request("PATCH", url, headers=headers, data=payload)
  print(response.status_code, response.text)
```
