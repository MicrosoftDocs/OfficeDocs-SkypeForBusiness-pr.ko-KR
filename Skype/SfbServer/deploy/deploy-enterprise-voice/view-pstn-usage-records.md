---
title: 비즈니스용 Skype에서 PSTN 사용 레코드 보기
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
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: '요약: 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 PSTN 사용 레코드를 보는 방법을 설명하는 방법을 제공합니다.'
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830538"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="cda9e-103">비즈니스용 Skype에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="cda9e-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="cda9e-104">**요약:** 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 PSTN 사용 레코드를 보는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="cda9e-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="cda9e-105">PSTN(Public Switched Telephone Network) 사용 레코드는 조직의 여러 사용자 또는 사용자 그룹이 만들 수 있는 통화 클래스(내부, 로컬 또는 시거리)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cda9e-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="cda9e-106">자세한 내용은 계획 설명서에서 [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cda9e-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="cda9e-107">비즈니스용 Skype 서버 제어판을 사용하여 PSTN 사용 레코드를 확인</span><span class="sxs-lookup"><span data-stu-id="cda9e-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cda9e-108">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="cda9e-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="cda9e-109">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭하고 **PSTN 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cda9e-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="cda9e-110">**PSTN 사용** 페이지에서 보려는 PSTN 사용 레코드를 강조 표시하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cda9e-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cda9e-111">선택한 PSTN 사용 레코드의 읽기 전용 페이지에 연결된 경로 및 음성 정책이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cda9e-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="cda9e-112">비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하여 PSTN 사용 정보를 확인</span><span class="sxs-lookup"><span data-stu-id="cda9e-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="cda9e-113">모든 PSTN 사용에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda9e-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="cda9e-114">이 명령은 다음과 비슷한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cda9e-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="cda9e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cda9e-115">See also</span></span>

[<span data-ttu-id="cda9e-116">음성 정책 만들기 또는 수정 및 비즈니스용 Skype에서 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="cda9e-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

