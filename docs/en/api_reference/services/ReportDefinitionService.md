# ReportDefinitionService
ReportDefinitionService is to get, add or delete report definition. <br>
Report defines report type, date range, and fields. <br>
It also provides operation to get available report fields for specific report type.

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/ReportDefinitionService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/ReportDefinitionService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### Service Overview
The following operations are provided:
- Get report definitions
- Add report definitions
- Delete report definitions
- Get report fields' information

[Maximum number of report definitions to be saved]
- Up to 30 definitions for a scheduled report can be added as a template for regular and proxy authentications combined.
- There is no upper limits to the number of report definitions for one-time report that is not saved as a template.<br>
Example：<br>
If you have already saved 20 report definitions as a report template for regular authentication, you can add a maximum of 10 definitions for proxy authentication.<br> 
　*If you wish to add more definitions though the upper saving limit is reached, delete some of the definitions you already saved.
 
[Note]
- All of the report definitions created using the same API account ID can be confirmed regardless of authentication method.

#### Operation
Explains the operations provided by ReportDefinitionService.

## get
Get information related to report definition.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
| selector | Req | [ReportDefinitionSelector](../data/ReportDefinitionSelector.md) | Report definition relate to the operations to apply. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountID>xxxxxxxxxxxxxxxxxx</ns1:apiAccountID>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:reportIds>200000001</ns1:reportIds>
        <ns1:reportIds>200000002</ns1:reportIds>
        <ns1:reportIds>200000003</ns1:reportIds>
        <ns1:paging>
          <ns1:startIndex>1</ns1:startIndex>
          <ns1:numberResults>500</ns1:numberResults>
        </ns1:paging>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields for normal case.

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionPage](../data/ReportDefinitionPage.md) | Entry of report definitions to be generated. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportDefinitionService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>ReportDefinitionPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportDefinition>
            <ns1:reportId>100000001</ns1:reportId>
            <ns1:reportName>Sample LANDING_PAGE_URL Report</ns1:reportName>
            <ns1:reportType>LANDING_PAGE_URL</ns1:reportType>
            <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
            <ns1:dateRange>
              <ns1:startDate>20160101</ns1:startDate>
              <ns1:endDate>20161231</ns1:endDate>
            </ns1:dateRange>
            <ns1:fields>CAMPAIGN_ID</ns1:fields>
            <ns1:fields>ADGROUP_ID</ns1:fields>
            <ns1:fields>CAMPAIGN_NAME</ns1:fields>
            <ns1:fields>ADGROUP_NAME</ns1:fields>
            <ns1:fields>COST</ns1:fields>
            <ns1:fields>IMPS</ns1:fields>
            <ns1:fields>CLICKS</ns1:fields>
            <ns1:fields>CLICK_RATE</ns1:fields>
            <ns1:fields>AVG_CPM</ns1:fields>
            <ns1:fields>AVG_CPC</ns1:fields>
            <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
            <ns1:fields>REVENUE</ns1:fields>
            <ns1:fields>UNIQUE_CONVERSION</ns1:fields>
            <ns1:fields>UNIQUE_CONVERSION_RATE</ns1:fields>
            <ns1:fields>REVENUE_UNIQUE_CONVERSION</ns1:fields>
            <ns1:fields>TRACKING_URL</ns1:fields>
            <ns1:fields>CUSTOM_PARAMETERS</ns1:fields>
            <ns1:fields>LANDING_PAGE_URL</ns1:fields>
            <ns1:fields>NETWORK</ns1:fields>
            <ns1:fields>DEVICE</ns1:fields>
            <ns1:fields>DAY</ns1:fields>
            <ns1:fields>DAY_OF_WEEK</ns1:fields>
            <ns1:fields>QUARTER</ns1:fields>
            <ns1:fields>YEAR</ns1:fields>
            <ns1:fields>MONTH</ns1:fields>
            <ns1:fields>MONTH_OF_YEAR</ns1:fields>
            <ns1:fields>WEEK</ns1:fields>
            <ns1:fields>OBJECT_OF_CONVERSION_TRACKING</ns1:fields>
            <ns1:fields>CONVERSION_NAME</ns1:fields>
            <ns1:sortFields>
              <ns1:type>ASC</ns1:type>
              <ns1:field>CLICKS</ns1:field>
            </ns1:sortFields>
            <ns1:filters>
              <ns1:field>TRACKING_URL</ns1:field>
              <ns1:operator>IN</ns1:operator>
              <ns1:value>http://yahoo.co.jp</ns1:value>
              <ns1:value>http://marketing.yahoo.co.jp</ns1:value>
              <ns1:value>http://promotionalads.yahoo.co.jp</ns1:value>
            </ns1:filters>
            <ns1:filters>
              <ns1:field>IMPS</ns1:field>
              <ns1:operator>GREATER_THAN</ns1:operator>
              <ns1:value>0</ns1:value>
            </ns1:filters>
            <ns1:filters>
              <ns1:field>CAMPAIGN_ID</ns1:field>
              <ns1:operator>IN</ns1:operator>
              <ns1:value>200000001</ns1:value>
              <ns1:value>200000002</ns1:value>
              <ns1:value>200000003</ns1:value>
              <ns1:value>200000003</ns1:value>
              <ns1:value>200000004</ns1:value>
              <ns1:value>200000005</ns1:value>
            </ns1:filters>
            <ns1:isTemplate>FALSE</ns1:isTemplate>
            <ns1:intervalType>SPECIFYDAY</ns1:intervalType>
            <ns1:specifyDay>28</ns1:specifyDay>
            <ns1:format>CSV</ns1:format>
            <ns1:encode>UTF-8</ns1:encode>
            <ns1:language>EN</ns1:language>
            <ns1:compress>NONE</ns1:compress>
            <ns1:includeZeroImpressions>FALSE</ns1:includeZeroImpressions>
            <ns1:includeDeleted>FALSE</ns1:includeDeleted>
          </ns1:reportDefinition>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getReportFields
