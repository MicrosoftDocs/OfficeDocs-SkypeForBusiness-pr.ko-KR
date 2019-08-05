---
title: Skype 대화방 시스템 계정 관리
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Skype 대화방 시스템 계정을 관리 하는 방법에 대해 알아보려면이 항목을 읽으십시오.
ms.openlocfilehash: 5276bd1f2b74000e681efadd8961b9c048351c3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196389"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="e41ba-103">Skype 대화방 시스템 계정 관리</span><span class="sxs-lookup"><span data-stu-id="e41ba-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="e41ba-104">Skype 대화방 시스템 계정을 관리 하는 방법에 대해 알아보려면이 항목을 읽으십시오.</span><span class="sxs-lookup"><span data-stu-id="e41ba-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="e41ba-105">Microsoft 팀 대화방은 서로 다른 종속성 및 배포 절차와 다른 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="e41ba-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="e41ba-106">Microsoft 팀 대화방에 대 한 자세한 내용은 Microsoft 팀 대화방 [관리 개요](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e41ba-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="e41ba-107">풀 간에 Skype 대화방 시스템 계정 이동</span><span class="sxs-lookup"><span data-stu-id="e41ba-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="e41ba-108">Skype 대화방 시스템 계정을 한 대의 비즈니스용 Skype 서버 풀에서 다른 서버로 이동 해야 하는 경우 (예: 업그레이드 중) 다음 명령을 사용 하 여 Skype 대화방 시스템 계정 풀을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41ba-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="e41ba-109">비즈니스용 Skype 서비스의 Skype 대화방 시스템 계정 사용 중지</span><span class="sxs-lookup"><span data-stu-id="e41ba-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="e41ba-110">비즈니스용 skype Server 풀의 비즈니스용 Skype 서비스에서 기존 Skype 대화방 시스템 계정을 사용 하지 않도록 설정 해야 하는 경우 다음 명령을 사용 하 여 계정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41ba-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="e41ba-111">선택 사항: Active Directory에서 Skype 채팅방 시스템 관리자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="e41ba-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="e41ba-112">도메인에 가입한 각 Skype 룸 시스템 클라이언트는 Skype 룸 시스템 기기 PC에 대 한 로컬 관리자 권한이 있는 도메인 사용자에 의해 완전히 관리 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41ba-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="e41ba-113">따라서 Active Directory에 전용 관리자 그룹을 만들고 새 Skype 채팅방 시스템 시스템 설정 중에이 그룹의 관리자 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41ba-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

