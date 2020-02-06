---
title: 스키마 파티션 복제 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 스키마 확장이 Active Directory 도메인 서비스 포리스트에 성공적으로 복제 되었는지 확인 하려면 다음을 수행 합니다.
ms.openlocfilehash: 9a4b5ecde4b1f8912af12fb736858879e5f458ba
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794747"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="adb01-103">스키마 파티션 복제 확인</span><span class="sxs-lookup"><span data-stu-id="adb01-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="adb01-104">스키마 확장이 Active Directory 도메인 서비스 포리스트에 성공적으로 복제 되었는지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="adb01-105">스키마 확장이 엔터프라이즈 관리자 그룹의 구성원으로 적용 된 Active Directory 도메인 서비스 포리스트에서 도메인 컨트롤러 (스키마 마스터 역할을 보유 하는 도메인 컨트롤러 제외)에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="adb01-106">ADSI 편집 열기: **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **adsi 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="adb01-107">또는 **시작**을 클릭 하 고 **실행**을 클릭 한 다음 **ADSIEDIT** 를 입력 하 여 ADSI 편집을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="adb01-108">MMC (Microsoft Management Console) 트리에서 아직 선택 하지 않은 경우 ADSI 편집을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="adb01-109">**작업** 메뉴에서 **연결 대상**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="adb01-110">**연결 설정** 대화 상자의 **잘 알려진 명명 컨텍스트 선택**에서 **스키마**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="adb01-111">스키마 컨테이너 아래에서 CN = ms-RTC-SIP-SchemaVersion을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="adb01-112">이 개체가 존재 하 고, **Range upper** 특성의 값이 1150이 고, **range lower** 특성의 값이 3 이면 스키마가 성공적으로 업데이트 되 고 복제 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="adb01-113">이 개체가 존재 하지 않거나, **Range upper** 및- **lower** 특성 값이 지정 되지 않은 경우 스키마는 수정 되거나 복제 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="adb01-114">스키마 복제 검사에서 아직 복제에 실패 한 경우 약 15 분 후에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="adb01-115">Active Directory 복제는 일관성을 유지 하는 모델을 기반으로 하며, 서버와 인프라의 여러 요인에 따라 일부 복제 대기 시간이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb01-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

