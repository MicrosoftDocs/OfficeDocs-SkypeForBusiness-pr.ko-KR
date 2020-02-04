---
title: 프런트 엔드 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
ROBOTS: NOINDEX, NOFOLLOW
description: 다음 섹션에서 기존 프런트 엔드 풀 또는 Standard Edition 서버의 설정을 편집할 수 있습니다.
ms.openlocfilehash: 76992a6d88c25a1907e4bb2cc1f6dee69a418f01
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688520"
---
# <a name="front-end-general-settings-expander"></a><span data-ttu-id="c1f98-103">프런트 엔드 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="c1f98-103">Front End General Settings Expander</span></span>

<span data-ttu-id="c1f98-104">다음 섹션에서 기존 프런트 엔드 풀 또는 Standard Edition 서버의 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-104">To edit the settings for an existing Front End pool or Standard Edition server, you are presented with the following sections:</span></span>

- <span data-ttu-id="c1f98-105">일반 설정</span><span class="sxs-lookup"><span data-stu-id="c1f98-105">General settings</span></span>

- <span data-ttu-id="c1f98-106">탄성 설정</span><span class="sxs-lookup"><span data-stu-id="c1f98-106">Resiliency settings</span></span>

- <span data-ttu-id="c1f98-107">웹 서비스 설정</span><span class="sxs-lookup"><span data-stu-id="c1f98-107">Web services settings</span></span>

- <span data-ttu-id="c1f98-108">중재 서버 설정</span><span class="sxs-lookup"><span data-stu-id="c1f98-108">Mediation Server settings</span></span>

## <a name="front-end-pool"></a><span data-ttu-id="c1f98-109">프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="c1f98-109">Front End pool</span></span>

<span data-ttu-id="c1f98-p101">프런트 엔드 풀의 경우 일반, 탄성, 웹 서비스 및 중재 서버 설정을 구성할 수 있습니다. 자세한 내용은 다음과 같은 하위 섹션의 정보를 참조하세요. 프런트 엔드 풀의 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p101">For a Front End pool, you can configure general, resiliency, web services, and Mediation Server settings. For details, see the information in the following subsections. For details about defining and configuring the settings for the Front End pool, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>

### <a name="general-settings"></a><span data-ttu-id="c1f98-113">일반 설정</span><span class="sxs-lookup"><span data-stu-id="c1f98-113">General Settings</span></span>

<span data-ttu-id="c1f98-114">다음과 같은 일반 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-114">You can configure the following general settings:</span></span>

- <span data-ttu-id="c1f98-p102">**FQDN**. 풀의 FQDN을 편집하여 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p102">**FQDN**. Edit the FQDN of the pool to change it.</span></span>

- <span data-ttu-id="c1f98-p103">**하드웨어 부하 분산 장치 모니터링 포트 사용**. 확인란을 선택하고 하드웨어 부하 분산 장치에서 풀 서버의 상태를 모니터링하는 데 사용할 포트 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p103">**Enable hardware load balancer monitoring port**. Select the check box and enter the port number that your Hardware Load Balancer will use to monitor the state of the pool servers.</span></span>

- <span data-ttu-id="c1f98-p104">**특징 및 기능**에서 이 풀과 배치하려는 추가 역할을 정의합니다. 다음과 같은 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p104">In **Features and Functionality**, define the additional roles that you want to collocate with this pool. You can configure the following settings:</span></span>

  - <span data-ttu-id="c1f98-p105">**회의**. 오디오, 비디오 및 응용 프로그램 공유가 포함됩니다. 이 옵션을 선택하면 전화 접속(PSTN) 회의를 선택할 수 있습니다. 이 섹션의 뒷부분에 있는 "중재 서버 설정" 하위 섹션에서 공중 전화망(PSTN) 게이트웨이를 지정하고 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p105">**Conferencing**. Includes audio, video and application sharing. After you select this option, you can select Dial-in (PSTN) conferencing. You specify and define a public switched telephone network (PSTN) gateway in the "Mediation Server Settings" subsection later in this section.</span></span>

  - <span data-ttu-id="c1f98-125">**Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="c1f98-125">**Enterprise Voice**.</span></span> <span data-ttu-id="c1f98-126">자격 있는 단말기, 장치 및 비즈니스용 Skype 클라이언트에 대 한 내부 음성 over IP 통화를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-126">Enables internal voice over IP calls to qualified handsets and devices and Skype for Business clients.</span></span> <span data-ttu-id="c1f98-127">외부 통화 기능을 사용하도록 설정하려면 중재 서버를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-127">To enable external call capabilities, you need to include a Mediation Server.</span></span> <span data-ttu-id="c1f98-128">자세한 내용은 이 항목 뒷부분의 "중재 서버"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1f98-128">For details, see "Mediation Server" later in this topic.</span></span>

