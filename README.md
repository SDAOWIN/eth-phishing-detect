# eth-phishing-detect

Utility for detecting phishing domains targeting Ethereum users.

## Blocking Policy

We are constantly evolving the ideal policy that guides this list, but a few clearly defined rules have emerged. We will be quick and decisive to block websites that:
- Impersonate other known and established sites.
- Use their interfaces to collect user signing keys (especially cryptocurrency keys) and send them back to home servers.

There are other grounds for blocking, and we will ultimately do our best to keep our users safe.

### basic usage

```js
const checkForPhishing = require('eth-phishing-detect')

const value = checkForPhishing('etherclassicwallet.com')
console.log(value) // true
```

### advanced usage

```js
const PhishingDetector = require('eth-phishing-detect/src/detector')

const detector = new PhishingDetector({ whitelist, blacklist, fuzzylist, tolerance })
const value = detector.check('etherclassicwallet.com')
console.log(value)
/*
{
  type: "blacklist",
  result: true,
}
*/
```
