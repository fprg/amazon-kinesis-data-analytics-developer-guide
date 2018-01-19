# InputDescription<a name="API_InputDescription"></a>

Describes the application input configuration\. For more information, see [Configuring Application Input](http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-input.html)\. 

## Contents<a name="API_InputDescription_Contents"></a>

 **InAppStreamNames**   
Returns the in\-application stream names that are mapped to the stream source\.  
Type: Array of strings  
Length Constraints: Minimum length of 1\. Maximum length of 32\.  
Pattern: `[a-zA-Z][a-zA-Z0-9_]+`   
Required: No

 **InputId**   
Input ID associated with the application input\. This is the ID that Amazon Kinesis Analytics assigns to each input configuration you add to your application\.   
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 50\.  
Pattern: `[a-zA-Z0-9_.-]+`   
Required: No

 **InputParallelism**   
Describes the configured parallelism \(number of in\-application streams mapped to the streaming source\)\.  
Type: [InputParallelism](API_InputParallelism.md) object  
Required: No

 **InputProcessingConfigurationDescription**   
The description of the preprocessor that executes on records in this input before the application's code is run\.  
Type: [InputProcessingConfigurationDescription](API_InputProcessingConfigurationDescription.md) object  
Required: No

 **InputSchema**   
Describes the format of the data in the streaming source, and how each data element maps to corresponding columns in the in\-application stream that is being created\.   
Type: [SourceSchema](API_SourceSchema.md) object  
Required: No

 **InputStartingPositionConfiguration**   
Point at which the application is configured to read from the input stream\.  
Type: [InputStartingPositionConfiguration](API_InputStartingPositionConfiguration.md) object  
Required: No

 **KinesisFirehoseInputDescription**   
If an Amazon Kinesis Firehose delivery stream is configured as a streaming source, provides the delivery stream's ARN and an IAM role that enables Amazon Kinesis Analytics to access the stream on your behalf\.  
Type: [KinesisFirehoseInputDescription](API_KinesisFirehoseInputDescription.md) object  
Required: No

 **KinesisStreamsInputDescription**   
If an Amazon Kinesis stream is configured as streaming source, provides Amazon Kinesis stream's Amazon Resource Name \(ARN\) and an IAM role that enables Amazon Kinesis Analytics to access the stream on your behalf\.  
Type: [KinesisStreamsInputDescription](API_KinesisStreamsInputDescription.md) object  
Required: No

 **NamePrefix**   
In\-application name prefix\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 32\.  
Pattern: `[a-zA-Z][a-zA-Z0-9_]+`   
Required: No

## See Also<a name="API_InputDescription_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/kinesisanalytics-2015-08-14/InputDescription) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/kinesisanalytics-2015-08-14/InputDescription) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/kinesisanalytics-2015-08-14/InputDescription) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/kinesisanalytics-2015-08-14/InputDescription) 