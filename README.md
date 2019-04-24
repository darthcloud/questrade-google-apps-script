# questrade-google-apps-script
Class to interface with questrade's web API via Google Apps Scripts. I developed this to pull positions/balances into a Google Sheet in order to help balance/manage my portfolio.

## Install
Install clasp globally with npm:
`npm i -g clasp`

Install typescript and apps script ts types:
`npm install`

## Deploy
In `.clasp.json` edit the script ID to contain the ID of your script created within your google sheet (Can be found in File > Project Properties > Info Tab):
```
{
  "scriptId": "<your-script-id-here>",
  "rootDir": "src/",
  "fileExtension": "ts"
}
```

With the same script ID set the redirect address of your Questrade Personal Apps to:
`https://script.google.com/macros/d/{SCRIPT ID}/usercallback`
Make sure you click the '+' sign after entering for questrade to save the callback.

Login to clasp:
`clasp login` or `sudo clasp login`

Push to remote project:
`clasp push`

Open the project:
`clasp open`

On your questrade personal app beside the app name, hit the dropdown arrow menu to view the consumer key.
Navigate to script properties (File > Project Properties > Script Properties) and add your consumer key using the following key value pair:
`consumerKey <QUESTRADE_PERSONAL_APP_CONSUMER_KEY>`

A menu named Questrade will be added within a few seconds of opening the sheet. Select option `Pull` to get data from Questrade.
If no valid credential is stored, a link to authorize the script will appear on the side. Once authorize use `Questrade->Pull` again.
