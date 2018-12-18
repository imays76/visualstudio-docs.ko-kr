---
title: Visual Studio에서 Azure 코드 최적화 | Microsoft Docs
description: Azure 코드 최적화 도구 Visual Studio에서 도움말 더 강력 하 고 성능이 뛰어난 코드를 쉽게에 대해 알아봅니다.
author: ghogen
manager: douge
ms.assetid: ed48ee06-e2d2-4322-af22-07200fb16987
ms.topic: conceptual
ms.custom: vs-azure
ms.workload: azure-vs
ms.date: 11/11/2016
ms.author: ghogen
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: d1d0f5a69015a6c6596e1a2b7ee85b12f4116d6b
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002518"
---
# <a name="optimizing-your-azure-code"></a>Azure 코드 최적화
Microsoft Azure를 사용 하는 앱을 프로그래밍할 경우 몇 가지 코딩 사례 앱 안정성, 동작 및 클라우드 환경에서 성능 문제를 방지 하려면 수행 해야 합니다. Microsoft는 인식 하 고 다양 한 일반적으로 발생 하는 이러한 문제를 식별 하 고 해결 해 주는 Azure 코드 분석 도구를 제공 합니다. NuGet 통해 Visual Studio의 도구를 다운로드할 수 있습니다.

## <a name="azure-code-analysis-rules"></a>Azure 코드 분석 규칙
Azure 코드 분석 도구는 성능에 영향을 주는 알려진된 문제를 발견할 경우 Azure 코드를 자동으로 플래그를 설정 하려면 다음 규칙을 사용 합니다. 문제를 경고로 표시 검색 또는 컴파일러 오류입니다. 코드 수정 사항 또는 제안은 경고 또는 오류를 해결 하려면 종종 전구 아이콘을 통해 제공 됩니다.

## <a name="avoid-using-default-in-process-session-state-mode"></a>기본 (in-process) 세션 상태 모드를 사용 하지 마십시오
### <a name="id"></a>ID
AP0000

### <a name="description"></a>설명
기본 (in-process) 세션 상태 모드를 사용 하 여 클라우드 응용 프로그램에 대 한 세션 상태가 손실 될 수 있습니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
기본적으로 web.config 파일에 지정 된 세션 상태 모드를 진행 됩니다. 또한 구성 파일에 지정 된 항목이 없는 경우 세션 상태 모드를 기본값으로 진행 됩니다. In-process 모드는 웹 서버의 메모리에 세션 상태를 저장합니다. 인스턴스를 다시 시작 또는 새 인스턴스를 부하 분산 또는 장애 조치에 사용 되는 경우 웹 서버의 메모리에 저장 된 세션 상태 저장 되지 않습니다. 이 경우 클라우드에서 확장 가능한 없도록 응용 프로그램을 방지 합니다.

