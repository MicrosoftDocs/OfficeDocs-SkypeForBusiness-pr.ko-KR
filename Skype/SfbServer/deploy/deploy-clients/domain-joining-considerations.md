---
title: Skype 채팅방 시스템 도메인 참가 고려 사항
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 이 항목에서는 Skype 채팅방 시스템 기기 PC를 도메인에 참가 하는 방법에 대해 알아보세요.
ms.openlocfilehash: 2d2af20173708e199c1de5a205218d3295e7e0d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234386"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="883c0-103">Skype 채팅방 시스템 도메인 참가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="883c0-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="883c0-104">이 항목에서는 Skype 채팅방 시스템 기기 PC를 도메인에 참가 하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="883c0-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="883c0-105">도메인 가입 고려 사항</span><span class="sxs-lookup"><span data-stu-id="883c0-105">Domain joining considerations</span></span>

<span data-ttu-id="883c0-106">Skype 채팅방 System 기기 PC를 Active Directory 도메인에 가입 하거나 작업 그룹에 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="883c0-107">이러한 결정을 내리기 전에 다음 사항을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="883c0-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="883c0-108">도메인-Skype 대화방 시스템 기기 PC에 가입 하면 조직의 개인 루트 인증서 체인을 자동으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="883c0-109">Domain-Skype 채팅방 System 기기 PC에 가입 하면 도메인 사용자와 그룹의 관리자 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="883c0-110">이렇게 하면 로컬 컴퓨터 수준 관리자 계정 암호를 따로 저장할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="883c0-111">Skype 채팅방 System 기기 PC를 도메인에 참가 하는 경우, 모든 Skype 룸 시스템 개체가 있는 OU에 대 한 GPO (그룹 정책 개체) 제외를 제공할 수 있도록 별도의 OU (조직 구성 단위)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="883c0-112">이렇게 하는 경우, Skype 룸 시스템 기기 PC를 도메인에 참가 하기 전에 OU에 기계 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="883c0-113">많은 조직에는 Skype 실 시스템 기기 PC 기능에 영향을 주는 다음과 같은 Gpo가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="883c0-114">Skype 대화방 시스템 OU에서 Gpo의 상속을 무시 하거나 차단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="883c0-115">로그온 세션 제한 시간 (자동 잠금)</span><span class="sxs-lookup"><span data-stu-id="883c0-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="883c0-116">전원 관리 관련 정책</span><span class="sxs-lookup"><span data-stu-id="883c0-116">Power management related policies</span></span>
    
  - <span data-ttu-id="883c0-117">추가 인증 단계 필요</span><span class="sxs-lookup"><span data-stu-id="883c0-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="883c0-118">로컬 드라이브에 대 한 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="883c0-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="883c0-119">사용자에 게 느린 네트워크 연결을 묻는 메시지 표시</span><span class="sxs-lookup"><span data-stu-id="883c0-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="883c0-120">로그온 할 때 특정 프로그램 시작</span><span class="sxs-lookup"><span data-stu-id="883c0-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="883c0-121">모든 도메인에 가입 된 컴퓨터에서 다른 도메인 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="883c0-122">Skype 채팅방 시스템에 Windows 업데이트 푸시</span><span class="sxs-lookup"><span data-stu-id="883c0-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="883c0-123">또는, 기기 PC를 작업 그룹에 그대로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="883c0-124">비즈니스용 데스크톱 비즈니스용 Skype 클라이언트와 마찬가지로,이를 위해서는 Skype 채팅방 시스템 기기 PC에서 루트 인증서 체인을 수동으로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="883c0-125">비즈니스용 Skype 배포에서 공용 인증서 (예: Entrust, VeriSign 등)를 사용 하는 경우 루트 인증서 체인을 가져오지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="883c0-126">Skype room 시스템 컴퓨터를 도메인에 참가 하는 경우, 실수로 Skype 채팅방 시스템을 Gpo에서 사용할 수 없는 의도 하지 않은 OU에 가입 하는 것을 방지 하려면 올바른 OU에 가입 하 고 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="883c0-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="883c0-127">Skype 대화방 시스템 컴퓨터에서 다음 cmdlet을 사용 하 여 올바른 OU에 가입 하 고 LRS 기능을 차단할 수 있는 Gpo를 수신 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="883c0-128">다음 cmdlet을 실행 하려면 시스템 관리자 또는 OEM 파트너에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="883c0-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="883c0-129">별도의 OU를 만들고 상속을 차단 하는 경우에도 더 높은 수준에서 문제를 일으킬 수 있는 몇 가지 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="883c0-130">무시 설정이 없는 그룹 정책은 정책의 상속을 차단 하는 설정을 사용 하는 OU 보다 더 비트 합니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="883c0-131">자세한 내용은 그룹 정책 설명서에서 [정책 상속을 차단 하는 방법에 대 한 재정의 없음](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="883c0-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="883c0-132">이러한 문제를 해결 하는 방법에는 여러 가지가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="883c0-133">Active Directory 전문가와 상의 하 여 적절 한 GPO 설정이 나 적어도 이전에 설명한 정책이 존재 하지 않는 OU를 사용 하는 ou를 제공 하도록 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="883c0-134">Skype 채팅방 시스템 장치에 QoS (서비스 품질)를 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="883c0-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="883c0-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="883c0-135">See also</span></span>
  
[<span data-ttu-id="883c0-136">장치 구성: 새로 만들기 또는 기존 항목 편집</span><span class="sxs-lookup"><span data-stu-id="883c0-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="883c0-137">서비스 품질 관리</span><span class="sxs-lookup"><span data-stu-id="883c0-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
