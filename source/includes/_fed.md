# Fed Funds Rate

## Markets#show

```shell
curl -u username:password http://home.inklingmarkets.com/markets/62672.xml
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<dateranges>
  <created-at type="datetime">2014-10-14T04:58:44-07:00</created-at>
  <ends-at type="datetime">2015-03-30T23:59:00-07:00</ends-at>
  <exclusive type="boolean">false</exclusive>
  <id type="integer">62672</id>
  <notes-count type="integer">3</notes-count>
  <opinion type="boolean">false</opinion>
  <resolved type="boolean">false</resolved>
  <resolved-at type="datetime" nil="true"></resolved-at>
  <scale type="float">1</scale>
  <slush nil="true"></slush>
  <starts-at type="datetime" nil="true"></starts-at>
  <trades-count type="integer">82</trades-count>
  <updated-at type="datetime">2015-02-16T10:52:06-08:00</updated-at>
  <name>In which quarter will the U.S. Federal Reserve first increase its target for the Fed Funds Rate?</name>
  <description>...</description>
  <category-id type="integer">6</category-id>
  <widget-access-key>...</widget-access-key>
  <tags type="array">
    <tag>
      <id type="integer">1088</id>
      <name>fed</name>
    </tag>
    <tag>
      <id type="integer">154</id>
      <name>Funds</name>
    </tag>
    <tag>
      <id type="integer">1090</id>
      <name>interest</name>
    </tag>
    <tag>
      <id type="integer">1122</id>
      <name>Rates</name>
    </tag>
  </tags>
  <closed type="boolean">false</closed>
  <membership><id type="integer">313004</id></membership>
  <stocks type="array">
    <stock>
      <created-at type="datetime">2014-10-14T05:00:07-07:00</created-at>
      <eod-price type="integer">1938</eod-price>
      <id type="integer">233922</id>
      <price type="integer">1938</price>
      <price-before-resolution type="integer">1938</price-before-resolution>
      <refunded type="boolean" nil="true"></refunded>
      <resolved-at type="datetime" nil="true"></resolved-at>
      <slush nil="true"></slush>
      <starting-price type="integer">1050</starting-price>
      <name>3rd 2015</name>
      <description></description>
      <symbol>32</symbol>
      <closed type="boolean">false</closed>
    </stock>
    <stock>
      <created-at type="datetime">2014-10-14T05:00:32-07:00</created-at>
      <eod-price type="integer">1869</eod-price>
      <id type="integer">233923</id>
      <price type="integer">1869</price>
      <price-before-resolution type="integer">1869</price-before-resolution>
      <refunded type="boolean" nil="true"></refunded>
      <resolved-at type="datetime" nil="true"></resolved-at>
      <slush nil="true"></slush>
      <starting-price type="integer">1050</starting-price>
      <name>4th 2015</name>
      <description></description>
      <symbol>422</symbol>
      <closed type="boolean">false</closed>
    </stock>
    <stock>
    ...
    </stock>
  </stocks>
</dateranges>
```

The concept for this market is the same - we're just looking at a different type, in this case **dateranges**.

The market in question can be seen <a href='http://home.inklingmarkets.com/markets/62672'>here.</a>


## Trades#list

```shell
curl -u username:password http://home.inklingmarkets.com/markets/58931/trades.xml
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<trades type="array">
  <sell>
    <id type="integer">4298550</id>
    <membership>
      <id type="integer">270578</id>
    </membership>
    <stock>
      <id type="integer">233922</id>
    </stock>
    <created-at type="datetime">2015-02-12T07:26:43-08:00</created-at>
    <quantity type="integer">10</quantity>
    <paid type="integer">-19693</paid>
    <reason></reason>
    <starting_price type="integer">2001</starting_price>
    <final_price type="integer">1938</final_price>
    <login>user1</login>
  </sell>
  <sell>
    <id type="integer">4298549</id>
    <membership>
      <id type="integer">270578</id>
    </membership>
    <stock>
      <id type="integer">233923</id>
    </stock>
    <created-at type="datetime">2015-02-12T07:26:22-08:00</created-at>
    <quantity type="integer">10</quantity>
    <paid type="integer">-18851</paid>
    <reason></reason>
    <starting_price type="integer">1915</starting_price>
    <final_price type="integer">1855</final_price>
    <login>user1</login>
  </sell>
  <buy>
  ...
  </buy>
</trades>
```

As with the market above, we see a list of the trades made on the market, along with information on who made those trades.