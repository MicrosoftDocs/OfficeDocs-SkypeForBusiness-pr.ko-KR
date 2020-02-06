---
title: 영구 채팅 풀에 대한 속성 및 옵션 정의
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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 다음 속성을 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 옵션을 구성 합니다.
ms.openlocfilehash: 39816bcc4c76a5be07e90c63dfa9064c4a0670d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820190"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="52c76-103">영구 채팅 풀에 대한 속성 및 옵션 정의</span><span class="sxs-lookup"><span data-stu-id="52c76-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="52c76-104">다음 속성을 정의 하 여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대 한 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="52c76-105">**영구 채팅 풀의 표시 이름**:이 영구 채팅 서버 또는 영구 채팅 서버 풀에 대해 표시 되는 사용자 친근 한 이름을 정의 하는 필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="52c76-106">**영구 채팅 포트**:이 영구 채팅 서버 또는 영구 채팅 서버 풀이 수신 대기할 포트 번호를 정의 하는 필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="52c76-107">**준수 사용**: 선택적 영구 채팅 준수 기능 및 데이터베이스를 배포 하 고 구현 하려는 경우 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="52c76-108">**백업 Sql server 저장소를 사용 하 여 장애 복구**를 사용 하도록 설정 하려면 다음을 수행 합니다. 다른 sql server에 저장소의 구성 된 백업 집합에서 영구 채팅 SQL Server 저장소의 재난 복구를 배포 하 고 구현 하려는 경우이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="52c76-109">자세한 내용은 비즈니스용 [Skype 서버 2015에서 영구 채팅 서버용으로 고가용성 및 재해 복구 구성을](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="52c76-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="52c76-110">이 옵션은 서버가 여러 개 포함된 풀에 대해서만 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="52c76-111">이 **풀을이 서버 또는 풀을 \<구성\>하는 사이트 사이트의 기본값으로 사용**:이 확인란을 해당 사이트의 기본 영구 채팅 서버 또는 영구 채팅 서버 풀로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="52c76-112">기본 영구 채팅 서버 또는 사이트 당 pol 하나 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="52c76-113">토폴로지에 사이트가 여러 개 포함되는 경우에는 **이 풀을 모든 사이트의 기본 풀로 사용** 확인란도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="52c76-114">이전 풀 정의 대화 상자로 돌아가려면 **뒤로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="52c76-115">이 풀에 대 한 옵션을 모두 입력 하 고 영구 채팅 서버 풀 정의를 진행 하는 과정을 완료 한 후 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="52c76-116">모든 변경 내용을 취소하고 **새 영구 채팅 풀 정의** 마법사를 종료하려면 **취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="52c76-117">이 페이지와 같은 상황에 맞는 도움말에 액세스하려면 **도움말**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="52c76-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52c76-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52c76-118">See also</span></span>

[<span data-ttu-id="52c76-119">비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="52c76-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="52c76-120">비즈니스용 Skype Server 2015 토폴로지에 영구 채팅 서버 추가</span><span class="sxs-lookup"><span data-stu-id="52c76-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
