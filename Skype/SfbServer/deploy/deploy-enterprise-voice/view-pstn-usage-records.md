---
title: 비즈니스용 Skype에서 PSTN 사용 레코드 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: '요약: 비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 PSTN 사용 레코드를 보는 방법에 대해 알아봅니다.'
ms.openlocfilehash: bbc9b7f174ff4b6710009af47dbdcd20e12334d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240246"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="a46d7-103">비즈니스용 Skype에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="a46d7-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="a46d7-104">**요약:** 비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 PSTN 사용 레코드를 보는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a46d7-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="a46d7-105">PSTN (공개 통신 네트워크) 사용 레코드는 조직의 여러 사용자 또는 사용자 그룹에 의해 이루어질 수 있는 통화 클래스 (예: 내부, 지역 또는 시외)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46d7-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="a46d7-106">자세한 내용은 계획 설명서의 [PSTN 사용 레코드](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a46d7-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a46d7-107">비즈니스용 Skype Server 제어판을 사용 하 여 PSTN 사용 레코드를 보려면</span><span class="sxs-lookup"><span data-stu-id="a46d7-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a46d7-108">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a46d7-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a46d7-109">왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **PSTN 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46d7-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="a46d7-110">**Pstn 사용** 페이지에서 보려는 PSTN 사용 레코드를 강조 표시 하 고 **편집** 을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46d7-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a46d7-111">선택한 PSTN 사용 레코드의 읽기 전용 페이지에 연결 된 경로와 관련 음성 정책이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a46d7-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="a46d7-112">비즈니스용 Skype 서버 관리 셸 cmdlet을 사용 하 여 PSTN 사용 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="a46d7-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="a46d7-113">모든 PSTN 용도에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a46d7-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="a46d7-114">이 명령은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46d7-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="a46d7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a46d7-115">See also</span></span>

[<span data-ttu-id="a46d7-116">비즈니스용 Skype에서 음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="a46d7-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

