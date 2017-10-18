
# A basic consumption of messages from Azure Service Bus and .NET Core 2.0

## blogs:
* [Creating a library to simplify Azure Service Bus message processing](https://messagedriven.wordpress.com/2017/09/23/creating-a-library-to-simplify-message-handling/)

## sample usage
create implementation of the IProcessMessage<T>

public class ThirdPartyRateProcessor : IProcessMessage<ThirdPartyRate>
{..}

in Startup.cs inject the dependencies: 
services.AddQueueHandler<ThirdPartyRate, ThirdPartyRateProcessor> (connectionString, queueName);
services.AddTopicSender<NewQuoteReceived>(connectionString, topicName);
.
.
app.RegisterHandler<ThirdPartyRate>(serviceProvider);


