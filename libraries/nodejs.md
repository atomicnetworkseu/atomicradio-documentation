---
description: "The official documentation of atomicradio api, with all information about usage and upcoming maintenance. \U0001F36D"
---

# Node.JS

{% hint style="info" %}
You find our Java library on GitHub.  
[atomicnetworkseu/**atomicradio-node**](https://github.com/atomicnetworkseu/atomicradio-node)\*\*\*\*
{% endhint %}

## Installation

```bash
npm install atomicradio
```

## Example

The use of our library is very simple. Here you can see an example, more information can be found at Github [atomicnetworkseu/**atomicradio-node**](https://github.com/atomicnetworkseu/atomicradio-node) ****or at NPM [atomicradio](https://www.npmjs.com/package/atomicradio).

```javascript
import AtomicAPI from "atomicradio";

const api = new AtomicAPI();

async function test() {
    let value = await api.getChannel("one").getHistory();
    console.log(value);
}
test();
```


