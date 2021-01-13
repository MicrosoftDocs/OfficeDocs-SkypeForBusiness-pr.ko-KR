---
title: Skype 룸 시스템 계정 관리
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 이 항목을 읽고 Skype 채팅방 시스템 계정을 관리하는 방법을 배워 읽습니다.
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805558"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="c13cd-103">Skype 룸 시스템 계정 관리</span><span class="sxs-lookup"><span data-stu-id="c13cd-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="c13cd-104">이 항목을 읽고 Skype 채팅방 시스템 계정을 관리하는 방법을 배워 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c13cd-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="c13cd-105">Microsoft Teams 룸은 종속성 및 배포 절차가 서로 다른 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="c13cd-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="c13cd-106">Microsoft Teams 룸에 대한 자세한 내용은 Microsoft Teams 룸 관리 [개요를 참조하세요.](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)</span><span class="sxs-lookup"><span data-stu-id="c13cd-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="c13cd-107">풀 간에 Skype 룸 시스템 계정 이동</span><span class="sxs-lookup"><span data-stu-id="c13cd-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="c13cd-108">비즈니스용 Skype 서버 풀의 Skype 룸 시스템 계정을 다른 풀로 이동해야 하는 경우(예: 업그레이드 중) 다음 명령을 사용하여 Skype 룸 시스템 계정 풀을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c13cd-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="c13cd-109">비즈니스용 Skype 서비스에 대해 Skype 룸 시스템 계정을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="c13cd-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="c13cd-110">비즈니스용 Skype 서버 풀의 비즈니스용 Skype 서비스에서 기존 Skype 룸 시스템 계정을 사용하지 않도록 설정해야 하는 경우 다음 명령을 사용하여 계정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c13cd-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="c13cd-111">선택 사항: Active Directory에서 Skype 룸 시스템 관리자 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="c13cd-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="c13cd-112">도메인에 가입하는 각 Skype 룸 시스템 클라이언트는 Skype 룸 시스템 어플라이언스 PC에서 로컬 관리자 권한이 있는 도메인 사용자가 완전히 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13cd-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="c13cd-113">따라서 Active Directory에서 전용 관리자 그룹을 만들고 새 Skype 룸 시스템 시스템을 설정하는 동안 이 그룹에 관리 권한을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13cd-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

