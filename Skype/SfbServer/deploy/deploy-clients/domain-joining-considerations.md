---
title: Skype 룸 시스템 도메인 가입 고려 사항
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 이 항목을 읽고 Skype 룸 시스템 어플라이언스 PC를 도메인에 가입하는 방법을 알아보십시오.
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805918"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="30874-103">Skype 룸 시스템 도메인 가입 고려 사항</span><span class="sxs-lookup"><span data-stu-id="30874-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="30874-104">이 항목을 읽고 Skype 룸 시스템 어플라이언스 PC를 도메인에 가입하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="30874-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="30874-105">도메인 가입 고려 사항</span><span class="sxs-lookup"><span data-stu-id="30874-105">Domain joining considerations</span></span>

<span data-ttu-id="30874-106">Skype 룸 시스템 어플라이언스 PC를 Active Directory 도메인에 가입하거나 작업(Workgroup)에 그대로 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30874-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="30874-107">이러한 결정을 내리기 전에 다음을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="30874-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="30874-108">Skype 룸 시스템 어플라이언스 PC를 도메인에 가입하면 조직의 개인 루트 인증서 체인을 자동으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="30874-109">Skype 룸 시스템 어플라이언스 PC를 도메인에 가입하면 도메인 사용자 및 그룹에 관리 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="30874-110">이렇게 하면 로컬 컴퓨터 수준 관리자 계정 암호를 기억할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="30874-111">Skype 룸 시스템 어플라이언스 PC를 도메인에 가입할 때 모든 Skype 룸 시스템 컴퓨터 개체가 있는 OU에 GPO(그룹 정책 개체) 제외를 제공할 수 있도록 별도의 OU(조직 구성 단위)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30874-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="30874-112">이렇게 하는 경우 Skype 룸 시스템 어플라이언스 PC를 도메인에 가입하기 전에 OU에서 컴퓨터 개체를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="30874-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="30874-113">대부분의 조직에는 Skype 룸 시스템 어플라이언스 PC 기능에 영향을 주는 다음과 같은 GOS가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="30874-114">Skype 룸 시스템 OU에서 이러한 GOS의 상속을 다시 설정하거나 차단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30874-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="30874-115">로그온 세션의 시간 제한(자동 잠금)</span><span class="sxs-lookup"><span data-stu-id="30874-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="30874-116">전원 관리 관련 정책</span><span class="sxs-lookup"><span data-stu-id="30874-116">Power management related policies</span></span>
    
  - <span data-ttu-id="30874-117">추가 인증 단계 필요</span><span class="sxs-lookup"><span data-stu-id="30874-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="30874-118">로컬 드라이브에 대한 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="30874-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="30874-119">사용자에게 느린 네트워크 연결을 요청하는 메시지 표시</span><span class="sxs-lookup"><span data-stu-id="30874-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="30874-120">로그온 시 특정 프로그램 시작</span><span class="sxs-lookup"><span data-stu-id="30874-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="30874-121">도메인에 가입된 모든 컴퓨터의 다른 도메인 사용자 계정을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="30874-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="30874-122">Skype 채팅방 시스템에 Windows 업데이트 푸시</span><span class="sxs-lookup"><span data-stu-id="30874-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="30874-123">또는 어플라이언스 PC를 작업대에 그대로 두는 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="30874-124">데스크톱 비즈니스용 Skype 클라이언트와 같은 경우 Skype 룸 시스템 어플라이언스 PC에서 루트 인증서 체인을 수동으로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30874-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="30874-125">비즈니스용 Skype 배포에서 공용 인증서(예: Entrust, VeriSign 등)를 사용하는 경우 루트 인증서 체인을 가져올 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="30874-126">Skype 채팅방 시스템 컴퓨터를 도메인에 가입하려면 의도하지 않은 OU에 Skype 룸 시스템 컴퓨터의 가입을 방지합니다. GOS에서 무료가 아 않을 수 있습니다. 올바른 OU에 가입해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30874-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="30874-127">Skype 룸 시스템 컴퓨터의 다음 cmdlet을 사용하여 올바른 OU에 가입할 수 있으며 LRS 기능을 차단할 수 있는 GOS를 수신하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="30874-128">시스템 관리자 또는 OEM 파트너에게 문의하여 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="30874-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="30874-129">별도의 OU를 만들고 상속을 차단하는 경우에도 더 높은 수준에서 문제를 일으킬 수 있는 몇 가지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="30874-130">정책에 대한 정책 상속 차단 설정이 있는 그룹 정책은 OU를 지날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="30874-131">자세한 내용은 그룹 정책 설명서에서 정책 상속 차단과 비교하여 No [Override](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="30874-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="30874-132">이러한 문제를 해결하는 여러 가지 접근 방식이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="30874-133">Active Directory 전문가에게 문의하여 적절한 GPO 설정이 있는 OU 또는 앞서 설명한 정책이 없는 OU를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30874-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="30874-134">Skype 룸 시스템 장치에 대해 QoS(서비스 품질)를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="30874-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="30874-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30874-135">See also</span></span>
  
[<span data-ttu-id="30874-136">장치 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="30874-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="30874-137">서비스 품질 관리</span><span class="sxs-lookup"><span data-stu-id="30874-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
