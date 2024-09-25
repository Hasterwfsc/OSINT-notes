# Hunting Emails and Breached Data

## theHarvester

<figure><img src="../../.gitbook/assets/image (155).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>



### Running theHarvester&#x20;

```
theHarvester -d <domain name> -b all 
```

\-b is the source that we are using (search engines)&#x20;

<figure><img src="../../.gitbook/assets/image (157).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
If we search too much, we may get blocked by google&#x20;
{% endhint %}



We can control our search to using a single search engine with lesser results&#x20;

```
theHarvester -d tesla.com -b yahoo -l 100 
```

\-l is the total number of search results&#x20;

<figure><img src="../../.gitbook/assets/image (174).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Breachparse and H8Mail and not mandatory
{% endhint %}

## Breachparse

refer to PEH breah parse enumeration&#x20;



## H8Mail

already built in into OSINT vim&#x20;

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

#### Functions that require an api key&#x20;

key icon shows that u need an api key for that functionality&#x20;

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

#### Example usage&#x20;

```
h8mail -t shark@tesla.com 
```

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>
