---
title: 스키마 파티션의 복제 확인
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
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: Active Directory 도메인 서비스 포리스트에 해당 확장이 복제된 것을 확인하려면 다음을 완료합니다.
ms.openlocfilehash: db30087e6b996b70fe97e3249c1bf2eaa97a694c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800548"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="8099b-103">스키마 파티션의 복제 확인</span><span class="sxs-lookup"><span data-stu-id="8099b-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="8099b-104">Active Directory 도메인 서비스 포리스트에 해당 확장이 복제된 것을 확인하려면 다음을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="8099b-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="8099b-105">Enterprise Admins 그룹의 구성원으로 적용된 Active Directory 도메인 서비스 포리스트에서 도메인 컨트롤러(스마마 마스터 역할을 보유하는 도메인 컨트롤러가 아님)에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8099b-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="8099b-106">**시작**, **관리 도구** 를 차례로 클릭한 다음 **ADSI 편집** 을 클릭하여 ADSI 편집을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8099b-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8099b-107">또는 **시작**, **실행** 을 차례로 클릭한 다음 **adsiedit.msc** 를 입력하여 ADSI 편집을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8099b-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="8099b-108">MMC(Microsoft Management Console) 트리에서 아직 선택되어 있지 않으면 ADSI 편집을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8099b-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="8099b-109">**동작** 메뉴에서 **연결** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8099b-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="8099b-110">**잘 알려진 명명 컨텍스트를 선택합니다.** 아래에 있는 **연결 설정** 대화 상자에서 **스키마** 를 선택한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8099b-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="8099b-p101">스키마 컨테이너 아래에서 CN=ms-RTC-SIP-SchemaVersion을 검색합니다. 이 개체가 있고 **rangeUpper** 특성 값이 1150이고 **rangeLower** 특성 값이 3이면 스키마가 업데이트 및 복제된 것입니다. 이 개체가 없거나 **rangeUpper** 및 **rangeLower** 특성 값이 지정된 대로가 아니면 스키마가 수정되지 않았거나 복제되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8099b-p101">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion. If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated. If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8099b-114">스키마 복제 확인 시 아직 복제에 성공했음이 표시되지 않으면 약 15분간 기다린 다음 다시 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="8099b-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="8099b-115">Active Directory 복제는 느슨한 일관성 모델을 기반으로 하여 서버 및 인프라의 여러 요인에 따라 일부 복제 대기 시간이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8099b-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

