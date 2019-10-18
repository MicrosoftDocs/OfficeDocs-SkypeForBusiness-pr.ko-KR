---
title: Microsoft 팀의 보존 정책에 대 한 알려진 문제점
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Microsoft 팀 보존 정책에 대 한 알려진 문제점의 현재 목록입니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a7dd5bac7c82814befab66247b1bfa8cf4943f6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569965"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="460c8-103">Microsoft 팀의 보존 정책에 대 한 알려진 문제점</span><span class="sxs-lookup"><span data-stu-id="460c8-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="460c8-104">다음은 추적 및 조사 중인 팀의 보존 정책에 대 한 알려진 문제점입니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="460c8-105">팀 채널 메시지 위치 행의 팀 선택에서 팀이 아닌 Office 365 그룹이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="460c8-106">이 문제는 향후 해결 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="460c8-107">팀 채팅 위치 행의 사용자 선택에서 게스트 및 사서함이 아닌 사용자가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="460c8-108">보존 정책은 게스트에 대해 설정 되지 않으며, 목록에서 제거 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="460c8-109">ELC (Exchange 수명 주기 도우미)는 매일 실행 되지만 SLA는 7 일입니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="460c8-110">따라서 팀 보존 정책에서 60 일 보다 오래 된 항목을 삭제 하는 경우 이러한 항목은 최대 67 일 동안 유지 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="460c8-111">이는 Exchange 모델을 따르는 새로운 상황이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="460c8-112">물론 대부분의 경우에는 지연이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![결정 지점을 나타내는 아이콘](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="460c8-114">판단 요점</span><span class="sxs-lookup"><span data-stu-id="460c8-114">Decision point</span></span>         |<span data-ttu-id="460c8-115">조직에서 필요로 하는 보안 및 준수 기능은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="460c8-115">What security and compliance features does your organization require?</span></span> <span data-ttu-id="460c8-116">조직에 보안 및 규정 준수 업무 요구 사항을 충족 하는 데 필요한 라이선스가 있나요?</span><span class="sxs-lookup"><span data-stu-id="460c8-116">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![다음 단계를 나타내는 아이콘](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="460c8-118">다음 단계</span><span class="sxs-lookup"><span data-stu-id="460c8-118">Next steps</span></span>         |<span data-ttu-id="460c8-119">필요한 보안 및 준수 기능을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="460c8-119">Document your required security and compliance features.</span></span>         |
