![license](https://img.shields.io/github/license/hhk7734/docusaurus-plugin-google-adsense)
![node](https://img.shields.io/github/package-json/v/hhk7734/docusaurus-plugin-google-adsense?sort=semver)
![language](https://img.shields.io/github/languages/top/hhk7734/docusaurus-plugin-google-adsense)

# docusaurus-plugin-google-adsense

This plugin is for Docusaurus v2.

## Usage

Run `yarn add -D docusaurus-plugin-google-adsense`.

Modify `docusaurus.config.js`:
```javascript
module.exports = {
  //...
  themeConfig: {
    //...
    googleAdsense: {
      dataAdClient: "ca-pub-xxxxxxxxxx",
    },
  },

  plugins: [
    'docusaurus-plugin-google-adsense',
  ],
};
```