ASP.NET 세션 상태는 세션 상태 데이터에 대 한 여러 가지 저장소 옵션을 지원 합니다: InProc, StateServer, SQLServer, 사용자 지정을 해제 합니다. 사용 하는 사용자 지정 모드에 호스트 데이터를 외부 세션 상태 저장소와 같은 것이 좋습니다 [Redis 용 Azure 세션 상태 제공자](http://go.microsoft.com/fwlink/?LinkId=401521)합니다.

### <a name="solution"></a>솔루션
권장 되는 한 가지 해결 managed cache service의 세션 상태를 저장 하는 것입니다. 사용 방법 알아보기 [Redis 용 Azure 세션 상태 제공자](http://go.microsoft.com/fwlink/?LinkId=401521) 에 세션 상태를 저장 합니다. 또한 클라우드에서 응용 프로그램을 확장할 수 있도록 다른 곳에서 세션 상태를 저장할 수 있습니다. 읽어보세요 대체 솔루션에 자세히 알아보려면 [세션 상태 모드](https://msdn.microsoft.com/library/ms178586)합니다.

## <a name="run-method-should-not-be-async"></a>메서드 실행된에 비동기를 사용 해야 합니다.
### <a name="id"></a>ID
AP1000

### <a name="description"></a>설명
비동기 메서드를 만듭니다 (같은 [await](https://msdn.microsoft.com/library/hh156528.aspx)) 외부 합니다 [run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) 메서드 다음에서 비동기 메서드를 호출 [run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)합니다. 선언 된 [ [run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) 메서드를 비동기로 하면 작업자 역할이 다시 시작 루프를 입력 합니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
내에서 비동기 메서드를 호출 합니다 [run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) 메서드를 사용 하면 클라우드 서비스 런타임이 작업자 역할을 재활용 합니다. 모든 프로그램 실행 내에서 수행 됩니다 작업자 역할이 시작 되 면 합니다 [run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) 메서드. 종료 합니다 [run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) 메서드를 사용 하면 작업자 역할이 다시 시작 합니다. 작업자 역할 런타임이 비동기 메서드에 도달 하면 비동기 메서드 이후에 모든 작업을 발송 하 고 반환 합니다. 이렇게 하면 작업자 역할이 종료 합니다 [ [ [ [run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) 메서드 및 다시 시작 합니다. 실행의 다음 반복에서는 작업자 역할 비동기 메서드를 다시 방문 횟수 및 다시 시작 되 면 작업자 역할이 다시 재순환 합니다.

### <a name="solution"></a>솔루션
외부의 모든 비동기 작업을 배치 합니다 [run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) 메서드. 그런 다음 내에서 리팩터링된 비동기 메서드를 호출 합니다 [ [run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) RunAsync ().wait과 같이 합니다. Azure 코드 분석 도구는이 문제를 해결할 수 있습니다.

다음 코드 조각은이 문제의 코드 수정 사항을 보여 줍니다.

```
public override void Run()
{
    RunAsync().Wait();
}

public async Task RunAsync()
{
    //Asynchronous operations code logic
    // This is a sample worker implementation. Replace with your logic.

    Trace.TraceInformation("WorkerRole1 entry point called");

    HttpClient client = new HttpClient();

    Task<string> urlString = client.GetStringAsync("http://msdn.microsoft.com");

    while (true)
    {
        Thread.Sleep(10000);
        Trace.TraceInformation("Working");

        string stream = await urlString;
    }

}
```

## <a name="use-service-bus-shared-access-signature-authentication"></a>Service Bus 공유 액세스 서명 인증 사용
### <a name="id"></a>ID
AP2000

### <a name="description"></a>설명
인증에 대 한 공유 액세스 서명 (SAS)을 사용 합니다. Service bus 인증에 대 한 access Control Service (ACS) 되지 않습니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
보안 향상된을 위해 Azure Active Directory는 SAS 인증을 사용 하 여 ACS 인증을 대체 합니다. 참조 [Azure Active Directory가 ACS의 미래](https://cloudblogs.microsoft.com/enterprisemobility/2013/06/22/azure-active-directory-is-the-future-of-acs/) 전환 계획에 대 한 정보에 대 한 합니다.

### <a name="solution"></a>솔루션
앱에서 SAS 인증을 사용 합니다. 다음 예제에서는 service bus 네임 스페이스 또는 엔터티에 액세스 하는 기존 SAS 토큰을 사용 하는 방법을 보여 줍니다.

```
MessagingFactory listenMF = MessagingFactory.Create(endpoints, new StaticSASTokenProvider(subscriptionToken));
SubscriptionClient sc = listenMF.CreateSubscriptionClient(topicPath, subscriptionName);
BrokeredMessage receivedMessage = sc.Receive();
```

자세한 내용은 다음 항목을 참조 하세요.

* 개요를 참조 하세요. [공유 액세스 서명 인증 Service Bus를 사용 하 여](https://msdn.microsoft.com/library/dn170477.aspx)
* [Service Bus를 사용한 공유 액세스 서명 인증을 사용 하는 방법](https://msdn.microsoft.com/library/dn205161.aspx)
* 샘플 프로젝트를 참조 하세요. [Service Bus 구독을 사용 하 여 공유 액세스 서명 (SAS)를 사용 하 여 인증](http://code.msdn.microsoft.com/windowsazure/Using-Shared-Access-e605b37c)

## <a name="consider-using-onmessage-method-to-avoid-receive-loop"></a>"수신 루프"를 방지 하려면 OnMessage 메서드를 사용 하는 것이 좋습니다.
### <a name="id"></a>ID
AP2002

### <a name="description"></a>설명
"수신 루프"를 방지 하기를 호출 합니다 **OnMessage** 메서드는 호출 보다 메시지를 받기 위한 더 나은 솔루션을 **수신** 메서드. 그러나 사용 해야 하는 경우는 **수신** 메서드를 기본이 아닌 서버 대기 시간을 지정, 서버 대기 시간 1 분 이상 인지 확인 합니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
호출할 때 **OnMessage**, 클라이언트는 큐 또는 구독을 지속적으로 폴링하는 내부 메시지 펌프를 시작 합니다. 이 메시지 펌프는 메시지를 수신 하는 호출을 실행 하는 무한 루프를 포함 합니다. 호출 시간이 초과 되 면 새 호출을 실행 합니다. 제한 시간 간격의 값에 따라 결정 됩니다 합니다 [OperationTimeout](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.messagingfactorysettings.operationtimeout.aspx) 의 속성을 [MessagingFactory](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.messagingfactory.aspx)사용 되는 합니다.

사용 하는 이점은 **OnMessage** 비교할 **수신** 는 사용자가 필요가 수동으로 메시지에 대 한 폴링, 예외 처리, 동시에 여러 메시지를 처리 및 메시지를 완료 합니다.

호출 하는 경우 **수신** 기본값으로 사용 하지 않고 확인 해야 합니다 *ServerWaitTime* 값은 1 분 이상. 설정 *ServerWaitTime* 1 분을 초과 하는 메시지가 완전히 수신 되기 전에 시간 초과가 서버를 방지 합니다.

### <a name="solution"></a>솔루션
권장된 사용법에 대 한 다음 코드 예제를 참조 하세요. 자세한 내용은 참조 하세요. [QueueClient.OnMessage 메서드 (Microsoft.ServiceBus.Messaging)](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.queueclient.onmessage.aspx)하 고 [QueueClient.Receive 메서드 (Microsoft.ServiceBus.Messaging)](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.queueclient.receive.aspx)합니다.

Azure 메시징 인프라의 성능 향상을 위해 디자인 패턴을 참조 [비동기 메시징 입문서](https://msdn.microsoft.com/library/dn589781.aspx)합니다.

다음은 사용 하는 예로 **OnMessage** 메시지를 받을 수 있습니다.

```
void ReceiveMessages()
{
    // Initialize message pump options.
    OnMessageOptions options = new OnMessageOptions();
    options.AutoComplete = true; // Indicates if the message-pump should call complete on messages after the callback has completed processing.
    options.MaxConcurrentCalls = 1; // Indicates the maximum number of concurrent calls to the callback the pump should initiate.
    options.ExceptionReceived += LogErrors; // Enables you to get notified of any errors encountered by the message pump.

    // Start receiving messages.
    QueueClient client = QueueClient.Create("myQueue");
    client.OnMessage((receivedMessage) => // Initiates the message pump and callback is invoked for each message that is recieved, calling close on the client will stop the pump.
    {
        // Process the message.
    }, options);
    Console.WriteLine("Press any key to exit.");
    Console.ReadKey();
```

다음은 사용 하는 예로 **수신** 기본 서버를 사용 하 여 대기 시간입니다.

```
string connectionString =  
CloudConfigurationManager.GetSetting("Microsoft.ServiceBus.ConnectionString");

QueueClient Client =  
    QueueClient.CreateFromConnectionString(connectionString, "TestQueue");

while (true)  
{   
   BrokeredMessage message = Client.Receive();
   if (message != null)
   {
      try  
      {
         Console.WriteLine("Body: " + message.GetBody<string>());
         Console.WriteLine("MessageID: " + message.MessageId);
         Console.WriteLine("Test Property: " +  
            message.Properties["TestProperty"]);

         // Remove message from queue
         message.Complete();
      }

      catch (Exception)
      {
         // Indicate a problem, unlock message in queue
         message.Abandon();
      }
   }
```

다음은 사용 하는 예로 **수신** 기본이 아닌 서버 대기 시간입니다.

```
while (true)  
{   
   BrokeredMessage message = Client.Receive(new TimeSpan(0,1,0));

   if (message != null)
   {
      try  
      {
         Console.WriteLine("Body: " + message.GetBody<string>());
         Console.WriteLine("MessageID: " + message.MessageId);
         Console.WriteLine("Test Property: " +  
            message.Properties["TestProperty"]);

         // Remove message from queue
         message.Complete();
      }

      catch (Exception)
      {
         // Indicate a problem, unlock message in queue
         message.Abandon();
      }
   }
}
```
## <a name="consider-using-asynchronous-service-bus-methods"></a>비동기 Service Bus 메서드를 사용 하는 것이 좋습니다.
### <a name="id"></a>ID
AP2003

### <a name="description"></a>설명
조정 된 메시징을 사용 하 여 성능 향상을 위해 비동기 Service Bus 메서드를 사용 합니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
비동기 메서드를 사용 하 여 호출을 실행할 때마다 메인 스레드가 차단 하지 때문에 응용 프로그램 동시성이 수 있습니다. Service Bus 메시징 메서드를 수행 하는 작업을 사용 하는 경우 (보내기, 받기, 삭제 등)는 데 시간이 걸립니다. 이 작업을 처리 하는 요청 및 응답의 대기 시간 외에도 Service Bus 서비스에 포함 됩니다. 시간당 작업 수를 늘리려면 작업이 동시에 실행 해야 합니다. 자세한 내용은를 참조 하십시오 [성능을 사용 하 여 Service Bus 조정 된 메시징을 향상에 대 한 모범 사례](https://msdn.microsoft.com/library/azure/hh528527.aspx)합니다.

### <a name="solution"></a>솔루션
참조 [QueueClient 클래스 (Microsoft.ServiceBus.Messaging)](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.queueclient.aspx) 권장된 비동기 메서드를 사용 하는 방법에 대 한 정보에 대 한 합니다.

Azure 메시징 인프라의 성능 향상을 위해 디자인 패턴을 참조 [비동기 메시징 입문서](https://msdn.microsoft.com/library/dn589781.aspx)합니다.

## <a name="consider-partitioning-service-bus-queues-and-topics"></a>Service Bus 큐 및 토픽 분할 고려
### <a name="id"></a>ID
AP2004

### <a name="description"></a>설명
파티션 Service Bus 큐 및 Service Bus 메시징을 사용 하 여 성능 향상을 위해는 항목입니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
Service Bus 큐 및 토픽 분할 되므로 분할 된 큐 또는 토픽의 전체적인 처리량을 단일 메시지 브로커 또는 메시징 저장소의 성능으로 제한 되지 않습니다 성능 처리량과 서비스 가용성이 증가 됩니다. 또한 메시징 저장소의 일시적 중단 되어도 분할 된 큐 또는 항목을 사용할 수 없는. 자세한 내용은 [메시징 엔터티 분할](https://msdn.microsoft.com/library/azure/dn520246.aspx)합니다.

### <a name="solution"></a>솔루션
다음 코드 조각은 메시징 엔터티를 분할 하는 방법을 보여 줍니다.

```
// Create partitioned topic.
NamespaceManager ns = NamespaceManager.CreateFromConnectionString(myConnectionString);
TopicDescription td = new TopicDescription(TopicName);
td.EnablePartitioning = true;
ns.CreateTopic(td);
```

자세한 내용은 참조 하세요. [분할 된 Service Bus 큐 및 토픽 | Microsoft Azure 블로그](https://azure.microsoft.com/blog/2013/10/29/partitioned-service-bus-queues-and-topics/) 체크 아웃 하 고는 [Microsoft Azure Service Bus 분할 큐](https://code.msdn.microsoft.com/windowsazure/Service-Bus-Partitioned-7dfd3f1f) 샘플입니다.

## <a name="do-not-set-sharedaccessstarttime"></a>SharedAccessStartTime을 설정 하지 마십시오
### <a name="id"></a>ID
AP3001

### <a name="description"></a>설명
공유 액세스 정책을 즉시 시작 하려면 현재 시간으로 SharedAccessStartTimeset을 사용 하지 않아야 합니다. 나중에 공유 액세스 정책을 시작 하려는 경우이 속성을 설정 해야 합니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
클록 동기화는 데이터 센터 간에 약간의 시간 차이 발생합니다. 예를 들어 DateTime.Now을 사용 하 여 저장소 SAS 정책의 시작 시간을 현재 시간으로 설정 합니다. 논리적으로 생각 또는 비슷한 메서드 SAS 정책이 즉시 적용 됩니다. 그러나 약간의 시간 차이가 데이터 센터 간에 데이터 센터 경우도 빠르거나 하는 동안 시작 시간 보다 조금 늦은 될 수 문제가 발생할 수 있습니다. SAS 정책이 빠르게 (또는 즉시) 만료 될 수 있습니다 결과적으로, 정책 수명을 너무 짧게 설정할 경우.

공유 액세스 서명을 사용 하 여 Azure storage에 대 한 지침은 참조 하세요 [소개 테이블 SAS (공유 액세스 서명), 큐 SAS 및 Blob SAS-Microsoft Azure Storage 팀 블로그-업데이트 사이트 홈-MSDN 블로그](http://blogs.msdn.com/b/windowsazurestorage/archive/2012/06/12/introducing-table-sas-shared-access-signature-queue-sas-and-update-to-blob-sas.aspx)합니다.

### <a name="solution"></a>솔루션
공유 액세스 정책의 시작 시간을 설정 하는 문을 제거 합니다. Azure 코드 분석 도구는이 문제에 대 한 해결 방법을 제공 합니다. 보안 관리에 대 한 자세한 내용은 디자인 패턴을 참조 하세요 [Valet 키 패턴](https://msdn.microsoft.com/library/dn568102.aspx)합니다.

다음 코드 조각은이 문제의 코드 수정 사항을 보여 줍니다.

```
// The shared access policy provides  
// read/write access to the container for 10 hours.
blobPermissions.SharedAccessPolicies.Add("mypolicy", new SharedAccessBlobPolicy()
{
   // To ensure SAS is valid immediately, don’t set start time.
   // This way, you can avoid failures caused by small clock differences.
   SharedAccessExpiryTime = DateTime.UtcNow.AddHours(10),
   Permissions = SharedAccessBlobPermissions.Write |
      SharedAccessBlobPermissions.Read
});
```

## <a name="shared-access-policy-expiry-time-must-be-more-than-five-minutes"></a>공유 액세스 정책 만료 시간은 5 분 이상 이어야 합니다.
### <a name="id"></a>ID
AP3002

### <a name="description"></a>설명
최대 5 분의 "시계 기울이기입니다." 라고 하는 조건으로 인해 서로 다른 위치에 있는 데이터 센터 간의 클럭 차이가 만큼 수 있습니다. SAS를 방지 하기 위해 만료 정책 토큰이 계획 보다 빨리 만료 될 시간을 5 분 넘게를 설정 합니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
전 세계 여러 위치에서 데이터 센터는 클록 신호를 여는 동기화합니다. 클록 신호가 다른 위치로 이동 하는 시간이 걸리므로 있을 수 있습니다 다른 지리적 위치에 있는 데이터 센터 간 시간 차이가 있지만 모든 코드가 동기화 됩니다. 이 시간 차이 공유 액세스 정책 시작 시간 및 만료 간격을 달라질 수 있습니다. 따라서 공유 액세스 정책을 즉시 적용 되도록 시작 시간 지정 하지 마세요. 또한 만료 시간은 5 분 이상 조기 시간 초과 방지 해야 합니다.

공유 액세스 서명을 사용 하 여 Azure storage에 대 한 자세한 내용은 참조 하세요. [소개 테이블 SAS (공유 액세스 서명), 큐 SAS 및 Blob SAS-Microsoft Azure Storage 팀 블로그-업데이트 사이트 홈-MSDN 블로그](http://blogs.msdn.com/b/windowsazurestorage/archive/2012/06/12/introducing-table-sas-shared-access-signature-queue-sas-and-update-to-blob-sas.aspx)합니다.

### <a name="solution"></a>솔루션
보안 관리에 대 한 자세한 내용은 디자인 패턴을 참조 하세요 [Valet 키 패턴](https://msdn.microsoft.com/library/dn568102.aspx)합니다.

다음은 공유 액세스 정책의 시작 시간을 지정 하지 않는 예제입니다.

```
// The shared access policy provides  
// read/write access to the container for 10 hours.
blobPermissions.SharedAccessPolicies.Add("mypolicy", new SharedAccessBlobPolicy()
{
   // To ensure SAS is valid immediately, don’t set start time.
   // This way, you can avoid failures caused by small clock differences.
   SharedAccessExpiryTime = DateTime.UtcNow.AddHours(10),
   Permissions = SharedAccessBlobPermissions.Write |
      SharedAccessBlobPermissions.Read
});
```

다음은 5 분이 넘는 정책 만료 시간을 사용 하 여 공유 액세스 정책의 시작 시간을 지정 하는 예입니다.

```
// The shared access policy provides  
// read/write access to the container for 10 hours.
blobPermissions.SharedAccessPolicies.Add("mypolicy", new SharedAccessBlobPolicy()
{
   // To ensure SAS is valid immediately, don’t set start time.
   // This way, you can avoid failures caused by small clock differences.
  SharedAccessStartTime = new DateTime(2014,1,20),   
 SharedAccessExpiryTime = new DateTime(2014, 1, 21),
   Permissions = SharedAccessBlobPermissions.Write |
      SharedAccessBlobPermissions.Read
});
```

자세한 내용은 [만들고 공유 액세스 서명을 사용 하 여](https://msdn.microsoft.com/library/azure/jj721951.aspx)입니다.

## <a name="use-cloudconfigurationmanager"></a>CloudConfigurationManager 사용
### <a name="id"></a>ID
AP4000

### <a name="description"></a>설명
사용 하는 [ConfigurationManager](https://msdn.microsoft.com/library/system.configuration.configurationmanager\(v=vs.110\).aspx) Azure 웹 사이트 및 Azure 모바일 서비스 하면 런타임 문제가 발생 하지 않습니다 같은 프로젝트에 대 한 클래스입니다. 그러나 모범 사례로,는 것이 클라우드를 사용 하는 것이 좋습니다[ConfigurationManager](https://msdn.microsoft.com/library/system.configuration.configurationmanager\(v=vs.110\).aspx) 모든 Azure 클라우드 응용 프로그램에 대 한 구성을 관리 하는 통일된 된 방법으로 합니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
CloudConfigurationManager는 응용 프로그램 환경에 적절 한 구성 파일을 읽습니다.

[CloudConfigurationManager](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.cloudconfigurationmanager.aspx)

### <a name="solution"></a>솔루션
사용 하도록 코드를 리팩터링 합니다 [CloudConfigurationManager 클래스](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.cloudconfigurationmanager.aspx)합니다. 이 문제에 대 한 코드 수정 Azure 코드 분석 도구를 통해 제공 됩니다.

다음 코드 조각은이 문제의 코드 수정 사항을 보여 줍니다. 바꾸기

`var settings = ConfigurationManager.AppSettings["mySettings"];`

다음 문자열로 바꾸세요.

`var settings = CloudConfigurationManager.GetSetting("mySettings");`

App.config 또는 Web.config 파일에 구성 설정을 저장 하는 방법의 예는 다음과 같습니다. 구성 파일의 appSettings 섹션에 설정을 추가 합니다. 다음은 이전 코드 예제에 대 한 Web.config 파일입니다.

```
<appSettings>
    <add key="webpages:Version" value="3.0.0.0" />
    <add key="webpages:Enabled" value="false" />
    <add key="ClientValidationEnabled" value="true" />
    <add key="UnobtrusiveJavaScriptEnabled" value="true" />
    <add key="mySettings" value="[put_your_setting_here]"/>
  </appSettings>  
```

## <a name="avoid-using-hard-coded-connection-strings"></a>하드 코드 된 연결 문자열을 사용 하지 마십시오
### <a name="id"></a>ID
AP4001

### <a name="description"></a>설명
하드 코드 된 연결 문자열을 사용 하 고 나중에 업데이트가 필요한 경우에 소스 코드를 변경 하 고 응용 프로그램을 다시 컴파일해야 하는 것이 해야 합니다. 그러나 구성 파일에서 연결 문자열을 저장 하는 경우 변경할 수 있습니다 나중에 구성 파일을 업데이트 하 여 합니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
하드 코드 연결 문자열을 신속 하 게 변경 해야 하는 경우 문제가 야기 하므로 연결 문자열에 바람직하지 않습니다. 또한 프로젝트를 소스 제어에 체크 인해야 하는 경우 하드 코드 된 연결 문자열 보안에 취약해를 집니다 있으므로 소스 코드에서 문자열을 볼 수 있습니다.

### <a name="solution"></a>솔루션
구성 파일 또는 Azure 환경에서 연결 문자열을 저장 합니다.

* 독립 실행형 응용 프로그램에 대 한 app.config를 사용 하 여 연결 문자열 설정을 저장 합니다.
* IIS에서 호스팅되는 웹 응용 프로그램에 대 한 web.config를 사용 하 여 연결 문자열을 저장 합니다.
* ASP.NET vNext 응용 프로그램의 경우 configuration.json 사용 하 여 연결 문자열을 저장 합니다.

Web.config 또는 app.config와 같은 구성 파일 사용에 대 한 자세한 내용은 [ASP.NET 웹 구성 지침](https://msdn.microsoft.com/library/vstudio/ff400235\(v=vs.100\).aspx)합니다. Azure 환경 변수의 작동 방식에 대 한 내용은 참조 하세요 [Azure 웹 사이트: 응용 프로그램 설정 하는 방법 및 연결 문자열 작동](https://azure.microsoft.com/blog/2013/07/17/windows-azure-web-sites-how-application-strings-and-connection-strings-work/)합니다. 소스 제어에서 연결 문자열 저장에 대 한 내용은 참조 하세요 [연결 문자열과 같은 중요 한 정보 소스 코드 리포지토리에 저장 된 파일에 두지 않는](http://www.asp.net/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/source-control)합니다.

## <a name="use-diagnostics-configuration-file"></a>진단 구성 파일 사용
### <a name="id"></a>ID
AP5000

### <a name="description"></a>설명
Microsoft.WindowsAzure.Diagnostics 프로그래밍 API를 사용 하 여 같은 코드에서 진단 설정을 구성 하는 대신 diagnostics.wadcfg 파일의 진단 설정을 구성 해야 합니다. (또는 Azure SDK 2.5를 사용 하는 경우에 diagnostics.wadcfgx). 이 작업을 수행 하 여 코드를 다시 컴파일하지 않고도 진단 설정을 변경할 수 있습니다.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
여러 가지 방법을 사용 하 여 구성할 수 있습니다 (Azure 진단 1.3 사용)는 Azure SDK 2.5에서 Azure 진단 (WAD) 전에: 명령적 코드, 선언적 구성 또는 기본값을 사용 하 여 구성 blob 저장소에 추가 구성입니다. 그러나 진단을 구성 하는 기본 방법은 응용 프로그램 프로젝트에서 XML 구성 파일 (diagnostics.wadcfg 또는 SDK 2.5 이상용 diagnositcs.wadcfgx)을 사용 하는 것입니다. 이 방식에서는 diagnostics.wadcfg 파일을 완전히 구성을 정의 합니다. 업데이트과 가능를 다시 배포 합니다. 사용 하 여 구성을 설정 하는 프로그래밍 방법도 함께 diagnostics.wadcfg 구성 파일의 사용을 혼합 합니다 [DiagnosticMonitor](https://msdn.microsoft.com/library/microsoft.windowsazure.diagnostics.diagnosticmonitor.aspx)하거나 [RoleInstanceDiagnosticManager](https://msdn.microsoft.com/library/microsoft.windowsazure.diagnostics.management.roleinstancediagnosticmanager.aspx)클래스 혼란을 초래할 합니다. 참조 [변경 Azure 진단 구성 초기화 또는](https://msdn.microsoft.com/library/azure/hh411537.aspx) 자세한 내용은 합니다.

WAD 1.3 (Azure SDK 2.5를 사용 하 여 포함) 부터는 것이 더 이상 코드를 사용 하 여 진단을 구성할 수 없습니다. 결과적으로, 구성을 적용 하거나 진단 확장을 업데이트할 때만 제공할 수 있습니다.

### <a name="solution"></a>솔루션
진단 설정을 진단 구성 파일 (diagnositcs.wadcfg 또는 diagnositcs.wadcfgx SDK 2.5 이상)를 이동할 진단 구성 디자이너를 사용 합니다. 설치 하는 것이 좋습니다 [Azure SDK 2.5](http://go.microsoft.com/fwlink/?LinkId=513188) 최신 진단 기능을 사용 합니다.

1. 구성 하려는 역할에 대 한 바로 가기 메뉴에서 속성을 선택 하 고 구성 탭을 선택 합니다.
2. 에 **진단** 섹션에서 확인 합니다 **진단을 사용 하도록 설정** 확인란을 선택 합니다.
3. 선택 된 **구성** 단추입니다.

   ![진단 사용 옵션 액세스](./media/vs-azure-tools-optimizing-azure-code-in-visual-studio/IC796660.png)

   참조 [Azure Cloud Services 및 Virtual Machines 용 진단 구성](vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines.md) 자세한 내용은 합니다.

## <a name="avoid-declaring-dbcontext-objects-as-static"></a>DbContext 개체를 정적으로 선언 하지 마십시오
### <a name="id"></a>ID
AP6000

### <a name="description"></a>설명
메모리를 절약 하려면 DBContext 개체를 정적으로 선언 하지 마십시오.

귀하의 아이디어와 피드백에서 공유 [Azure 코드 분석 피드백](http://go.microsoft.com/fwlink/?LinkId=403771)합니다.

### <a name="reason"></a>이유
DBContext 개체는 각 호출의 쿼리 결과 보관 합니다. 정적 DBContext 개체는 응용 프로그램 도메인이 언로드될 때까지 삭제 되지 않습니다. 따라서 정적 DBContext 개체는 많은 양의 메모리를 사용할 수 있습니다.

### <a name="solution"></a>솔루션
DBContext를 지역 변수 또는 비정적 인스턴스 필드로 선언 하 고 사용 하 여 태스크의 경우 사용 후 삭제 되도록 하면.

다음 예제에서는 MVC 컨트롤러 클래스에는 DBContext 개체를 사용 하는 방법을 보여 줍니다.

```
public class BlogsController : Controller
    {
        //BloggingContext is a subclass to DbContext        
        private BloggingContext db = new BloggingContext();
        // GET: Blogs
        public ActionResult Index()
        {
            //business logics…
            return View();
        }
        protected override void Dispose(bool disposing)
        {
            if (disposing)
            {
                db.Dispose();
            }
            base.Dispose(disposing);
        }
    }
```

## <a name="next-steps"></a>다음 단계
자세한에 대 한 최적화 및 문제 해결 Azure 앱에 알아보려면 [Visual Studio를 사용 하 여 Azure App Service에서 웹 앱 문제 해결](/azure/app-service/web-sites-dotnet-troubleshoot-visual-studio)합니다.
