# Error Handling<a name="error-handling"></a>

Amazon Kinesis Data Analytics returns API or SQL errors directly to you\. For more information about API operations, see [Actions](API_Operations.md)\. For more information about handling SQL errors, see [Amazon Kinesis Data Analytics SQL Reference](http://docs.aws.amazon.com/kinesisanalytics/latest/sqlref/analytics-sql-reference.html)\.

Amazon Kinesis Data Analytics reports runtime errors using an in\-application error stream called `error_stream`\. 

## Reporting Errors Using an In\-Application Error Stream<a name="error-handling-errorstream"></a>

Amazon Kinesis Data Analytics reports runtime errors to the in\-application error stream called `error_stream`\. The following are examples of errors that might occur:

+ A record read from the streaming source does not conform to the input schema\. 

+ Your application code specifies division by zero\. 

+ The rows are out of order \(for example, a record appears on the stream with a `ROWTIME` value that a user modified that causes a record to go out of order\)\.

+ The data in the source stream can't be converted to the data type specified in the schema \(Coercion error\)\. For information about what data types can be converted, see [Mapping JSON Data Types to SQL Data Types](sch-mapping.md#sch-mapping-datatypes)\.

We recommend that you handle these errors programmatically in your SQL code and/or persist the data on the error stream to an external destination\. This requires that you add an output configuration \(see [Configuring Application Output](how-it-works-output.md)\) to your application\. For an example of how the in\-application error stream works, see [Example: Explore the In\-Application Error Stream](app-explore-error-stream.md)\.

### Error Stream Schema<a name="error-handling-errorstream-schema"></a>

The error stream has the following schema:


****  

|  |  |  | 
| --- |--- |--- |
| *Field* | *Data Type* | *Notes* | 
| ERRORTIME | TIMESTAMP | The time when the error occurred | 
| ERROR\_LEVEL | VARCHAR\(10\) |  | 
| ERROR\_NAME | VARCHAR\(32\) |  | 
| MESSAGE | VARCHAR\(4096\) |  | 
| DATA\_ROWTIME | TIMESTAMP | The row time of the incoming record | 
| DATA\_ROW | VARCHAR\(49152\) | The hex\-encoded data in the original row | 
| PUMP\_NAME | VARCHAR\(128\) | The originating pump, as defined with `CREATE PUMP` | 