- <span data-ttu-id="c1f98-129">**연결**에서는 다음을 편집하거나 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-129">In **Associations**, edit or specify the following:</span></span>

  - <span data-ttu-id="c1f98-p107">**SQL 저장소**. 기존 SQL Server 데이터베이스를 수정하거나, 프런트 엔드 풀 데이터베이스를 보관할 SQL Server 기반의 새 데이터베이스를 만듭니다. 목록에서 새 SQL Server 인스턴스를 선택하거나 **새로 만들기**를 클릭하여 새 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p107">**SQL Store**. Modify an existing SQL Server database or create a new SQL Server-based database to hold the Front End pool databases. You can select a new instance of SQL Server from the list or create a new entry by clicking **New**.</span></span>

    <span data-ttu-id="c1f98-p108">**SQL Server 저장소 미러링 사용**을 선택한 다음 미러링에 사용할 서버를 선택합니다. 새 SQL Server 저장소를 만들려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p108">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>

    <span data-ttu-id="c1f98-p109">**자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용**을 선택하고 미러링 모니터 서버로 사용할 서버를 선택합니다. 새 SQL Server 저장소를 만들려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p109">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>

  - <span data-ttu-id="c1f98-p110">**파일 공유**. 프런트 엔드 풀에서 사용 중인 파일 저장소를 수정합니다. 목록에 있는 이미 정의된 저장소 중에서 새 파일 저장소를 선택하거나 **새로 만들기**를 클릭하여 새 파일 저장소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p110">**File share**. Modify the file store that the Front End pool is using. You can select a new file store from those already defined by selecting it from the list. You can create a new file store by clicking **New**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c1f98-141">새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-141">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

  - <span data-ttu-id="c1f98-p111">**보관**. 보관 서버 저장소를 프런트 엔드 풀과 연결합니다. 목록에 있는 이미 정의된 보관 SQL Server 저장소에서 서버를 선택하거나 **새로 만들기**를 클릭하여 새 보관 서버를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p111">**Archiving**. Associate an Archiving Server store with the Front End pool. You can select from an already defined Archiving SQL Server store by selecting the server from the list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c1f98-145">새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-145">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

    <span data-ttu-id="c1f98-p112">**SQL Server 저장소 미러링 사용**을 선택한 다음 미러링에 사용할 서버를 선택합니다. 새 SQL Server 저장소를 만들려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p112">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>

    <span data-ttu-id="c1f98-p113">**자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용**을 선택하고 미러링 모니터 서버로 사용할 서버를 선택합니다. 새 SQL Server 저장소를 만들려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p113">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>

  - <span data-ttu-id="c1f98-p114">**모니터링(CDR 및 QoE 기준)**. 모니터링 SQL Server 저장소를 프런트 엔드 풀과 연결하려면 선택합니다. 목록에 있는 이미 정의된 모니터링 서버에서 서버를 선택하거나 **새로 만들기**를 클릭하여 새 모니터링 서버를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p114">**Monitoring (CDR and QoE metrics)**. Select to associate a Monitoring SQL Server store with the Front End pool. You can select from an already defined Monitoring Server by selecting the server from the list, or click **New** to specify a new Monitoring Server.</span></span>

    <span data-ttu-id="c1f98-p115">**SQL Server 저장소 미러링 사용**을 선택한 다음 미러링에 사용할 서버를 선택합니다. 새 SQL Server 저장소를 만들려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p115">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>

    <span data-ttu-id="c1f98-p116">**자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용**을 선택하고 미러링 모니터 서버로 사용할 서버를 선택합니다. 새 SQL Server 저장소를 만들려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p116">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>

  - <span data-ttu-id="c1f98-p117">**에지 풀 연결(미디어 구성 요소)**. 에지 서버 또는 풀을 프런트 엔드 풀과 연결합니다. 목록에 있는 이미 정의된 에지 서버 또는 풀에서 서버를 선택하거나 **새로 만들기**를 클릭하여 새 에지 서버 또는 풀을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p117">**Associate Edge pool (for media components)**. Associate an Edge Server or pool with the Front End pool. You can select from an already defined Edge Server or pool by selecting the server from the list, or click **New** to specify a new Edge Server or pool.</span></span>

  - <span data-ttu-id="c1f98-p118">**Office Web Apps Server에 풀 연결**. Office Web Apps Server를 프런트 엔드 풀과 연결하려면 이 옵션을 선택합니다. 목록에서 기존 서버를 선택하거나 **새로 만들기**를 클릭하여 새 Office Web Apps Server를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p118">**Associate pool with an Office Web Apps Server**. Select this option to associate an Office Web Apps Server with the Front End pool. Select an existing server from the list, or click **New** to create a new Office Web Apps Server.</span></span>

