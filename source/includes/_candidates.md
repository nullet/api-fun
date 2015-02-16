# Presidential Candidate Announcements

## Markets#show

> If we want to see the information about this market, the API call is very simple.

```shell
curl -u username:password http://home.inklingmarkets.com/markets/58931.xml
```

> This will return everything you need to know about the market:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<options>
  <created-at type="datetime">2013-10-27T15:11:33-07:00</created-at>
  <ends-at type="datetime">2015-06-29T15:11:00-07:00</ends-at>
  <exclusive type="boolean">false</exclusive>
  <id type="integer">58931</id>
  <notes-count type="integer">5</notes-count>
  <opinion type="boolean">false</opinion>
  <resolved type="boolean">false</resolved>
  <resolved-at type="datetime" nil="true"></resolved-at>
  <scale type="float">1</scale>
  <slush nil="true"></slush>
  <starts-at type="datetime">2013-10-27T15:11:00-07:00</starts-at>
  <trades-count type="integer">481</trades-count>
  <updated-at type="datetime">2015-02-16T10:48:59-08:00</updated-at>
  <name>Which of these candidates will formally announce a U.S. presidential candidacy by July 1, 2015, for the 2016 race?</name>
  <description>...</description>
  <category-id type="integer">2</category-id>
  <widget-access-key>...</widget-access-key>
  <tags type="array">
    <tag>
      <id type="integer">794</id>
      <name>2016</name>
    </tag>
    <tag>
      <id type="integer">13831</id>
      <name>2016elections</name>
    </tag>
    <tag>
      <id type="integer">269</id>
      <name>Elections</name>
    </tag>
    <tag>
      <id type="integer">268</id>
      <name>President</name>
    </tag>
  </tags>
  <closed type="boolean">false</closed>
  <membership><id type="integer">19649</id></membership>
  <stocks type="array">
    <stock>
      <created-at type="datetime">2013-10-27T15:18:42-07:00</created-at>
      <eod-price type="integer">9669</eod-price>
      <id type="integer">218304</id>
      <price type="integer">9669</price>
      <price-before-resolution type="integer">9669</price-before-resolution>
      <refunded type="boolean" nil="true"></refunded>
      <resolved-at type="datetime" nil="true"></resolved-at>
      <slush nil="true"></slush>
      <starting-price type="integer">5000</starting-price>
      <name>Jeb Bush</name>
      <description></description>
      <symbol>JB2</symbol>
      <closed type="boolean">false</closed>
    </stock>
    <stock>
      <created-at type="datetime">2013-10-27T15:17:23-07:00</created-at>
      <eod-price type="integer">9003</eod-price>
      <id type="integer">218301</id>
      <price type="integer">9003</price>
      <price-before-resolution type="integer">9003</price-before-resolution>
      <refunded type="boolean" nil="true"></refunded>
      <resolved-at type="datetime" nil="true"></resolved-at>
      <slush nil="true"></slush>
      <starting-price type="integer">5000</starting-price>
      <name>Scott Walker</name>
      <description></description>
      <symbol>SW</symbol>
      <closed type="boolean">false</closed>
    </stock>
    <stock>
    ...
    </stock>
  </stocks>
</options>
```


The first market we'll look at is one regarding who will announce their candidacy for President by July of 2015. This is an **options** market with about 20 different stocks to trade (each of which represents a potential candidate).

The market itself can be found <a href="http://home.inklingmarkets.com/markets/58931">here.</a>

<aside class='notice'>There are several fields that aren't explained here. For more detailed explanations of what each field denotes, please <a href='http://developers.inklingmarkets.com/#list'>see this section of our API docs.</a></aside>

In the XML we get back from our API call here, we see the market (denoted by the `options` label) and all of the basic data we might want to know about it. Beneath the general info, we can see information about each stock in that market, including `starting-price` and the current `price` attributes.

The `price-before-resolution` will be the final trading price of the stock before it is closed. In the case of this market, the price will either be 0 (false) or 10000 (true) for each stock once the answer is determined.

None of this info gives us a history of the fluctations in the market, however. To do that, we can take a look at the trading history of the market.


## Trades#list

> Here's the call we need to make for trade data:

```shell
curl -u username:password http://home.inklingmarkets.com/markets/58931/trades.xml
```

> And we'll get the details of every trade:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<trades type="array">
  <sell>
    <id type="integer">4299459</id>
    <membership>
      <id type="integer">270823</id>
    </membership>
    <stock>
      <id type="integer">218311</id>
    </stock>
    <created-at type="datetime">2015-02-16T09:13:09-08:00</created-at>
    <quantity type="integer">140</quantity>
    <paid type="integer">-25493</paid>
    <reason></reason>
    <starting_price type="integer">237</starting_price>
    <final_price type="integer">137</final_price>
    <login>user1</login>
  </sell>
  <buy>
    <id type="integer">4298937</id>
    <membership>
      <id type="integer">235034</id>
    </membership>
    <stock>
      <id type="integer">218301</id>
    </stock>
    <created-at type="datetime">2015-02-13T13:24:11-08:00</created-at>
    <quantity type="integer">150</quantity>
    <paid type="integer">1302957</paid>
    <reason></reason>
    <starting_price type="integer">8321</starting_price>
    <final_price type="integer">9003</final_price>
    <login>user2</login>
  </buy>
</trades>
```

Let's say we'd like to see any and all trades made on the market. This call allows us to do that - which means we can view the price history of all stocks on the market.

The data is returned with the most recent trades at the top of the list.

We can also make calls for a specific user's trade history. All users can look at their own trade history via the API. That query would look like this:

`curl -u username:password http://home.inklingmarkets.com/trades.xml`

Admins, however, can view the trade history for any given user, or for all users:

`curl -u username:password http://home.inklingmarkets.com/:membership_id/trades.xml`

If we wanted to see everyone's trades all at once, we would just replace `:membership_id` with `all`.

## Memberships#show

```shell
curl -u username:password http://home.inklingmarkets.com/memberships/314825.xml
```

> This gives all the info on that user.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<membership>
  <id type="integer">314825</id>
  <portfolio type="integer">1761252</portfolio>
  <worth type="integer">6243740</worth>
  <available-balance type="integer">1812488</available-balance>
  <user>
    <active type="boolean">true</active>
    <first-name>firstname</first-name>
    <id type="integer">314898</id>
    <last-name>lastname</last-name>
    <login>truckasaurus</login>
    <push-closing-market-alerts type="boolean">true</push-closing-market-alerts>
    <push-new-comment-alerts type="boolean">true</push-new-comment-alerts>
    <push-new-market-alerts type="boolean">true</push-new-market-alerts>
    <push-price-alerts type="boolean">true</push-price-alerts>
    <email>email</email>
  </user>
  <balance type="integer">4482488</balance>
</membership>
```

Let's say we want to find out the worth of a particular user. We can do that via the memberships endpoint.

This call will allow an admin to look at any user's information.  The most salient data would typically be their `worth` and `available-balance` fields.