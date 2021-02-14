---
title: Skype 채팅방 시스템 도메인 가입 고려 사항
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
description: 관리자는 Skype 채팅방 시스템 어플라이언스 PC를 Active Directory 도메인에 가입하는 방법과 이를 위한 고려 사항을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905440"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="c2830-103">Skype 채팅방 시스템 도메인 가입 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c2830-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="c2830-104">이 항목을 읽고 Skype 채팅방 시스템 어플라이언스 PC를 도메인에 가입하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="c2830-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="c2830-105">도메인 가입 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c2830-105">Domain joining considerations</span></span>

<span data-ttu-id="c2830-106">Skype 채팅방 시스템 어플라이언스 PC를 Active Directory 도메인에 가입하거나 작업대에 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="c2830-107">이 결정을 내리기 전에 다음을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="c2830-108">Skype 채팅방 시스템 어플라이언스 PC를 도메인에 가입하면 조직의 개인 루트 인증서 체인을 자동으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="c2830-109">Skype 채팅방 시스템 어플라이언스 PC에 도메인 가입을 사용하면 도메인 사용자 및 그룹 관리 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="c2830-110">이렇게 하면 로컬 컴퓨터 수준 관리자 계정 암호를 기억할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="c2830-111">Skype 채팅방 시스템 어플라이언스 PC를 도메인에 가입할 때 모든 Skype 채팅방 시스템 컴퓨터 개체가 있는 OU에 GPO(그룹 정책 개체) 제외를 제공할 수 있도록 별도의 OU(조직 구성 단위)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="c2830-112">이렇게 하는 경우 Skype 채팅방 시스템 어플라이언스 PC를 도메인에 가입하기 전에 OU에서 컴퓨터 개체를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="c2830-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="c2830-113">대부분의 조직에는 Skype Room System 어플라이언스 PC 기능에 영향을 주는 다음과 같은 GPOS가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="c2830-114">Skype 채팅방 시스템 OU에서 이러한 GPOS의 상속을 다시 설정하거나 차단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="c2830-115">로그온 세션의 시간 제한(자동 잠금)</span><span class="sxs-lookup"><span data-stu-id="c2830-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="c2830-116">전원 관리 관련 정책</span><span class="sxs-lookup"><span data-stu-id="c2830-116">Power management related policies</span></span>
  - <span data-ttu-id="c2830-117">추가 인증 단계 요구</span><span class="sxs-lookup"><span data-stu-id="c2830-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="c2830-118">로컬 드라이브에 대한 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="c2830-118">Denying access to local drives</span></span>
  - <span data-ttu-id="c2830-119">사용자에게 느린 네트워크 연결 프롬프트</span><span class="sxs-lookup"><span data-stu-id="c2830-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="c2830-120">로그온 시 특정 프로그램 시작</span><span class="sxs-lookup"><span data-stu-id="c2830-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="c2830-121">모든 도메인에 가입된 머신에 다른 도메인 사용자 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="c2830-122">Skype 채팅방 시스템에 Windows 업데이트 푸시</span><span class="sxs-lookup"><span data-stu-id="c2830-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="c2830-123">또는 어플라이언스 PC를 작업대에 두기로 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="c2830-124">데스크톱 Microsoft Teams 또는 비즈니스용 Skype 클라이언트와 함께 Skype 채팅방 시스템 어플라이언스 PC에서 루트 인증서 체인을 수동으로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="c2830-125">배포에서 공용 인증서(예: Entrust, VeriSign 등)를 사용하는 경우 루트 인증서 체인을 가져올 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="c2830-126">Skype 채팅방 시스템 컴퓨터를 도메인에 가입할 계획인 경우 의도하지 않은 OU에 Skype 채팅방 시스템 머신이 의도하지 않은 OU에 가입하지 않도록 방지하려면 올바른 OU에 가입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="c2830-127">Skype 채팅방 시스템 머신에서 다음 cmdlet을 사용하여 올바른 OU에 가입할 수 있으며 LRS 기능을 차단할 수 있는 GPOS를 받지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="c2830-128">시스템 관리자 또는 OEM 파트너에게 문의하여 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="c2830-129">별도의 OU를 만들고 상속을 차단하는 경우에도 더 높은 수준에서 문제를 일으킬 수 있는 몇 가지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="c2830-130">[정책에 대한 설정 없음]이 있는 그룹 정책은 차단 정책 상속 설정을 사용하여 OU를 꺾습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="c2830-131">자세한 내용은 그룹 정책 [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 설명서의 차단 정책 상속과 비교하여 비재정 없음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2830-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="c2830-132">이러한 문제를 해결하기 위한 여러 가지 접근 방식이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="c2830-133">Active Directory 전문가에게 문의하여 적절한 GPO 설정이 있는 OU 또는 이전에 설명한 정책이 없는 OU를 제공하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="c2830-134">Skype 채팅방 시스템 장치에 QoS(서비스 품질)를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2830-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c2830-135">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c2830-135">Related topics</span></span>
  
[<span data-ttu-id="c2830-136">장치 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="c2830-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="c2830-137">서비스 품질 관리</span><span class="sxs-lookup"><span data-stu-id="c2830-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
