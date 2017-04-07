# api documentation for  [network-address (v1.1.2)](https://github.com/mafintosh/network-address)  [![npm package](https://img.shields.io/npm/v/npmdoc-network-address.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-network-address) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-network-address.svg)](https://travis-ci.org/npmdoc/node-npmdoc-network-address)
#### get the local network address of your machine

[![NPM](https://nodei.co/npm/network-address.png?downloads=true)](https://www.npmjs.com/package/network-address)

[![apidoc](https://npmdoc.github.io/node-npmdoc-network-address/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-network-address_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-network-address/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-network-address/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-network-address/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Mathias Buus Madsen",
        "email": "mathiasbuus@gmail.com"
    },
    "bin": {
        "network-address": "./cli.js"
    },
    "bugs": {
        "url": "https://github.com/mafintosh/network-address/issues"
    },
    "dependencies": {},
    "description": "get the local network address of your machine",
    "devDependencies": {
        "standard": "^6.0.7",
        "tape": "^3.0.3"
    },
    "directories": {},
    "dist": {
        "shasum": "4aa7bfd43f03f0b81c9702b13d6a858ddb326f3e",
        "tarball": "https://registry.npmjs.org/network-address/-/network-address-1.1.2.tgz"
    },
    "gitHead": "a4704e359a9b90ea60a50076215e901b3b5c9c8e",
    "homepage": "https://github.com/mafintosh/network-address",
    "keywords": [
        "network",
        "address"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "mafintosh",
            "email": "mathiasbuus@gmail.com"
        }
    ],
    "name": "network-address",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/mafintosh/network-address.git"
    },
    "scripts": {
        "test": "standard && tape test.js"
    },
    "version": "1.1.2"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module network-address](#apidoc.module.network-address)
1.  [function <span class="apidocSignatureSpan">network-address.</span>ipv4 (iface)](#apidoc.element.network-address.ipv4)
1.  [function <span class="apidocSignatureSpan">network-address.</span>ipv6 (iface)](#apidoc.element.network-address.ipv6)



# <a name="apidoc.module.network-address"></a>[module network-address](#apidoc.module.network-address)

#### <a name="apidoc.element.network-address.ipv4"></a>[function <span class="apidocSignatureSpan">network-address.</span>ipv4 (iface)](#apidoc.element.network-address.ipv4)
- description and source-code
```javascript
function ipv4(iface) {
  var interfaces = os.networkInterfaces()
  if (iface) interfaces = reduceInterfaces(interfaces, iface)
  return pickInterface(interfaces, 'IPv4')
}
```
- example usage
```shell
...

tape('ipv4', function (t) {
  t.ok(/^\d+\.\d+\.\d+\.\d+$/.test(address()), 'looks like a ipv4')
  t.end()
})

tape('ipv4 #2', function (t) {
  t.ok(/^\d+\.\d+\.\d+\.\d+$/.test(address.ipv4()), 'looks like a ipv4')
  t.end()
})

tape('ipv4 #3', function (t) {
  t.ok(/^\d+\.\d+\.\d+\.\d+$/.test(address.ipv4('lo')), 'looks like a ipv4')
  t.end()
})
...
```

#### <a name="apidoc.element.network-address.ipv6"></a>[function <span class="apidocSignatureSpan">network-address.</span>ipv6 (iface)](#apidoc.element.network-address.ipv6)
- description and source-code
```javascript
function ipv6(iface) {
  var interfaces = os.networkInterfaces()
  if (iface) interfaces = reduceInterfaces(interfaces, iface)
  return pickInterface(interfaces, 'IPv6')
}
```
- example usage
```shell
...

it is easy to use

''' js
var address = require('network-address')

console.log(address())      // prints something like 192.168.3.102
console.log(address.ipv6()) // prints something like fc00::5137:ecb:55be:c2fc
'''

it is also available as a command line tool

'''
npm install -g network-address
'''
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
