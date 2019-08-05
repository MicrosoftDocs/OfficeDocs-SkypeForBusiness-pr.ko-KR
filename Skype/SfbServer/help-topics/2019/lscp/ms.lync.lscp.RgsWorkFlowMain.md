---
title: 응답 그룹 워크플로
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
ROBOTS: NOINDEX, NOFOLLOW
description: 응답 그룹은 에이전트 그룹, 큐 및 워크플로로 구성 됩니다. 응답 그룹 워크플로는 응답 그룹 응용 프로그램이 전화를 받을 때 수행 되는 작업을 정의 합니다.
ms.openlocfilehash: dba5d07d922e652e0c80d97bf622fbb51747a00f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196249"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="1dd6d-104">응답 그룹 워크플로</span><span class="sxs-lookup"><span data-stu-id="1dd6d-104">Response Groups Workflow</span></span>

<span data-ttu-id="1dd6d-105">응답 그룹은 에이전트 그룹, 큐 및 워크플로로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="1dd6d-106">응답 그룹 워크플로는 응답 그룹 응용 프로그램이 전화를 받을 때 수행 되는 작업을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="1dd6d-107">**응답 그룹** - **워크플로** 페이지에는 조직에 대해 정의 된 모든 응답 그룹 워크플로 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="1dd6d-108">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="1dd6d-108">Tasks you can perform</span></span>

<span data-ttu-id="1dd6d-109">**응답 그룹** - **워크플로** 페이지에서 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="1dd6d-110">헌트 그룹 워크플로 만들기 또는 변경</span><span class="sxs-lookup"><span data-stu-id="1dd6d-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="1dd6d-111">대화형 워크플로 만들기 또는 변경</span><span class="sxs-lookup"><span data-stu-id="1dd6d-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1dd6d-112">UI 참조</span><span class="sxs-lookup"><span data-stu-id="1dd6d-112">UI Reference</span></span>

<span data-ttu-id="1dd6d-113">다음 목록에서는 페이지의 명령에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="1dd6d-114">**워크플로 만들기 또는 편집** 워크플로를 만들거나 편집할 응답 그룹 구성 도구를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="1dd6d-115">**새로 고침** 워크플로 목록을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="1dd6d-116">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="1dd6d-117">**이름** 워크플로에 할당 된 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="1dd6d-118">**서비스** 워크플로를 호스트 하는 **Applicationserver** 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="1dd6d-119">**SIP 주소** 워크플로 호출에 응답 하는 그룹의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="1dd6d-120">**전화 번호** 이 응답 그룹에 도달 하기 위해 호출 되는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="1dd6d-121">**언어가** 음성 인식 및 텍스트 음성 변환에 사용 되는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="1dd6d-122">**IVR** 워크플로가 헌트 그룹 또는 대화형 워크플로 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="1dd6d-123">**사용 하도록 설정** 워크플로가 통화를 수신할 수 있도록 활성화 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="1dd6d-124">응답 그룹 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [비즈니스용 Skype 서버에서 응답 그룹 응용 프로그램 계획](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="1dd6d-125">응답 그룹 워크플로 작업에 대 한 자세한 내용은 작업 설명서의 [응답 그룹 워크플로 관리](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd6d-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


