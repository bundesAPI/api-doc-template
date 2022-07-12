# [_TEMPLATE_]

## Quickstart

- Add openAPI spec inside _openapi.yml_
- Update _index.html_ (insert the api-name in the title)
- Update _generator_config.yaml_ (Update all values surrounded with <>)
- Update the url in _CNAME_ once the api has its own subdomain
- Replace this README


## Add Library to deutschland package

Fork the [deutschland](https://github.com/bundesAPI/deutschland) package:

1. In the `pyproject.toml` of the [deutschland-package](https://github.com/bundesAPI/deutschland/blob/main/pyproject.toml) add a entry in the dependency section. The values for `<NAME>` and `<VERSION>` must match with the values in `generator_config.yaml`
   For Example: 

   ```de-`<NAME>`  = {version= "^`<VERSION>`", optional = true}```
2. Under the ```[tool.poetry.extras]``` section add the following
   ```<NAME>`  =["de-`<NAME>`"]```
    
   Also add de-name in the all list:
```
    all = ["de-bundestag-lobbyregister","de-dip-bundestag","de-pegel-online","de-ausbildungssuche",
    "de-berufssprachkurssuche","de-coachingangebote","de-dip-bundestag","de-entgeltatlas",
    "de-hochwasserzentralen","de-pflanzenschutzmittelzulassung","de-studiensuche",
    "de-tagesschau", "de-weiterbildungssuche","de-feiertage",...,"de-`<NAME>`"]
```

3. Add apis into [test_imports.py](https://github.com/bundesAPI/deutschland/blob/main/tests/test_imports.py)
    ```
    from deutschland.<NAME>.apis import DefaultApi
   ```

4. Open a [merge request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).