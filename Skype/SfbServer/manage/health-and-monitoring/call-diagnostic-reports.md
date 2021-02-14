---
title: 비즈니스용 Skype 서버의 통화 진단 보고서
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
description: '요약: 비즈니스용 Skype 서버에서 사용되는 다중 사용자 통화 진단 보고서에 대해 자세히 알아보습니다.'
ms.openlocfilehash: f64f708832f01b4d1d7859b050ffe6687f11ffdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826508"
---
# <a name="call-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="bc428-103">비즈니스용 Skype 서버의 통화 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="bc428-103">Call Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="bc428-104">**요약:** 비즈니스용 Skype 서버에서 사용되는 다중 사용자 통화 진단 보고서에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-104">**Summary:** Learn about the multi-user Call Diagnostic Reports used in Skype for Business Server.</span></span>
  
<span data-ttu-id="bc428-105">통화 진단 보고서는 피어 투 피어 및 회의 세션에 대해 요약 정보 및 진단 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-105">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="bc428-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="bc428-106">In this section</span></span>

- <span data-ttu-id="bc428-107">[비즈니스용 Skype 서버의 통화 진단 요약 보고서](summary-report.md) 실패한 피어 투 피어 세션 및 회의 세션에 대한 전체 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-107">[Call Diagnostic Summary Report in Skype for Business Server](summary-report.md) Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="bc428-108">피어 투 피어 세션은 두 참가자만 참여하는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-108">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="bc428-109">회의 세션에는 참가자가 3명 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-109">Conferencing sessions involve three or more participants.</span></span>
    
- <span data-ttu-id="bc428-110">[비즈니스용 Skype](peer-to-peer-activity-diagnostic-report.md) 서버의 피어 투 피어 활동 진단 보고서 실패한 피어 투 피어 세션에 대한 전체 추세 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-110">[Peer-to-Peer Activity Diagnostic Report in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md) Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="bc428-111">피어 투 피어 세션에는 두 참가자만 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-111">A peer-to-peer session involves just two participants.</span></span>
    
- <span data-ttu-id="bc428-112">[비즈니스용 Skype 서버의 전화 회의 진단 보고서](conference-diagnostic-report.md) 실패한 회의 세션에 대한 전체 추세 보기와 각 회의의 추세 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-112">[Conference Diagnostic Report in Skype for Business Server](conference-diagnostic-report.md) Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="bc428-113">회의 세션에는 참가자가 3명 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-113">Conferencing sessions involve at least three participants.</span></span>
    
- <span data-ttu-id="bc428-114">[비즈니스용 Skype 서버의 상위 오류 보고서](top-failures-report.md) 시간 경과에 따라 가장 자주 발생하는 오류 및 추세 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-114">[Top Failures Report in Skype for Business Server](top-failures-report.md) Provides a list of the most frequent failures and their trends over time.</span></span>
    
- <span data-ttu-id="bc428-115">[비즈니스용 Skype 서버의 오류 배포 보고서](failure-distribution-report.md) 실패한 세션에 대한 분석을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-115">[Failure Distribution Report in Skype for Business Server](failure-distribution-report.md) Provides an analysis of failed sessions.</span></span>
    
- <span data-ttu-id="bc428-116">[비즈니스용 Skype 서버의 오류 목록 보고서](failure-list-report.md) 실패한 회의에 참가한 개별 참가자에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-116">[Failure List Report in Skype for Business Server](failure-list-report.md) Provides detailed information about the individual participants involved in a failed conference.</span></span>
    
- <span data-ttu-id="bc428-117">[비즈니스용 Skype 서버의 진단 보고서](diagnostic-report.md) 실패한 세션에 대한 진단 및 문제 해결 정보(SIP 응답 코드 및 진단 헤더 및 ID 포함)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc428-117">[Diagnostic Report in Skype for Business Server](diagnostic-report.md) Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>
    

