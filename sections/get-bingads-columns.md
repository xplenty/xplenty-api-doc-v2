## Get BingAds columns.

### Description
Information about possible bingads columns.

### Input Parameters
Possible to add **report_type** which by default is ```KeywordPerformanceReport```.
Information about other report types [Bing documentation](https://msdn.microsoft.com/en-us/library/bing-ads-reporting-report-types.aspx)


### Request (Curl Call) Syntax
```shell
$ curl -X GET "/:account_id/api/connections/metadata/bingads/columns" \
  -H "Accept: application/vnd.xplenty+json; version=2" -H "Content-Type: application/json"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
{
  "data": [],
  "fields": [
    {
      "ACCOUNT_NAME": "string"
    },
    {
      "ACCOUNT_NUMBER": "string"
    },
    {
      "ACCOUNT_ID": "string"
    },
    {
      "TIME_PERIOD": "string"
    },
    {
      "CAMPAIGN_NAME": "string"
    },
    {
      "CAMPAIGN_ID": "string"
    },
    {
      "AD_GROUP_NAME": "string"
    },
    {
      "AD_GROUP_ID": "string"
    },
    {
      "KEYWORD": "string"
    },
    {
      "KEYWORD_ID": "string"
    },
    {
      "AD_ID": "string"
    },
    {
      "AD_TYPE": "string"
    },
    {
      "DESTINATION_URL": "string"
    },
    {
      "CURRENT_MAX_CPC": "string"
    },
    {
      "CURRENCY_CODE": "string"
    },
    {
      "DELIVERED_MATCH_TYPE": "string"
    },
    {
      "AD_DISTRIBUTION": "string"
    },
    {
      "IMPRESSIONS": "string"
    },
    {
      "CLICKS": "string"
    },
    {
      "CTR": "string"
    },
    {
      "AVERAGE_CPC": "string"
    },
    {
      "SPEND": "string"
    },
    {
      "AVERAGE_POSITION": "string"
    },
    {
      "CONVERSIONS": "string"
    },
    {
      "CONVERSION_RATE": "string"
    },
    {
      "COST_PER_CONVERSION": "string"
    },
    {
      "AVERAGE_CPM": "string"
    },
    {
      "PRICING_MODEL": "string"
    },
    {
      "BID_MATCH_TYPE": "string"
    },
    {
      "DEVICE_TYPE": "string"
    },
    {
      "QUALITY_SCORE": "string"
    },
    {
      "KEYWORD_RELEVANCE": "string"
    },
    {
      "LANDING_PAGE_RELEVANCE": "string"
    },
    {
      "LANDING_PAGE_USER_EXPERIENCE": "string"
    },
    {
      "LANGUAGE": "string"
    },
    {
      "HISTORIC_QUALITY_SCORE": "string"
    },
    {
      "HISTORIC_KEYWORD_RELEVANCE": "string"
    },
    {
      "HISTORIC_LANDING_PAGE_RELEVANCE": "string"
    },
    {
      "HISTORIC_LANDING_PAGE_USER_EXPERIENCE": "string"
    },
    {
      "KEYWORD_MATCH_TYPE_ID": "string"
    },
    {
      "QUALITY_IMPACT": "string"
    },
    {
      "BUSINESS_LISTING_ID": "string"
    },
    {
      "BUSINESS_LISTING_NAME": "string"
    },
    {
      "BUSINESS_CATEGORY_ID": "string"
    },
    {
      "BUSINESS_CATEGORY_NAME": "string"
    },
    {
      "CAMPAIGN_STATUS": "string"
    },
    {
      "ACCOUNT_STATUS": "string"
    },
    {
      "AD_GROUP_STATUS": "string"
    },
    {
      "KEYWORD_STATUS": "string"
    },
    {
      "NETWORK": "string"
    },
    {
      "TOP_VS_OTHER": "string"
    },
    {
      "DEVICE_OS": "string"
    },
    {
      "ASSISTS": "string"
    },
    {
      "EXTENDED_COST": "string"
    },
    {
      "REVENUE": "string"
    },
    {
      "RETURN_ON_AD_SPEND": "string"
    },
    {
      "COST_PER_ASSIST": "string"
    },
    {
      "REVENUE_PER_CONVERSION": "string"
    },
    {
      "REVENUE_PER_ASSIST": "string"
    },
    {
      "BOUNCE_RATE": "string"
    },
    {
      "TOTAL_VISITS": "string"
    },
    {
      "AVERAGE_PAGES_PER_VISIT": "string"
    },
    {
      "AVERAGE_DURATION_PER_VISIT": "string"
    }
  ]
}
```