### <a name="resiliency"></a><span data-ttu-id="c1f98-163">탄성</span><span class="sxs-lookup"><span data-stu-id="c1f98-163">Resiliency</span></span>

<span data-ttu-id="c1f98-p119">탄성은 풀에 대해 재해 복구 및 고가용성을 제공합니다. 백업을 제공하는 경우 기본 서버에 오류가 발생하면 백업 서버가 작업을 대신 수행하므로 사용자가 로그인 및 통신할 수 있습니다. 기본 서버와 함께 오류가 발생한 시스템에 따라서는 사용자의 기능이 축소될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p119">Resiliency provides disaster recovery and high availability for the pool. By providing a backup, if the primary server fails, the backup server can take over, enabling users to sign in and communicate. There may be reduced functionality for users, depending on which systems have failed with the primary server.</span></span>

<span data-ttu-id="c1f98-p120">목록에서 풀의 백업 서버로 작동하도록 할 프런트 엔드 풀 또는 Standard Edition 서버를 선택합니다. 장애 조치(failover) 및 대체 시간 간격을 설정하도록 선택할 수도 있습니다. 장애 조치(failover) 및 대체 시간 간격(초)을 설정하면 오류가 발생한 서버를 자동으로 감지하고 대체 시간 동안 기본 서버가 백업되는지 자동으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p120">From the list, select the Front End pool or Standard Edition server that will act as the backup server for the pool. You can also select to enable Failover and Fallback time intervals. Enabling the failover and fallback time settings (specified in seconds) enables automatic detection of a failed server, and a fallback time to allow for automatic determination that the primary is back up.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1f98-p121">실패 검색 및 대체 간격을 정의할 경우, 서버가 잠깐 동안 응답하지 않을 때 장애 조치(failover) 및 대체가 수행되지 않도록 충분한 간격을 입력해야 합니다. 풀이나 서버를 로드하는 시간에 따라 기본 서버가 잠깐 동안 응답하지 않을 수도 있습니다. 장애 조치(failover) 및 대체의 기본값은 풀 간의 경우 300초, 풀과 Standard Edition 서버 간의 경우 600초입니다. 사이트의 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버와 풀 또는 Standard Edition 서버 간의 장애 조치(failover) 기본값은 120초, 대체 기본값은 240초입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p121">When defining the Failure detection and the Fallback interval, you should be careful not to enter an interval that will cause the failover and fallback to occur if the server fails to respond for a short period of time. It is possible that the primary server may not respond for short periods of time, depending on the loading of the pool or servers. The default values for the failover and fallback are 300 seconds and 600 seconds for pool to pool, or pool to Standard Edition server. In the event of a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition server, the default values are 120 seconds for failover and 240 seconds for fallback.</span></span>

> [!CAUTION]
> <span data-ttu-id="c1f98-p122">**장애 조치(failover) 간격**의 최소값은 90초 미만으로 설정하지 않아야 합니다. 값을 90초 미만으로 설정할 경우 90초가 값으로 사용됩니다. intercluster ping 시간은 30초이며, 시간을 90초 미만으로 설정하면 기본 및 백업 서버 주기가 교대로 바뀌어 두 서버가 서로의 가변 상태를 확인하려고 시도하기 때문에 프로덕션에 부정적인 영향을 줄 수 있습니다. 값이 90초 미만인 경우 기본 서버가 실제로 사용 가능한지 확인하는 데 필요한 시간이 부족해집니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p122">The minimum value for the **failover interval** should not be set lower than 90 seconds. If you do set the value to less than 90 seconds, the value of 90 seconds is used. The intercluster ping time is 30 seconds, and a setting lower than 90 seconds may cause the primary and backup servers to cycle up and down, causing an undesirable impact to production, as the servers try to resolve the viable status of the other. Less than 90 seconds does not allow for enough time to determine that the primary server is actually unavailable or not.</span></span>

