---
title: Skype Room System 도메인 조인 고려 사항
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: 관리자는 Skype Room System 어플라이언스 PC를 Active Directory 도메인에 가입하는 방법에 대해 알아보고 이를 위한 고려 사항을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117556"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="00124-103">Skype Room System 도메인 조인 고려 사항</span><span class="sxs-lookup"><span data-stu-id="00124-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="00124-104">이 항목에서 Skype Room System 어플라이언스 PC를 도메인에 조인하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="00124-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="00124-105">도메인 가입 고려 사항</span><span class="sxs-lookup"><span data-stu-id="00124-105">Domain joining considerations</span></span>

<span data-ttu-id="00124-106">Skype Room System 어플라이언스 PC를 Active Directory 도메인에 조인하거나 Workgroup에 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="00124-107">이 결정을 내리기 전에 다음을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="00124-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="00124-108">Skype Room System 어플라이언스 PC 도메인에 가입하면 조직의 개인 루트 인증서 체인을 자동으로 가져오는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00124-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="00124-109">Skype Room System 어플라이언스 PC에 도메인에 가입하면 도메인 사용자 및 그룹 관리 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="00124-110">이렇게 하면 로컬 컴퓨터 수준 관리자 계정 암호를 기억할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="00124-111">Skype Room System 어플라이언스 PC를 도메인에 조인하는 경우 모든 Skype Room System 컴퓨터 개체가 있는 OU에 그룹 정책 개체(GPO) 제외를 제공할 수 있도록 별도의 조직 단위(OU)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00124-111">When you join a Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="00124-112">이렇게 할 때 Skype Room System 어플라이언스 PC를 도메인에 조인하기 전에 OU에서 컴퓨터 개체를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="00124-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="00124-113">많은 조직에는 Skype Room System 어플라이언스 PC 기능에 영향을 주는 다음과 같은 GPOS가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="00124-114">Skype Room System OU에서 이러한 GPOS의 상속을 오버라이드하거나 차단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00124-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="00124-115">로그온 세션의 시간 제한(자동 잠금)</span><span class="sxs-lookup"><span data-stu-id="00124-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="00124-116">전원 관리와 관련된 정책</span><span class="sxs-lookup"><span data-stu-id="00124-116">Policies related to power management</span></span>
  - <span data-ttu-id="00124-117">추가 인증 단계 필요</span><span class="sxs-lookup"><span data-stu-id="00124-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="00124-118">로컬 드라이브에 대한 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="00124-118">Denying access to local drives</span></span>
  - <span data-ttu-id="00124-119">느린 네트워크 연결에 대한 사용자에게 묻는 메시지</span><span class="sxs-lookup"><span data-stu-id="00124-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="00124-120">로그온에서 특정 프로그램 시작</span><span class="sxs-lookup"><span data-stu-id="00124-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="00124-121">도메인에 가입된 모든 머신에서 다른 도메인 사용자 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="00124-122">Skype Room System으로 Windows 업데이트 푸시</span><span class="sxs-lookup"><span data-stu-id="00124-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="00124-123">또는 어플라이언스 PC를 작업대에 그대로 두는 것이 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="00124-124">데스크톱 Microsoft Teams 또는 비즈니스용 Skype 클라이언트와 함께 이 경우 Skype Room System 어플라이언스 PC에서 루트 인증서 체인을 수동으로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00124-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="00124-125">배포에서 공용 인증서(예: Entrust, VeriSign 등)를 사용하는 경우 루트 인증서 체인을 가져올 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="00124-126">Skype Room System 머신을 도메인에 조인할 계획인 경우 의도하지 않은 OU에 Skype Room System Machine에 의도하지 않은 OU에 가입하지 않도록 하기 위해 올바른 OU에 가입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00124-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="00124-127">Skype Room System 머신에서 다음 cmdlet을 사용하여 올바른 OU에 참가할 수 있으며 LRS 기능을 차단할 수 있는 GPOS를 수신하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="00124-128">시스템 관리자 또는 OEM 파트너에게 문의하여 이러한 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00124-128">Contact your system administrator or OEM partner to run these cmdlets:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="00124-129">별도의 OU를 만들고 상속을 차단하는 경우에도 더 높은 수준에서 문제를 일으킬 수 있는 몇 가지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-129">Even if you create a separate OU and block inheritance, there are some policies that could cause issues at a higher level.</span></span> <span data-ttu-id="00124-130">OU를 오버라이드하지 않습니다 설정이 있는 그룹 정책은 블록 정책 상속 설정을 사용하여 OU를 꺾습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="00124-131">자세한 내용은 [그룹](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 정책 설명서에서 차단 정책 상속과 비교하여 에라이드 없음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00124-131">For more information, see [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="00124-132">이러한 문제를 해결하기 위한 여러 가지 접근 방식이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="00124-133">적절한 GPO 설정이 있는 OU 또는 이전에 설명한 정책이 없는 OU를 제공하도록 Active Directory 전문가와 상의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-133">We advise you to consult with your Active Directory experts to ensure that you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="00124-134">Skype Room System 디바이스에 대한 QoS(서비스 품질)를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00124-134">We advise to enabling Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00124-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="00124-135">Related topics</span></span>
  
[<span data-ttu-id="00124-136">장치 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="00124-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="00124-137">서비스 품질 관리</span><span class="sxs-lookup"><span data-stu-id="00124-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)