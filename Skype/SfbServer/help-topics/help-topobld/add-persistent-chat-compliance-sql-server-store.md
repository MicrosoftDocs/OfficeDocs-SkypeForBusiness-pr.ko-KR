---
title: 영구 채팅 준수 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 영구 채팅 SQL Server 또는 영구 채팅 서버 준수 기능에 대한 데이터베이스를 제공할 준수 저장소를 구성합니다.
ms.openlocfilehash: 1f931df0135e857b53a8067b114e3f9f438c614c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818698"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="6fd36-103">영구 채팅 준수 SQL Server 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="6fd36-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="6fd36-104">영구 채팅 SQL Server 또는 영구 채팅 서버 준수 기능에 대한 데이터베이스를 제공할 준수 저장소를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="6fd36-105">**SQL Server 저장소:** 기존 SQL Server 영구 채팅 인스턴스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="6fd36-106">새로 **고치려면** 새 SQL Server 영구 채팅 준수 데이터에 대한 새 인스턴스(선택 사항)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="6fd36-107">저장소 **SQL Server** 사용 확인란을 선택하여 SQL Server 데이터베이스 및 영구 채팅 준수 데이터에 대한 미러된 데이터베이스를 제공할 선택적 인스턴스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="6fd36-108">영구 채팅  준수 정책에 SQL Server 미러링 SQL Server 미러로 사용할 SQL Server 및 선택적 인스턴스를 저장하는 미러링 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fd36-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="6fd36-109">새로 **고침을** 클릭하여 새 SQL Server 영구 채팅 서버 미러링에 대한 새 SQL Server 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="6fd36-110">장애 조치(failover) 시나리오에서 미러링 모니터 서버로 사용할 SQL Server를 **자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용** 목록에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="6fd36-111">미러링된 서버는 영구 채팅 서버에 대한 데이터를 미러링하거나 호스팅하지 않지만 미러된 SQL Server 서버 하나만 활성 SQL Server 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="6fd36-112">새로 **고침을** 클릭하여 미러링 SQL Server 미러링된 영구 채팅 준수에 대한 인스턴스를 선택적으로 SQL Server 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="6fd36-113">이전 풀 정의 대화 상자로 돌아가려면 **뒤로** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="6fd36-114">이 **풀의** 백업 저장소 구성에 대한 옵션 입력을 완료하고 SQL Server 채팅 서버 풀 정의를 계속하려면 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="6fd36-115">모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="6fd36-116">이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd36-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6fd36-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fd36-117">See also</span></span>

[<span data-ttu-id="6fd36-118">비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="6fd36-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="6fd36-119">비즈니스용 Skype 서버 2015에 대한 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6fd36-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="6fd36-120">영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항(비즈니스용 Skype 서버 2015)</span><span class="sxs-lookup"><span data-stu-id="6fd36-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="6fd36-121">비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대한 준수 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="6fd36-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