### <a name="web-services"></a><span data-ttu-id="c1f98-178">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="c1f98-178">Web Services</span></span>

<span data-ttu-id="c1f98-179">프런트 엔드 풀의 웹 서비스에 대한 추가 설정을 편집하거나 지정하려면 **내부 웹 서비스** 및 **외부 웹 서비스**의 설정을 수정하거나 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-179">To edit or specify additional setting for the web services on the Front End pool, modify or specify settings in **Internal Web services** and **External Web services**.</span></span>

<span data-ttu-id="c1f98-180">**내부 웹 서비스**에서는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-180">In **Internal Web services**, specify the following:</span></span>

> [!CAUTION]
> <span data-ttu-id="c1f98-181">프런트 엔드 풀 또는 프런트 엔드 서버를 둘 이상 사용 하는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-181">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="c1f98-182">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 **pool01.contoso.com**로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 **pool01.contoso.com** 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-182">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="c1f98-183">디렉터를 배포 하는 경우에는 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN이 다른 모든 디렉터 또는 디렉터 풀에서 고유 해야 하며 모든 프런트 엔드 풀 또는 프런트 엔드 서버에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-183">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool, as well as from any Front End pool or Front End Server.</span></span> <span data-ttu-id="c1f98-184">내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-184">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director, or Director pool.</span></span>

- <span data-ttu-id="c1f98-p124">**FQDN 다시 정의**를 선택하면 풀의 **내부 웹** 서비스 ID에 대해 다른 FQDN을 지정할 수 있습니다. 기본적으로 프런트 엔드 풀에 정의된 현재 풀 이름이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p124">If you select **Override FQDN**, you can specify a different FQDN for the **Internal Web** services identity on the pool. By default, the setting is the current pool name as defined for the Front End pool.</span></span>

- <span data-ttu-id="c1f98-p125">배포에 필요한 HTTP 및 HTTPS용 수신 대기 및 게시 포트를 지정할 수 있습니다. 기본 설정(HTTP의 경우 포트 80, HTTPS의 경우 포트 443)은 가장 일반적인 설정이므로 조직 내에 특정 요구 사항이 있거나 인프라 디자인에 필요한 경우가 아니면 기본 설정을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p125">Listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed, unless you have specific requirements within your organization and infrastructure design.</span></span>

<span data-ttu-id="c1f98-189">**외부 웹 서비스**에서는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-189">In **External Web services**, specify the following:</span></span>

- <span data-ttu-id="c1f98-p126">외부 웹 서비스의 FQDN을 지정합니다. 여기에 지정되는 FQDN은 일반적으로 외부 연결 요구 사항(예: 역방향 프록시)에 따라 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p126">The FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>

- <span data-ttu-id="c1f98-192">배포에 필요한 HTTP 및 HTTPS용 수신 대기 및 게시 포트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-192">Listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="c1f98-193">처음에는 HTTP의 경우 포트 8080, HTTPS의 경우 포트 4443이 기본 설정으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-193">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="c1f98-194">수신 대기 포트의 이러한 설정은 역방향 프록시 및 외부 네트워크 요구 사항에 따라 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-194">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="c1f98-195">게시된 포트는 기본적으로 HTTP의 경우 포트 80, HTTPS의 경우 포트 443으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-195">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="c1f98-196">이러한 값에 따라 풀에서 들어오는 요청을 수신 대기할 포트가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-196">These values determine what ports the pool will listen for incoming requests.</span></span> <span data-ttu-id="c1f98-197">일반적으로 풀의 포트 요구 사항 충돌이 없는 경우에는 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-197">Typically, these do not need to be changed, unless there is a conflict of port requirements on the pool.</span></span> <span data-ttu-id="c1f98-198">게시된 내부 및 외부 포트에서 동일한 포트 값을 사용하는 것은 이미 예상되는 상황입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-198">Internal and external published ports using the same port values are expected.</span></span> <span data-ttu-id="c1f98-199">즉, 포트가 충돌하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-199">This is not a conflict.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="c1f98-200">중재 서버</span><span class="sxs-lookup"><span data-stu-id="c1f98-200">Mediation Server</span></span>

