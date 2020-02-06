---
title: 영구 채팅 준수 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 영구 채팅 서버 또는 영구적 채팅 서버 준수 기능에 대 한 데이터베이스를 제공 하는 준수 SQL Server 저장소를 구성 합니다.
ms.openlocfilehash: fd51b3d582c915d02799f2f633869e84f3659c4f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820690"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="0156f-103">영구 채팅 준수 SQL Server 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="0156f-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="0156f-104">영구 채팅 서버 또는 영구적 채팅 서버 준수 기능에 대 한 데이터베이스를 제공 하는 준수 SQL Server 저장소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="0156f-105">**Sql server 스토어**: 기존 SQL server를 선택 하 고 필요에 따라 영구 채팅 인스턴스를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="0156f-106">**새로 만들기** 를 클릭 하 여 새 SQL Server를 정의 하 고 필요에 따라 영구 채팅 준수 데이터에 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="0156f-107">Sql server **스토어 미러링 사용** 확인란을 선택 하 여 sql server 데이터베이스를 구성 하 고 지속적인 채팅 준수 데이터에 미러된 데이터베이스를 제공 하는 선택적 인스턴스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="0156f-108">영구 채팅 준수 SQL Server에 대 한 SQL server 미러 역할을 하는 목록 미러링 sql server **저장소** 의 sql server 및 선택적 인스턴스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="0156f-109">**새로 만들기** 를 클릭 하 여 새 sql server를 정의 하 고 선택적으로 영구 채팅 SQL server 미러링에 대 한 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="0156f-110">장애 조치(failover) 시나리오에서 미러링 모니터 서버로 사용할 SQL Server를 **자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용** 목록에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="0156f-111">미러링 모니터 서버는 영구 채팅 서버에 대 한 데이터를 미러링 또는 호스팅하지 않으며, 미러링된 구성에서 한 SQL Server만 언제 든 지 활성 SQL 서버를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="0156f-112">**새로 만들기** 를 클릭 하 여 새 sql server 미러링 (선택적으로 지속적인 채팅 준수 SQL server 미러링 모니터에 대 한 인스턴스)을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="0156f-113">이전 풀 정의 대화 상자로 돌아가려면 **뒤로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="0156f-114">이 풀의 백업 SQL Server 저장소 구성에 대 한 옵션을 모두 입력 하 고 영구 채팅 서버 풀 정의를 진행 하려면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="0156f-115">모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="0156f-116">이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0156f-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0156f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0156f-117">See also</span></span>

[<span data-ttu-id="0156f-118">비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="0156f-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="0156f-119">비즈니스용 Skype 서버 2015의 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0156f-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="0156f-120">영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0156f-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="0156f-121">영구 채팅 서버에 대한 준수 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="0156f-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
