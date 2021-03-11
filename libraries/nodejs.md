---
description: "A little help for all NodeJS developers who would like to include our services in their projects, we are happy to support you! \U0001F4DA"
---

# Node.JS

{% hint style="info" %}
More information and examples of how to integrate the library can be found [here](https://github.com/atomicnetworkseu/atomicradio-node), we hope you enjoy experimenting!
{% endhint %}

## Installation

```bash
npm install atomicradio
```

## Example

The use of our library is very simple. Here you can see an example, more information can be found at Github [atomicnetworkseu/**atomicradio-node**](https://github.com/atomicnetworkseu/atomicradio-node) _\*\*_or at NPM [atomicradio](https://www.npmjs.com/package/atomicradio).

```javascript
import AtomicAPI from "atomicradio";

const api = new AtomicAPI();

async function test() {
    let value = await api.getChannel("one").getHistory();
    console.log(value);
}
test();
```

