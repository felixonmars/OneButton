# OneButton

OneButton is a one-click solution for ipa to finish all hackathon duties at once. Some features are mentioned in [hackpad]( https://g0v.hackpad.com/%25E7%25AC%25AC%25E5%25A3%25B9%25E6%25AC%25A1%25E5%259F%25BA%25E7%25A4%258E%25E6%259D%25BE#-2016612).

## Prerequisite

* `brew install phantomjs`
* `npm install -g casperjs`
* Update **config.js**
  * kktix's account, password 
  * hackpad's id, secret (each hackpad subdomain has differnet hackpad id, secret)
  * bit.ly's access token

#### Google OAuth

In order to use google drive api, please follow the guide from
[Google Drive APIs](https://developers.google.com/drive/v3/web/quickstart/nodejs#step_1_turn_on_the_api_name) to turn on google drive api and generate a client secret. Once a secret is downloaded, you need to update the path of your GAPI secret and where a token is to stored in config.js. After that, you have generate a token using:

```
$ node js/gapi-gen-token.js
```

## Run

You can fork and create event manually now:
*  `casperjs --ignore-ssl-errors=yes --ssl-protocol=tlsv1 --slug="EVENT_SLUG" --name="EVENT_NAME" --start_at="2016/06/24 09:00" --end_at="2016/06/24 18:00" js/kktix.js`

To create an event spreadsheet manually:
* `node js/spreadsheet.js EVENT_NUMBER EVENT_NAME`

Or run `node js/input.js` to create event in CUI.

## Contributors

* ipa (https://github.com/ipaaa) & ttcat (https://github.com/ttcat) for feature planning.
* hlb (https://github.com/hlb) for project structure.
* Lee (https://github.com/jessy1092) for hackpad and hackfolder integration.
* Jim (https://github.com/lemonlatte) for google spreadsheet creation
