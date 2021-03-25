---
title: 사용자에 대해 그룹 통화 Pickup을 사용하도록 설정하고 비즈니스용 Skype에서 그룹 번호 할당
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 사용자가 비즈니스용 Skype 서버에서 그룹 통화 Enterprise Voice 사용하도록 설정하고 그룹 번호를 할당합니다.
ms.openlocfilehash: 5469e9634e16b855993518092114184a2dca7359
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111834"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="fdcfe-103">사용자에 대해 그룹 통화 Pickup을 사용하도록 설정하고 비즈니스용 Skype에서 그룹 번호 할당</span><span class="sxs-lookup"><span data-stu-id="fdcfe-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="fdcfe-104">사용자가 비즈니스용 Skype 서버에서 그룹 통화 Enterprise Voice 사용하도록 설정하고 그룹 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfe-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="fdcfe-105">통화 파킹된 통화 번호 테이블에 통화 Pickup 그룹 번호를 추가한 후 SEFAUtil 도구를 사용하여 사용자에게 그룹 번호를 할당하고 그룹 통화 Pickup을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfe-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="fdcfe-106">하이브리드 배포에서는 온라인에 있는 사용자에게 그룹 통화 선택 그룹을 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfe-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="fdcfe-107">온라인에 있는 사용자는 그룹 통화 Pickup에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfe-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="fdcfe-108">즉, 다른 사용자가 통화에 응답할 수 있으며 다른 사용자의 통화에 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfe-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="fdcfe-109">그룹 번호를 할당하고 사용자에 대해 그룹 통화 선택을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fdcfe-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="fdcfe-110">관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfe-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="fdcfe-111">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfe-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="fdcfe-112">예를 들어 사용자에게 그룹 번호 199를 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="fdcfe-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="fdcfe-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fdcfe-113">See also</span></span>

[<span data-ttu-id="fdcfe-114">사용자에 대해 그룹 선택 사용 안 하게 설정</span><span class="sxs-lookup"><span data-stu-id="fdcfe-114">Disable Group Pickup for Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)