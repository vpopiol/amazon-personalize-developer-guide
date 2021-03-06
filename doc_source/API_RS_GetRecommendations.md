# GetRecommendations<a name="API_RS_GetRecommendations"></a>

Returns a list of recommended items\. The required input depends on the recipe type used to create the solution backing the campaign, as follows:
+ RELATED\_ITEMS \- `itemId` required, `userId` not used
+ USER\_PERSONALIZATION \- `itemId` optional, `userId` required

**Note**  
Campaigns that are backed by a solution created using a recipe of type PERSONALIZED\_RANKING use the [GetPersonalizedRanking](API_RS_GetPersonalizedRanking.md) API\.

## Request Syntax<a name="API_RS_GetRecommendations_RequestSyntax"></a>

```
POST /recommendations HTTP/1.1
Content-type: application/json

{
   "[campaignArn](#personalize-RS_GetRecommendations-request-campaignArn)": "string",
   "[itemId](#personalize-RS_GetRecommendations-request-itemId)": "string",
   "[numResults](#personalize-RS_GetRecommendations-request-numResults)": number,
   "[userId](#personalize-RS_GetRecommendations-request-userId)": "string"
}
```

## URI Request Parameters<a name="API_RS_GetRecommendations_RequestParameters"></a>

The request does not use any URI parameters\.

## Request Body<a name="API_RS_GetRecommendations_RequestBody"></a>

The request accepts the following data in JSON format\.

 ** [campaignArn](#API_RS_GetRecommendations_RequestSyntax) **   <a name="personalize-RS_GetRecommendations-request-campaignArn"></a>
The Amazon Resource Name \(ARN\) of the campaign to use for getting recommendations\.  
Type: String  
Length Constraints: Maximum length of 256\.  
Pattern: `arn:([a-z\d-]+):personalize:.*:.*:.+`   
Required: Yes

 ** [itemId](#API_RS_GetRecommendations_RequestSyntax) **   <a name="personalize-RS_GetRecommendations-request-itemId"></a>
The item ID to provide recommendations for\.  
Required for `RELATED_ITEMS` recipe type\.  
Type: String  
Length Constraints: Maximum length of 256\.  
Required: No

 ** [numResults](#API_RS_GetRecommendations_RequestSyntax) **   <a name="personalize-RS_GetRecommendations-request-numResults"></a>
The number of results to return\. The default is 25\. The maximum is 500\.  
Type: Integer  
Valid Range: Minimum value of 0\.  
Required: No

 ** [userId](#API_RS_GetRecommendations_RequestSyntax) **   <a name="personalize-RS_GetRecommendations-request-userId"></a>
The user ID to provide recommendations for\.  
Required for `USER_PERSONALIZATION` recipe type\.  
Type: String  
Length Constraints: Maximum length of 256\.  
Required: No

## Response Syntax<a name="API_RS_GetRecommendations_ResponseSyntax"></a>

```
HTTP/1.1 200
Content-type: application/json

{
   "[itemList](#personalize-RS_GetRecommendations-response-itemList)": [ 
      { 
         "[itemId](API_RS_PredictedItem.md#personalize-Type-RS_PredictedItem-itemId)": "string"
      }
   ]
}
```

## Response Elements<a name="API_RS_GetRecommendations_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [itemList](#API_RS_GetRecommendations_ResponseSyntax) **   <a name="personalize-RS_GetRecommendations-response-itemList"></a>
A list of recommendations sorted in ascending order by prediction score\. There can be a maximum of 500 items in the list\.  
Type: Array of [PredictedItem](API_RS_PredictedItem.md) objects

## Errors<a name="API_RS_GetRecommendations_Errors"></a>

 **InvalidInputException**   
Provide a valid value for the field or parameter\.  
HTTP Status Code: 400

 **ResourceNotFoundException**   
The specified resource does not exist\.  
HTTP Status Code: 404

## See Also<a name="API_RS_GetRecommendations_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/personalize-runtime-2018-05-22/GetRecommendations) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/personalize-runtime-2018-05-22/GetRecommendations) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/personalize-runtime-2018-05-22/GetRecommendations) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/personalize-runtime-2018-05-22/GetRecommendations) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/personalize-runtime-2018-05-22/GetRecommendations) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/personalize-runtime-2018-05-22/GetRecommendations) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/personalize-runtime-2018-05-22/GetRecommendations) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/personalize-runtime-2018-05-22/GetRecommendations) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/personalize-runtime-2018-05-22/GetRecommendations) 