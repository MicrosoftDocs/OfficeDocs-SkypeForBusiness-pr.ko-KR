---
title: 도메인에서 복제 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: '1 단계: 스키마 준비에서 수행한 도메인 준비의 복제를 확인 하려면 비즈니스용 Skype Server Management Shell Lync Server 관리 셸에서 cmdlet을 실행 해야 합니다. Windows PowerShell cmdlet을 실행 하려면 준비한 도메인의 구성원 인 컴퓨터 (도메인 관리자 그룹의 구성원)에 로그온 합니다. 이렇게 하려면 다음을 수행합니다.'
ms.openlocfilehash: da61941bacd1d5463c11cf044d9ce8a6442ef9d4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823292"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="7d141-105">도메인에서 복제 확인</span><span class="sxs-lookup"><span data-stu-id="7d141-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="7d141-106">**1 단계: 스키마 준비**에서 수행한 도메인 준비의 복제를 확인 하려면 비즈니스용 Skype Server Management Shell Lync Server 관리 셸에서 cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="7d141-107">Windows PowerShell cmdlet을 실행 하려면 준비한 도메인의 구성원 인 컴퓨터 (도메인 관리자 그룹의 구성원)에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="7d141-108">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-108">Do the following:</span></span>
  
1. <span data-ttu-id="7d141-109">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7d141-110">Windows PowerShell에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="7d141-111">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="7d141-112">GlobalSettingsDomainController 매개 변수를 통해 전역 설정이 저장되어 있는 위치를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="7d141-113">설정이 시스템 컨테이너에 저장 된 경우 (구성 컨테이너에 전역 설정이 마이그레이션되지 않은 업그레이드 배포의 경우), Active Directory 도메인 서비스 포리스트의 루트에 도메인 컨트롤러를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="7d141-114">전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="7d141-115">이 매개 변수를 지정 하지 않으면 cmdlet이 구성 컨테이너에 저장 된 것으로 간주 하 고 Active Directory의 모든 도메인 컨트롤러를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="7d141-116">Domain 매개 변수를 지정하지 않으면 값이 로컬 도메인으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="7d141-117">이 cmdlet은 도메인 준비가 성공적이면 **LC_DOMAIN_SETTINGS_STATE_READY** 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d141-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

