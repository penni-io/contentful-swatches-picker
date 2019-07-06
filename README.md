# About Swatches Picker

## Read more on contentful extensions
https://www.contentful.com/r/knowledgebase/ui-extensions-guide/


## How to install or update
`$ npm install -g contentful-cli`


### Setup credentials
`$ export SPACE=177udz22h888`
`$ export CONTENTFUL_MANAGEMENT_ACCESS_TOKEN=superSecretKey`


### Install new extension
`$ contentful extension create --space-id $SPACE`


### Update existing extension
`$ contentful extension update --space-id $SPACE --force`



### Testing from your local development environment
It is a common practice to develop and test extensions from your local environment to avoid redeploying it each time you need to preview your changes. To do that, first run your extension on a local server as follows:

`python -m SimpleHTTPServer 3000`

This will allow your extension to be available at http://localhost:3000/. Then, you may update your extension again by overriding its src via the following command:

`contentful extension update --space-id $SPACE --force --src http://localhost:3000/`

Note: since Contentful runs in an HTTPS environment, running this requires to disable temporarily the security checks from your web browser ("Load unsafe scripts" in Chrome for example).

Important: once finished with debugging, you should redeploy your extension without the src argument override to let it run from Contentful's servers or any other external hosting solution you chose. *NB. when hosting at Contenful the src property needs to be srcdoc in the extension file*