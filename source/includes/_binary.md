# Binary

## Markets#show

```shell
curl -u username:password http://home.inklingmarkets.com/markets/63356.xml
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<binary>
  <created-at type="datetime">2015-01-06T11:51:59-08:00</created-at>
  <ends-at type="datetime">2015-03-30T23:59:00-07:00</ends-at>
  <exclusive type="boolean">false</exclusive>
  <id type="integer">63356</id>
  <notes-count type="integer">1</notes-count>
  <opinion type="boolean">false</opinion>
  <resolved type="boolean">false</resolved>
  <resolved-at type="datetime" nil="true"></resolved-at>
  <scale type="float">1</scale>
  <slush nil="true"></slush>
  <starts-at type="datetime" nil="true"></starts-at>
  <trades-count type="integer">44</trades-count>
  <updated-at type="datetime">2015-02-16T09:02:46-08:00</updated-at>
  <name>Based upon closing prices during the quarter, will the S&amp;P 500 experience a 10% decline any time during the second quarter of 2015?</name>
  <description>...</description>
  <category-id type="integer">6</category-id>
  <widget-access-key>...</widget-access-key>
  <tags type="array">
    <tag>
      <id type="integer">1083</id>
      <name>500</name>
    </tag>
    <tag>
      <id type="integer">335</id>
      <name>market</name>
    </tag>
    <tag>
      <id type="integer">1082</id>
      <name>S&amp;P</name>
    </tag>
    <tag>
      <id type="integer">33</id>
      <name>stock</name>
    </tag>
    <tag>
      <id type="integer">536</id>
      <name>stocks</name>
    </tag>
  </tags>
  <closed type="boolean">false</closed>
  <membership><id type="integer">313004</id></membership>
  <stocks type="array">
    <stock>
      <created-at type="datetime">2015-01-06T11:51:59-08:00</created-at>
      <eod-price type="integer">3489</eod-price>
      <id type="integer">237335</id>
      <price type="integer">3489</price>
      <price-before-resolution type="integer">3489</price-before-resolution>
      <refunded type="boolean" nil="true"></refunded>
      <resolved-at type="datetime" nil="true"></resolved-at>
      <slush nil="true"></slush>
      <starting-price type="integer">5000</starting-price>
      <name>Yes</name>
      <description nil="true"></description>
      <symbol>YES</symbol>
      <closed type="boolean">false</closed>
    </stock>
  </stocks>
</binary>
```

This market is different from the first two. It's a **binary** market, so it only has one stock being traded. Conceptually, it is otherwise identical.

This market can be viewed <a href='http://home.inklingmarkets.com/markets/63356'>here.</a>

## Trades#list

```shell
curl -u username:password http://home.inklingmarkets.com/markets/63356/trades.xml
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<trades type="array">
  <sell>
    <id type="integer">4298923</id>
    <membership>
      <id type="integer">309326</id>
    </membership>
    <stock>
      <id type="integer">237335</id>
    </stock>
    <created-at type="datetime">2015-02-13T11:56:25-08:00</created-at>
    <quantity type="integer">50</quantity>
    <paid type="integer">-186008</paid>
    <reason></reason>
    <starting_price type="integer">3956</starting_price>
    <final_price type="integer">3489</final_price>
    <login>user1</login>
  </sell>
  <buy>
    <id type="integer">4298903</id>
    <membership>
      <id type="integer">270578</id>
    </membership>
    <stock>
      <id type="integer">237335</id>
    </stock>
    <created-at type="datetime">2015-02-13T10:27:10-08:00</created-at>
    <quantity type="integer">10</quantity>
    <paid type="integer">39080</paid>
    <reason></reason>
    <starting_price type="integer">3861</starting_price>
    <final_price type="integer">3956</final_price>
    <login>user2</login>
  </buy>
  <sell>
  ...
  </sell>
</trades>
```

Again, we see a list of trades made on the market here. The key difference is that the `stock id` is going to be the same on every single trade.