<span data-ttu-id="c1f98-201">**중재 서버**에서는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-201">In **Mediation Server**, specify the following:</span></span>

- <span data-ttu-id="c1f98-p128">중재 서버를 풀에 배치하려면 **배치된 중재 서버 사용됨** 확인란을 선택합니다. 중재 서버를 배치하지 않도록 선택하면 이 섹션에서 정의할 수 있는 설정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p128">If you collocate the Mediation Server with the pool, select the **Collocated Mediation Server enabled** check box. If you choose not to collocate the Mediation Server, none of the settings are available in this section.</span></span>

- <span data-ttu-id="c1f98-p129">중재 서버 배치를 사용하도록 설정하면 TLS(전송 계층 보안)를 사용하도록 풀 서버의 수신 대기 포트 범위를 정의합니다. 기본적으로 이 포트는 5067입니다. **TCP 포트 사용**을 선택하면 배치된 중재 서버의 TCP(Transmission Control Protocol) 포트를 정의해야 합니다. 이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 PSTN 요구 사항을 참조하여 확인해야 합니다. 기본적으로 TCP 포트 값은 5068입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p129">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

- <span data-ttu-id="c1f98-p130">배치된 중재 서버와 연결된 트렁크를 정의합니다. 이미 트렁크를 정의한 경우 해당 트렁크를 중재 서버와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p130">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span>

- <span data-ttu-id="c1f98-p131">중재 서버에 트렁크가 두 개 이상 연결된 경우 원하는 게이트웨이를 선택하고 **기본값으로 설정**을 클릭하여 기본 트렁크를 지정할 수 있습니다. 기본값으로 설정한 게이트웨이의 선택을 취소하려면 **기본값으로 설정 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p131">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the gateway and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="c1f98-213">프런트 엔드 풀의 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1f98-213">For details about defining and configuring the settings for the Front End pool, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>

## <a name="standard-edition-server"></a><span data-ttu-id="c1f98-214">Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="c1f98-214">Standard Edition Server</span></span>

