---
title: 영구 채팅 백업 SQL Server 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 백업 데이터베이스를 제공 하는 백업 SQL Server 저장소를 구성 합니다.
ms.openlocfilehash: 39e5e1ead6ed3cb089545406852de16170d782dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197535"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="1ee52-103">영구 채팅 백업 SQL Server 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="1ee52-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="1ee52-104">영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 백업 데이터베이스를 제공 하는 백업 SQL Server 저장소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="1ee52-105">**Sql server 스토어**: 기존 SQL server를 선택 하 고 필요에 따라 영구 채팅 인스턴스를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="1ee52-106">**새로 만들기** 를 클릭 하 여 새 SQL Server를 정의 하 고 선택적으로 영구 채팅 백업 데이터에 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="1ee52-107">Sql server **스토어 미러링 사용** 확인란을 선택 하 여 sql server 데이터베이스와 영구 채팅 백업 데이터에 미러된 데이터베이스를 제공할 선택적 인스턴스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="1ee52-108">목록 미러링 sql server **저장소** 에서 영구 채팅 백업 sql SERVER의 sql server 미러 역할을 하는 sql server 및 선택적 인스턴스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="1ee52-109">**새로 만들기** 를 클릭 하 여 새 sql server를 정의 하 고 선택적으로 영구 채팅 SQL server 미러링에 대 한 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="1ee52-110">장애 조치(failover) 시나리오에서 미러링 모니터 서버로 사용할 SQL Server를 **자동 장애 조치(failover)를 사용하려면 SQL Server 미러링 모니터 서버 사용** 목록에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="1ee52-111">미러링 모니터 서버는 영구 채팅 서버에 대 한 데이터를 미러링 또는 호스팅하지 않으며, 미러링된 구성에서 한 SQL Server만 언제 든 지 활성 SQL 서버를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="1ee52-112">**새로 만들기** 를 클릭 하 여 새 sql server 감시를 정의 합니다 (선택적으로 영구 채팅 백업 SQL server 미러링 감시 용 인스턴스).</span><span class="sxs-lookup"><span data-stu-id="1ee52-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="1ee52-113">이전 풀 정의 대화 상자로 돌아가려면 **뒤로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="1ee52-114">이 풀의 백업 SQL Server 저장소 구성에 대 한 옵션을 모두 입력 하 고 영구 채팅 서버 풀 정의를 진행 하려면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="1ee52-115">모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="1ee52-116">이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ee52-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ee52-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ee52-117">See also</span></span>

[<span data-ttu-id="1ee52-118">비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="1ee52-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="1ee52-119">비즈니스용 Skype 서버 2015의 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ee52-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="1ee52-120">영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ee52-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="1ee52-121">영구 채팅 서버를 위한 고가용성 및 재해 복구 구성</span><span class="sxs-lookup"><span data-stu-id="1ee52-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
