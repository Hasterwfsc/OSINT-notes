---
description: Twint is utilised to scrape twitter information
---

# Social Media OSINT

Twint - [https://github.com/twintproject/twint](https://github.com/twintproject/twint) (built in) (no longer can be used)

Twint does not rely on twitter api, this means that it does not have the 3200 most recent tweets limitation&#x20;

<figure><img src="../../.gitbook/assets/image (132).png" alt=""><figcaption></figcaption></figure>

We need to upgrade twint

```
pip3 install --upgrade -e git+https://github.com/twintproject/twint.git@origin/master#egg=twint
```

```
pip3 install --upgrade aiohttp_socks
```

\


#### Example usage&#x20;

```
twint -u cybermentor 
```

```
twint -u <username> 
```

<figure><img src="../../.gitbook/assets/image (133).png" alt=""><figcaption></figcaption></figure>

\-s will target tweets that have the specified keyword&#x20;

```
twint -u cybermentor -s dog
```

<figure><img src="../../.gitbook/assets/image (134).png" alt=""><figcaption></figcaption></figure>

### For more information u can refer to the below link&#x20;

Twint - [https://github.com/twintproject/twint](https://github.com/twintproject/twint) (built in)
