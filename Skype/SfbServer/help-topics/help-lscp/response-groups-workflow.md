---
title: 응답 그룹 워크플로
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: 응답 그룹은 에이전트 그룹, 큐 및 워크플로로 구성됩니다. 응답 그룹 워크플로는 응답 그룹 응용 프로그램에서 전화 통화를 받을 때 수행되는 작업을 정의합니다.
ms.openlocfilehash: 7f35fc32670e6374be69430a72c506a0bf9fae5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829288"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="c15a5-104">응답 그룹 워크플로</span><span class="sxs-lookup"><span data-stu-id="c15a5-104">Response Groups Workflow</span></span>

<span data-ttu-id="c15a5-105">응답 그룹은 에이전트 그룹, 큐 및 워크플로로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="c15a5-106">응답 그룹 워크플로는 응답 그룹 응용 프로그램에서 전화 통화를 받을 때 수행되는 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="c15a5-107">응답 **그룹 워크플로** 페이지에는 조직에 대해 정의된 모든 응답 그룹 워크플로  -   목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c15a5-108">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="c15a5-108">Tasks you can perform</span></span>

<span data-ttu-id="c15a5-109">응답 그룹 워크플로 페이지에서는 **다음 작업을 수행할**  -  **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="c15a5-110">헌트 그룹 워크플로 만들기 또는 변경</span><span class="sxs-lookup"><span data-stu-id="c15a5-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="c15a5-111">대화형 워크플로 만들기 또는 변경</span><span class="sxs-lookup"><span data-stu-id="c15a5-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c15a5-112">UI 참조</span><span class="sxs-lookup"><span data-stu-id="c15a5-112">UI Reference</span></span>

<span data-ttu-id="c15a5-113">다음 목록에서는 페이지의 명령에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="c15a5-114">**워크플로 만들기 또는 편집** 워크플로를 만들거나 편집하기 위한 응답 그룹 구성 도구를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="c15a5-115">**새로 고침** 워크플로 목록을 새로 고침합니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="c15a5-116">다음 목록에서는 페이지의 필드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c15a5-117">**이름** 워크플로에 할당되는 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="c15a5-118">**서비스** 워크플로를 **호스팅하는 ApplicationServer** 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="c15a5-119">**SIP 주소** 워크플로 호출에 응답할 그룹의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="c15a5-120">**전화** 이 응답 그룹에 연결하기 위해 호출된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="c15a5-121">**언어** 음성 인식 및 텍스트 음성 입력에 사용되는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="c15a5-122">**IVR** 워크플로가 헌트 그룹인지 대화형 워크플로인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="c15a5-123">**사용** 통화를 받기 위해 워크플로가 활성화되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c15a5-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="c15a5-124">응답 그룹 기능에 대한 자세한 내용은 계획 설명서에서 비즈니스용 [Skype 서버 2015의](../../plan-your-deployment/enterprise-voice-solution/response-group.md) 응답 그룹 응용 프로그램 계획을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c15a5-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="c15a5-125">응답 그룹 워크플로 사용에 대한 자세한 [](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) 내용은 작업 설명서에서 응답 그룹 워크플로 관리를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c15a5-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


