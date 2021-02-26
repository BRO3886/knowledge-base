# Random Stuff

## Colab

### Download Notebook as PDF (jupyter generated)
```bash
!apt-get install texlive texlive-xetex texlive-latex-extra pandoc
!pip install pypandoc

from google.colab import drive
drive.mount('/content/drive')

!cp drive/My Drive/Colab Notebooks/Untitled.ipynb ./

!jupyter nbconvert --to PDF "Untitled.ipynb"
```

## Selenium

`pip install selenium`
