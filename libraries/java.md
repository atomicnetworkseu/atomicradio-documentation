---
description: "A little help for all Java developers who would like to include our services in their projects, we are happy to support you! \U0001F4DA"
---

# Java

{% hint style="info" %}
More information and examples of how to integrate the library can be found [here](https://github.com/atomicnetworkseu/atomicradio-library),  
we hope you enjoy experimenting!
{% endhint %}

## Using with Maven

```markup
<repositories>
    <repository>
        <id>jitpack.io</id>
        <url>https://jitpack.io</url>
    </repository>
</repositories>

<dependency>
    <groupId>com.github.atomicnetworkseu</groupId>
    <artifactId>atomicradio-library</artifactId>
    <version>1.0.1</version>
</dependency>
```

## Using with Gradle

```text
allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
}

dependencies {
      implementation 'com.github.atomicnetworkseu:atomicradio-library:1.0.0'
}
```

## Example

The use of our library is very simple. Here you can see an example, more information can be found at Github [atomicnetworkseu/**atomicradio-library**](https://github.com/atomicnetworkseu/atomicradio-library).

```java
private AtomicClient atomicClient;

private void test() {
  this.atomicClient = new AtomicClient();

  Channel channel = this.atomicClient.getChannelOne();
  Channel.Song song = channel.getSong();

  System.out.println(MessageFormat.format("[{0}] {1} - {2}", channel.getName(), song.getArtist(), song.getTitle()));
}
```

