![license](https://img.shields.io/github/license/hhk7734/docusaurus-plugin-google-adsense)
![node](https://img.shields.io/github/package-json/v/hhk7734/docusaurus-plugin-google-adsense?sort=semver)
![language](https://img.shields.io/github/languages/top/hhk7734/docusaurus-plugin-google-adsense)

# docusaurus-plugin-google-adsense

This plugin is for Docusaurus v2 and v3.

## Installation

```shell
yarn add docusaurus-plugin-google-adsense
```

## Usage

Modify `docusaurus.config.ts`:

```ts
import type { Config } from "@docusaurus/types";

const config: Config = {
  plugins: ['docusaurus-plugin-google-adsense'],

  themeConfig: {
    googleAdsense: {
      dataAdClient: 'ca-pub-xxxxxxxxxx',
    },
  },
};

export default config;
```

[Swizzle](https://docusaurus.io/docs/swizzling) `DocItem/Content`

```shell
yarn swizzle @docusaurus/theme-classic DocItem/Content --wrap
```

Modify `src/theme/DocItem/Content/index.tsx` like this:

```tsx
import React from "react";
import Content from "@theme-original/DocItem/Content";
import type ContentType from "@theme/DocItem/Content";
import type { WrapperProps } from "@docusaurus/types";

import AdSense from "react-adsense";

type Props = WrapperProps<typeof ContentType>;

export default function ContentWrapper(props: Props): JSX.Element {
  return (
    <>
      <div>
        <AdSense.Google
          client="ca-pub-xxxxxxxxxx"
          slot="yyyyyyyyyy"
          style={{ display: "block" }}
          format="auto"
          responsive="true"
        />
      </div>

      <br />

      <Content {...props} />

      <br />

      <div>
        <AdSense.Google
          client="ca-pub-xxxxxxxxxx"
          slot="yyyyyyyyyy"
          style={{ display: "block" }}
          format="auto"
          responsive="true"
        />
      </div>
    </>
  );
}
```

## Publish

```shell
npm login
```

```shell
npm publish
```