Returns the available report fields for a given report type.

### Request
| Parameter | Restrictions | Data Type | Description | 
|---|---|---|---|
|reportType | Req | enum [ReportType](../data/ReportType.md) | Type of report. |

##### Request Sample (LANDING_PAGE_URL)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <soapenv:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
    </ns1:RequestHeader>
  </soapenv:Header>
  <soapenv:Body>
    <ns1:getReportFields>
      <ns1:reportType>LANDING_PAGE_URL</ns1:reportType>
    </ns1:getReportFields>
  </soapenv:Body>
</soapenv:Envelope>
```

### Response
Response Fields for normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionFieldValue](../data/ReportDefinitionFieldValue.md) | Entry of available report fields list. | 

##### Response Sample (LANDING_PAGE_URL)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>ReportDefinitionService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.2087</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getReportFieldsResponse>
         <ns1:rval>
            <ns1:operationSucceeded>true</ns1:operationSucceeded>
            <ns1:fields>
               <ns1:fieldName>CAMPAIGN_ID</ns1:fieldName>
               <ns1:displayFieldNameJA>キャンペーンID</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>CampaignID</ns1:displayFieldNameEN>
               <ns1:fieldType>LONG</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>ADGROUP_ID</ns1:fieldName>
               <ns1:displayFieldNameJA>広告グループID</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Ad Group ID</ns1:displayFieldNameEN>
               <ns1:fieldType>LONG</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>CAMPAIGN_NAME</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>CAMPAIGN_NAME</ns1:fieldName>
               <ns1:displayFieldNameJA>キャンペーン名</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Campaign Name</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_NAME</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>AD_NAME</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>ADGROUP_NAME</ns1:fieldName>
               <ns1:displayFieldNameJA>広告グループ名</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Ad Group Name</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>AD_NAME</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>TITLE</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>COST</ns1:fieldName>
               <ns1:displayFieldNameJA>コスト</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Cost</ns1:displayFieldNameEN>
               <ns1:fieldType>LONG</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>DESCRIPTION</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>COST</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>IMPS</ns1:fieldName>
               <ns1:displayFieldNameJA>インプレッション数</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Impressions</ns1:displayFieldNameEN>
               <ns1:fieldType>LONG</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>CLICKS</ns1:fieldName>
               <ns1:displayFieldNameJA>クリック数</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Clicks</ns1:displayFieldNameEN>
               <ns1:fieldType>LONG</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>CLICK_RATE</ns1:fieldName>
               <ns1:displayFieldNameJA>クリック率</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>CTR</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>AVG_CPM</ns1:fieldName>
               <ns1:displayFieldNameJA>平均CPM</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Avg. CPM</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>AVG_CPC</ns1:fieldName>
               <ns1:displayFieldNameJA>平均CPC</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Avg. CPC</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>AVG_DELIVER_RANK</ns1:fieldName>
               <ns1:displayFieldNameJA>平均掲載順位</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Avg. Position</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>REVENUE</ns1:fieldName>
               <ns1:displayFieldNameJA>合計売上金額</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Total Revenue</ns1:displayFieldNameEN>
               <ns1:fieldType>LONG</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>UNIQUE_CONVERSION</ns1:fieldName>
               <ns1:displayFieldNameJA>ユニークコンバージョン数</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Unique Conversions</ns1:displayFieldNameEN>
               <ns1:fieldType>LONG</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>UNIQUE_CONVERSION_RATE</ns1:fieldName>
               <ns1:displayFieldNameJA>ユニークコンバージョン率</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Unique Conversion Rate</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>REVENUE_UNIQUE_CONVERSION</ns1:fieldName>
               <ns1:displayFieldNameJA>売上/ユニークコンバージョン数</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Revenue / Unique Conversions</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>REVENUE_CONVERSION</ns1:fieldName>
               <ns1:displayFieldNameJA>売上/総コンバージョン数</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Revenue / Total Conversions</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>CONVERSION</ns1:fieldName>
               <ns1:displayFieldNameJA>総コンバージョン数</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Total Conversions</ns1:displayFieldNameEN>
               <ns1:fieldType>LONG</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>CONVERSION_RATE</ns1:fieldName>
               <ns1:displayFieldNameJA>総コンバージョン率</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Total Conversion Rate</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>COST_UNIQUE_CONVERSION</ns1:fieldName>
               <ns1:displayFieldNameJA>コスト/ユニークコンバージョン数</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Cost / Unique Conversions</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>CPA</ns1:fieldName>
               <ns1:displayFieldNameJA>コスト/総コンバージョン数</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Cost / Total Conversions</ns1:displayFieldNameEN>
               <ns1:fieldType>DOUBLE</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>TRACKING_URL</ns1:fieldName>
               <ns1:displayFieldNameJA>トラッキングURL</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Tracking URL</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>LANDING_PAGE_URL</ns1:fieldName>
               <ns1:displayFieldNameJA>最終リンク先URL</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Landing Page URL</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>NETWORK</ns1:fieldName>
               <ns1:displayFieldNameJA>広告掲載方式の指定</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Network</ns1:displayFieldNameEN>
               <ns1:fieldType>ENUM</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>DEVICE</ns1:fieldName>
               <ns1:displayFieldNameJA>デバイス</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Device</ns1:displayFieldNameEN>
               <ns1:fieldType>ENUM</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>DAY</ns1:fieldName>
               <ns1:displayFieldNameJA>日</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Day</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>DAY_OF_WEEK</ns1:fieldName>
               <ns1:displayFieldNameJA>曜日</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Day of week</ns1:displayFieldNameEN>
               <ns1:fieldType>ENUM</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>QUARTER</ns1:fieldName>
               <ns1:displayFieldNameJA>四半期</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Quarter</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>YEAR</ns1:fieldName>
               <ns1:displayFieldNameJA>年間</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Year</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>MONTH</ns1:fieldName>
               <ns1:displayFieldNameJA>毎月</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Month</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>MONTH_OF_YEAR</ns1:fieldName>
               <ns1:displayFieldNameJA>月</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Month of Year</ns1:displayFieldNameEN>
               <ns1:fieldType>ENUM</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>WEEK</ns1:fieldName>
               <ns1:displayFieldNameJA>毎週</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Week</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>OBJECT_OF_CONVERSION_TRACKING</ns1:fieldName>
               <ns1:displayFieldNameJA>コンバージョン測定の目的</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Objective of Conversion Tracking</ns1:displayFieldNameEN>
               <ns1:fieldType>ENUM</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
            <ns1:fields>
               <ns1:fieldName>CONVERSION_NAME</ns1:fieldName>
               <ns1:displayFieldNameJA>コンバージョン名</ns1:displayFieldNameJA>
               <ns1:displayFieldNameEN>Conversion Name</ns1:displayFieldNameEN>
               <ns1:fieldType>STRING</ns1:fieldType>
               <ns1:canSelect>true</ns1:canSelect>
               <ns1:canFilter>true</ns1:canFilter>
               <ns1:impossibleCombinationFields>CAMPAIGN_ID</ns1:impossibleCombinationFields>
               <ns1:impossibleCombinationFields>ADGROUP_ID</ns1:impossibleCombinationFields>
            </ns1:fields>
         </ns1:rval>
      </ns1:getReportFieldsResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (ADD)
Adds report definitions.

### Request
| Parameter | Restrictions | Data type | Description | 
|---|---|---|---|
| operation | Req | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | Report definitions and operation details to be processed. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
         <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:operand>
               <ns1:reportId>111111</ns1:reportId>
               <ns1:reportName>Sample LANDING_PAGE_URL Report</ns1:reportName>
               <ns1:reportType>LANDING_PAGE_URL</ns1:reportType>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20160101</ns1:startDate>
                  <ns1:endDate>20161231</ns1:endDate>
               </ns1:dateRange>
               <ns1:fields>CAMPAIGN_ID</ns1:fields>
               <ns1:fields>ADGROUP_ID</ns1:fields>
               <ns1:fields>CAMPAIGN_NAME</ns1:fields>
               <ns1:fields>ADGROUP_NAME</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>IMPS</ns1:fields>
               <ns1:fields>CLICKS</ns1:fields>
               <ns1:fields>CLICK_RATE</ns1:fields>
               <ns1:fields>AVG_CPM</ns1:fields>
               <ns1:fields>AVG_CPC</ns1:fields>
               <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
               <ns1:fields>REVENUE</ns1:fields>
               <ns1:fields>UNIQUE_CONVERSION</ns1:fields>
               <ns1:fields>UNIQUE_CONVERSION_RATE</ns1:fields>
               <ns1:fields>REVENUE_UNIQUE_CONVERSION</ns1:fields>
               <ns1:fields>TRACKING_URL</ns1:fields>
               <ns1:fields>CUSTOM_PARAMETERS</ns1:fields>
               <ns1:fields>LANDING_PAGE_URL</ns1:fields>
               <ns1:fields>NETWORK</ns1:fields>
               <ns1:fields>DEVICE</ns1:fields>
               <ns1:fields>DAY</ns1:fields>
               <ns1:fields>DAY_OF_WEEK</ns1:fields>
               <ns1:fields>QUARTER</ns1:fields>
               <ns1:fields>YEAR</ns1:fields>
               <ns1:fields>MONTH</ns1:fields>
               <ns1:fields>MONTH_OF_YEAR</ns1:fields>
               <ns1:fields>WEEK</ns1:fields>
               <ns1:fields>OBJECT_OF_CONVERSION_TRACKING</ns1:fields>
               <ns1:fields>CONVERSION_NAME</ns1:fields>
               <ns1:sortFields>
                  <ns1:type>ASC</ns1:type>
                  <ns1:field>CLICKS</ns1:field>
               </ns1:sortFields>
               <ns1:filters>
                  <ns1:field>TRACKING_URL</ns1:field>
                  <ns1:operator>IN</ns1:operator>
                  <ns1:value>http://yahoo.co.jp</ns1:value>
                  <ns1:value>http://marketing.yahoo.co.jp</ns1:value>
                  <ns1:value>http://promotionalads.yahoo.co.jp</ns1:value>
               </ns1:filters>
              <ns1:filters>
                  <ns1:field>CAMPAIGN_ID</ns1:field>
                  <ns1:operator>IN</ns1:operator>
                  <ns1:value>200000001</ns1:value>
                  <ns1:value>200000002</ns1:value>
                  <ns1:value>200000003</ns1:value>
                  <ns1:value>200000003</ns1:value>
                  <ns1:value>200000004</ns1:value>
                  <ns1:value>200000005</ns1:value>
               </ns1:filters>
               <ns1:isTemplate>FALSE</ns1:isTemplate>
               <ns1:intervalType>SPECIFYDAY</ns1:intervalType>
               <ns1:specifyDay>28</ns1:specifyDay>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:language>EN</ns1:language>
               <ns1:compress>NONE</ns1:compress>
               <ns1:includeZeroImpressions>TRUE</ns1:includeZeroImpressions>
               <ns1:includeDeleted>FALSE</ns1:includeDeleted>
            </ns1:operand>
        </ns1:operations>
     </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields for normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container for report definition including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>ReportDefinitionService</ns1:service>
         <ns1:remainingQuota>993</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.7982</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>111111</ns1:reportId>
                  <ns1:reportName>Sample LANDING_PAGE_URL Report</ns1:reportName>
                  <ns1:reportType>LANDING_PAGE_URL</ns1:reportType>
                  <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                  <ns1:dateRange>
                     <ns1:startDate>20160101</ns1:startDate>
                     <ns1:endDate>20161231</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:fields>CAMPAIGN_ID</ns1:fields>
                  <ns1:fields>ADGROUP_ID</ns1:fields>
                  <ns1:fields>CAMPAIGN_NAME</ns1:fields>
                  <ns1:fields>ADGROUP_NAME</ns1:fields>
                  <ns1:fields>COST</ns1:fields>
                  <ns1:fields>IMPS</ns1:fields>
                  <ns1:fields>CLICKS</ns1:fields>
                  <ns1:fields>CLICK_RATE</ns1:fields>
                  <ns1:fields>AVG_CPM</ns1:fields>
                  <ns1:fields>AVG_CPC</ns1:fields>
                  <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
                  <ns1:fields>REVENUE</ns1:fields>
                  <ns1:fields>UNIQUE_CONVERSION</ns1:fields>
                  <ns1:fields>UNIQUE_CONVERSION_RATE</ns1:fields>
                  <ns1:fields>REVENUE_UNIQUE_CONVERSION</ns1:fields>
                  <ns1:fields>TRACKING_URL</ns1:fields>
                  <ns1:fields>CUSTOM_PARAMETERS</ns1:fields>
                  <ns1:fields>LANDING_PAGE_URL</ns1:fields>
                  <ns1:fields>NETWORK</ns1:fields>
                  <ns1:fields>DEVICE</ns1:fields>
                  <ns1:fields>DAY</ns1:fields>
                  <ns1:fields>DAY_OF_WEEK</ns1:fields>
                  <ns1:fields>QUARTER</ns1:fields>
                  <ns1:fields>YEAR</ns1:fields>
                  <ns1:fields>MONTH</ns1:fields>
                  <ns1:fields>MONTH_OF_YEAR</ns1:fields>
                  <ns1:fields>WEEK</ns1:fields>
                  <ns1:fields>OBJECT_OF_CONVERSION_TRACKING</ns1:fields>
                  <ns1:fields>CONVERSION_NAME</ns1:fields>
                  <ns1:sortFields>
                     <ns1:type>ASC</ns1:type>
                     <ns1:field>CLICKS</ns1:field>
                  </ns1:sortFields>
                  <ns1:filters>
                     <ns1:field>TRACKING_URL</ns1:field>
                     <ns1:operator>IN</ns1:operator>
                     <ns1:value>http://yahoo.co.jp</ns1:value>
                     <ns1:value>http://marketing.yahoo.co.jp</ns1:value>
                     <ns1:value>http://promotionalads.yahoo.co.jp</ns1:value>
                  </ns1:filters>
                  <ns1:filters>
                     <ns1:field>IMPS</ns1:field>
                     <ns1:operator>GREATER_THAN</ns1:operator>
                     <ns1:value>0</ns1:value>
                  </ns1:filters>
                  <ns1:filters>
                     <ns1:field>CAMPAIGN_ID</ns1:field>
                     <ns1:operator>IN</ns1:operator>
                     <ns1:value>200000001</ns1:value>
                     <ns1:value>200000002</ns1:value>
                     <ns1:value>200000003</ns1:value>
                     <ns1:value>200000003</ns1:value>
                     <ns1:value>200000004</ns1:value>
                     <ns1:value>200000005</ns1:value>
                  </ns1:filters>
                  <ns1:isTemplate>FALSE</ns1:isTemplate>
                  <ns1:intervalType>SPECIFYDAY</ns1:intervalType>
                  <ns1:specifyDay>28</ns1:specifyDay>
                  <ns1:format>CSV</ns1:format>
                  <ns1:encode>UTF-8</ns1:encode>
                  <ns1:language>EN</ns1:language>
                  <ns1:compress>NONE</ns1:compress>
                  <ns1:includeZeroImpressions>TRUE</ns1:includeZeroImpressions>
                  <ns1:includeDeleted>FALSE</ns1:includeDeleted>
               </ns1:reportDefinition>
            </ns1:values>
        </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (REMOVE)
Removes report definitions.

### Request
| Parameter | Restrictions | Data type | Description | 
|---|---|---|---|
| operation | Req | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | Report definitions and operation details to be processed. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>100000001</ns1:accountId>
      <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
      <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>REMOVE</ns1:operator>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:operand>
          <ns1:reportId>123456789</ns1:reportId>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields for normal cases.

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container for report definition including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>ReportDefinitionService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:reportDefinition>
            <ns1:reportId>123456789</ns1:reportId>
          </ns1:reportDefinition>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
