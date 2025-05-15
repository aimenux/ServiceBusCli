# ServiceBusCli
```
A net global tool helping to interact with azure service bus
```

> In this repo, i m building a cli tool that allows to interact with azure service bus.
>
> The cli tool provide commands to :
> 
><details>
>
><summary>List queues</summary>
>
>#### 📌 list top max queues : `sb q -c dev`
>#### 📌 list top 10 queues : `sb q -c dev -m 10`
>#### 📌 list all queues : `sb q -c dev -a`
>#### 📌 list all queues sorted by last access date asc : `sb q -c dev -a -s LastAccessDate:asc`
>#### 📌 list all queues sorted by size in megabytes dsc : `sb q -c dev -a -s SizeInMegabytes:dsc`
>#### 📌 list all queues sorted by active messages dsc : `sb q -c dev -a -s ActiveMessages:dsc`
> 
></details>
>
><details>
>
><summary>Filter queues</summary>
>
>#### 📌 filter queues by single keyword : `sb q -c dev -f order`
>#### 📌 filter queues by multiple keywords : `sb q -c dev -f email -f sms`
>#### 📌 filter queues by field ActiveMessages : `sb q -c dev -f ActiveMessages:1-10`
>#### 📌 filter queues by field DeadLetterMessages : `sb q -c dev -f DeadLetterMessages:1-10`
>#### 📌 filter queues by field SizeInMegabytes : `sb q -c dev -f SizeInMegabytes:1-10`
>#### 📌 filter queues by field CreationDate : `sb q -c dev -f CreationDate:01/05/2024-01/05/2025`
>#### 📌 filter queues by field LastAccessDate : `sb q -c dev -f LastAccessDate:01/05/2024-01/05/2025`
>
></details>
>
><details>
>
><summary>Export queues</summary>
>
>#### 📌 export top max queues : `sb q -c dev x`
>#### 📌 export top 10 queues : `sb q -c dev x -m 10`
>#### 📌 export all queues : `sb q -c dev x -a`
>#### 📌 export all queues sorted by last access date asc : `sb q -c dev x -a -s LastAccessDate:asc`
>#### 📌 export all queues sorted by size in megabytes dsc : `sb q -c dev x -a -s SizeInMegabytes:dsc`
>#### 📌 export all queues sorted by active messages dsc : `sb q -c dev x -a -s ActiveMessages:dsc`
>
></details>
>
><details>
>
><summary>Get queue info</summary>
>
>#### 📌 get queue info : `sb q -c dev -n some-queue-name`
>
></details>
>
><details>
>
><summary>Send messages to queue</summary>
>
>#### 📌 send single message to queue : `sb q -c dev -n some-queue-name s -p some-message-json-file`
>#### 📌 send single message to queue after some delay in minutes : `sb q -c dev -n some-queue-name s -p some-message-json-file --delay 5`
>#### 📌 send multiple message to queue : `sb q -c dev -n some-queue-name s -p some-message-json-file --count 10`
>#### 📌 send multiple message to queue after some delay in minutes : `sb q -c dev -n some-queue-name s -p some-message-json-file --count 10 --delay 5`
>
></details>
>
><details>
>
><summary>List dead-letter queues</summary>
>
>#### 📌 list top max dead-letter queues : `sb dlq -c dev`
>#### 📌 list top 10 dead-letter queues : sb dlq -c dev -m 10`
>#### 📌 list all dead-letter queues : sb dlq -c dev -a`
>#### 📌 list all dead-letter queues sorted by last access date asc : `sb dlq -c dev -a -s LastAccessDate:asc`
>#### 📌 list all dead-letter queues sorted by size in megabytes dsc : `sb dlq -c dev -a -s SizeInMegabytes:dsc`
>#### 📌 list all dead-letter queues sorted by dead letter messages dsc : `sb dlq -c dev -a -s DeadLetterMessages:dsc`
>
></details>
>
><details>
>
><summary>Filter dead-letter queues</summary>
>
>#### 📌 filter dead-letter queues by single keyword : `sb dlq -c dev -f order`
>#### 📌 filter dead-letter queues by multiple keywords : `sb dlq -c dev -f email -f sms`
>#### 📌 filter dead-letter queues by field ActiveMessages : `sb dlq -c dev -f ActiveMessages:1-10`
>#### 📌 filter dead-letter queues by field DeadLetterMessages : `sb dlq -c dev -f DeadLetterMessages:1-10`
>#### 📌 filter dead-letter queues by field SizeInMegabytes : `sb dlq -c dev -f SizeInMegabytes:1-10`
>#### 📌 filter dead-letter queues by field CreationDate : `sb dlq -c dev -f CreationDate:01/05/2024-01/05/2025`
>#### 📌 filter dead-letter queues by field LastAccessDate : `sb dlq -c dev -f LastAccessDate:01/05/2024-01/05/2025`
>
></details>
>
><details>
>
><summary>Export dead-letter queues</summary>
>
>#### 📌 export top max dead-letter queues : `sb dlq -c dev x`
>#### 📌 export top 10 dead-letter queues : `sb dlq -c dev x -m 10`
>#### 📌 export all dead-letter queues : `sb dlq -c dev x -a`
>#### 📌 export all dead-letter queues sorted by last access date asc : `sb dlq -c dev x -a -s LastAccessDate:asc`
>#### 📌 export all dead-letter queues sorted by size in megabytes dsc : `sb dlq -c dev x -a -s SizeInMegabytes:dsc`
>#### 📌 export all dead-letter queues sorted by dead-letter messages dsc : `sb dlq -c dev x -a -s DeadLetterMessages:dsc`
>
></details>
>
><details>
>
><summary>Get dead-letter queue info</summary>
>
>#### 📌 get dead-letter queue info : `sb dlq -c dev -n some-queue-name`
>#### 📌 get dead-letter queue filtered info by text : `sb dlq -c dev -n some-queue-name -f SomeException`
>#### 📌 get dead-letter queue filtered info by date : `sb dlq -c dev -n some-queue-name -f 01/04/2025`
>#### 📌 get dead-letter queue filtered info by date range : `sb dlq -c dev -n some-queue-name -f 01/04/2025-01/05/2025`
>#### 📌 get dead-letter queue filtered info by specific field ErrorType : `sb dlq -c dev -n some-queue-name-f ErrorType:SomeException`
>#### 📌 get dead-letter queue filtered info by specific field ErrorMessage : `sb dlq -c dev -n some-queue-name-f ErrorMessage:SomeException`
>#### 📌 get dead-letter queue filtered info by specific field ErrorDate : `sb dlq -c dev -n some-queue-name-f ErrorDate:01/04/2025-01/05/2025`
>
></details>
>
><details>
>
><summary>View dead-letter queue messages</summary>
>
>#### 📌 view all dead letter messages : `sb dlq -c dev -n some-queue-name v`
>#### 📌 view filtered dead letter messages by text : `sb dlq -c dev -n some-queue-name v -f SomeException`
>#### 📌 view filtered dead letter messages by date : `sb dlq -c dev -n some-queue-name v -f 01/04/2025`
>#### 📌 view filtered dead letter messages by sequence numbers : `sb dlq -c dev -n some-queue-name v -f 100-200`
>#### 📌 view a specific dead letter message by its sequence number : `sb dlq -c dev -n some-queue-name v -f 200`
>
></details>
>
><details>
>
><summary>Purge dead-letter queue messages</summary>
>
>#### 📌 purge all dead letter messages : `sb dlq -c dev -n some-queue-name p`
>#### 📌 purge filtered dead letter messages by text : `sb dlq -c dev -n some-queue-name p -f SomeException`
>#### 📌 purge filtered dead letter messages by date : `sb dlq -c dev -n some-queue-name p -f 01/04/2025`
>#### 📌 purge filtered dead letter messages by date range : `sb dlq -c dev -n some-queue-name p -f 01/04/2025-01/05/2025`
>#### 📌 purge filtered dead letter messages by sequence numbers : `sb dlq -c dev -n some-queue-name p -f 100-200`
>
></details>
>
><details>
>
><summary>Replay dead-letter queue messages</summary>
>
>#### 📌 replay all dead letter messages : `sb dlq -c dev -n some-queue-name r`
>#### 📌 replay all dead letter messages after some delay in minutes : `sb dlq -c dev -n some-queue-name r --delay 5`
>#### 📌 replay all dead letter messages with some ttl in days : `sb dlq -c dev -n some-queue-name r --ttl 1`
>#### 📌 replay filtered dead letter messages by text : `sb dlq -c dev -n some-queue-name r -f SomeException`
>#### 📌 replay filtered dead letter messages by date : `sb dlq -c dev -n some-queue-name r -f 01/04/2025`
>#### 📌 replay filtered dead letter messages by date range : `sb dlq -c dev -n some-queue-name r -f 01/04/2025-01/05/2025`
>#### 📌 replay filtered dead letter messages by sequence numbers : `sb dlq -c dev -n some-queue-name r -f 100-200`
>
></details>
>
><details>
>
><summary>Export dead-letter queue messages</summary>
>
>#### 📌 export all dead letter messages : `sb dlq -c dev -n some-queue-name x`
>#### 📌 export filtered dead letter messages by text : `sb dlq -c dev -n some-queue-name x -f SomeException`
>#### 📌 export filtered dead letter messages by date : `sb dlq -c dev -n some-queue-name x -f 01/04/2025`
>#### 📌 export filtered dead letter messages by date range : `sb dlq -c dev -n some-queue-name x -f 01/04/2025-01/05/2025`
>#### 📌 export filtered dead letter messages by sequence numbers : `sb dlq -c dev -n some-queue-name x -f 100-200`
>
></details>
> 
> To install the tool from [nuget source](https://www.nuget.org/packages/ServiceBusCli), type command :
> - For stable version : `dotnet tool install -g ServiceBusCli --ignore-failed-sources`
> - For prerelease version : `dotnet tool install -g ServiceBusCli --version "*-*" --ignore-failed-sources`
>
> To update the tool, type command :
> - `dotnet tool update -g ServiceBusCli`
>
> 
> To uninstall global tool, type command :
> - `dotnet tool uninstall -g ServiceBusCli`
>
>

Notes :
>
> 🚧 This tool is still under development. 🚧
>
> ⚠️ This tool is not open source, it could be in the future, but it's free to use. ⚠️
>
> 📢 This tool is provided as is, without any warranty or support. Use it at your own risk. 📢