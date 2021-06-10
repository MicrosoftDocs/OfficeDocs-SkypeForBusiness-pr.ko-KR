---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 직접 라우팅 호출 알림
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341799"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="5e89c-103">통화 알림 관리</span><span class="sxs-lookup"><span data-stu-id="5e89c-103">Manage call notifications</span></span>

<span data-ttu-id="5e89c-104">이 문서에서는 사용자의 통화 알림을 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="5e89c-105">PBX(개인 분기)Teams(PBX) 또는 세션 경계 컨트롤러(Exchange)에 대해 호출 엔드포인트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="5e89c-106">이 기능은 사용자의 휴대폰 및 책상 전화에 동시에 전화를 보내고자 하는 경우와 같은 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="5e89c-107">다음 다이어그램에서 사용자 Irena에는 두 개의 엔드포인트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="5e89c-108">Teams 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="5e89c-108">A Teams endpoint</span></span>
- <span data-ttu-id="5e89c-109">타사 SBC에 연결된 SIP 전화</span><span class="sxs-lookup"><span data-stu-id="5e89c-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="5e89c-110">호출이 도착하면 SBC는 직접 라우팅과 타사 전화 시스템 간에 호출을 포크합니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![포크된 엔드포인트를 Teams 다이어그램](media/direct-routing-call-notification-1.png)

<span data-ttu-id="5e89c-112">Fork 2에서 호출이 수락된 경우(타사 SBC에서) Teams "부재 중 전화" 알림이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="5e89c-113">다음과 같이 포크 1에서 취소를 보내기 위해 SBC를 구성하여 "부재 중 전화" 알림을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="5e89c-114">이유: SIP; cause=200;text"call completed elsewhere"</span><span class="sxs-lookup"><span data-stu-id="5e89c-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="5e89c-115">호출은 성공한 호출로 Microsoft 전화 시스템의 통화 세부 정보 레코드에 등록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="5e89c-116">호출은 최종 SIP 코드 "487", 최종 Microsoft 하위 코드 "540200", 최종 SIP 코드 구 "다른 곳에서 완료된 호출"으로 "시도"로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>  <span data-ttu-id="5e89c-117">(통화 세부 정보 레코드를 확인하려면 관리 Teams, 분석 및 보고서, 사용 현황 보고서를 이동하고 PSTN 사용량을 선택합니다.)</span><span class="sxs-lookup"><span data-stu-id="5e89c-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="5e89c-118">아래 다이어그램에서는 Fork 1용 SIP 사다리에 대해 설명하고, 호출 흐름 및 취소 메시지에서 예상된 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e89c-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![포크된 엔드포인트를 Teams 다이어그램](media/direct-routing-call-notification-2.png)
