---
title: Microsoft Teams 모니터링 및 경고
author: vaibhav
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 사용할 수 있는 Teams 경고 및 알림 기능에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1be3ca52d4b03cfbf82d82310148ef4c2bb7f06d
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819493"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="595dc-103">Microsoft Teams 모니터링 및 경고</span><span class="sxs-lookup"><span data-stu-id="595dc-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="595dc-104">Microsoft Teams에 대한 새로운 모니터링 및 경고 기능은 Teams 관리 센터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="595dc-105">Teams 관리 센터의 알림  & 섹션에서 사용할 수 있는 다양한 규칙 집합을 사용하여 Teams 기능을 모니터링하고 경고를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="595dc-106">예를 들어 예기치 않게 오프라인으로 전환되는 경우 IP Phone, 공동 작업 막대 등의 Teams 디바이스의 상태도 적극적으로 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="595dc-107">조직에서는 Teams 모니터링 및 경고를 사용하여 다음 항목을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="595dc-108">Teams 기능 자동으로 관리</span><span class="sxs-lookup"><span data-stu-id="595dc-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="595dc-109">예기치 않은 무언가가 표시될 경우 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="595dc-110">수정 작업을 수행하여 작업을 다시 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="595dc-111">모니터링 및 경고를 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="595dc-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="595dc-112">경고 규칙을 구성하려면 Microsoft 365의 전역 관리자 또는 Teams 서비스 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="595dc-113">Teams [관리자 역할을](../using-admin-roles.md) 사용하여 Teams 관리에 대해 자세히 알아보고 각 관리자 역할에 액세스할 수 있는 보고를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="595dc-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="595dc-114">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="595dc-115">왼쪽 탐색에서 알림 & **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="595dc-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="595dc-116">규칙 에서 구성할 규칙을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="595dc-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="595dc-117">팀 모니터링 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="595dc-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="595dc-118">다양한 모니터링 기능과 구성 기능을 추가하여 Teams 모니터링 환경을 계속 추가하고 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="595dc-119">다음은 Teams 관리 센터에서 현재 사용할 수 있는 Teams 모니터링 규칙 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="595dc-120">규칙</span><span class="sxs-lookup"><span data-stu-id="595dc-120">Rule</span></span>  |<span data-ttu-id="595dc-121">모니터링 기능</span><span class="sxs-lookup"><span data-stu-id="595dc-121">Monitoring capability</span></span>|<span data-ttu-id="595dc-122">모니터링되는 기능을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="595dc-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="595dc-123">디바이스 상태 상태</span><span class="sxs-lookup"><span data-stu-id="595dc-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="595dc-124">Teams 디바이스</span><span class="sxs-lookup"><span data-stu-id="595dc-124">Teams Devices</span></span> | <span data-ttu-id="595dc-125">오프라인으로 전환하는 경우 Teams 디바이스를 적극적으로 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="595dc-125">Pro-actively monitor Teams devices if they go offline.</span></span>|