<span data-ttu-id="c1f98-p132">Standard Edition 서버의 경우 일반, 탄성, 웹 서비스 및 중재 서버 설정을 구성할 수 있습니다. 자세한 내용은 다음과 같은 하위 섹션의 정보를 참조하세요. Standard Edition 서버의 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) 및 [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p132">For a Standard Edition server, you can configure general, resiliency, web services, and Mediation Server settings. For details, see the information in the following subsections. For details about defining and configuring the settings for the Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>

### <a name="general-settings"></a><span data-ttu-id="c1f98-218">일반 설정</span><span class="sxs-lookup"><span data-stu-id="c1f98-218">General Settings</span></span>

<span data-ttu-id="c1f98-219">다음과 같은 일반 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-219">You can configure the following general settings:</span></span>

- <span data-ttu-id="c1f98-220">**FQDN**.</span><span class="sxs-lookup"><span data-stu-id="c1f98-220">**FQDN**.</span></span> <span data-ttu-id="c1f98-221">FQDN은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-221">Note that the FQDN cannot be changed.</span></span> <span data-ttu-id="c1f98-222">Standard Edition 서버와 연결된 FQDN을 변경하려면 Standard Edition 서버를 제거하고 다시 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-222">You must remove and redefine the Standard Edition server to change the FQDN associated with it.</span></span>

- <span data-ttu-id="c1f98-p134">**구성된 모든 IP 주소 사용** 또는 **선택한 IP 주소로 서비스 사용 제한**을 선택합니다. 서비스를 정의된 IP 주소로 제한하도록 선택하는 경우 서버에서 PSTN을 제외한 모든 통신에 사용할 기본 IP 주소를 정의합니다. PSTN에 사용할 별도의 IP 주소를 정의할 수 있습니다. **IPv6 사용**을 선택하여 이 서버에 대해 IPv6을 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p134">Select **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to limit the service to defined IP addresses, you will define the Primary IP address that the server will use for all communications, except for PSTN. You define a separate IP address for PSTN usage. You can also select **Enable IPv6** to enable IPv6 for this server.</span></span>

- <span data-ttu-id="c1f98-p135">**하드웨어 부하 분산 장치 모니터링 포트 사용**. 확인란을 선택하고 하드웨어 부하 분산 장치에서 서버의 상태를 모니터링하는 데 사용할 포트 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p135">**Enable Hardware Load Balancer monitoring port**. Select the check box and enter the port number that your Hardware Load Balancer will use to monitor the state of the server.</span></span>

- <span data-ttu-id="c1f98-p136">**특징 및 기능**에서 이 서버와 배치하려는 추가 역할을 정의합니다. 다음과 같은 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p136">In **Features and Functionality**, define the additional roles that you want to collocate with this server. You can configure the following settings:</span></span>

  - <span data-ttu-id="c1f98-p137">**회의**. 오디오, 비디오 및 응용 프로그램 공유가 포함됩니다. 이 옵션을 선택하면 **전화 접속(PSTN) 회의**를 선택할 수 있습니다. 나중에 중재 서버 설정에서 PSTN 게이트웨이를 지정하고 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p137">**Conferencing**. Includes audio, video and application sharing. After you select this option, you can select **Dial-in (PSTN) conferencing**. You can specify and define a PSTN gateway later under Mediation Server settings.</span></span>

  - <span data-ttu-id="c1f98-235">**Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="c1f98-235">**Enterprise Voice**.</span></span> <span data-ttu-id="c1f98-236">자격 있는 단말기, 장치 및 비즈니스용 Skype 클라이언트에 대 한 내부 음성 over IP 통화를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-236">Enables internal voice over IP calls to qualified handsets and devices and Skype for Business clients.</span></span> <span data-ttu-id="c1f98-237">외부 통화 기능을 사용하도록 설정하려면 중재 서버를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-237">To enable external call capabilities, you need to include a Mediation Server.</span></span> <span data-ttu-id="c1f98-238">자세한 내용은 이 항목 뒷부분의 "중재 서버"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1f98-238">For details, see "Mediation Server" later in this topic.</span></span>

- <span data-ttu-id="c1f98-239">**연결**에서는 다음을 편집하거나 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-239">In **Associations** you can edit or specify the following:</span></span>

  - <span data-ttu-id="c1f98-p139">**SQL Server 저장소**를 프런트 엔드 서버와 연결하려면 SQL Server 저장소를 선택합니다. 미러링을 사용하도록 설정하고 미러링 모니터 서버를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p139">Select **SQL Server store** to associate a SQL Server store with the Front End server. You can also enable mirroring and select a mirroring witness server.</span></span>

  - <span data-ttu-id="c1f98-p140">**파일 공유**. Standard Edition 서버에서 사용 중인 파일 저장소를 수정합니다. 목록에 있는 이미 정의된 저장소 중에서 새 파일 저장소를 선택하거나 **새로 만들기**를 클릭하여 새 파일 저장소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p140">**File share**. Modify the file store that the Standard Edition server is using. You can select a new file store from those already defined by selecting it from the list. You can create a new file store by clicking **New**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c1f98-246">새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-246">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

  - <span data-ttu-id="c1f98-p141">**보관**. 보관 SQL Server 저장소를 Standard Edition 서버와 연결합니다. 목록에 있는 이미 정의된 보관 저장소에서 서버를 선택하거나 **새로 만들기**를 클릭하여 새 보관 저장소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p141">**Archiving**. Associate an Archiving SQL Server store with the Standard Edition server. You can select from an already defined Archiving store by selecting the server from the list, or click **New** to specify a new Archiving store.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c1f98-250">새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-250">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

  - <span data-ttu-id="c1f98-p142">**모니터링(CDR 및 QoE 기준)**. 모니터링 SQL Server 저장소를 Standard Edition 서버와 연결합니다. 목록에 있는 이미 정의된 모니터링 서버에서 서버를 선택하거나 **새로 만들기**를 클릭하여 새 모니터링 서버를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p142">**Monitoring (CDR and QoE metrics**. Associate a Monitoring SQL Server store with the Standard Edition server. You can select from an already defined Monitoring Server by selecting the server from the list, or click **New** to specify a new Monitoring Server.</span></span>

  - <span data-ttu-id="c1f98-p143">**Office Web Apps Server에 풀 연결**. Office Web Apps Server를 프런트 엔드 풀과 연결하려면 이 옵션을 선택합니다. 목록에서 기존 서버를 선택하거나 **새로 만들기**를 클릭하여 새 Office Web Apps Server를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p143">**Associate pool with an Office Web Apps Server**. Select this option to associate an Office Web Apps Server with the Front End pool. Select an existing server from the list, or click **New** to create a new Office Web Apps Server.</span></span>

  - <span data-ttu-id="c1f98-p144">**에지 풀 연결**. 에지 서버를 Standard Edition 서버와 연결합니다. 목록에 있는 이미 정의된 에지 서버 또는 풀에서 서버를 선택하거나 **새로 만들기**를 클릭하여 새 에지 서버 또는 풀을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p144">**Associate Edge pool**. Associate an Edge Server or pool with the Standard Edition server. You can select from an already defined Edge Server or pool by selecting the server from the list, or click **New** to specify a new Edge Server or pool.</span></span>

### <a name="resiliency"></a><span data-ttu-id="c1f98-260">탄성</span><span class="sxs-lookup"><span data-stu-id="c1f98-260">Resiliency</span></span>

<span data-ttu-id="c1f98-p145">탄성은 서버에 대해 재해 복구 및 고가용성을 제공합니다. 백업을 제공하는 경우 기본 서버에 오류가 발생하면 백업 서버가 작업을 대신 수행하므로 사용자가 로그인 및 통신할 수 있습니다. 함께 오류가 발생한 시스템에 따라서는 사용자의 기능이 축소될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p145">Resiliency provides disaster recovery and high availability for the server. By providing a backup, if the primary server fails, the backup can take over, enabling users to sign in and communicate. It is possible that there will be reduced functionality for users, depending on what systems have also failed.</span></span>

<span data-ttu-id="c1f98-p146">목록에서 서버의 백업으로 작동하도록 할 프런트 엔드 풀 또는 Standard Edition 서버를 선택합니다. 장애 조치(failover) 및 대체 시간 간격을 설정하도록 선택할 수도 있습니다. 장애 조치(failover) 및 대체 시간 간격(초)을 설정하면 오류가 발생한 등록자를 자동으로 감지하고 대체 시간 동안 기본 서버가 백업되는지 자동으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p146">From the list, select the Front End pool or Standard Edition server that will act as the backup for the server. You can also select to enable Failover and Fallback time intervals. Enabling the failover and fallback time settings (specified in seconds) enables automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1f98-p147">실패 검색 및 대체 간격을 정의할 경우, 서버가 잠깐 동안 응답하지 않을 때 장애 조치(failover) 및 대체가 수행되지 않도록 충분한 간격을 입력해야 합니다. 풀이나 서버를 로드하는 시간에 따라 기본 서버가 잠깐 동안 응답하지 않을 수도 있습니다. 장애 조치(failover) 및 대체의 기본값은 풀 간의 경우 300초, 풀과 Standard Edition 서버 간의 경우 600초입니다. 사이트의 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버와 풀 또는 Standard Edition 서버 간의 장애 조치(failover) 기본값은 120초, 대체 기본값은 240초입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p147">When defining the Failure detection and the Fallback interval, you should be careful not to enter an interval that will cause the failover and fallback to occur if the server should fail to respond for a short period of time. It is possible that the primary server may not respond for short periods of time, based on the loading of the pool or servers. The default values for the failover and fallback are 300 seconds and 600 seconds for pool to pool, or pool to Standard Edition server. In the event of a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition server, the default values are 120 seconds for failover and 240 seconds for fallback.</span></span>

### <a name="web-services"></a><span data-ttu-id="c1f98-271">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="c1f98-271">Web Services</span></span>

<span data-ttu-id="c1f98-272">서버의 웹 서비스에 대한 추가 설정을 편집하거나 지정하려면 **내부 웹 서비스** 및 **외부 웹 서비스**의 설정을 수정하거나 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-272">To edit or specify additional setting for the web services on the server, modify or specify settings in **Internal Web services** and **External Web services**.</span></span>

<span data-ttu-id="c1f98-273">**내부 웹 서비스**에 대해 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-273">For **Internal Web services**, you can specify the following:</span></span>

- <span data-ttu-id="c1f98-p148">FQDN 다시 정의를 선택하면 서버의 내부 웹 서비스 ID에 대해 다른 FQDN을 지정할 수 있습니다. 기본적으로 Standard Edition 서버에 정의된 현재 서버 이름이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p148">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the server. By default, the setting is the current server name as defined for the Standard Edition server.</span></span>

- <span data-ttu-id="c1f98-p149">배포에 필요한 HTTP 및 HTTPS용 수신 대기 및 게시 포트를 지정할 수 있습니다. 기본 설정(HTTP의 경우 포트 80, HTTPS의 경우 포트 443)은 가장 일반적인 설정이므로 조직 내에 특정 요구 사항이 있거나 인프라 디자인에 필요한 경우가 아니면 기본 설정을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p149">Listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings, and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>

<span data-ttu-id="c1f98-278">**외부 웹 서비스**에 대해 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-278">For **External Web services**, you can specify the following:</span></span>

- <span data-ttu-id="c1f98-p150">외부 웹 서비스의 FQDN을 지정합니다. 여기에 지정되는 FQDN은 일반적으로 외부 연결 요구 사항(예: 역방향 프록시)에 따라 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p150">The FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>

- <span data-ttu-id="c1f98-p151">배포에 필요한 HTTP 및 HTTPS용 수신 대기 포트를 지정할 수 있습니다. 처음에는 HTTP의 경우 포트 8080, HTTPS의 경우 포트 4443이 기본 설정으로 정의됩니다. 수신 대기 포트의 이러한 설정은 역방향 프록시 및 외부 네트워크 요구 사항에 따라 변경할 수 있습니다. 이러한 값에 따라 서버에서 들어오는 요청을 수신 대기할 포트가 결정됩니다. 일반적으로 서버에서 포트 요구 사항이 충돌하지 않는 한 이러한 설정을 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p151">Listening ports for HTTP and HTTPS that your deployment requires. The default setting of port 8080 for HTTP and port 4443 for HTTPS is defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. These values determine what ports the server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the server.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="c1f98-286">중재 서버</span><span class="sxs-lookup"><span data-stu-id="c1f98-286">Mediation Server</span></span>

<span data-ttu-id="c1f98-287">**중재 서버**에 대해 다음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-287">For **Mediation Server**, you can specify the following:</span></span>

- <span data-ttu-id="c1f98-p152">중재 서버를 서버에 배치하려면 **배치된 중재 서버 사용됨** 확인란을 선택합니다. 중재 서버를 배치하지 않도록 선택하면 이 섹션에서 정의할 수 있는 설정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p152">If you collocate the Mediation Server with the server, select the check box **Collocated Mediation Server enabled**. If you choose not to collocate the Mediation Server, none of the settings are available in this section.</span></span>

- <span data-ttu-id="c1f98-p153">중재 서버 배치를 사용하도록 설정하면 TLS를 사용하도록 서버의 수신 대기 포트 범위를 정의할 수 있습니다. 기본적으로 이 포트는 5067입니다. **TCP 포트 사용**을 선택하면 배치된 중재 서버의 TCP 포트를 정의해야 합니다. 이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 PSTN 요구 사항을 참조하여 확인해야 합니다. 기본적으로 TCP 포트 값은 5068입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p153">If you have enabled the collocation of the Mediation Server, you define the listening port range on the server for TLS. By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

- <span data-ttu-id="c1f98-p154">배치된 중재 서버와 연결된 트렁크를 정의합니다. 이미 트렁크를 정의한 경우 해당 트렁크를 중재 서버와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p154">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span>

- <span data-ttu-id="c1f98-p155">중재 서버에 게이트웨이가 두 개 이상 연결된 경우 원하는 게이트웨이를 선택하고 **기본값으로 설정**을 클릭하여 기본 게이트웨이를 지정할 수 있습니다. 기본값으로 설정한 게이트웨이의 선택을 취소하려면 **기본값으로 설정 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f98-p155">If you have more than one gateway associated with a Mediation Server, you can specify a default gateway by selecting the gateway and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="c1f98-299">Standard Edition 서버의 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) 및 [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1f98-299">For details about defining and configuring the settings for the Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


