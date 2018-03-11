# Piwik Logs Analyzer

# Setup

## Python Kernel

No specific setup.

## Node.js Kernel

> https://github.com/notablemind/jupyter-nodejs

```bash
$ npm install
```

## Récupérer les stats

La meilleure manière d'exporter les stats est de passer par l'API :

https://stats.data.gouv.fr/?module=API&method=Live.getLastVisitsDetails&idSite=1

Références :
- [construire l'url](https://developer.matomo.org/guides/reporting-api-tutorial#build-the-url)
- [appeler la méthode](Live.getLastVisitsDetails)
- [l'idSite à utiliser](https://developer.matomo.org/api-reference/reporting-api)

La procédure d'installation pour convertir un notebook en script (grace à `jupyter nbconvert`)
```
sudo apt-get install python3
sudo apt-get install ipython
sudo apt-get install jupyter
jupyter nbconvert --to script 1.fetch_logs.ipynb
virtualenv -p /usr/bin/python3 py3env
source ./py3env/bin/activate
pip install requests
pip install pandas
mkdir ../raw_visit_logs/
python3 ./1.fetch_logs.py
```

Une autre possibilité est d'utiliser Anaconda 2.7
