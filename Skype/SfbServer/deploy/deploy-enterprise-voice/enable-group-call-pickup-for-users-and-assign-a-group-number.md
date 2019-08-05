---
title: 비즈니스용 Skype에서 그룹 통화 픽업으로 사용자를 설정 하 고 그룹 번호를 할당 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 사용자가 사용 하도록 설정 하 고 그룹 번호를 할당 합니다.
ms.openlocfilehash: 14f17d3e217fa9ea44cc81db4d8fa6bf12644894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192072"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="bcfd8-103">비즈니스용 Skype에서 그룹 통화 픽업으로 사용자를 설정 하 고 그룹 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="bcfd8-104">비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 사용자가 사용 하도록 설정 하 고 그룹 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="bcfd8-105">통화 번호 궤도 테이블에 통화 픽업 그룹 번호를 추가한 후에는 SEFAUtil 도구를 사용 하 여 그룹 번호를 사용자에 게 할당 하 고 그룹 통화 픽업 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="bcfd8-106">하이브리드 배포의 경우 그룹 통화 픽업 그룹을 온라인 상태인 사용자에 게 할당 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="bcfd8-107">홈 인터넷에 연결 된 사용자는 그룹 통화 픽업에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="bcfd8-108">즉, 다른 사용자가 해당 통화에 대 한 응답을 받을 수 없으며 다른 사용자에 게 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="bcfd8-109">그룹 번호를 할당 하 고 사용자에 대 한 그룹 통화 픽업 기능을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="bcfd8-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="bcfd8-110">관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="bcfd8-111">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-111">At the command line, run:</span></span>

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="bcfd8-112">예를 들어 사용자에 게 그룹 번호 199를 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-112">For example, to assign group number 199 to a user:</span></span>

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="bcfd8-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcfd8-113">See also</span></span>

[<span data-ttu-id="bcfd8-114">사용자 용 그룹 픽업 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="bcfd8-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

